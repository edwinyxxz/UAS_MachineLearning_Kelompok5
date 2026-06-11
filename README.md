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
  - isi
  - isi
  - isi
  
---

## Transform (Pembersihan & Transformasi)

- **Cleaning:**
  - isi
  - isi

- **Transformasi:**
  - isi
  - isi

---

## Load ( Pemindahan ke Target ) benarkan saja

- **Target:**
  - isi
 
- **Metode:**
  - isi
  - isi
 
- **apa lagi**

---

## Arsitektur / Workflow ETL

- **Alur (benarkan)**
  - isi saja
 
- **Tools**
  - isi saja
 
---

## Kode Program

- **Struktur Kode:**
  - isi
  - isi
    
- **Machine Learning:**
  - isi
  - isi
 
- **Link Projek:**
  - ETL Pipeline: https://colab.research.google.com/drive/1oQ-F58hhUYGuqi2PGdh4xIWsMjDFdTYu?usp=sharing
  - Machine Learning: https://colab.research.google.com/drive/1xX4YnwnWZZX2fDltjM0hc4EEZ2jMGyb3?usp=sharing
  - Looker Studio: https://datastudio.google.com/s/l8-FB9oS7QE
