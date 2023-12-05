# Pertemuan 11
## Profil

| Variable |    isi     |
|----------|------------|
|Nama      |Ariq ibtihal|
|NIM       |312310446   |
|Kelas     |TI.23.A5    |
|Matkul    |Bahasa Pemrograman |

## Latihan 
# Ubah kode dibawah ini menjadi fungsi lambda
```
import math
def a (x):
return x**2
def b(x,y):
return math.sqrt(x**2 + y**2)
def c(*args):
return sum(args)/len(args)
def d(s):
return "".join(set(s))
```


## Setelah di ubah
```
import math

# Fungsi a(x) mengembalikan kuadrat dari x
def a(x):
    return x ** 2

# Fungsi lambda ac melakukan hal yang sama seperti fungsi a
ac = lambda x: x ** 2

# Mencetak hasil dari pemanggilan fungsi a dengan argumen 8
print(a(8))

# Mencetak hasil dari pemanggilan fungsi ac dengan argumen 11
print(ac(11))

# Fungsi b(x, y) mengembalikan akar kuadrat dari jumlah kuadrat x dan y
def b(x, y):
    return math.sqrt(x*2 + y*2)

# Fungsi lambda bc melakukan hal yang sama seperti fungsi b
bc = lambda x, y: math.sqrt(x*2 + y*2)

# Mencetak hasil dari pemanggilan fungsi b dengan argumen 1 dan 4
print(b(1, 4))

# Mencetak hasil dari pemanggilan fungsi bc dengan argumen 2 dan 5
print(bc(2, 5))

# Fungsi c(*args) mengembalikan rata-rata dari argumen yang diberikan
def c(*args):
    return sum(args) / len(args)

#### Fungsi lambda cC melakukan hal yang sama seperti fungsi c
cC = lambda *args: sum(args) / len(args)

# Mencetak hasil dari pemanggilan fungsi c dengan argumen 100 dan 50
print(c(100, 50))

# Mencetak hasil dari pemanggilan fungsi cC dengan argumen 100 dan 25
print(cC(100, 25))

# Fungsi d(s) mengembalikan string unik dari karakter dalam s
def d(s):
    return "".join(set(s))

# Fungsi lambda dc melakukan hal yang sama seperti fungsi d
dc = lambda s: "".join(set(s))

# Mencetak hasil dari pemanggilan fungsi d dengan argumen "ILoveeYou"
print(d("ILoveeYou"))

# Mencetak hasil dari pemanggilan fungsi dc dengan argumen "ILoveeYouToo"
print(dc("ILoveeYouToo"))
```
## Outputnya
![Alt text](<Gambar 1.png>)
# Tugas Praktikum
Buat program sederhana dengan mengaplikasikan penggunaan fungsi yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Fungsi tambah() untuk menambah data
- Fungsi tapilkan() untuk menampilkan data
- Fungsi hapus(nama) untuk menghapus data berdasarkan nama
- Fungsi ubah(nama) untuk mengubah data berdasarkan nama
- Buat flowchart dan penjelasan programnya pada README.md
# Kode program
```
list = {}

def garis():
    '''Fungsi garis'''
    print("~"*78)

    # Menambahkan data inputan 
def tambah():
    print("Tambah data :\n")
    nama    = input("Nama           : ")
    nim     = int(input("NIM            : "))
    uts     = int(input("Nilai UTS      : "))
    uas     = int(input("Nilai UAS      : "))
    tugas   = int(input("Nilai Tugas    : "))
    akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
    list[nama] = [nim, tugas, uts, uas, akhir]

    # Mengubah data inputan
def ubah():
    print("Ubah Data :")
    nama = input("\nMasukkan Nama  : ")
    if nama in list.keys():
        nim     = int(input("NIM            : "))
        uts     = int(input("Nilai UTS      : "))
        uas     = int(input("Nilai UAS      : "))
        tugas   = int(input("Nilai Tugas    : "))
        akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
        list[nama] = [nim, tugas, uts, uas, akhir]
    else:
        print("NAMA {0} TIDAK ADA!".format(nama))

    # Menghapus inputan Nama
def hapus():
    print("Hapus berdasarkan nama inputan :")
    nama = input("\nMasukkan Nama  : ")
    if nama in list.keys():
        del list[nama]
        print("\nData {0} berhasil di hapus".format(nama))
    else:
        print("NAMA {0} TIDAK ADA!".format(nama))
    
    # Mencari data yg sudah di input
def cari():
    print("Cari data berdasarkan nama inputan :")
    nama = input("\nMasukkan Nama : ")
    if nama in list.keys():
        print(f"\nNama        : {nama}")
        print(f"NIM         : {list[nama][0]}")
        print(f"Nilai UTS   : {list[nama][2]}")
        print(f"Nilai UAS   : {list[nama][3]}")
        print(f"Nilai Tugas : {list[nama][1]}")                  
        print(f"Nilai Akhir : {list[nama][4]}") 
    else:
        print("NAMA {0} TIDAK ADA!".format(nama))
    
    # Menampilkan seluruh data 
def lihat():
    if list.items():
        print("-"*78)
        print("|                               Daftar Mahasiswa                             |")
        print("-"*78)                 
        print("| No |       Nama      |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
        print("="*78)
        i = 0
        for data in list.items():
            i += 1
            print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                .format(data[0][:13], data[1][0], data[1][2], data[1][3], data[1][1], data[1][4], no=i))
            print("-"*78)
    else:
        print("-"*78)
        print("|                               Daftar Mahasiswa                             |")
        print("-"*78)
        print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
        print("-"*78)
        print("|                       TIDAK ADA DATA! Silakan tambah data                  |")
        print("-"*78)


print("="*20)
print("|PROGRAM INPUT DATA|")
print("="*20)

while True: 
    print()
    menu = input("[(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar] : ")
    garis()
    print()

    if menu.lower() == 't':
        tambah()

    elif menu.lower() == 'u':
        ubah()       

    elif menu.lower() == "h":
        hapus() 

    elif menu.lower() == "c":
        cari()

    elif menu.lower() == "l":
        lihat() 

    elif menu.lower() == "k":
        print("Program telah selesai, Terima Kasih :) ")
        break

    else:
        print("\n INPUT {} Tidak valid ! , Silakan pilih [T/U/H/C/L] untuk menjalankan program!".format(menu))
```
### Penjelasan 
- Pada dasar ny program ini sama seperti di Pertemuan-10, bedanya di program ini di tambahkan ```Function``` / Sub rutin. Seperti program ada di atas ```def``` yg berati definision, & contoh ```def garis()``` Untuk membuat fungsi garis yg di panggil dari ```print("~"*80).```

- Kalau ```def tambah(), def ubah(), def hapus(), def cari(), def lihat()``` di panggil dari program berikut :
```
while True: 
    print()
    menu = input("[(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar] : ")
    garis("~"*80)
    print()

    if menu.lower() == 't':
        tambah()

    elif menu.lower() == 'u':
        ubah()       

    elif menu.lower() == "h":
        hapus() 

    elif menu.lower() == "c":
        cari()

    elif menu.lower() == "l":
        lihat() 

    elif menu.lower() == "k":
        print("Program telah selesai, Terima Kasih :) ")
        break

    else:
        print("\n INPUT {} Tidak valid ! , Silakan pilih [T/U/H/C/L] untuk menjalankan program!".format(menu))
```     
# Outputnya   
## Tambah data
![Alt text](<gambar 2.png>)
## Ubah data
![Alt text](<gambar 3.png>)
## Hapus data
![Alt text](<gambar 6.png>)
## Cari data
![Alt text](<gambar 4.png>)
## Lihat data
![Alt text](<gambar 5.png>)
## Keluar
![Alt text](<gambar 7.png>)
## Flowchart
![Alt text](<flowchart sebelas.jpg>)
# Terima kasih
