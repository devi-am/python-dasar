### Opsi Tools:
| Tool | Keterangan |
|------|------------|
| Python | Bahasa pemrograman utama |
| Jupyter Notebook | Editor berbasis web interaktif |
| Google Colab | Jupyter Notebook berbasis cloud, gratis |
| VSCode | Editor kode yang ringan dan fleksibel |

# Language of python
- **Variables**: Represent data stored as strings, tuples, dictionaries, lists, and objects (note: future readings explain these categories)
- **Keywords**: Special words that are reserved for specific purposes and that can only be used for those purposes
- **Operators**: Symbols that perform operations on objects and values
- **Expressions**: A combination of numbers, symbols, and variables to compute and return a result upon evaluation
- **Functions**: A group of related statements to perform a task and return a value
- **Conditional** **statements**: Sections of code that direct program execution based on specified conditions

## Naming Rules
 - tidak bisa mengandung **spasi**
 - bisa dicampur **uppercase lowwercase**
 - tidak bisa diawali **angka**, tapi setelahnya boleh ada angka
 - nama variable & function harus **snake_case**
 - nama **deskriptif** lebih baik daripada **singkatan** (student_name daripada sn)

# Data Type (Tipe Data)
 - **annotate** = mendefinisikan tipe data suatu variabel (fungsi utk reduces the chance of common mistakes, helps in documenting your code for others to reuse, and allows integrated development software (IDEs) and other tools to give you better feedback)
 - tipe data python dinamis (**dinamic typing**) atau gaperlu deklarasiin tipe datanya kyk bhs C
 - annotate python bisa dilakukan dgn: <br>kasi komen  ```captain = “Picard”      # type: str``` <br>annotate langsung  ```captain: str = “Picard”```
 - Text Type:	```str```
 - Numeric Types:	```int```, ```float```, ```complex```

#### String
```python
x = "Hello World"
print(type(x))
```

#### Integer
Int, atau integer, adalah semua angka, positive atau negative, tanpa desimal, dengan ukuran tak terbatas.
```python
x = 1
y = 35656222554887711
z = -3255522

print(type(x))
print(type(y))
print(type(z))
```

#### Float
Float, atau "floating point number" adalah angka, positive atau negative, yang mengandung satu atau lebih desimal.
```python
x = 1.10
y = 1.0
z = -35.59

print(type(x))
print(type(y))
print(type(z))
```
Float juga bisa menggunakan angka scientific menggunakan "e" untuk menandakan pangkat 10.
```python
x = 35e3
y = 12E4
z = -87.7e100

print(type(x))
print(type(y))
print(type(z))
```

#### Complex
Mengandung bilangan imajinary
```python
x = 3+5j
y = 5j
z = -5j

print(type(x))
print(type(y))
print(type(z))
```

## Convertion (konversi)
contoh:
```python
base = 6
height = 3
area = (base*height)/2
print("The area of the triangle is: " + str(area)) 
```

## Expressions and variables
- **expression** - kombinasi angka, simbol, alau values lain yang menghasilkan result saat dievaluasi
- **data types** - classes of data (e.g., string, int, float, Boolean, etc.), which include the properties and behaviors of instances of the data type (variables)
- **variable** - an instance of a data type class, represented by a unique name within the code, that stores changeable values of the specific data type
- **implicit conversion** - saat Python interpreter mengonversi otomatis suatu data type ke tipe lain
- **explicit conversion** - when code is written to manually convert one data type to another using a data type conversion function:
  * ```str()``` - converts a value (often numeric) to a string data type
  * ```int()``` - converts a value (usually a float) to an integer data type
  * ```float()``` - converts a value (usually an integer) to a float data type

# Operasi Aritmatika
![image](https://github.com/user-attachments/assets/adb594ef-3dd4-45dd-896a-cc8fa5b6489b)

## Assignment Operator
![image](https://github.com/user-attachments/assets/3b1089a7-5a6a-436e-bc6e-0c71815f7dac)

## Comparing atau True False (Boolean)
### Comparison Operator
- **==**    (equality) 
- **!=**    (not equal to) 
- **>**     (greater than)
- **<**     (less than)
- **>=**    (greater than or equal to)
- **<=**    (less than or equal to)
> kalo beda tipe data gabisa dibandingin **selain** pake == dan =!
> <br>return True/False (boolean)

### Comparison String
- kalo dibandingin yang dibandingin nilai ACII nya.
- yang dibandingin huruf **pertama** string
![image](https://github.com/user-attachments/assets/f2c1d8d3-92c3-4b08-bf36-fd8116f1c0c9)

### Logical Operators
hasilnya sama kyk gerbang logika
- AND
  | Syarat 1 | Syarat 2 | Hasil |
  | -------- | -------- | ----- |
  | True | True | True |
  | True | False | False |
  | False | True | False |
  | False | False | False |
- OR
  | Syarat 1 | Syarat 2 | Hasil |
  | -------- | -------- | ----- |
  | True | True | True |
  | True | False | True |
  | False | True | True |
  | False | False | False |
- NOT
