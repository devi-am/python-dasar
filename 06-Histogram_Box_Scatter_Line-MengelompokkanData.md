## Histogram
Grafik ini digunakan untuk menggambarkan distribusi dari data kuantitatif, tidak seperti car chart biasa yang menggunakan data kategorik. 
Pada grafik histogram, sumbu X digunakan untuk menampung **range nilai** dari data kuantitatif yang dikenal dengan istilah bins.<br>
Ukuran bins harus tepat<br>
![image](https://github.com/user-attachments/assets/ccbfb0e4-7a2c-491b-a1c0-3f56c3bf3f36)
### Matplotlib
menggunakan function ```hist()``` yang disediakan oleh library matplotlib. Parameter:
- x: menampung data yang akan divisualisasikan.
- bins: menampung jumlah bins (sebanding dengan ukurannya) yang akan digunakan untuk membuat grafik histogram.
```python
import matplotlib.pyplot as plt
import numpy as np
 
x = np.random.normal(15, 5, 250)
 
plt.hist(x=x, bins=15)
plt.show()
```
Pada contoh kode di atas, kita menggunakan function ```random.normal()``` yang disediakan oleh library numpy untuk menghasilkan sampel data acak yang memiliki distribusi normal. 
Sample data random tersebut memiliki **jumlah 250 titik** data dengan nilai **mean sebesar 15** dan **standard deviation** sebesar **5**.
### Seaborn
Grafik histogram dengan library seaborn menggunakan function ```histplot()```.
```python
import seaborn as sns
 
sns.histplot(x=x, bins=15)
plt.show()
```
Untuk mempermudah dalam mengidentifikasi distribusi dari sebuah data kuantitatif, kita bisa menambahkan parameter ```kde=True```
```python
sns.histplot(x=x, bins=15, kde=True)
plt.show()
```
Garis tersebut menunjukkan densitas distribusi berdasarkan grafik histogram yang dihasilkan.

## Box Plot
Bisa digunakan untuk mengidentifikasi distribusi pada data kuantitatif<br>
Bisa digunakan untuk mengidentifikasi **outlier** atau pencilan yang ada pada data kuantitatif.<br>
![image](https://github.com/user-attachments/assets/74d0abb9-bb34-4472-ac25-8438027d6d84)<br>
Menggunakan function ```boxplot()``` yang disediakan oleh library seaborn.
```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
 
x = np.random.normal(15, 5, 250)
sns.boxplot(x=x)
plt.show()
```

## Scatter Plot
Digunakan untuk melihat hubungan antara dua atau lebih variabel data kuantitatif.
### Matplotlib
Menggunakan function bernama ```scatter()```
```python
import matplotlib.pyplot as plt
 
lemon_diameter = [6.44, 6.87, 7.7, 8.85, 8.15, 
                  9.96, 7.21, 10.04, 10.2, 11.06]
lemon_weight = [112.05, 114.58, 116.71, 117.4, 128.93, 
                132.93, 138.92, 145.98, 148.44, 152.81]
 
plt.scatter(x=lemon_diameter, y=lemon_weight)
plt.show()
```
### Seaborn
Menggunakan function bernama ```scatterplot()```
```python
import matplotlib.pyplot as plt
import seaborn as sns
 
sns.scatterplot(x=lemon_diameter, y=lemon_weight)
plt.show()
```
Uuntuk mempermudah dalam melihat korelasi atau hubungan antar variabel, bisa menggunakan function ```regplot()``` yang disediakan oleh library seaborn. 
Function tersebut memadukan scatter plot dan regression function (metode statistik untuk memperkirakan korelasi antar independent dan dependent variable) untuk melihat tren serta korelasi antar variabel. 
```python
sns.regplot(x=lemon_diameter, y=lemon_weight)
plt.show()
```
Garis biru menunjukkan garis korelasi dari hasil regression sedangkan pita di sekitar garis tersebut menunjukkan confidence level dari hasil regression tersebut. 
Semakin kecil bentuk pita yang dihasilkan menandakan tingkat confidence level yang tinggi.

## Line Chart
Grafik yang umum digunakan untuk menggambarkan tren nilai dari suatu variabel terhadap variabel lain. 
Menggunakan function ```plot()``` oleh Matplotlib
```python
import matplotlib.pyplot as plt
 
lemon_diameter = [6.44, 6.87, 7.7, 8.85, 8.15, 
                  9.96, 7.21, 10.04, 10.2, 11.06]
lemon_weight = [112.05, 114.58, 116.71, 117.4, 128.93, 
                132.93, 138.92, 145.98, 148.44, 152.81]
 
plt.plot(lemon_diameter, lemon_weight)
plt.show()
```
Bentuk visualisasi data ini umumnya digunakan untuk melihat trend dari data berbentuk time series (data yang direkam dalam interval waktu yang konsisten). 
Berikut contoh kode untuk menampilkan plot harga saham Bank Central Asia dengan kode saham BBCA.
```python
import pandas as pd
import matplotlib.pyplot as plt
import requests
 
url = 'https://query1.finance.yahoo.com/v8/finance/chart/BBCA.JK?events=capitalGain%7Cdiv%7Csplit&formatted=true&includeAdjustedClose=true&interval=1d&period1=1704165596&period2=1735689600&symbol=BBCA&userYfid=true&lang=en-US&region=US'
 
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'
}
 
# Ambil data dari URL
response = requests.get(url, headers=headers)
 
# Konversi data JSON menjadi DataFrame
data = response.json()
 
# Ekstraksi data dari JSON
timestamps = data['chart']['result'][0]['timestamp']
indicators = data['chart']['result'][0]['indicators']['quote'][0]
 
# Membuat DataFrame
df = pd.DataFrame({
    'timestamp': pd.to_datetime(timestamps, unit='s'),
    'open': indicators['open'],
    'high': indicators['high'],
    'low': indicators['low'],
    'close': indicators['close'],
    'volume': indicators['volume'],
})
 
plt.figure(figsize=(12, 5))
plt.plot(df['timestamp'], df['close'], color='red')
plt.xlabel('Date',size=15)
plt.ylabel('Price',size=15)
plt.show()
```

# Komponen Visual Tambahan
## Membandingkan lebih dari 1 data dalam 1 grafik
### Clustered Bar Chart
Merupakan bentuk modifikasi dari bar chart dengan menambahkan variabel kategoris lain. 
Modifikasi ini memungkinkan untuk melihat distribusi serta hubungan antar dua atau lebih variabel kategoris. <br>
Untuk membuat clustered bar chart, kita bisa menggunakan parameter ```hue``` pada function ```barplot()``` yang disediakan oleh library seaborn.
```python
import seaborn as sns
import matplotlib.pyplot as plt
 
penguins = sns.load_dataset("penguins")
 
sns.barplot(data=penguins, x="species", y="body_mass_g", hue="sex", errorbar=None)
plt.show()
```

### Boxplot
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
 
url = 'https://query1.finance.yahoo.com/v7/finance/download/BBCA.JK?period1=1644796800&period2=1676332800&interval=1d&events=history&includeAdjustedClose=true'
df = pd.read_csv(url)
df['Date'] = pd.to_datetime(df['Date'])
 
df_boxplot = df[["Open", "High", "Low", "Close", "Adj Close"]]
 
sns.boxplot(data=df_boxplot, palette="rocket")
plt.ylabel('Price',size=15)
plt.show()
```
### Scatter plot
```python
import seaborn as sns
 
penguins = sns.load_dataset("penguins")
 
sns.scatterplot(data=penguins, x="body_mass_g", y="flipper_length_mm", hue="species", style="species")
plt.show()
```
<br><br>
> Dokumentasi palet warna: [Pilihan warna](https://seaborn.pydata.org/tutorial/color_palettes.html)

<br><br>

# Mengelompokkan Data
Pada proses analisis data, kita bisa menggunakan konsep pivot table untuk menghitung parameter statistik dari kelompok data tertentu. 
Selain itu, ia juga dapat digunakan untuk kebutuhan visualisasi data dan pembuatan report. <br>

Proses pembuatan pivot table, diawali dengan melakukan split atau proses pengelompokkan pasangan key-values. 
Tahap berikutnya adalah proses apply atau perhitungan parameter dari setiap kelompok pasangan key-value. 
Tahap terakhir ialah menggabungkan (combine) seluruh key dengan nilai parameternya ke dalam satu tabel.
![image](https://github.com/user-attachments/assets/892fd8d7-cb89-405e-aff7-bb5f729cdbf1)

##Group by
Pengelompokan data bisa menggunakan **library Pandas** menggunakan ```groupby()``` dan bisa dipadukan dengan berbagai method untuk menghitung parameter statistik, seperti ```mean()```, ```mode()```, dll.
```python
import pandas as pd
 
body_measurement_df = pd.DataFrame.from_records((
  (2, 83.82, 8.4),
  (4, 99.31, 16.97),
  (3, 96.52, 14.41),
  (6, 114.3, 20.14),
  (4, 101.6, 16.91),
  (2, 86.36, 12.64),
  (3, 92.71, 14.23),
  (2, 85.09, 11.11),
  (2, 85.85, 14.18),
  (5, 106.68, 20.01),
  (4, 99.06, 13.17),
  (5, 109.22, 15.36),
  (4, 100.84, 14.78),
  (6, 115.06, 20.06),
  (2, 84.07, 10.02),
  (7, 121.67, 28.4),
  (3, 94.49, 14.05),
  (6, 116.59, 17.55),
  (7, 121.92, 22.96),
), columns=("age", "height_cm", "weight_kg"))
 
body_measurement_df.groupby(by="age").mean()
```
## Agregate
Untuk membuat pivot table dengan lebih dari 1 prameter bisa menggunakan method ```agg()```.
```python
body_measurement_df.groupby(by='age').agg({
    'height_cm': 'mean',
    'weight_kg': ['mean','max', 'min'],
})
```

### Beberapa Parameter Statistik lainnya
| Fungsi      | Kegunaan                                                        |
| ----------- | --------------------------------------------------------------- |
| `mean()`    | Menghitung rata-rata                                            |
| `max()`     | Nilai maksimum                                                  |
| `min()`     | Nilai minimum                                                   |
| `sum()`     | Menjumlahkan nilai                                              |
| `count()`   | Menghitung jumlah baris (bisa dipakai untuk frekuensi)          |
| `median()`  | Mengambil nilai tengah                                          |
| `std()`     | Standar deviasi                                                 |
| `var()`     | Varians                                                         |
| `first()`   | Nilai pertama dalam grup                                        |
| `last()`    | Nilai terakhir dalam grup                                       |
| `nunique()` | Jumlah nilai unik                                               |
| `size()`    | Jumlah elemen per grup (mirip `count()` tapi untuk semua kolom) |
| `mode()`    | Nilai yang paling sering muncul                                 |

> [Dokumentasi Group by](https://pandas.pydata.org/pandas-docs/stable/reference/groupby.html#)

## Short value
Berfungsi untuk mengurutkan data pada pivot tabel.
```python
# Urutkan berdasarkan rata-rata berat dari terbesar
body_measurement_df.groupby("age")["weight_kg"].mean().sort_values(ascending=False)
```
