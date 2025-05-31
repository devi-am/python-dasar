# Latihan Pemrograman Python: String, List, Tuple, dan Dictionary

## Soal Latihan Materi
### String
1.	Buatlah sebuah variabel bertipe string yang berisi kalimat: Saya sedang belajar Python.
2.	Tampilkan karakter ke-5 dari string tersebut.
3.	Tampilkan 10 karakter pertama dari string tersebut.
4.	Ubah string tersebut menjadi huruf kapital.
5.	Ubah string tersebut menjadi huruf kecil.
6.	Hitung berapa banyak huruf 'a' pada string tersebut.
7.	Gabungkan dua string: 'Halo' dan 'Dunia' menjadi 'Halo Dunia'.
8.	Ganti kata 'belajar' menjadi 'mengajar' pada string di soal nomor 1.

### List
9.	Buatlah sebuah list berisi 5 nama buah.
10.	Tambahkan satu buah baru ke list tersebut menggunakan method append.
11.	Tambahkan buah di awal list menggunakan insert.
12.	Hapus buah ketiga dari list menggunakan method remove.
13.	Gunakan loop untuk mencetak seluruh isi list.
14.	Gunakan list comprehension untuk membuat list baru berisi panjang tiap nama buah.

### Tuple
15.	Buat sebuah fungsi bernama `konversi_detik` yang menerima input detik dan mengembalikan jam, menit, dan detik (dalam bentuk tuple).
16.	Cetak hasil dari pemanggilan fungsi tersebut dengan input 7260.

### Dictionary
17.	Buat dictionary dengan key: nama, umur, dan alamat.
18.	Tambahkan key baru: 'pekerjaan' dengan value 'mahasiswa'.
19.	Tampilkan semua key yang ada dalam dictionary.
20.	Tampilkan semua value dari dictionary.
21.	Gunakan loop untuk mencetak key dan valuenya.
 
## Soal Gabungan (Naratif)
### Soal Gabungan 1
Dina memiliki sebuah string: "Saya suka makan apel dan jeruk". 
Gunakan slicing untuk mengambil kata "apel" dan simpan dalam list. Kemudian, tambahkan "anggur" ke dalam list tersebut.
Terakhir, buat dictionary dengan key 'buah_favorit' dan value-nya adalah list buah tersebut.

Contoh Output:
``` python
['apel', 'anggur']
{'buah_favorit': ['apel', 'anggur']}
```

### Soal Gabungan 2
Buatlah program yang meminta input berupa string nama lengkap.
Pisahkan nama depan dan nama belakang ke dalam tuple. Kemudian simpan hasilnya ke dalam dictionary dengan key 'nama' dan value-nya adalah tuple tersebut.

Contoh Output:
``` python
Input: Budi Santoso
Tuple: ('Budi', 'Santoso')
Dictionary: {'nama': ('Budi', 'Santoso')}
```

### Soal Gabungan 3
Buat list berisi 3 angka. Kalikan setiap angka dengan panjang string 'Python' dan simpan hasilnya di list baru.
Lalu, buat dictionary dengan key 'hasil' dan value-nya adalah list hasil perkalian tersebut.

Contoh Output:
``` python
List hasil: [36, 60, 84]
Dictionary: {'hasil': [36, 60, 84]}
```
