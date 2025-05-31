# Latihan Pemrograman Python: String, List, Tuple, dan Dictionary

## Soal Latihan Materi
### String
1.	Buatlah sebuah variabel bertipe string yang berisi kalimat: Saya sedang belajar Python.
    ``` python
    # 1. Buat variabel bertipe string
    kalimat = "Saya sedang belajar Python."
    ```
2.	Tampilkan karakter ke-6 dari string tersebut.
    ``` python
    # 2. Tampilkan karakter ke-6 (indeks ke-5 karena indeks dimulai dari 0)
    karakter_ke_6 = kalimat[5]
    print("Karakter ke-6:", karakter_ke_6)
    ```
3.	Tampilkan 10 karakter pertama dari string tersebut.
    ``` python
    # 3. Tampilkan 10 karakter pertama (indeks 0 sampai 9)
    sepuluh_karakter_pertama = kalimat[:10]
    print("10 karakter pertama:", sepuluh_karakter_pertama)
    ```
4.	Ubah string tersebut menjadi huruf kapital.
    ``` python
    # 4. Ubah string menjadi huruf kapital (uppercase)
    huruf_kapital = kalimat.upper()
    print("Huruf kapital:", huruf_kapital)
    ```
5.	Ubah string tersebut menjadi huruf kecil.
    ``` python
    # 5. Ubah string menjadi huruf kecil (lowercase)
    huruf_kecil = kalimat.lower()
    print("Huruf kecil:", huruf_kecil)
    ```
6.	Hitung berapa banyak huruf 'a' pada string tersebut.
    ``` python
    # 6. Hitung jumlah huruf 'a'
    jumlah_a = kalimat.count('a')
    print("Jumlah huruf 'a':", jumlah_a)
    ```
7.	Gabungkan dua string: 'Halo' dan 'Dunia' menjadi 'Halo Dunia' menggunakan join().
    ``` python
    # Dua string
    kata1 = "Halo"
    kata2 = "Dunia"

    # Gabungkan dengan join dan spasi sebagai pemisah
    hasil = ' '.join([kata1, kata2])
    print("Gabungan:", hasil)
    ```
8.	Ganti kata 'belajar' menjadi 'mengajar' pada string di soal nomor 1.
    ```python
    kalimat = "Saya sedang belajar Python."
    kalimat_baru = kalimat.replace("belajar", "mengajar")
    print("Kalimat setelah diganti:", kalimat_baru)
    ```

### List
9.	Buatlah sebuah list berisi 5 nama buah.
    ```python
    # 9. Buat list berisi 5 nama buah
    buah = ["apel", "mangga", "jeruk", "pisang", "semangka"]
    ```
10.	Tambahkan satu buah baru ke list tersebut menggunakan method append.
    ```python
    # 10. Tambahkan satu buah baru ke list menggunakan append
    buah.append("nanas")
    ```
11.	Tambahkan buah di awal list menggunakan insert.
    ```python
    # 11. Tambahkan buah di awal list menggunakan insert
    buah.insert(0, "stroberi")
    ```
12.	Hapus buah ketiga dari list menggunakan method remove.
    ```python
    # 12. Hapus buah ketiga dari list menggunakan remove
    buah.remove(buah[2])  # buah ketiga (indeks ke-2)
    ```
13.	Gunakan loop untuk mencetak seluruh isi list.
    ```python
    # 13. Gunakan loop untuk mencetak seluruh isi list
    print("Daftar buah:")
    for b in buah:
        print("-", b)
    ```
14.	Gunakan list comprehension untuk membuat list baru berisi panjang tiap nama buah.
    ```python
    # 14. List comprehension: panjang tiap nama buah
    panjang_buah = [len(nama) for nama in buah]
    print("Panjang tiap nama buah:", panjang_buah)
    ```

### Tuple
15.	Buat sebuah tuple berisi 5 nama hewan: kucing, anjing, kelinci, rubah, bison.
    ```python
    hewan = ("kucing", "anjing", "kelinci", "rubah", "bison")
    ```
16.	Tampilkan item ke-3 dari tuple tersebut
    ```python
    print("Item ke-3:", hewan[2])
    ```
