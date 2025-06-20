# Data Wragling
Data wrangling merupakan sebuah proses atau kumpulan kegiatan yang meliputi pengumpulan data (Gathering data), penilaian data (Assessing data), serta pembersihan data (Cleaning data) sebelum data digunakan dalam proses analisis data.
- Gathering data<br>
  Tahap data wrangling, dimulai dengan proses pengumpulan data. Pada proses ini kita akan mengumpulkan semua data yang dibutuhkan untuk menjawab semua pertanyaan atau masalah bisnis yang ingin kita hadapi.
- Assessing data<br>
  Setelah semua data yang dibutuhkan terkumpul, proses selanjutnya ialah penilaian terhadap data tersebut. Proses ini dilakukan untuk menilai kualitas dan struktur dari sebuah data. Selain itu, proses ini juga bertujuan untuk mengidentifikasi berbagai masalah yang terdapat dalam data, seperti missing value, unstandard value, dll.
- Cleaning data<br>
  Apabila pada proses sebelumnya kita menemukan masalah (missing value, outlier, dll.) yang terdapat di dalam sebuah data, masalah tersebut harus dibersihkan sebelum masuk tahap analisis data. Terdapat beberapa teknik yang dapat kita gunakan untuk membersihkan data. Seluruh teknik tersebut akan kita pelajari pada beberapa materi ke depan.
