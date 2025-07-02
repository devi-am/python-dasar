# Regression Linear
Regresi linier menggunakan hubungan antara titik-titik data untuk menggambar garis lurus melalui semuanya.
Garis ini merupakan pola yang dapat digunakan untuk memprediksi nilai-nilai di masa mendatang.

- Model hanya bisa dipakai untuk hubungan linier (lurus).
- Kalau hubungan datanya tidak lurus (misal kurva), perlu metode lain.
- Untuk prediksi yang lebih kompleks biasa menggunakan regresi ganda atau machine learning model lain.

Contohnya, kalau kita pengen tahu berapa harga rumah berdasarkan luas tanah, kita bisa gambar garis yang kira-kira ngasih tebakan harga.
Dari gambar garis atau grafik, kadang bisa nebak makin tinggi, makin mahal (linear).

```python
import seaborn as sns
import matplotlib.pyplot as plt

# contoh data harga rumah dan luas tanah
x = [50, 60, 70, 80, 90, 100]
y = [150, 160, 180, 190, 200, 210]

sns.scatterplot(x=x, y=y)
plt.xlabel("Luas Rumah (m2)")
plt.ylabel("Harga (juta)")
plt.title("Hubungan Luas vs Harga Rumah")
plt.show()
```

![image](https://github.com/user-attachments/assets/bf9f2236-8ecb-4224-b973-74c3b2fdb787)

Dari grafik terlihat, semakin besar rumah maka semakin mahal. Kalau kita gambar garis di tengah-tengah titik-titik ini, itu namanya garis regresi.

### Rumus Regresi Linier
```python
from sklearn.linear_model import LinearRegression
import numpy as np

X = np.array(x).reshape(-1, 1)
model = LinearRegression()
model.fit(X, y)

prediksi = model.predict([[85]])
print("Prediksi harga rumah 85 m2:", prediksi[0])

## Output
## Prediksi harga rumah 85 m2: 193.95238095238093
```

### Hasil Model
```python
print("Kemiringan garis (slope):", model.coef_[0])
print("Titik potong (intercept):", model.intercept_)

## Output
## Kemiringan garis (slope): 1.2285714285714286
## Titik potong (intercept): 89.5238095238095
```
Slope = seberapa banyak nilai berubah setiap tambahan 1 meter persegi (setiap nilai x bertambah 1) <br>
Intercept = nilai awal dari garis regresi saat X = 0. Disebut juga titik potong dengan sumbu Y.

### Prediksi
Ini adalah visualisasi regresi linear yang dibuat
```python
plt.scatter(x, y)
plt.plot(x, model.predict(X), color='red')  # garis regresi
plt.xlabel("Luas Rumah (m2)")
plt.ylabel("Harga (Juta)")
plt.title("Garis Regresi Linear")
plt.grid(True)
plt.show()
```
memprediksi nilai
```python
prediksi = model.predict([[85]])
print("Prediksi harga jika luas rumah 85 m2:", prediksi[0], "juta")
```

# Decision Tree
Decision tree adalah metode yang digunakan untuk membuat keputusan berdasarkan serangkaian pertanyaan.
Bentuknya seperti pohon bercabang, setiap cabang mewakili kondisi/pertanyaan, dan setiap daun mewakili hasil akhir.

| Panas (1/0) | Hujan (1/0) | Beli Es Krim |
| ----------- | ----------- | ------------ |
| 1           | 0           | ya           |
| 1           | 1           | tidak        |
| 0           | 0           | ya           |
| 0           | 1           | tidak        |

```python
from sklearn.tree import DecisionTreeClassifier

# data
X = [[1, 0], [1, 1], [0, 0], [0, 1]]
y = ["ya", "tidak", "ya", "tidak"]

# model
tree = DecisionTreeClassifier()
tree.fit(X, y)
```

### Prediksi
```python
print(tree.predict([[1, 0]]))  # panas, tidak hujan → ya
print(tree.predict([[0, 1]]))  # tidak panas, hujan → tidak
```

### Visualisasi Struktur Tree
```python
from sklearn.tree import plot_tree
import matplotlib.pyplot as plt

plt.figure(figsize=(6, 4))
plot_tree(tree,
          feature_names=["panas", "hujan"],
          class_names=tree.classes_,
          filled=True)
plt.show()

```

- Setiap cabang → “pertanyaan”
- Komputer mencari pertanyaan yang membagi data paling rapi
- Tujuannya: memisahkan kelas (label) sejelas mungkin
- Model belajar dari data masa lalu → supaya bisa memutuskan untuk data baru
