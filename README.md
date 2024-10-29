# Perancangan-Aplikasi-Sederhana-Menggunakan-Fungsi
- Nama: Fikri Abiyyu Rahmanm
- NIM : 2409116063

```python
from colorama import Fore, Back, Style
```
Kode ini mengimpor modul colorama, yang berguna untuk menampilkan teks dengan warna.
```python
saldo = [10000]
gems = [0]
```
Variabel saldo dan gems adalah dua variabel utama yang disimpan dalam bentuk list agar bisa diubah nilainya dalam fungsi. saldo dimulai dengan 10,000 dan gems dengan 0.
```python
def cek_saldo():
    print(f"\nSaldo anda sekarang adalah {saldo} ")
    print()
    selamat_datang()
```
Fungsi ini menampilkan jumlah saldo yang ada.
```python
def isi_saldo():
    try:
        print("\nSilahkan isi sesuai dengan kebutuhan kamu!")
        nominal_isi = int(input("Masukkan jumlah nominal pengisian : "))
        saldo[0] += nominal_isi
        print(f"\nSaldo berhasil diisi. Saldo Anda sekarang adalah {saldo}")
        print()
    except ValueError:
        print("Silahkan masukan angka!")
    selamat_datang()
```
Fungsi ini memungkinkan pengguna untuk menambah saldo. Jika input bukan angka, akan ada pesan kesalahan, lalu program akan kembali ke menu utama.
```python
def cek_gems():
    print(f"\nGems anda sekarang adalah {gems} ")
    print()
    selamat_datang()
```
Fungsi ini menampilkan jumlah gems yang dimiliki pengguna.
```python
def top_up():
    try:
        print("\nSilahkan pilih opsi Gems!")
        print(f"Saldo sekarang = {saldo}")
        print()
        print("[1] 35 Gems = 10000")
        print("[2] 80 Gems = 20000")
        print("[3] 120 Gems = 35000")
        print("[4] 210 Gems = 50000")
        print("[5] 500 Gems = 100000")
        print("[6] Kembali")
        print()
        pilihan_gems = int(input("Silahkan pilih opsi : "))
        if pilihan_gems == 1 and saldo[0] >= 10000:
            saldo[0] -= 10000
            gems[0] += 35
            print("\nSelamat anda sudah isi sebanyak 35 gems!")
            print()
            top_up()
        elif pilihan_gems == 2 and saldo[0] >= 20000:
            saldo[0] -= 20000
            gems[0] += 80
            print("\nSelamat anda sudah isi sebanyak 80 gems!")
            print()
            top_up()
        elif pilihan_gems == 3 and saldo[0] >= 35000:
            saldo[0] -= 35000
            gems[0] += 120
            print("\nSelamat anda sudah isi sebanyak 120 gems!")
            print()
            top_up()
        elif pilihan_gems == 4 and saldo[0] >= 50000:
            saldo[0] -= 50000
            gems[0] += 210
            print("\nSelamat anda sudah isi sebanyak 210 gems!")
            print()
            top_up()
        elif pilihan_gems == 5 and saldo[0] >= 100000:
            saldo[0] -= 100000
            gems[0] += 500
            print("\nSelamat anda sudah isi sebanyak 500 gems!")
            print()
            top_up()
        elif pilihan_gems == 6:
            selamat_datang()
        else:
            print("Saldo tidak cukup atau pilihan tidak valid")
            top_up()
    except ValueError:
        print("Pilihan tidak valid")
        top_up()
```
Fungsi ini memberikan opsi kepada pengguna untuk membeli gems dengan mengurangi saldo. Tiap opsi memiliki harga berbeda, dan jumlah saldo diperiksa sebelum pengurangan.
```python
def beli_skin():
    try:
        print("\nSilahkan beli skin yang kalian suka")
        print(f"Jumlah Gems sekarang = {gems}")
        print()
        print("[1] Alucrod dingin, 120 Gems")
        print("[2] Guson belah tengah, 210 Gems")
        print("[3] Agus Emo, 350 Gems")
        print("[4] Kembali")
        beli = int(input("\nSilahkan pilih skin apa yang ingin dibeli! : "))
        if beli == 1 and gems[0] >= 120:
            gems[0] -= 120
            print("\nSelamat anda telah membeli skin Alucrod dingin")
            beli_skin()
        elif beli == 2 and gems[0] >= 210:
            gems[0] -= 210
            print("\nSelamat anda telah membeli skin Guson belah tengah")
            beli_skin()
        elif beli == 3 and gems[0] >= 350:
            gems[0] -= 350
            print("\nSelamat anda telah membeli skin Agus Emo")
            beli_skin()
        elif beli == 4:
            selamat_datang()
        else:
            print("Pilihan tidak valid")
            beli_skin()
    except ValueError:
        print("Pilihan tidak valid")
        beli_skin()
```
Fungsi ini memungkinkan pengguna membeli skin menggunakan gems jika memiliki jumlah yang cukup.
```python
def selamat_datang():
    try:
        print(Style.RESET_ALL)
        print("[1] Cek Saldo")
        print("[2] Isi Saldo")
        print("[3] Cek Gems")
        print("[4] Isi Gems")
        print("[5] Beli Skin!")
        print("[6] Keluar")
        pilihan_awal = int(input("Silahkan pilih opsi : "))
        if pilihan_awal == 1:
            cek_saldo()
        elif pilihan_awal == 2:
            isi_saldo()
        elif pilihan_awal == 3:
            cek_gems()
        elif pilihan_awal == 4:
            top_up()
        elif pilihan_awal == 5:
            beli_skin()
        elif pilihan_awal == 6:
            print("Sampai jumpa lagi!")
            exit
        else:
            print("Pilihan tidak valid")
            selamat_datang()
    except ValueError:
        print("Pilihan tidak valid")
        selamat_datang()
```
Fungsi ini adalah menu utama yang menampilkan semua opsi bagi pengguna untuk mengecek saldo, menambah saldo, mengecek gems, melakukan top-up, atau membeli skin.
``` python
nama = input("Silahkan masukkan nama kamu : ")
id = int(input("Silahkan masukkan ID kalian, contoh(2409116063) : "))
print(Fore.BLUE + f"\nSelamat datang {id} ({nama}), di Toko Pikri")
selamat_datang()
```
