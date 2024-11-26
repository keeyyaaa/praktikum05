# Praktikum 5 Dictionary: Program Sederhana Daftar Nilai Mahasiswa

Nama : Ica Rizqiah

Kelas : TI.24.A5

Nim : 312410554

Mata kuliah: Bahasa pemrogaman

## Berikut Flowchart alur

![foto](https://github.com/keeyyaaa/praktikum05/blob/main/FLOWCHART%20LABPY05.jpg?raw=true)

# Penjelasan kode program

## 1. Import dan Struktur Data
   
   ```data_mahasiswa = {}```

   Penjelasan: data_mahasiswa adalah dictionary kosong yang digunakan untuk menyimpan semua data mahasiswa. NIM akan digunakan sebagai key, dan nilai (value) berupa dictionary berisi nama, nilai tugas, UTS, UAS, dan nilai akhir.

## 2. Fungsi `tambah_data`

  ```python
def tambah_data():
    print("Tambah Data")
    nim = input("NIM        : ")
    nama = input("Nama       : ")
    tugas = float(input("Nilai Tugas: "))
    uts = float(input("Nilai UTS  : "))
    uas = float(input("Nilai UAS  : "))
    nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
    data_mahasiswa[nim] = {"nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": nilai_akhir}
    print("Data berhasil ditambahkan!\n")
```

Fungsi ini menerima masukan NIM, nama, dan nilai tugas, UTS, serta UAS dari pengguna.

Nilai akhir dihitung menggunakan rumus:

Nilai akhir=(30%*tugas)+(35%*UTS)+(35%*UAS)

Data mahasiswa disimpan dalam dictionary `data_mahasiswa` dengan NIM sebagai kunci.

## 3. Fungsi `tampilkan_data`

```python
def tampilkan_data():
    if not data_mahasiswa:
        print("\nDaftar Nilai\n")
        print("TIDAK ADA DATA\n")
    else:
        print("\nDaftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |   NAMA   | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        for i, (nim, data) in enumerate(data_mahasiswa.items(), start=1):
            print(f"| {i:2} | {nim:8} | {data['nama']:8} | {data['tugas']:5} | {data['uts']:3} | {data['uas']:3} | {data['akhir']:.2f} |")
        print("=" * 50)
    print()
```

Penjelasan:

Jika tidak ada data di dictionary, program menampilkan pesan "TIDAK ADA DATA".

Jika ada data, program menampilkan daftar nilai mahasiswa dalam format tabel. Data diambil dari dictionary menggunakan perulangan for.

Fungsi `enumerate` digunakan untuk memberikan nomor urut (index), mulai dari 1.

## 4.  Fungsi `ubah_data`

```python
def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    if nim in data_mahasiswa:
        print("Data ditemukan. Masukkan data baru:")
        data_mahasiswa[nim]['nama'] = input("Nama       : ")
        data_mahasiswa[nim]['tugas'] = float(input("Nilai Tugas: "))
        data_mahasiswa[nim]['uts'] = float(input("Nilai UTS  : "))
        data_mahasiswa[nim]['uas'] = float(input("Nilai UAS  : "))
        data_mahasiswa[nim]['akhir'] = (data_mahasiswa[nim]['tugas'] * 0.3) + \
                                       (data_mahasiswa[nim]['uts'] * 0.35) + \
                                       (data_mahasiswa[nim]['uas'] * 0.35)
        print("Data berhasil diubah!\n")
    else:
        print("Data tidak ditemukan!\n")
```

Penjelasan:

Fungsi ini mencari data berdasarkan NIM yang diinputkan pengguna.

Jika data ditemukan, pengguna diminta memasukkan data baru, dan nilai akhir diperbarui dengan rumus yang sama seperti sebelumnya.

Jika NIM tidak ditemukan, program menampilkan pesan "Data tidak ditemukan!".

## 5. Fungsi `hapus_data`

```python
def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    if nim in data_mahasiswa:
        del data_mahasiswa[nim]
        print("Data berhasil dihapus!\n")
    else:
        print("Data tidak ditemukan!\n")
```

Penjelasan:

Fungsi ini mencari data berdasarkan NIM yang diinputkan.

Jika NIM ditemukan, data mahasiswa dihapus menggunakan perintah del.

Jika tidak ditemukan, program menampilkan pesan "Data tidak ditemukan!".

## 6. Fungsi `cari_data`

```python
def cari_data():
    nim = input("Masukkan NIM yang dicari: ")
    if nim in data_mahasiswa:
        data = data_mahasiswa[nim]
        print("\nData ditemukan:")
        print(f"NIM        : {nim}")
        print(f"Nama       : {data['nama']}")
        print(f"Nilai Tugas: {data['tugas']}")
        print(f"Nilai UTS  : {data['uts']}")
        print(f"Nilai UAS  : {data['uas']}")
        print(f"Nilai Akhir: {data['akhir']:.2f}\n")
    else:
        print("Data tidak ditemukan!\n")
```

Penjelasan:

Fungsi ini mencari data mahasiswa berdasarkan NIM.

Jika ditemukan, data lengkap mahasiswa ditampilkan.

Jika tidak ditemukan, program menampilkan pesan "Data tidak ditemukan!".

## 7. Menu Utama

```python
while True:
    print("Program Input Nilai")
    print("===================")
    print("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar")
    pilihan = input("Pilihan: ").lower()

    if pilihan == 'l':
        tampilkan_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program. Terima kasih!")
        break
    else:
        print("Pilihan tidak valid!\n")
```

Penjelasan:

Program menampilkan menu pilihan setiap kali perulangan dijalankan.

Input pengguna diterjemahkan ke huruf kecil menggunakan .lower().

Berdasarkan pilihan pengguna:

'l': Menampilkan semua data.

't': Menambah data baru.

'u': Mengubah data mahasiswa.

'h': Menghapus data mahasiswa.

'c': Mencari data mahasiswa berdasarkan NIM.

'k': Keluar dari program.

# Berikut adalah contoh penggunaan program

![foto](

   
