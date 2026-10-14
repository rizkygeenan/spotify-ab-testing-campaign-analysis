# 🎵 A/B Testing: Spotify Targeted Campaign Strategy

Proyek analisis A/B Testing berbasis data untuk mengevaluasi efektivitas kampanye promosi terpersonalisasi terhadap peningkatan **Payment Conversion Rate (CVR)** pengguna paket *Free* Spotify serta dampaknya terhadap **User Engagement (Duration Played)**.

---

## 📌 Executive Summary

* **Masalah Utama**: Tingkat *drop-off* pada kelompok Control masih tinggi (30,3% pengguna *Free* keluar tanpa melakukan konversi pembayaran).
* **Inisiatif Eksperimen**: Mengevaluasi kampanye promosi terpersonalisasi (banner diskon/uji coba khusus + rekomendasi konten yang relevan) pada kelompok Target.
* **Hasil Utama**:
  * **Success Metric (Payment CVR)**: Naik secara signifikan sebesar **+10.1%** (dari 69.7% menjadi 79.8%, p-value = 0.0000 < 0.05).
  * **Guardrail Metric (Duration Played)**: Rata-rata durasi mendengarkan pengguna naik sebesar **+39.84 menit** (dari 120.07 menit menjadi 159.91 menit, p-value = 0.0000 < 0.05).
* **Keputusan Bisnis**: **Full Rollout (100%)** kampanye terpersonalisasi ke seluruh pengguna paket *Free*.

---

## 🎯 Objectives & Assignment Scope

1. **Eksperimen & Desain A/B Testing**: Merancang alur eksperimen, menentukan *Success Metric* dan *Guardrail Metric*, serta melakukan uji hipotesis statistik secara tepat.
2. **Monitoring & Evaluasi**: Menganalisis kondisi *Before vs. After* dan memastikan tidak terjadi kanibalisasi pada metrik keterlibatan pengguna.
3. **Rekomendasi Bisnis**: Memberikan rekomendasi keputusan strategis berbasis konklusi kuantitatif.
4. **Pertanyaan Reflektif**: Menjelaskan urgensi detail perancangan sampel, penanganan kondisi *current* vs. inovasi, dan langkah pasca-implementasi.

---

## 📁 Repository Structure

```text
.
├── Assignment - spotify_campaign_data.csv   # Dataset A/B Testing (100,000 sampel)
├── AB_Testing_Spotify_Campaign.ipynb         # Python Colab Notebook (Data Cleaning & Hypothesis Testing)
├── A_B Testing Spotify Campaign.pptx         # Slide Presentasi & Visualisasi Storytelling
└── README.md                                 # Dokumentasi Portofolio Data Analyst
```

---

## 🛠️ Tools & Technologies Used

- **Python (Google Colaboratory)**: Data Manipulation (`pandas`, `numpy`) & Statistical Testing (`statsmodels`, `scipy`).
- **Power BI / Slide Visuals**: Pembuatan grafik perbandingan dan visualisasi funnel performa kampanye.
- **Statistik Terapan**: Two-Sample Proportion Z-Test & Independent Two-Sample T-Test.

---

## 📐 Experiment Design & Metrics Definition

### 1. Identify Change
- **Kondisi Saat Ini (Control / Group A)**: Pengguna *Free* melihat iklan suara standar dan banner promosi umum tanpa penawaran khusus.
- **Perubahan Diajukan (Target / Group B)**: Pengguna *Free* menerima penawaran diskon/uji coba yang dipersonalisasi serta rekomendasi konten yang disesuaikan.

### 2. Hypothesis Definition
> *"Menerapkan kampanye promosi khusus dan rekomendasi terpersonalisasi akan meningkatkan tingkat konversi pembayaran pengguna Free ke Premium karena penawaran yang relevan dapat mendorong engagement dan mengurangi rate user drop-off."*

### 3. Key Metrics & Statistical Formulation

| Kategori Metrik | Nama Metrik | Definisi Operasional | Uji Statistik | Formulasi Hipotesis |
| :--- | :--- | :--- | :--- | :--- |
| **Success Metric** | **Payment Conversion Rate (CVR)** | Persentase pengguna yang melakukan pembayaran (`Payment = Yes`) | Two-Sample Proportion Z-Test | `H0: CVR_Target <= CVR_Control`<br>`H1: CVR_Target > CVR_Control` |
| **Guardrail Metric** | **Average Session Duration** | Rata-rata durasi waktu mendengarkan (`Duration Played` dalam menit) | Independent T-Test | `H0: Avg_Target <= Avg_Control`<br>`H1: Avg_Target > Avg_Control` |

