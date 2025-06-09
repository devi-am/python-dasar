## Set
Set menggunakan kurung kurawal {}
> item Set tidak dapat diubah, tapi bisa menghapus item dan menambah item baru.<br>
> item Set dapat muncul dalam urutan yang berbeda setiap kali dipakai, tidak bisa dirujuk pakai index atau key.<br>
> tidak boleh memiliki item duplikat
```python
myset = {"apple", "banana", "cherry"}
```
### Set bisa mengandung berbagai tipe data
```python
set1 = {"apple", "banana", "cherry"}
set2 = {1, 5, 7, 9, 3}
set3 = {True, False, False}
set4 = {"abc", 34, True, 40, "male"}
```
### Akses Item Set
- menggunakan for loop
  ```python
  thisset = {"apple", "banana", "cherry"}

  for x in thisset:
    print(x)
  ```
- menggunakan IF
  ```python
  thisset = {"apple", "banana", "cherry"}

  if "banana" in thisset:
    print("banana" in thisset)
  ```
### Menambahkan Set
- menggunakan add()
  ```python
  thisset = {"apple", "banana", "cherry"}

  thisset.add("orange")

  print(thisset)
  ```
- menggunakan update()
  ```python
  # contoh 1
  thisset = {"apple", "banana", "cherry"}
  tropical = {"pineapple", "mango", "papaya"}

  thisset.update(tropical)

  print(thisset)

  # contoh 2
  thisset = {"apple", "banana", "cherry"}
  mylist = ["kiwi", "orange"]

  thisset.update(mylist)

  print(thisset)
  ```

### Menggabungkan 2 Set
```python
set1 = {"apple", "banana"}
set2 = {"cherry", "banana"}
set3 = set1.union(set2)
print(set3)
```

### Menghapus Set
- menggunakan remove()
  ```python
  thisset = {"apple", "banana", "cherry"}

  thisset.remove("banana")

  print(thisset)
  ```
- menggunakan discard()
  ```python
  thisset = {"apple", "banana", "cherry"}

  thisset.discard("banana")

  print(thisset)
  ```
- menggunakan pop() untuk menghapus item **random**
  ```python
  thisset = {"apple", "banana", "cherry"}

  x = thisset.pop()

  print(x)
  print(thisset)
  ```
- menggunakan clear() dan del untuk menghapus seluruh Set
  ```python
  thisset = {"apple", "banana", "cherry"}

  thisset.clear()

  print(thisset)
  ```
  ```python
  thisset = {"apple", "banana", "cherry"}

  del thisset

  print(thisset)
  ```

## Function
Fungsi di python menggunakan keyword ```def```
```python
def my_function():
  print("Hello from a function")
```

### Fungsi dengan parameter
```python
def luas_segitiga(alas, tinggi):
    luas = alas * tinggi /2
    print(luas)
```

### Return
```python
def luas_persegi(sisi):
    luas = sisi**2

    return luas
```

### Memanggil Fungsi
```python
def my_function():
  print("Hello from a function")

my_function()
```
- memanggil dengan argumen
  ```python
  def my_function(fname):
  print(fname + " Refsnes")

  my_function("Emil")
  my_function("Tobias")
  my_function("Linus")
  ```
## Modul
Modul adalah file Python (.py) yang berisi kumpulan fungsi, variabel, atau class yang bisa digunakan ulang di program lain.<br>
### import
Untuk bisa memakai modul pertama harus melakukan ```import``` modul. Contoh di bawah ini adalah pemanggilan beberapa modul
```python
import math  # modul untuk matematika
import random  # modul untuk membuat angka random
```
### import as
Bisa juga memisalkan nama modul menjadi huruf atau kata singkat agar lebih ringkas saat memanggil modul.
```python
import math as m
import datetime as dt
```

### Menggunakan modul
Untuk menggunakan modul, caranya adalah dengan memanggil nama modulnya (bisa ketik permisalannya kalau dimisalkan dengan ```as```) kemudian mengetik fungsi dari modul tersebut yang mau dipakai
```python
import math as m
import datetime as dt

nilai_pi = m.pow(2, 3)  # 2 pangkat 3 (2^3)  # menggunakan fungsi pow() pada modul math untuk pemangkatan

tanggal_hari_ini = dt.date.today()  # menggunakan fungsi date.today() pada modul datetime untuk mengambil tanggal hari ini
```