17.	Cek apakah kata “bison” ada dalam tuple menggunakan IF
    ```python
    if "bison" in hewan:
        print("Bison ada dalam tuple.")
    else:
        print("Bison tidak ada dalam tuple.")
    ```

### Dictionary
18.	Buat dictionary dengan key: nama, umur, dan alamat.
    ```python
    # Buat dictionary
    data_diri = {
        "nama": "Andi",
        "umur": 21,
        "alamat": "Surakarta"
    }
    ```
19.	Tambahkan key baru: 'pekerjaan' dengan value 'mahasiswa'.
    ```python
    # Tambahkan key 'pekerjaan'
    data_diri["pekerjaan"] = "mahasiswa"
    ```
20.	Tampilkan semua key yang ada dalam dictionary.
    ```python
    # Tampilkan semua key
    print("Key dalam dictionary:", data_diri.keys())
    ```
21.	Tampilkan semua value dari dictionary.
    ```python
    # Tampilkan semua value
    print("Value dalam dictionary:", data_diri.values())
    ```
22.	Gunakan loop untuk mencetak key dan valuenya.
    ```python
    # Gunakan loop untuk mencetak key dan value
    print("Isi dictionary:")
    for key, value in data_diri.items():
        print(f"{key}: {value}")
    ```
 
## Soal Naratif
### Soal Naratif 1
Buat sebuah program yang bisa menerima inputan berupa kalimat string. Kemudian pisah kalimat tersebut menjadi per kata menggunakan split() dan simpan inputan tersebut dalam bentuk list.
Contoh output:
```python
Masukkan kalimat Anda: saya memiliki kucing oren yang sangat gila
List: [“saya”, “memiliki”, “kucing”, “oren”, “yang”, “sangat”, “gila”]
```


### Soal Naratif 2
Dina memiliki sebuah string: "Saya suka makan apel dan jeruk". 
Gunakan slicing untuk mengambil kata "apel" dan simpan dalam list. Kemudian, tambahkan "anggur" ke dalam list tersebut.
Terakhir, buat dictionary dengan key 'buah_favorit' dan value-nya adalah list buah tersebut.

Contoh Output:
``` python
['apel', 'anggur']
{'buah_favorit': ['apel', 'anggur']}
```

### Soal Naratif 3
Buatlah program yang meminta input berupa string nama lengkap.
Pisahkan nama depan dan nama belakang ke dalam tuple. Kemudian simpan hasilnya ke dalam dictionary dengan key 'nama' dan value-nya adalah tuple tersebut.

Contoh Output:
``` python
Input: Budi Santoso
Tuple: ('Budi', 'Santoso')
Dictionary: {'nama': ('Budi', 'Santoso')}
```

### Soal Naratif 4
Buat list berisi 3 angka. Kalikan setiap angka dengan panjang string 'Python' dan simpan hasilnya di list baru.
Lalu, buat dictionary dengan key 'hasil' dan value-nya adalah list hasil perkalian tersebut.

Contoh Output:
``` python
List hasil: [36, 60, 84]
Dictionary: {'hasil': [36, 60, 84]}
```

### Soal Naratif 5
Buatlah program Python yang menerima sebuah kata atau kalimat dari pengguna, lalu mengecek apakah kata atau kalimat tersebut merupakan palindrome atau bukan.
Note:
-	Palindrome adalah kata yang jika dibalik tetap sama, contoh: "katak", "radar", "level".
-	Gunakan konsep indexing dan slicing untuk menyelesaikan soal ini.
Contoh Output:
``` python
Contoh 1:
Masukkan sebuah kata: katak
'katak' adalah palindrome
Contoh 2:
Masukkan sebuah kata: rumah
'rumah' bukan palindrome
Contoh 3:
Masukkan sebuah kata: kasur rusak
'kasur rusak’ adalah palindrome
```

### Soal Naratif 6
Buat sebuah variable yang bisa menampung Kumpulan kata sekaligus. Kemudian buat program Python untuk:
1.	Mencari kata terpanjang dari kumpulan kata tersebut
2.	Mencari kata terpendek dari kumpulan kata tersebut
Contoh:
Terdapat Kumpulan kata “pisang", "apel", "anggur", "kiwi", "semangka", "leci".
Contoh output yang diharapkan:
``` python
Kata terpanjang adalah: semangka
Kata terpendek adalah: kiwi
```