---

## 📊 Statistical Analysis & Results

Uji statistik dilakukan terhadap 100.000 total populasi sampel ($N = 50.000$ per kelompok Control dan Target).

### 1. Success Metric: Payment Conversion Rate (CVR)
- **Control CVR**: 69.7% (34,844 converted / 50,000 users)
- **Target CVR**: 79.8% (39,907 converted / 50,000 users)
- **Absolute Uplift**: +10.1% (+1,010 bps)
- **Z-Statistic**: 36.8534
- **P-value**: 0.0000 (p < 0.05)
- **Konklusi**: **Tolak H0**. Terdapat peningkatan *Payment Conversion Rate* yang signifikan secara statistik pada kelompok Target.

### 2. Guardrail Metric: Session Duration Played
- **Control Mean Duration**: 120.07 menit
- **Target Mean Duration**: 159.91 menit
- **Absolute Uplift**: +39.84 menit (+33.2%)
- **P-value**: 0.0000 (p < 0.05)
- **Konklusi**: **Tolak H0**. Peningkatan konversi pembayaran **TIDAK mengorbankan durasi sesi pengguna**. Sebaliknya, *engagement* pengguna meningkat secara signifikan.

---

## 💡 Strategic Recommendations & Monitoring

1. **Full Rollout Strategy**: Meluncurkan (*rollout*) fitur kampanye promosi terpersonalisasi dan sistem rekomendasi ke 100% pengguna *Free* Spotify.
2. **Monitoring Before vs. After**:
   - Melakukan pemantauan CVR mingguan pasca-peluncuran penuh untuk memastikan tidak ada penurunan performa karena efek kecenderungan baru (*novelty effect*).
   - Memantau indikator retensi jangka panjang (*30-day Retention Rate*) pada pengguna baru yang melakukan konversi ke Premium.
3. **Optimisasi Lebih Lanjut**: Melakukan segmentasi audiens berbasis preferensi genre musik untuk membuat penawaran diskon yang lebih spesifik pada *cohort* pengguna berkonversi rendah.

---

## 💭 Reflection Questions

### 1. Mengapa perancangan detail eksperimen (durasi, pemilihan sampel, dll.) sangat krusial?
Detail perancangan sangat krusial untuk menjaga kelayakan ilmiah eksperimen:
- **Sampel**: Pemilihan sampel wajib acak (*random assignment*) agar bebas dari bias latar belakang (*confounding variables*).
- **Ukuran Sampel (Sample Size)**: Menentukan sampel yang cukup memastikan kekuatan uji statistik (*statistical power*) memadai dalam mendeteksi perbedaan nyata (*Minimum Detectable Effect*).
- **Durasi Eksperimen**: Menjalankan eksperimen dengan durasi yang sesuai mencegah bias musiman (*seasonality*) dan *novelty effect* (efek penasaran pengguna di awal kemunculan fitur baru).

### 2. Apa yang harus dilakukan jika kondisi current ternyata lebih baik daripada kondisi inovasi?
Jika inovasi menghasilkan performa lebih buruk (*Failed Experiment*):
- **Gagal Tolak H0 / Rollback**: Membatalkan peluncuran variasi baru dan mempertahankan kondisi *current* (Control).
- **Root Cause Analysis**: Melakukan analisis mendalam (*post-mortem analysis*) untuk memahami mengapa inovasi tidak berhasil (misalnya: pesan promosi dianggap mengganggu, kendala UI/UX, atau harga uji coba tidak menarik).
- **Iterasi Hipotesis**: Memperbaiki rancangan kampanye berdasarkan *feedback* data, lalu menyiapkan hipotesis baru sebelum melakukan pengujian ulang.

### 3. Jika rekomendasi sudah diimplementasikan, apa langkah selanjutnya?
Setelah implementasi (*post-implementation step*):
- **Continuous Guardrail Monitoring**: Memantau dampak jangka panjang terhadap ketersediaan server, *churn rate* paket Premium, dan *customer lifetime value* (CLV).
- **Guard Against Cannibalization**: Memastikan promosi diskon tidak membuat pengguna yang sebenarnya bersedia membayar harga penuh beralih memilih paket diskon termurah (*margin erosion*).
- **Mulai Siklus A/B Test Baru**: Mencari area optimisasi berikutnya (misal: pengujian variasi *copywriting* penawaran atau letak tombol *Call-to-Action*).

---

## 👤 Author

- **Nama**: Muhammad Rizky Ginanjar
- **Role**: Data Analyst
- **LinkedIn**: [Muhammad Rizky Ginanjar](https://www.linkedin.com/in/rizkyginan/)
