# Visualisasi Data
Visualisasi data adalah proses menyajikan data dalam bentuk grafik atau gambar, agar lebih mudah dipahami & dianalisis. Contoh: grafik batang, diagram garis, atau heatmap.

## Jenis Grafik Umum
1.	Bar Chart: Menampilkan perbandingan antar kategori
2.	Line Chart: Menampilkan tren data dari waktu ke waktu
3.	Scatter Plot: Menunjukkan hubungan antara dua variabel numerik
4.	Histogram: Menampilkan distribusi frekuensi data numerik
5.	Pie Chart: Menampilkan proporsi antar bagian dalam satu keseluruhan
6.	Heatmap: Menunjukkan nilai dalam matriks dua dimensi dengan warna

### Perbedaan Bar dan Histogram
| Aspek                     | **Bar Chart**                                | **Histogram**                                                            |
| ------------------------- | -------------------------------------------- | ------------------------------------------------------------------------ |
| **Data yang ditampilkan** | Data **kategori**                            | Data **numerik (angka)**                                                 |
| **Sumbu X**               | Label kategori (misal: "Apel", "Jeruk")      | Interval angka (misal: 0–10, 10–20)                                      |
| **Tujuan**                | Bandingkan **jumlah/ukuran tiap kategori**   | Tampilkan **distribusi frekuensi** dari data numerik                     |
| **Pemisah antar batang**  | Ada jarak antar batang                       | Tidak ada jarak antar batang (karena kontinu)                            |
| **Contoh**                | Menampilkan penjualan buah berdasarkan jenis | Menampilkan seberapa sering suatu nilai muncul (frekuensi tinggi-rendah) |

## Modul ```Pandas``` untuk Manipulasi Data
Modul ```pandas``` berfungsi untuk manipulasi, analisis, dan persiapan data sebelum divisualisasikan atau dianalisis lebih lanjut.
### Menyimpan data ke variabel menggunakan pandas
```python
import pandas as pd

buah = ('apel', 'jeruk', 'semangka', 'anggur')
jumlah = (29, 12, 42, 32)

df = pd.DataFrame({
    'Buah': buah,
    'Jumlah': jumlah,
})
```

### Membaca File CSV/Excel
```python
import pandas as pd

# Membaca file CSV
df = pd.read_csv('data.csv')

# Membaca file Excel
df = pd.read_excel('data.xlsx')
```

### Menampilkan Data
Untuk menampilkan atau melihat struktur data bisa menggunakan fungsi berikut (coba satu per satu).
```python
df.head()        # Menampilkan 5 baris pertama
df.tail()        # Menampilkan 5 baris terakhir
df.info()        # Info struktur data (tipe data, null)
df.describe()    # Statistik ringkasan kolom numerik
df.columns       # Menampilkan nama-nama kolom
df.shape         # (baris, kolom)
```

### Indexing dan Slicing
```python
df["nama_kolom"]           # Akses kolom
df[0:5]                    # Ambil baris ke-0 sampai 4
df.loc[0, "nama_kolom"]    # Berdasarkan label
df.iloc[0, 2]              # Berdasarkan posisi indeks
```

### Filter dan GroupBy
```python
df[df["usia"] > 25]                         # Filter: usia > 25
df[df["status"] == "aktif"]                 # Filter: status aktif
df.groupby("jenis_kelamin")["gaji"].mean()  # Rata-rata gaji per jenis kelamin
df.groupby("jurusan").agg({
    "ipk": "mean",
    "nama": "count"
})  # Agregasi multi-kolom
```

### Menangani Missing Values
```python
df.isnull()                                # Cek nilai kosong
df.dropna()                                # Hapus baris yang mengandung null
df.fillna(0)                               # Isi null dengan 0
df["nilai"].fillna(df["nilai"].mean())    # Isi null dengan rata-rata
```


