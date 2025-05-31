# String
Strings di python diapit oleh petik dua ("") atau petik satu ('').<br>
contoh:
```python
data = "Ini adalah data string"
```
### Quotes di dalam Quotes
Kalimat di dalam data string bisa mengandung tanda petik, asalkan tidak matching dengan tanda petik yang melingkup string

contoh:
```python
print("It's alright")
print("He is called 'Johnny'")
print('He is called "Johnny"')
```

### Menggunakan loop untuk memanggil string
```python
for x in "banana":
  print(x)
```

### string bisa dikali integer
  ```python
  "example" * 3
  # Output
  # exampleexampleexample
  ```
###  bisa gunain **index** juga untuk memanggil string
   ```python
   fruit = "Pineapple"
   print(fruit[2])
   print(fruit[:4])
   print(fruit[4:])
   ```
### mengganti string:
   ```python
   message = "A kong string with a silly typo"
   # cara 1
   new_message = message[0:2] + "l" + message[3:]

   # cara 2
   message = "And another one"
   ```
###  mencari index suatu character di dalam string
   ```python
   pets="Cats & Dogs"
   pets.index("&")
   ```
### contoh lain mengganti huruf dalam string:
```python
email = "12@gmail.com"
old_domain = "gmail.com"
new_domain = "yahoo.com"

if "@" + old_domain in email:
  index = email.index("@" + old_domain)
  new_email = email[:index] + "@" + new_domain
 
print(index)
print(new_email)

# Output:
# 2
# 12@yahoo.com
```
### Fungsi Fungsi untuk String
- ```len()``` - utk mencari panjang string
- ```.upper()``` - ganti string jadi kapital
- ```.lower()``` - ganti string jadi lowercase
- ```.strip()``` - hapus " " kiri string dan kanan string)
- ```.lstrip()``` - hapus " " kiri string
- ```.rstrip()``` - hapus " " kanan string
- ```.count()``` - hitung banyak character/substring dlm string
- ```.endswith()``` - return Boolean, cek akhir string
- ```.isnumeric()``` - return Boolean, cek apakah numerik
- ```.isalpha()``` - Returns Boolean, cek apakah hanya ada huruf di String.
- ```int()``` - ubah tioe data ke integer
- ```.replace(old, nes)``` - returrn string baru
  ```python
  test = "How-much-wood-would-a-woodchuck-chuck"
  print(test.replace("wood", "plastic"))  # prints "How much plastic would a plasticchuck chuck"
  ```
- ```.join()``` - mengisi join gabungan string 
  ```python
  "...".join(["This", "is", "a", "phrase", "joined", "by", "triple", "dots"])
  # Output
  This...is...a...phrase...joined...by...triple...dots
  ```
- ```.split()```
  ```python
  "This is another example".split()
  # Output
  # ['This', 'is', 'another', 'example']
  ```
### cara memanggil string dan tipe data lain
  ```python
  # cara 1
  name = "Manny"
  number = len(name) * 3
  print("Hello {}, your lucky number is {}".format(name, number))
  
  # cara 2
  name = "Manny"
  print("Your lucky number is {number}, {name}.".format(name=name, number=len(name)*3))

  # cara 3
  price = 7.5
  with_tax = price * 1.09
  print(price, with_tax)
  print("Base price: ${:.2f}. With Tax: ${:.2f}".format(price, with_tax))

  # cara  4
  def to_celsius(x):
  return (x-32)*5/9
  
  for x in range(0,101,10):
  print("{:>3} F | {:>6.2f} C".format(x, to_celsius(x)))
  ```