![image](https://github.com/user-attachments/assets/fdbed69e-6c59-43b5-97a1-249b4c0de2a8)

## Gathering Data
Proses pengumpulan data. Beberapa sumber data yang bersifat publik dan sering digunakan oleh para praktisi data.
- Kaggle<br>
  Kaggle merupakan platform andalan bagi praktisi data untuk mencari dataset. Selain menyediakan dataset, kaggle juga menyediakan berbagai kompetisi dan challenge terkait data science dan machine learning. Kaggle juga memungkinkan para praktisi data dan machine learning saling berbagai kode dan pengetahuan terkait data serta machine learning.
- UCI Machine Learning Repository<br>
  UCI Machine Learning Repository merupakan sebuah repositori yang menampung berbagai dataset yang bersifat publik.
- Google Dataset Search<br>
  Google Dataset Search merupakan sebuah search engine yang disediakan oleh Google. Ia dibuat untuk mempermudah para praktisi data dan juga researcher dalam mencari dataset yang bersifat publik.
- Satu Data Indonesia<br>
  Tahukah Anda bahwa pemerintah Indonesia sebetulnya telah menyediakan sebuah platform bernama Satu Data Indonesia atau sering disingkat SDI.
Selain menggunakan berbagai sumber dataset publik tersebut, para praktisi data juga seringkali menggunakan data internal yang bersifat privat. Data seperti ini umumnya disimpan dalam sebuah sistem pengolahan database. 

#### Format File
Pandas menyediakan beberapa function yang dapat digunakan untuk membaca atau mengakses data menjadi sebuah DataFrame. Saat ini, Pandas mendukung pembacaan atau pengaksesan data dari berbagai format berkas data dan sumber data seperti pada contoh di bawah ini.
- Format berkas CSV<br>
  Berkas CSV (Comma Separated Values) merupakan format berkas data tabel yang paling sering digunakan dan telah menjadi standar dalam industri. Pandas menyediakan sebuah function read_csv() untuk membaca berkas CSV.
  ```python
  import pandas as pd
 
  df = pd.read_csv("data.csv", delimiter=",")
  ```
- Format berkas XLSX atau XLS<br>
  Berkas XLSX atau XLS merupakan format berkas spreadsheet yang dibuat menggunakan aplikasi Microsoft Excel. Pandas juga menyediakan function read_excel() untuk membaca berkas data dengan format XLSX atau XLS.
  ```python
  import pandas as pd
 
  df = pd.read_excel("data.xlsx", sheet_name="Sheet1")
  ```
- Format berkas JSON<br>
  Berkas JSON (JavaScript Object Notation) merupakan format berkas data yang memiliki struktur data yang mirip seperti data structure dictionary dalam Python yang terdiri dari pasangan keys dan values. Pandas juga menyediakan function read_json() untuk membaca berkas data berformat JSON.
  ```python
  import pandas as pd
 
  df = pd.read_json("data.json")
  ```
- Format berkas HTML<br>
  HTML atau dikenal juga sebagai HyperText Markup Language merupakan sebuah markup language standar yang digunakan untuk merancang tampilan sebuah dokumen/halaman di web browser. Untuk membaca berkas ini, pandas menyediakan function read_html().
  ```python
  import pandas as pd
 
  url = "https://www.fdic.gov/resources/resolutions/bank-failures/failed-bank-list"
  df = pd.read_html(url)[0]
  ```
- Format berkas XML<br>
  Format data selanjutnya yang akan kita bahas ialah XML yang merupakan singkatan dari Extensible Markup Language. Ia sering digunakan untuk merepresentasikan berbagai struktur informasi, seperti dokumen, data, konfigurasi, dll. Pandas menyediakan function read_xml() untuk membaca format data ini.
  ```python
  import pandas as pd
 
  df = pd.read_xml("https://www.w3schools.com/xml/books.xml")
  ```
- Akses data dari SQL database<br>
  Selain membaca data dari berbagai format, library pandas juga memungkinkan kita untuk mengakses data langsung dari sebuah database, seperti PostgreSQL, MySQL, dll. Tentunya untuk mengakses database tersebut kita membutuhkan library pendukung yaitu SQLAlchemy.

## Assessing Data
Data yang kotor umumnya memiliki masalah dalam kontennya. Berikut beberapa masalah yang umum dijumpai dalam sebuah data.
- Missing value<br>
  Masalah ini muncul karena adanya nilai yang hilang dari sebuah data dan biasanya direpresentasikan sebagai nilai NaN dalam library pandas. Hal ini biasanya terjadi karena adanya human error, masalah privasi, proses merging/join, dll.<br>
  Library pandas menyediakan sebuah method bernama isnull() atau isna() untuk mengidentifikasi missing value dalam sebuah DataFrame. Keduanya sering dipadukan dengan method sum() untuk menghitung total missing value pada setiap kolom dalam sebuah DataFrame.
  ```python
  import pandas as pd
  product_df = pd.read_csv("product.csv")
 
  product_df.isnull().sum()
  ```
- Invalid value<br>
  Masalah ini muncul ketika terdapat beberapa nilai yang tidak masuk akal, tidak sesuai dengan ketentuan, dan background knowledge dari data tersebut.<br>
  Untuk mendeteksi masalah seperti ini, kita membutuhkan teknik sedikit advance. Salah satu teknik yang paling sering digunakan ialah teknik filtering data menggunakan regex.
- Duplicate data<br>
  Duplicate data merupakan masalah lain yang umum dijumpai di industri. Ia terjadi ketika terdapat sebuah observasi (semua nilai dalam satu unit baris) yang memiliki nilai yang sama persis pada setiap kolomnya. Pandas menyediakan sebuah method duplicated() untuk mengidentifikasi apakah terdapat duplikasi pada sebuah DataFrame.
  ```python
  import pandas as pd
 
  url = "https://www.fdic.gov/resources/resolutions/bank-failures/failed-bank-list"
  df = pd.read_html(url)[0]
  df.duplicated().sum()
  ```
- Inaccurate value<br>
  Inaccurate value merupakan masalah yang muncul ketika nilai dalam sebuah data tidak sesuai dengan hasil observasi. Masalah ini umumnya muncul karena adanya human error atau sistem error.
- Inconsistent value<br>
  Inconsistent value adalah masalah yang muncul ketika sebuah data memiliki nilai yang tidak konsisten baik dari segi satuan maupun ketentuan penilaian. Inkonsistensi ini umumnya muncul karena adanya perbedaan standar dalam proses pengumpulan nilai.
- Outlier<br>
  Outlier atau dalam bahasa indonesia disebut pencilan merupakan titik data yang berada sangat jauh dari titik data yang lain dalam sebuah dataset. Nilai yang sangat jauh ini tentunya akan berdampak terhadap beberapa parameter statistik yang digunakan untuk menganalisis data, seperti nilai mean dan standard deviation.
  ```python
  import numpy as np
 
  # Data di bawah cuma contoh data saja biar bisa lihat hasil kode
  data = [10, 12, 13, 11, 15, 14, 13, 16, 11, 10, 100, 2, 13, 15]
  
  # kode untuk melihat nilai outlier
  q25, q75 = np.percentile(data, 25), np.percentile(data, 75)
  iqr = q75 - q25
  cut_off = iqr * 1.5
  minimum, maximum = q25 - cut_off, q75 + cut_off
 
  outliers = [x for x in data if x < minimum or x > maximum]
  ```
  ![image](https://github.com/user-attachments/assets/51b3979f-9511-4d63-bf5e-b0a7d26607e7)

## Cleaning Data
### Mengatasi Missing Value
- Dropping
  ```python
  import pandas as pd
 
  products_df = pd.read_csv("product.csv")
 
  products_df.dropna(axis=0, inplace=True)
  ```
- Imputation
  ```python
  import pandas as pd
 
  data=pd.read_csv('employee_data.csv')
 
  data.age.fillna(value=data.age.mean(), inplace=True)
  ```
- Interpolation<br>
  Interpolasi merupakan salah satu pendekatan numerik yang digunakan untuk menghitung titik data baru berdasarkan range data yang sudah ada. Perhitungan ini menggunakan sebuah persamaan garis linear ataupun polynomial.
  ```python
  import pandas as pd
 
  data=pd.read_csv('bbca_index.csv')
 
  data.close_price.interpolate(method='linear', limit_direction='forward', inplace=True)
  ```
### Mengatasi Outlier
- Dropping
  ```python
  import pandas as pd
 
  df = pd.read_csv("data.csv")
 
  Q1 = (df['TotalCharges']).quantile(0.25)
  Q3 = (df['TotalCharges']).quantile(0.75)
  IQR = Q3 - Q1
 
  maximum = Q3 + (1.5*IQR)
  minimum = Q1 - (1.5*IQR)
 
  kondisi_lower_than = df['TotalCharges'] < minimum
  kondisi_more_than = df['TotalCharges'] > maximum
 
  df.drop(df[kondisi_lower_than].index, inplace=True)
  df.drop(df[kondisi_more_than].index, inplace=True)
  ```
- Imputation
  ```python
  df = pd.read_csv("data.csv")
 
  Q1 = (df['TotalCharges']).quantile(0.25)
  Q3 = (df['TotalCharges']).quantile(0.75)
  IQR = Q3 - Q1
 
  maximum = Q3 + (1.5*IQR)
  minimum = Q1 - (1.5*IQR)
 
  kondisi_lower_than = df['TotalCharges'] < minimum
  kondisi_more_than = df['TotalCharges'] > maximum
 
  df.mask(cond=kondisi_more_than, maximum, axis=1, inplace=True)
  df.mask(cond=kondisi_lower_than, minimum, axis=1, inplace=True)
  ```
### Mengatasi Duplicate Data
Pakai ```drop_duplicates()``` untuk menghapus data yang duplikat
```python
import pandas as pd
 
df = pd.read_csv("data.csv")
df.drop_duplicates(inplace=True)
```
