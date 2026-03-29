# 🚀 Praktikum 5 — Big Data Analytics & Decision-Oriented System

**Industrial Big Data Pipeline (Spark Structured Streaming + Analytics + Alert System + Streamlit Dashboard)**

Praktikum ini membahas implementasi **Big Data Analytics berbasis streaming** dengan membangun **Decision-Oriented System** menggunakan **Apache Spark Structured Streaming** serta visualisasi data secara real-time menggunakan **Streamlit Dashboard**.

Pipeline pada praktikum ini merupakan pengembangan dari praktikum sebelumnya dengan menambahkan domain **Smart Transportation** serta integrasi **analytics layer dan alert system** untuk menghasilkan insight dan keputusan secara real-time.

Praktikum ini mensimulasikan workflow **Streaming Data → Analytics → Insight → Alert → Dashboard** yang digunakan dalam sistem Big Data modern.

**Topik:** Streaming Analytics, Smart Transportation, Data Lake, Decision-Oriented System, Real-Time Dashboard, Alert System

---

## 🧑‍🎓 Informasi Mahasiswa

| Informasi         | Data                                                             |
| ----------------- | ---------------------------------------------------------------- |
| Mata Kuliah       | Teknologi Big Data                                               |
| Dosen Pengampu    | Muhayat, M.IT                                                    |
| Praktikum         | Big Data Analytics & Use Case                                    |
| Nama Mahasiswa    | Husna Norgina                                                    |
| NIM               | 230104040056                                                     |
| Kelas             | TI23B                                                            |
| Repo GitHub       | https://github.com/husna-norgina/bigdata-technology-praktikum-05 |
| Tanggal Praktikum | 26-03-2026                                                       |

---

# 🎯 Tujuan Praktikum

1. Memahami konsep **Big Data Analytics berbasis streaming**
2. Mengimplementasikan **Spark Structured Streaming untuk data real-time**
3. Membangun **Data Lake menggunakan Parquet**
4. Mengembangkan **analytics layer untuk menghasilkan insight**
5. Membangun **alert system berbasis data real-time**
6. Membuat **dashboard interaktif menggunakan Streamlit**
7. Memahami konsep **Decision-Oriented System dalam Big Data**

---

# 🏛 Arsitektur Pipeline

```
Data Generator (JSON)
        ↓
Streaming Layer (Spark Structured Streaming)
        ↓
Data Lake (Parquet)
        ↓
Analytics Engine (Python)
        ↓
Alert System
        ↓
Dashboard (Streamlit)
```

Pipeline ini menggambarkan **end-to-end Decision-Oriented Big Data System**.

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

---

# 🧱 Struktur Project

```
bigdata-project/
│
├── scripts/
│   └── transportation/
│       ├── trip_generator.py
│       └── streaming_trip_layer.py
│
├── analytics/
│   ├── __init__.py
│   └── transportation_analytics.py
│
├── alerts/
│   ├── __init__.py
│   └── transportation_alert.py
│
├── dashboard/
│   └── dashboard_transportation.py
│
├── data/
│   ├── serving/
│   │   └── transportation/
│   └── checkpoints/
│
├── evidence/
└── README.md
```

---

# 🔥 Implementasi Streaming Layer

Streaming layer dibuat menggunakan **Apache Spark Structured Streaming** untuk memproses data secara real-time.

Spark membaca data dari:

```
stream_data/transportation
```

dan memprosesnya dalam bentuk **micro-batch streaming**.

---

# 🚗 Trip Generator

Trip generator digunakan untuk **mensimulasikan data perjalanan secara real-time**.

Script menghasilkan data JSON setiap beberapa detik.

Contoh data:

```json
{
 "vehicle_type": "motor",
 "location": "Jakarta",
 "distance": 12.5,
 "fare": 25000,
 "timestamp": "2026-03-28 10:15:22"
}
```

---

# 📊 Analytics Layer

Analytics layer digunakan untuk menghasilkan insight seperti:

* Total Trips
* Total Fare
* Top Location
* Peak Hour

---

# 🚨 Alert System

Alert system digunakan untuk mendeteksi kondisi seperti:

* Lonjakan volume perjalanan
* Tarif tinggi
* Kemacetan

---

# 📊 Real-Time Dashboard (Streamlit)

Dashboard menampilkan data secara real-time, seperti:

* Total Trips
* Total Fare
* Top Location
* Peak Hour
* Vehicle Distribution
* Mobility Trend
* Alerts
* Live Trip Data

Dashboard dapat diakses melalui:

```
http://localhost:8501
```

---

# 📸 Screenshot Praktikum

Berikut dokumentasi hasil praktikum.

---

# 1️⃣ Screenshot Struktur Project

![Struktur Project](evidence/1.%20Screenshot%20struktur%20project.png)

Menampilkan struktur folder project yang berisi:

* pipeline Smart Transportation
* analytics layer
* alert system
* dashboard
* data serving

---

# 2️⃣ Screenshot Generator Berjalan

![Generator](evidence/2.%20Screenshot%20generator%20berjalan.png)

Menampilkan proses eksekusi script:

```
python scripts/transportation/trip_generator.py
```

Script menghasilkan data trip secara real-time.

---

# 3️⃣ Screenshot Spark Streaming

![Spark Streaming](evidence/3.%20Screenshot%20Spark%20streaming.png)

![Spark Streaming 1](evidence/4.%20Screenshot%20Spark%20streaming_1.png)

Menampilkan eksekusi pipeline streaming menggunakan:

```
spark-submit scripts/transportation/streaming_trip_layer.py
```

Spark memproses data dalam bentuk **micro-batch processing**.

---

# 4️⃣ Screenshot Folder data/serving

![Serving](evidence/5.%20Screenshot%20folder%20data_serving.png)

Folder ini berisi hasil pemrosesan data dalam format **Parquet Data Lake**.

---

# 5️⃣ Screenshot Dashboard (Insight + Alert)

## Smart Transportation – Real-Time Analytics

![Dashboard 1](evidence/6.%20Screenshot%20dashboard%20(insight_alert)_1.png)

## Fare per Location & Vehicle Distribution

![Dashboard 2](evidence/7.%20Screenshot%20dashboard%20(insight_alert)_2.png)

## Mobility Trend

![Dashboard 3](evidence/8.%20Screenshot%20dashboard%20(insight_alert)_3.png)

## Abnormal Trips

![Dashboard 4](evidence/9.%20Screenshot%20dashboard%20(insight_alert)_4.png)

## Live Trip Data

![Dashboard 5](evidence/10.%20Screenshot%20dashboard%20(insight_alert)_5.png)

Dashboard menampilkan insight dan alert secara real-time.

---

# 📄 Laporan Praktikum 5

📎 [230104040056_Husna Norgina_TBG_P5.pdf](evidence/230104040056_Husna%20Norgina_TBG_P5.pdf)

Isi laporan meliputi:

* Tujuan praktikum
* Konteks Industri
* Arsitektur pipeline
* Output hasil
* Insight + Konteks Decision-Oriented System
* Analisis
* Kesimpulan

---

# 📊 Insight Sistem

Dari sistem yang dibuat dapat dipahami bahwa:

* Data diproses secara real-time
* Sistem menghasilkan insight dan alert otomatis
* Dashboard membantu monitoring secara langsung
* Mendukung pengambilan keputusan berbasis data

---

# ✅ Kesimpulan

Praktikum 5 berhasil mengimplementasikan **Big Data Analytics berbasis streaming** dalam arsitektur *Decision-Oriented System* pada domain *Smart Transportation*.

Melalui praktikum ini dapat dipahami bahwa:

* Event streaming dapat diproses secara kontinu menggunakan **Spark Structured Streaming**
* Data streaming disimpan dalam **Parquet Data Lake** sebagai media penyimpanan
* Analytics layer digunakan untuk menghasilkan insight seperti total trips, total fare, top location, dan peak hour
* Alert system mampu mendeteksi kondisi tertentu seperti lonjakan volume dan tarif tinggi secara real-time
* Streamlit digunakan sebagai **Real-Time Visualization Layer**
* Dashboard memungkinkan pengguna memantau data, insight, dan alert secara langsung

Praktikum ini memberikan gambaran end-to-end workflow **Streaming Data → Analytics → Insight → Alert → Dashboard** dalam sistem Big Data modern yang mendukung pengambilan keputusan secara cepat dan berbasis data. 

---

📝 *Disusun oleh Husna Norgina (230104040056) — Praktikum 5 Teknologi Big Data*

---