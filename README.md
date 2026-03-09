# 🚀 Praktikum 3 — Batch Analytics & Visualization with Spark + Power BI

**Enterprise Edition (WSL + VS Code + Spark + Business Intelligence Dashboard)**

Praktikum ini membahas implementasi **Analytics Layer dan Visualization Layer** pada arsitektur **Big Data Pipeline** menggunakan **Apache Spark (PySpark)** serta visualisasi data menggunakan **Microsoft Power BI**.

Pipeline data pada praktikum ini melanjutkan proses dari **Batch Processing Pipeline (Praktikum 2)** dan menghasilkan dataset analitik yang siap digunakan untuk **Business Intelligence Dashboard**.

Praktikum ini mensimulasikan workflow **Data Engineering → Business Intelligence** pada industri modern.

**Topik:** Analytics Layer, KPI Generation, Serving Layer, Business Intelligence, Dashboard Visualization, PySpark, Power BI

---

## 🧑‍🎓 Informasi Mahasiswa

| Informasi         | Data                                                             |
| ----------------- | ---------------------------------------------------------------- |
| Mata Kuliah       | Teknologi Big Data                                               |
| Dosen Pengampu    | Muhayat, M.IT                                                    |
| Praktikum         | Batch Data Analytics + Visualization Layer                       |
| Nama Mahasiswa    | Husna Norgina                                                    |
| NIM               | 230104040056                                                     |
| Kelas             | TI23B                                                            |
| Repo GitHub       | https://github.com/husna-norgina/bigdata-technology-praktikum-03 |
| Tanggal Praktikum | 05-03-2026                                                       |

---

# 🎯 Tujuan Praktikum

1. Memahami peran **Analytics Layer dalam Big Data Pipeline**
2. Menghasilkan **KPI bisnis menggunakan Apache Spark**
3. Membuat **Serving Layer dataset untuk BI tools**
4. Menghubungkan dataset Spark ke **Power BI**
5. Membuat **dashboard analitik sederhana**
6. Menyajikan insight bisnis dari data transaksi e-commerce

Tujuan utama praktikum ini adalah memahami bagaimana **data engineer menyediakan dataset untuk kebutuhan analisis bisnis dan dashboard eksekutif**.

---

# 🏛 Arsitektur Pipeline

Pipeline pada praktikum ini adalah:

```
Raw Dataset (CSV)
       ↓
Spark Processing
       ↓
Clean Data (Parquet)
       ↓
Analytics Layer
       ↓
Serving Layer (CSV)
       ↓
Power BI Dashboard
```

Pipeline ini menggambarkan **end-to-end Big Data Architecture** dari data mentah hingga dashboard bisnis. 

---

# 🛠 Tools & Environment

Tools yang digunakan dalam praktikum ini:

* Ubuntu (WSL – Linux Server Environment)
* Visual Studio Code (Remote WSL)
* Python 3
* PySpark
* Bash CLI
* Microsoft Power BI Desktop
* Git & GitHub

Tools tersebut mencerminkan **stack teknologi modern dalam Data Engineering dan Business Intelligence**.

---

# 🧱 Struktur Project

```
bigdata-project/
│
├── data/
│   ├── clean/
│   │   └── parquet/
│   │
│   └── serving/
│       ├── total_revenue/
│       ├── top_products/
│       ├── category_revenue/
│       └── avg_transaction/
│
├── logs/
├── reports/
├── scripts/
│   ├── analytics_layer.py
│   ├── batch_pipeline_enterprise.py
│   └── visualization_layer.py
│
├── evidence/
├── README.md
```

Struktur ini mencerminkan arsitektur **Analytics Layer dan Serving Layer dalam Data Engineering pipeline**.

---

# 🔥 Implementasi Analytics Layer

Analytics Layer dibuat menggunakan **Apache Spark (PySpark)**.

Inisialisasi Spark:

```python
SparkSession.builder \
    .appName("AnalyticsLayer") \
    .master("local[*]") \
    .getOrCreate()
```

Dataset yang digunakan berasal dari:

```
data/clean/parquet
```

Kemudian dilakukan agregasi untuk menghasilkan beberapa **Key Performance Indicators (KPI)**.

---

# 📊 KPI yang Dihasilkan

Analytics Layer menghasilkan beberapa metrik bisnis penting:

### 1️⃣ Total Revenue

Menghitung total pendapatan dari seluruh transaksi.

Output disimpan pada:

```
data/serving/total_revenue
```

---

### 2️⃣ Top Products

Menghitung produk dengan jumlah penjualan tertinggi.

Output disimpan pada:

```
data/serving/top_products
```

---

### 3️⃣ Revenue per Category

Menghitung total pendapatan berdasarkan kategori produk.