### formating expressions
  ![image](https://github.com/user-attachments/assets/73e568f1-afbf-4cc3-832f-712355eeca6e)


# Array
**Array** adalah struktur data yang menyimpan banyak nilai dalam satu variabel dengan **jenis data yang sama** dan tersimpan dalam **urutan**.<br>
Contoh: array yang menyimpan hanya angka: `[1, 2, 3, 4]`

> Catatan: Python tidak memiliki array bawaan seperti bahasa C, tapi menggunakan:
> - `list` → alternatif array fleksibel
> - `array` (dari modul `array`) → array efisien dengan tipe tetap
> - `numpy.array` → array modern dan powerful untuk scientific computing


### Array dengan Modul `array`

### Import dan Membuat Array
```python
import array

angka = array.array('i', [10, 20, 30, 40])
print(angka)

## List
```python
x = ["Now", "we", "are", "cooking!"]
print(type(x))
print(x)
print(len(x))
print(x[0])

# Output
# <class 'list'>
# ['Now', 'we', 'are', 'cooking!']
# 4
# Now
```
### modifying content List
- append (tambah belakang sendiri)
  ```python
  fruits = ["Pineapple", "Banana", "Apple", "Melon"]
  fruits.append("Kiwi")
  print(fruits)
  
  # Output
  # ['Pineapple', 'Banana', 'Apple', 'Melon', 'Kiwi']
  ```
- insert (tambah depan sendiri atau sesuai index)
  no index
  ```python
  fruits = ["Pineapple", "Banana", "Apple", "Melon"]
  fruits.insert(0, "Orange")
  print(fruits)

  # Output
  # ['Orange', 'Pineapple', 'Banana', 'Apple', 'Melon']
  ```
  with index
  ```python
  fruits = ["Pineapple", "Banana", "Apple", "Melon"]
  fruits.insert(25, "Peach")
  print(fruits)

  # Output
  # ['Pineapple', 'Pineapple', 'Banana', 'Apple', 'Melon', 'Peach']
  ```
- remove
  ```python
  fruits = ["Pineapple", "Banana", "Apple", "Melon"]
  fruits.remove("Banana")
  print(fruits)

  # Output
  # ['Pineapple', 'Apple', 'Melon']
  ```
- pop
  ```python
  fruits = ["Pineapple", "Banana", "Apple", "Melon"]
  fruits.pop(3)
  print(fruits)

  # Output
  # ["Pineapple", "Banana", "Melon"]
  ```

## Tuple
Tuple pakai kurung (), bukan kurung persegi kyk list [] <br>
```python
thistuple = ("apple", "banana", "cherry")
print(thistuple)
```
### Tuple berisi 1 item
untuk membuat tuple berisi 1 item, tambahkan koma (,) di akhir
```python
thistuple = ("apple",)
print(type(thistuple))

#NOT a tuple
thistuple = ("apple")
print(type(thistuple))
```
### Tuple bisa mengandung berbagai tipe data
```python
tuple1 = ("apple", "banana", "cherry")
tuple2 = (1, 5, 7, 9, 3)
tuple3 = (True, False, False)
tuple4 = ("abc", 34, True, 40, "male")
```

### Akses Tuple
- indexing
  ```python
  thistuple = ("apple", "banana", "cherry")
  print(thistuple[1])
  ```
- range index
  ```python
  thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")
  print(thistuple[2:5])
  ```
- akses dengan IF
  ```pythom
  thistuple = ("apple", "banana", "cherry")
  if "apple" in thistuple:
    print("Yes, 'apple' is in the fruits tuple")
  ```

# Perbedaan List dan Tuple: <br>
| List | Tuple |
| ---- | ----- |
| Isinya bisa diubah | Isinya tidak bisa diubah |
| Pakai kurung persegi [] | pakai kurung biasa () |

# List 
List adalah data yang berisi list/urutan element tapi isinya bisa diubah <br>
contoh:
```python
thislist = ["apple", "banana", "cherry"]
print(thislist)
```
Item 'List' urut, dapat diubah, dan memungkinkan nilai duplikat.<br>
Item 'List' memiliki index, item pertama memiliki indeks [0], item kedua memiliki indeks [1], dst.<br>

### List len()
```python
thislist = ["apple", "banana", "cherry"]
print(len(thislist))

# Output:
# 3
```

### List Items - Data Types
List dapat menampung berbagai tipe data
```python
list1 = ["apple", "banana", "cherry"]
list2 = [1, 5, 7, 9, 3]
list3 = [True, False, False]
list4 = ["abc", 34, True, 40, "male"]
```

### Access Items
- menggunakan index
  ```python
  thislist = ["apple", "banana", "cherry"]
  print(thislist[1])

  # Output
  # "banana"
  ```
- menggunakan IF untuk mengecek if Item Exists
  ```python
  thislist = ["apple", "banana", "cherry"]
  if "apple" in thislist:
    print("Yes, 'apple' is in the fruits list")
  ```
- menggunakan Loops
  ```python
  thislist = ["apple", "banana", "cherry"]
  for x in thislist:
    print(x)
  ```
- Loops range
  ```python
  thislist = ["apple", "banana", "cherry"]
  for i in range(len(thislist)):
    print(thislist[i])
  ```

### List comprehension
contoh 1:
```python
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```
contoh 2:
```python
### Simple List Comprehension
print("List comprehension result:")

# The following list comprehension compacts several lines 
# of code into one line:
print([x*2 for x in range(1,11)])

### Long form for loop
print("Long form code result:")

# The list comprehension above accomplishes the same result as
# the long form version of the code shown below:
my_list = []
for x in range(1,11):
    my_list.append(x*2)
print(my_list)

# Select Run to compare the two results.
```

# Dictionary
Dictionary berfungsi menyimpan data dengan format key:value.<be>
Dictionary menggunakan kurung kurawal {}
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
```

> Sejak Python versi 3.7, dictionary bersifat terurut.
> Pada Python 3.6 dan versi sebelumnya, dictionary tidak terurut.

> Maksud dictionary terurut, artinya item-item di dalamnya memiliki urutan yang terdefinisi, dan urutan tersebut tidak akan berubah.
> Sedangkan tidak terurut berarti item-item di dalamnya tidak memiliki urutan yang pasti, sehingga item tidak bisa diakses berdasarkan indeks.

### Duplicates Not Allowed
Dictionary tidak bisa memiliki dua item dengan key yang sama<br>
Nilai yang duplikat akan menimpa nilai yang sudah ada.
```ptyhon
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964,
  "year": 2020
}
print(thisdict)
```

### Dictionary Items - Data Types
Dictionary bisa menampung berbagai tipe data
```python
thisdict = {
  "brand": "Ford",
  "electric": False,
  "year": 1964,
  "colors": ["red", "white", "blue"]
}
```

### Accessing Items
- Merujuk pada **nama key**
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }
  x = thisdict["model"]
  print(x)

  # Output
  # Mustang
  ```
- Menggunakan get()
  ```python
  x = thisdict.get("model")
  ```
- Menggunakan IF untuk mengecek if exist
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }
  if "model" in thisdict:
    print("Yes, 'model' is one of the keys in the thisdict dictionary")
  ```

### Loops di Dictionary
- memanggil semua nama **key**
 ```python
  thisdict = {
   "brand": "Ford",
    "model": "Mustang",
   "year": 1964
 }

  for x in thisdict:
  print(x)
  ```
- memanggil semua **value**
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }

  for x in thisdict:
  print(thisdict[x])
  ```
- key() untuk return key di dict
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }

  for x in thisdict.keys():
  print(x)
  ```
- memanggil key dan value menggunakan item()
    ```python
    thisdict = {
      "brand": "Ford",
      "model": "Mustang",
      "year": 1964
    }

    for x, y in thisdict.items():
    print(x, y)
    ```
