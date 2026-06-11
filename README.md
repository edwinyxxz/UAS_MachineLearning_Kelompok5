# KAI-2026 Passenger Forecasting Analytics

---

# Kontribusi

| Role | Name |
|-----|------|
| Data Engineer | Edwin Nur Cahyo |
| Data Analyst | Dheandra Khairunnisa P |
| Project Manager | Julyo Firnanda |

---

# Deskripsi Project

Mengembangkan sistem analisis untuk meramalkan peningkatan jumlah penumpang kereta api jarak jauh saat angkutan tahun 2026. Membangun sistem visual analitik (dashboard) dan model perkiraan untuk memprediksi jumlah dan peningkatan penumpang kereta api berdasarkan kategori layanan (Jabodetabek, MRT, Kereta Cepat, dan lain-lain) selama operasional tahun 2026.

Dengan mempertimbangkan data inflasi pada tahun 2026 untuk meramalkan jumlah penumpang kereta api pada masa angkutan tahun 2026, serta mengevaluasi rata-rata penumpang berdasarkan data historis dari tahun 2024 hingga 2025.

**Tujuan Project**  
- Membangun model *Multiple Linear Regression* spesifik per kategori layanan untuk memprediksi secara akurat volume penumpang kereta api sepanjang tahun 2026.
- Mengukur dan memetakan korelasi antara fluktuasi inflasi bulanan (*Month-to-Month*) terhadap mobilitas komuter dan antarkota.
- Menyediakan visualisasi data interaktif yang merangkum data historis (2024-2025) serta proyeksi masa depan untuk mempermudah pemahaman pengguna akhir.

**Manfaat Project**
- Menjadi landasan strategis untuk *capacity planning* dalam mengantisipasi puncak lonjakan penumpang pada kuartal keempat (Desember 2026).
- Membantu pembuat kebijakan dalam mengevaluasi resiliensi mobilitas masyarakat terhadap guncangan inflasi ekonomi.
- Membuktikan efisiensi, transparansi, dan keandalan algoritma *Multiple Linear Regression* untuk penyelesaian masalah *time-series forecasting* pada sektor transportasi.

---

# Pipeline

---

## Extract Data

- **Sumber Data:**
  - Jumlah Penumpang Kereta Api (Ribu Orang), Tahun 2024 - website
    ( https://www.bps.go.id/id/statistics-table/2/NzIjMg==/jumlah-penumpang-kereta-api.html )
  - Jumlah Penumpang Kereta Api (Ribu Orang), Tahun 2025 - website
    ( https://www.bps.go.id/id/statistics-table/2/NzIjMg==/jumlah-penumpang-kereta-api.html )
  - Inflasi Bulanan (M-to-M) (Persen), Tahun 2024 - website
    ( https://www.bps.go.id/id/statistics-table/2/MSMy/inflasi-bulanan-m-to-m-.html )
  - Inflasi Bulanan (M-to-M) (Persen), Tahun 2025 - website
    ( https://www.bps.go.id/id/statistics-table/2/MSMy/inflasi-bulanan-m-to-m-.html )

- **Metode Pengambilan:**
  - Menggunakan pandas read_csv untuk membaca data dalam bentuk csv. hasil dari pengambilan tersebut disimpan pada dataframe yang siap untuk dilakukan transform
  
---

## Transform (Pembersihan & Transformasi)

- **Cleaning:**
  - Filter inflasi agar hanya menggunakan data Indonesia sebagai acuan data nasional.
  - Rename kolom Kategori pada jumlah penumpang kereta. 

- **Transformasi:**
  - Melt data inflasi dan jumlah penumpang kereta untuk mengubah format data dari wide ke long.
  - Merge Cleaned data inflasi dan jumlah penumpang pada kolom Tahun dan Bulan.
  - Sort Cleaned data final berdasarkan Tanggal.

---

## Load ( Pemindahan ke Target )

- **Target:**
  - Sebuah tabel baru di dalam database pada server Aiven. Tabel ini merupakan output utama yang dapat diakses oleh layanan lain untuk melakukan analisis langsung di database.
 
- **Metode:**
  - Fungsi to_sql() dari pandas digunakan untuk menulis data dari DataFrame langsung ke tabel di database MySQL.
 
- **Check Data**
  - Check data apakah sudah masuk kedalam database dengan pandas read_sql yang berisi query "SELECT * FROM Tablename WHERE Tahun = 2024 limit 15;"

## Arsitektur / Workflow ETL

- **Alur**
  - Extract data mentah inflasi dan jumlah penumpang 2024-2025
  - Transform data mentah seperti filter kolom sesuai dengan kebutuhan, Melt agar mengubah format wide ke long, dan Merge cleaned data inflasi dan jumlah penumpang kereta menjadi 1 data utuh cleaned_data.
  - Load cleaned_data ke Aiven database dengan pandas.to_sql() dan sqlalchemy untuk koneksi ke database Mysql aiven.
 
- **Tools**
  - Python 3
  - Library: pandas, glob, re(RegexExpression), sqlalchemy, sklearn(Linear regression), matplotlib.pyplot.
  - Playform: Google colab 
 
---

## Kode Program

- **Struktur Kode:**
  - Terdapat 2 notebook: Pipeline untuk ETL dan Machine Learning.
    
- **Machine Learning:**
  - Model: Linear regression
  - Visualisasi: matplotlib.pyplot
 
- **Link Projek:**
  - ETL Pipeline: https://colab.research.google.com/drive/1oQ-F58hhUYGuqi2PGdh4xIWsMjDFdTYu?usp=sharing
  - Machine Learning: https://colab.research.google.com/drive/1xX4YnwnWZZX2fDltjM0hc4EEZ2jMGyb3?usp=sharing
  - Looker Studio: https://datastudio.google.com/s/l8-FB9oS7QE
