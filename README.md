# 🚀 Praktikum 4 — Streaming Processing & Real-Time Dashboard

**Industrial Streaming Analytics (Spark Structured Streaming + Streamlit)**

Praktikum ini membahas implementasi **Streaming Processing dan Real-Time Analytics** pada arsitektur **Big Data Pipeline** menggunakan **Apache Spark Structured Streaming** serta visualisasi data secara real-time menggunakan **Streamlit Dashboard**.

Pipeline data pada praktikum ini melanjutkan arsitektur Big Data dari praktikum sebelumnya dan menambahkan **Streaming Layer** untuk memproses event transaksi secara real-time.

Praktikum ini mensimulasikan workflow **Real-Time Data Engineering → Streaming Analytics → Dashboard Monitoring** yang banyak digunakan dalam sistem Big Data modern.

**Topik:** Stream Processing, Event Streaming, Spark Structured Streaming, Parquet Data Lake, Real-Time Dashboard, Streamlit, Data Engineering

---

## 🧑‍🎓 Informasi Mahasiswa

| Informasi         | Data                                                             |
| ----------------- | ---------------------------------------------------------------- |
| Mata Kuliah       | Teknologi Big Data                                               |
| Dosen Pengampu    | Muhayat, M.IT                                                    |
| Praktikum         | Streaming Processing + Real-Time Dashboard                       |
| Nama Mahasiswa    | Husna Norgina                                                    |
| NIM               | 230104040056                                                     |
| Kelas             | TI23B                                                            |
| Repo GitHub       | https://github.com/husna-norgina/bigdata-technology-praktikum-04 |
| Tanggal Praktikum | 12-03-2026                                                       |

---

# 🎯 Tujuan Praktikum

1. Memahami konsep **stream processing dalam sistem Big Data**
2. Mensimulasikan **event streaming menggunakan file incremental**
3. Mengimplementasikan **Spark Structured Streaming untuk memproses data real-time**
4. Menyimpan hasil streaming ke **Serving Layer (Parquet Data Lake)**
5. Membangun **dashboard analitik real-time menggunakan Streamlit**
6. Mengintegrasikan pipeline **Streaming → Analytics → Visualization**

Tujuan utama praktikum ini adalah memahami bagaimana **pipeline data real-time bekerja dalam arsitektur Big Data modern**. 

---

# 🏛 Arsitektur Pipeline

Pipeline streaming pada praktikum ini adalah:

```
Transaction Generator
        ↓
stream_data/
(JSON events)
        ↓
Spark Structured Streaming
        ↓
Parquet Data Lake
data/serving/stream
        ↓
Real-Time Dashboard
(Streamlit)
```

Pipeline ini menggambarkan **end-to-end streaming analytics system** yang digunakan dalam sistem monitoring real-time.

---

# 🛠 Tools & Environment

Tools yang digunakan dalam praktikum ini:

* Ubuntu (WSL – Linux Server Environment)
* Visual Studio Code (Remote WSL)
* Python 3
* Apache Spark (PySpark)
* Streamlit
* Bash CLI
* Parquet Data Lake
* Git & GitHub

Stack teknologi ini mencerminkan **arsitektur modern dalam Data Engineering dan Real-Time Analytics**.

---

# 🧱 Struktur Project

```
bigdata-project/
│
├── stream_data/
│
├── data/
│   └── serving/
│       └── stream/
│
├── scripts/
│   ├── streaming_layer.py
│   └── transaction_generator.py
│
├── dashboard/
│   └── dashboard_streamlit.py
│
├── logs/
├── reports/
├── evidence/
└── README.md
```

Struktur ini mencerminkan arsitektur **Streaming Processing Pipeline** pada sistem Big Data.

---

# 🔥 Implementasi Streaming Layer

Streaming Layer dibuat menggunakan **Apache Spark Structured Streaming**.

Inisialisasi Spark:

```python
spark = SparkSession.builder \
    .appName("StreamingPipeline") \
    .getOrCreate()
```

Spark membaca event streaming dari folder:

```
stream_data
```

dan memprosesnya menggunakan **micro-batch streaming**.

---

# 📊 Transaction Generator

Transaction generator digunakan untuk **mensimulasikan event transaksi e-commerce secara real-time**.

Script ini akan menghasilkan file JSON setiap **3 detik**.

Contoh event transaksi:

```json
{
 "user_id": 152,
 "product": "Keyboard",
 "price": 1075,
 "city": "Medan",
 "timestamp": "2026-03-13 21:45:46"
}
```

Event ini disimpan dalam folder:

```
stream_data/
```

---

# 📊 Streaming Processing

Spark membaca file JSON secara streaming:

```python
spark.readStream \
    .schema(schema) \
    .option("maxFilesPerTrigger",1) \
    .json("stream_data")
```

Hasil pemrosesan disimpan dalam format **Parquet Data Lake** pada:

```
data/serving/stream
```

Format Parquet dipilih karena:

* efisien untuk analytics
* ukuran file lebih kecil
* performa query lebih cepat

---

# 📊 Real-Time Dashboard (Streamlit)

Data streaming kemudian divisualisasikan menggunakan **Streamlit Dashboard**.

Dashboard menampilkan:

* Total Transactions
* Total Revenue
* Average Transaction
* Revenue per City
* Top Products
* Revenue Trend
* Live Transactions Table

Dashboard dapat diakses melalui:

```
http://localhost:8501
```

Dashboard ini menampilkan **analitik transaksi secara real-time**.

---

# 📸 Screenshot Praktikum

Berikut dokumentasi hasil praktikum.

---

# 1️⃣ Screenshot Struktur Project

![Struktur Project](evidence/1.%20Screenshot%20struktur%20project.png)

Menampilkan struktur folder project yang berisi:

* streaming scripts
* dashboard
* serving layer
* streaming data

---

# 2️⃣ Screenshot Generator Transaksi Berjalan

![Generator](evidence/2.%20Screenshot%20generator%20transaksi%20berjalan.png)

Menampilkan proses eksekusi script:

```
python3 scripts/transaction_generator.py
```

Script menghasilkan event transaksi setiap **3 detik**.

---

# 3️⃣ Screenshot Spark Streaming Berjalan

![Spark Streaming](evidence/3.%20Screenshot%20Spark%20streaming%20berjalan.png)

Menampilkan eksekusi pipeline streaming menggunakan:

```
spark-submit scripts/streaming_layer.py
```

Spark memproses data streaming dalam bentuk **micro-batch processing**.

---

# 4️⃣ Screenshot Folder data/serving/stream

![Serving Stream](evidence/4.%20Screenshot%20folder%20data_serving_stream.png)

Folder ini berisi file hasil streaming dalam format:

```
part-00000.snappy.parquet
```

File ini merupakan **output dari Spark Structured Streaming**.

---

# 5️⃣ Screenshot Dashboard Real-Time

### Dashboard View

![Dashboard](evidence/5.%20Screenshot%20dashboard%20real-time_1.png)

### Revenue Charts

![Dashboard](evidence/6.%20Screenshot%20dashboard%20real-time_2.png)

### Revenue Trend

![Dashboard](evidence/7.%20Screenshot%20dashboard%20real-time_3.png)

### Live Transactions

![Dashboard](evidence/8.%20Screenshot%20dashboard%20real-time_4.png)

Dashboard ini menampilkan **analitik transaksi e-commerce secara real-time**.

---

# 📄 Laporan Praktikum 4

📎 [230104040056_Husna Norgina_P4.pdf](evidence/230104040056_Husna%20Norgina_P4.pdf)

Isi laporan meliputi:

* Tujuan praktikum
* Konteks industri streaming data
* Arsitektur pipeline streaming
* Output hasil praktikum
* Analisis
* Kesimpulan

---

# 📊 Insight Sistem Streaming

Dari pipeline yang dibuat dapat dipahami bahwa:

* Event transaksi dapat diproses secara **real-time**
* Spark Structured Streaming memproses data dalam **micro-batch**
* Data streaming disimpan dalam **Parquet Data Lake**
* Dashboard Streamlit memungkinkan **monitoring transaksi secara langsung**

Pipeline ini mensimulasikan sistem **Real-Time Analytics Platform** yang digunakan oleh perusahaan teknologi modern.

---

# ✅ Kesimpulan

Praktikum 4 berhasil mengimplementasikan **Streaming Processing dan Real-Time Analytics** dalam arsitektur Big Data.

Melalui praktikum ini dapat dipahami bahwa:

* Event streaming dapat diproses secara kontinu menggunakan **Spark Structured Streaming**
* Data streaming disimpan dalam **Parquet Data Lake**
* Streamlit digunakan sebagai **Real-Time Visualization Layer**
* Dashboard memungkinkan pengguna memantau transaksi secara langsung.

Praktikum ini memberikan gambaran **end-to-end workflow Real-Time Big Data Analytics dari event streaming hingga dashboard monitoring**.

---

📝 *Disusun oleh Husna Norgina (230104040056) — Praktikum 4 Teknologi Big Data*

---