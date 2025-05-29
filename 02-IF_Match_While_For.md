# Branching
## IF statement
Sebuah IF terdiri dari if, condition, dan statement
```python
if (condition):
  statement 1
else:
  statement 2
```

![image](https://github.com/user-attachments/assets/2b22c4a9-b5f0-4ebd-9df5-069781e6e553)

contoh
```python
if len(username) < 3:
  print("Invalid username. Must be at least 3 characters long")
else:
  print("Valid username")
```

If statement, without indentation (will raise an **error**):
```python
a = 33
b = 200
if b > a:
print("b is greater than a") # you will get an error
```

### Elif
Keyword ```elif``` adalah cara Python mengatakan "jika kondisi sebelumnya tidak benar, maka coba kondisi ini".

![image](https://github.com/user-attachments/assets/1ceb0a0f-1d8d-4f20-92b1-26087198558d)
- Jika ekspresi pertama benar, pernyataan1 dieksekusi sebelum program melanjutkan dengan pernyataan_berikutnya.
- Jika ekspresi pertama tidak benar, ekspresi kedua akan dicek. Jika ekspresi pertama tidak benar, dan ekspresi kedua benar, pernyataan2 dijalankan. 
- Jika kedua ekspresi salah, pernyataan3 dieksekusi. Hanya satu dari tiga pernyataan yang dieksekusi.
- Jumlah dari kondisi yang menjadi pilihan tak terbatas.

```python
if b > a:
a = 33
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```

### Else
Keyword ```else``` menangkap apa pun yang tidak ditangkap oleh kondisi sebelumnya.
```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

### Short Hand If ... Else
Dipakai kalau if else nya dingkat dan hanya punya 1 statement
```python
a = 2
b = 330
print("A") if a > b else print("B")
```

### Nested IF
```python
x = 41

if x > 10:
  print("Above ten,")
  if x > 20:
    print("and also above 20!")
  else:
    print("but not above 20.")
```

## Match
- Ekspresi ```match``` dievaluasi sekali.
- Nilai ekspresi dibandingkan dengan nilai setiap kasus.
- Jika ada kecocokan, blok kode terkait dieksekusi.
```python
day = 4
match day:
  case 1:
    print("Monday")
  case 2:
    print("Tuesday")
  case 3:
    print("Wednesday")
  case 4:
    print("Thursday")
  case 5:
    print("Friday")
  case 6:
    print("Saturday")
  case 7:
    print("Sunday")
```

### Combine Values
```python
day = 4
match day:
  case 1 | 2 | 3 | 4 | 5:
    print("Today is a weekday")
  case 6 | 7:
    print("I love weekends!")
```

### IF segabai guard match
```python
month = 5
day = 4
match day:
  case 1 | 2 | 3 | 4 | 5 if month == 4:
    print("A weekday in April")
  case 1 | 2 | 3 | 4 | 5 if month == 5:
    print("A weekday in May")
  case _:
    print("No match")
```

## While Loop
Di while loop, kode atau statement akan dieksekusi selama conditionnya **true**.

Perulangan while memerlukan variabel relevan sebelum memulai loop, di contoh ini kita perlu mendefinisikan variabel pengindeksan, x, yang kita tetapkan ke 0.
```python
x =   0      # Initializing nilai x
while x < 3:
    print("Not there yet, x=" + str(x))
    x = x + 1
print("x=" + str(x))

# Output
# Not there yet, x=0
# Not there yet, x=1
# Not there yet, x=2
# x=3
```
> Initializing - memberi nilai inisial pada variabel

### Break
break statement bisa menghentikan loop bahkan kalaupun kondisinya masih True
```python
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```

### Continue
```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

### else in while
```python
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```

## For Loop
contoh 1 **in range()**
```python
for x in range(3):
    print(x)
# Output
# 0
# 1
# 2
```

contoh 2 **in range() dengan batas**
```python
product = 1
for n in range(2,4):    # nilai n mulai dr 2 sampai sebelum 4
  product = product * n

print(product)
# Output
# 6
```