Output disimpan pada:

```
data/serving/category_revenue
```

---

### 4️⃣ Average Transaction Value

Menghitung rata-rata nilai transaksi per pelanggan.

Output disimpan pada:

```
data/serving/avg_transaction
```

Dataset tersebut menjadi **Serving Layer** yang akan digunakan oleh tools Business Intelligence.

---

# 📊 Visualization Layer (Power BI)

Dataset dari folder **data/serving** kemudian dihubungkan ke **Power BI Desktop** untuk membuat dashboard analitik.

Visualisasi yang dibuat meliputi:

* KPI Card → Total Revenue
* Bar Chart → Top Products
* Bar Chart → Revenue per Category

Dashboard disusun dengan layout:

```
---------------------------------
E-Commerce Sales Dashboard
---------------------------------
Total Revenue
---------------------------------
Top Product | Revenue per Category
---------------------------------
```

Dashboard ini membantu **pengambil keputusan bisnis memahami performa penjualan secara cepat**.

---

# 📸 Screenshot Praktikum

Berikut dokumentasi hasil praktikum.

---

### 1️⃣ Dashboard Power BI

![Dashboard Power BI](evidence/1.%20Screenshot%20dashboard%20Power%20BI.png)

Menampilkan dashboard **E-Commerce Sales Dashboard** yang berisi:

* KPI **Total Revenue**
* **Top Products Chart**
* **Revenue per Category Chart**

---

### 2️⃣ Dataset Serving Layer

![Serving Dataset](evidence/2.%20Screenshot%20folder%20serving%20dataset%20data_serving.png)

Screenshot folder:

```
data/serving
```

Menunjukkan dataset hasil **Analytics Layer** yang siap digunakan oleh Power BI.

---

### 3️⃣ Analytics Layer Execution

Menampilkan proses eksekusi script:

```
python scripts/analytics_layer.py
```

#### Screenshot 1

![Terminal 1](evidence/3.%20Screenshot%20terminal%20saat%20menjalankan%20python%20scripts1.png)

#### Screenshot 2

![Terminal 2](evidence/4.%20Screenshot%20terminal%20saat%20menjalankan%20python%20scripts2.png)

#### Screenshot 3

![Terminal 3](evidence/5.%20Screenshot%20terminal%20saat%20menjalankan%20python%20scripts3.png)

Menampilkan:

* Total records
* Total revenue
* Top products
* Revenue per category
* Status eksekusi pipeline

---

### 4️⃣ Visualisasi dengan Pandas + Matplotlib

![Visualization](evidence/6.%20Screenshot%20scripts%20Visualisasi%20dengan%20Pandas%20+%20Matplotlib.png)

Menampilkan proses pembuatan visualisasi menggunakan **Pandas dan Matplotlib**.

---

## 📄 Laporan Praktikum 3

📎 [230104040056_Husna Norgina_P3.pdf](evidence/230104040056_Husna%20Norgina_P3.pdf)

Isi laporan meliputi:

* Tujuan praktikum
* Konteks industri Big Data
* Arsitektur pipeline data
* Output hasil praktikum
* Analisis
* Kesimpulan

---

## 🗃 File Dashboard Power BI

📎 [bigdata_dashboard.pbix](evidence/bigdata_dashboard.pbix)

File ini berisi dashboard **E-Commerce Sales Dashboard** yang digunakan untuk menampilkan hasil analisis data secara visual.

---

# 📊 Insight Bisnis

Dari dashboard yang dibuat dapat diperoleh insight seperti:

* Total revenue perusahaan dari seluruh transaksi
* Produk dengan penjualan tertinggi
* Kategori produk dengan kontribusi revenue terbesar
* Pola nilai transaksi pelanggan

Insight ini membantu perusahaan dalam **mengoptimalkan strategi penjualan dan pengambilan keputusan bisnis**.

---

# ✅ Kesimpulan

Praktikum 3 berhasil mengimplementasikan **Analytics Layer dan Visualization Layer dalam Big Data Architecture**.

Melalui praktikum ini dapat dipahami bahwa:

* Apache Spark digunakan untuk melakukan pemrosesan dan analisis data.
* Analytics Layer menghasilkan dataset KPI yang siap digunakan untuk BI.
* Power BI berfungsi sebagai **Visualization Layer** yang menampilkan insight bisnis dalam bentuk dashboard.
* Data pipeline modern menghubungkan proses **Data Engineering → Business Intelligence**.

Praktikum ini memberikan gambaran **end-to-end workflow Big Data dari data mentah hingga dashboard analitik**.

---

📝 *Disusun oleh Husna Norgina (230104040056) — Praktikum 3 Teknologi Big Data*

---