## Visualisasi Data dengan Matplotlib
### Bar chart
![image](https://github.com/user-attachments/assets/40b5e640-1241-4489-b672-e523dde59bdd)

Bar chart atau diagram batang merupakan pilihan visualisasi data yang digunakan untuk menggambarkan distribusi dari suatu data kategoris (categorical data). 
```python
import matplotlib.pyplot as plt
 
cities = ('Bogor', 'Bandung', 'Jakarta', 'Semarang', 'Yogyakarta', 
          'Surakarta','Surabaya', 'Medan', 'Makassar')
 
populations = (45076704, 11626410, 212162757, 19109629, 50819826, 17579085,
               3481, 287750, 785409)
 
plt.bar(x=cities, height=populations)
plt.show()
```
label nama di sumbu-x pasti terlihat jelek, tambahkan fungsi ```.xticks()``` dan atur rotasinya pakai parameter ```rotation```
```python
plt.bar(x=cities, height=populations)
plt.xticks(rotation=45)
plt.show()
```
Bar chart di sumbu-y:
```python
plt.barh(y=cities, width=populations)
plt.show()
```
mengurutkan bedasarkan jumlah populasi terbanyak menggunakan ```.sort_values()```
```python
import pandas as pd
 
df = pd.DataFrame({
    'Cities': cities,
    'Population': populations,
})
 
df.sort_values(by='Population', inplace=True)
 
plt.barh(y=df["Cities"], width=df["Population"])
plt.show()
```
bisa tambahkan label pakai ```.xlabel()``` dan judul pakai ```.title()``` agar chart nya lebih informatif
```python
plt.barh(y=df["Cities"], width=df["Population"])
plt.xlabel("Population (Millions)")
plt.title("Population of Cities in Indonesia")
plt.show()
```

#### Menambahkan modul Seaborn
Untuk membuat bar chart menggunakan library seaborn, bisa menggunakan function ```barplot()```. <br>
Function ini akan menyediakan beberapa parameter penting seperti berikut.
- ```data```: menampung DataFrame yang akan digunakan.
- ```x```, ```y```: menampung nama kolom atau data yang divisualisasikan.
- ```orient```: orientasi dari bar chart yang akan digunakan (“v” atau “h”).
- ```color```: mendefinisikan warna yang akan digunakan.
Contoh kode:
```python
import seaborn as sns
 
sns.barplot(y=df["Cities"], x=df["Population"], orient="h", color='blue')
plt.xlabel("Population (Millions)")
plt.title("Population of Cities in Indonesia")
plt.show()
```

### Pie Chart
Pie chart adalah bentuk visualisasi data yang dapat digunakan untuk menggambarkan perbandingan frekuensi tiap kategori pada suatu data kategoris. Sebaiknya pie chart digunakan untuk merepresentasikan data yang memiliki jumlah kategori yang relatif sedikit. Hal ini dilakukan untuk mempermudah orang lain dalam memahami informasi yang ingin kita sampaikan.
![image](https://github.com/user-attachments/assets/e67f1bf1-1592-4f9c-93a4-888f057f3f7c)

Gunakan fungsi ```pie()``` pada modul matplotlib untuk menampilkan chart. Beberapa parameter ```pie()```:
- x: menampung data yang akan divisualisasikan.
- explode: menampung array atau list yang mengatur posisi tiap irisan lingkaran.
- labels: sekumpulan string yang digunakan untuk memberi label pada tiap irisan lingkaran.
- colors: sekumpulan warna yang akan digunakan pada tiap irisan lingkaran.
- autopct: string yang digunakan untuk memberi numerik label pada tiap irisan lingkaran.
```python
import matplotlib.pyplot as plt
 
flavors = ('Chocolate', 'Vanilla', 'Macha', 'Others')
votes = (50, 20, 30, 10)
colors = ('#8B4513', '#FFF8DC', '#93C572', '#E67F0D')
explode = (0.1, 0, 0, 0)
 
plt.pie(
    x=votes,
    labels=flavors,
    autopct='%1.1f%%',
    colors=colors,
    explode=explode
)
plt.show()
```

parameter ```wedeprops``` untuk membuat menjadi **donut chart** (bolong tengah)
```python
plt.pie(
    x=votes,
    labels=flavors,
    colors=colors,
    wedgeprops = {'width': 0.4}
)
plt.show()
```
