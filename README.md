# 🚀 Praktikum 2 — Batch Data Ingestion & Processing with Spark

**Enterprise Edition (WSL + VS Code + Data Lake + Partitioning)**

Praktikum ini membahas implementasi **Enterprise Batch Data Pipeline** menggunakan **Apache Spark (PySpark)** dalam lingkungan **Linux (WSL)** dengan pendekatan **Medallion Architecture (Raw – Clean – Curated)**.

Fokus utama praktikum adalah membangun pipeline data yang:

* Production-ready
* Menggunakan explicit schema
* Mengimplementasikan data cleaning & transformation
* Menggunakan format columnar (Parquet)
* Menerapkan partitioning strategy
* Menghasilkan insight bisnis sederhana

Praktikum ini mensimulasikan workflow industri e-commerce dalam memproses data transaksi skala besar.

**Topik:** Batch Processing, Distributed Computing, Data Lake, Parquet, Partition Pruning, Medallion Architecture, PySpark

---

## 🧑‍🎓 Informasi Mahasiswa

| Informasi         | Data                                                             |
| ----------------- | ---------------------------------------------------------------- |
| Mata Kuliah       | Teknologi Big Data                                               |
| Dosen Pengampu    | Muhayat, M.IT                                                    |
| Praktikum         | Batch Data Ingestion & Processing with Spark                     |
| Nama Mahasiswa    | Husna Norgina                                                    |
| NIM               | 230104040056                                                     |
| Kelas             | TI23B                                                            |
| Repo GitHub       | https://github.com/husna-norgina/bigdata-technology-praktikum-02 |
| Tanggal Praktikum | 26-02-2026                                                       |

---

## 🎯 Tujuan Praktikum

1. Menggunakan Linux environment (WSL) untuk data engineering
2. Mengintegrasikan VS Code dengan WSL
3. Mengelola virtual environment Python
4. Mengimplementasikan batch data ingestion dengan Spark
5. Menerapkan data cleaning & transformation
6. Mendesain struktur Data Lake (Raw, Clean, Curated)
7. Menggunakan format Parquet
8. Menerapkan partitioning strategy
9. Menghasilkan pipeline enterprise-ready

---

## 🏛 Arsitektur Pipeline

```
CSV Source
   ↓
Raw Layer
   ↓
Cleaning & Validation
   ↓
Transformation
   ↓
Clean Layer (Parquet)
   ↓
Curated Layer (Aggregation)
   ↓
Partitioned Data Lake
```

Konsep utama yang digunakan:

* Batch Processing
* Distributed Computing
* Medallion Architecture
* Columnar Storage (Parquet)
* Partition Pruning

---

## 🛠 Tools & Environment

* Ubuntu (WSL – Linux Server Environment)
* Visual Studio Code (Remote WSL)
* Python 3
* PySpark
* Bash CLI
* Git & GitHub

---

## 🧱 Struktur Project

```
bigdata-project/
│
├── data/
│   ├── raw/
│   ├── clean/
│   │   ├── parquet/
│   │   └── partitioned_by_category/
│   └── curated/
│       ├── category_revenue/
│       ├── top_products/
│       └── avg_transaction/
│
├── logs/
├── scripts/
│   └── batch_pipeline_enterprise.py
│
├── evidence/
├── README.md
```

Struktur ini mengikuti standar modern **Data Engineering & Data Lake Architecture**.

---

## 🔥 Implementasi Enterprise Pipeline

Pipeline dibangun menggunakan:

```python
SparkSession.builder \
    .appName("EnterpriseBatchPipelineDemo") \
    .master("local[*]") \
    .getOrCreate()
```

Tahapan utama:

### 1️⃣ Data Ingestion

* Load dataset `ecommerce_raw.csv`
* Menggunakan explicit schema (production best practice)

### 2️⃣ Data Cleaning

* dropDuplicates()
* dropna()
* Filter price & quantity > 0
* Validasi format tanggal

### 3️⃣ Transformation

* Membuat kolom `total_amount = price × quantity`

### 4️⃣ Aggregation

* Total revenue per category
* Top 5 Products (berdasarkan total quantity)
* Average transaction value per customer

### 5️⃣ Storage Optimization

* Simpan ke format Parquet
* Partitioning berdasarkan `category`

---

## 📸 Screenshot Praktikum

Berikut dokumentasi hasil praktikum:

### 1️⃣ Eksekusi Spark dan Proses Cleaning Data

![Spark](evidence/1.%20Eksekusi%20Spark%20dan%20Proses%20Cleaning%20Data.png)

Menampilkan:

* Spark Version
* Total Raw Records
* Total Cleaned Records
* Proses cleaning tanpa error

---

### 2️⃣ Hasil Agregasi dan Status Pipeline Berhasil

![Aggregation](evidence/2.%20Hasil%20Agregasi%20dan%20Status%20Pipeline%20Berhasil.png)

Menampilkan:

* Top 5 Products
* Category Revenue
* Pesan: **PIPELINE COMPLETED SUCCESSFULLY**

---

### 3️⃣ Perbandingan Ukuran CSV dan Parquet

![Parquet](evidence/3.%20Perbandingan%20Ukuran%20CSV%20dan%20Parquet.png)

Hasil pengujian:

* CSV ≈ 6.2 MB
* Parquet ≈ 2.3 MB

Parquet terbukti lebih efisien secara storage.

---

## 📄 Laporan Praktikum 2

📎 [230104040056_Husna Norgina_P2.pdf](evidence/230104040056_Husna%20Norgina_P2.pdf)

---

> Semua screenshot disimpan dalam folder:
> 📂 `evidence/`

---

## 📊 Analisis Singkat

* Pipeline berjalan tanpa error menggunakan Apache Spark.
* Explicit schema meningkatkan konsistensi dan reliability.
* Parquet (columnar storage) menghasilkan ukuran file lebih kecil dibanding CSV.
* Partitioning memungkinkan Partition Pruning sehingga meningkatkan performa query.
* Top 5 Products:

  * Tablet (40.898 unit)
  * Laptop (40.654 unit)
  * Monitor (40.629 unit)
  * Headphones (40.506 unit)
  * Phone (40.314 unit)

Pipeline ini tidak hanya berfungsi secara teknis, tetapi juga menghasilkan dataset siap analitik untuk pengambilan keputusan bisnis.

---

## ✅ Kesimpulan

Praktikum 2 berhasil mengimplementasikan **Enterprise Batch Data Pipeline** berbasis Apache Spark dengan pendekatan **Medallion Architecture (Raw – Clean – Curated)**.

Pipeline ini membuktikan bahwa:

* Distributed computing meningkatkan performa pemrosesan data.
* Parquet (columnar storage) lebih efisien dibanding CSV.
* Partitioning strategy meningkatkan efisiensi query.
* Data engineering mindset berfokus pada scalability, maintainability, dan production-readiness.

Praktikum ini menjadi fondasi penting dalam memahami arsitektur Big Data modern dan membangun pipeline yang siap digunakan dalam lingkungan industri.

---

📝 *Disusun oleh Husna Norgina (230104040056) — Praktikum 2 Teknologi Big Data* 

---