# Praktikum 5
## Membuuat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan menggunakan Dictionary

print("Program Input Nilai")
print("================")

daftar = {}

while True:

    perintah = input("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar: ")


## Masukan huruf T untuk menginput data (Daftar Nilai)

elif perintah.lower() == 't':
        nim = input("Masukan NIM: ")
        nama = input("Masukan nama: ")
        n_tugas = int(input("Masukan nilai tugas: "))
        n_UTS = int(input("Masukan nilai UTS: "))
        n_UAS = int(input("Masukan nilai UAS: "))
        a = n_tugas * 30 / 100
        b = n_UTS * 35 / 100
        c = n_UAS * 35 / 100
        n_akhir = a + b + c
        daftar[nama] = [nama, nim, n_tugas, n_UTS, n_UAS, n_akhir]

![Screenshot (62)](https://user-images.githubusercontent.com/56944673/70232708-e27dce80-1711-11ea-8326-5c5a698650e3.png)


## Masukan huruf L untuk melihat Daftar Nilai

elif perintah.lower() == 'l':
        print("Daftar Nilai:")
        print("===================================================================")
        print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
        print("===================================================================")
        no = 1
        for tabel in daftar.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                  (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1

![Screenshot (61)](https://user-images.githubusercontent.com/56944673/70233009-8f584b80-1712-11ea-9d83-f361ed10b46e.png)


## Masukan huruf U untuk mengubah data mahasiswa

elif perintah.lower() == 'u':
        nama = input("Masukan nama untuk mengubah data: ")
        if nama in daftar.keys():
            print("Masukan data yang ingin di ubah :")
            data = input("(Semua), (Nama), (NIM), "
                         "(Tugas), (UTS), (UAS) : ")
            if data.lower() == "semua":
                print("==========================")
                print("Ubah data {}.".format(nama))
                print("==========================")
                daftar[nama][1] = input("Edit NIM:")
                daftar[nama][2] = int(input("Edit Nilai Tugas: "))
                daftar[nama][3] = int(input("Edit Nilai UTS: "))
                daftar[nama][4] = int(input("Edit Nilai UAS: "))
                # print(daftar)
            elif data.lower() == "nim":
                daftar[nama][1] = input("NIM:")
            elif data.lower() == "tugas":
                daftar[nama][2] = int(input("Nilai Tugas: "))
            elif data.lower() == "uts":
                daftar[nama][3] = int(input("Nilai UTS: "))
            elif data.lower() == "uas":
                daftar[nama][4] = int(input("Nilai UAS: "))
            else:
                print("Perintah tidak ditemukan.")

        else:
            print("'{}' tidak ditemukan.".format(nama))

![Screenshot (65)](https://user-images.githubusercontent.com/56944673/70233469-74d2a200-1713-11ea-986a-870b1afcd98f.png)


## Masukan huruf C untuk mencari data nilai mahasiswa

elif perintah.lower() == 'c':
        print("Mencari daftar nilai: ")
        print("=================================================")
        nama = input("Masukan nama untuk mencari daftar nilai : ")
        if nama in daftar.keys():
            print("Nama {0}, dengan NIM : {1}\n"
                  "Nilai Tugas: {2}, UTS: {3}, dan UAS: {4}\n"
                  "dan nilai akhir {5}".format(nama, daftar[nama][1],
                                               daftar[nama][2], daftar[nama][3],
                                               daftar[nama][4], daftar[nama][5]))
        else:
            print("'{}' tidak ditemukan.".format(nama))

![Screenshot (64)](https://user-images.githubusercontent.com/56944673/70233609-c9761d00-1713-11ea-82aa-c49993bab2f5.png)


## Masukan huruf H untuk menghapus data nilai mahasiswa

elif perintah.lower() == 'h':
        nama = input("Masukan nama untuk menghapus data : ")
        if nama in daftar.keys():
            del daftar[nama]
            print("Data '{}' dihapus.".format(nama))
        else:
            print("'{}' tidak ditemukan.".format(nama))

![Screenshot (66)](https://user-images.githubusercontent.com/56944673/70234023-91bba500-1714-11ea-9630-81013ae0ec92.png)


## Masukan huruf K untuk keluar/selesai

if perintah.lower() == 'k':
        break

![Screenshot (67)](https://user-images.githubusercontent.com/56944673/70300420-540a5b00-17ac-11ea-82f9-c17a56e21147.png)


## FLOWCHART

![Screenshot (72)](https://user-images.githubusercontent.com/56944673/70300714-15c16b80-17ad-11ea-8a1a-04e83bc57065.png)