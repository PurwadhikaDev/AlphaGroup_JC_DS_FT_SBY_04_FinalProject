<h1> Prediksi pembatalan pemesanan hotel</h1>

## 1. Ringkasan Project 
Proyek ini bertujuan untuk menganalisis data bisnis guna mendapatkan wawasan, meningkatkan pengambilan keputusan, dan mengidentifikasi tren utama. Fokus utama adalah **memprediksi pembatalan pemesanan hotel agar dapat mengoptimalkan strategi pemesanan dan mengurangi risiko pembatalan.**

**Key Objectives:**
- Objektif 1: mempermudah hotel untuk memprediksi kemungkinan pembatalan
- Objektif 2: Mengidentifikasi faktor-faktor utama yang berkontribusi terhadap pembatalan pemesanan.
- Objektif 3: Mengoptimalkan strategi penjualan dan kebijakan pembatalan untuk meningkatkan pendapatan.

## 2. Data
- [Dataset 1](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand/data) - Hotel Bookings

## 3. Packages
- Programming Language: Python (pandas, numpy)
- Visualization: Matplotlib, Seaborn
- statistic : scipy, statmodels
- machine learning : scikit-learn, imblearn
- Version Control: Git
- Others: Jupyter Notebook

## 4. Stuktur project

```
├── README.md          <- Dokumentasi utama proyek ini.
├── data
│   ├── cleaned_data   <- Data yang telah dibersihkan dan diproses
│   ├── data-latih     <- Data yang digunakan untuk melatih sebuah model untuk mendapatkan model terbaik
│   ├── data-test      <- Data yang digunakan untuk menguji model
│   └── hotel_bookings <- Data original yang belum diproses 
│
├── models             <- Model yang telah dilatih dan dievaluasi.
│
├── notebooks          <- Notebook Jupyter untuk eksplorasi dan analisis data.
│
├── reports            <- Hasil analisis 
│
├── requirements.txt   <-  Daftar packages pada python yang digunakan dalam proyek ini.
│
└── src                <- Source code for use in this project.

```

## 5. Kesimpulan
### 5.1 Business Insight
1. **Model Terbaik:** **Gradient Boosting (After Tuning) dengan precision 85%**, memastikan bahwa ketika model memprediksi pembatalan, maka akurasi keputusan ini tinggi (minim false positives).
2. **Faktor Utama yang Mempengaruhi Pembatalan:**
    - `Lead Time`: Semakin lama jeda antara pemesanan dan tanggal check-in, semakin tinggi kemungkinan pembatalan.
    - `Tipe Pelanggan (Customer Type)`: Pelanggan "transient" lebih sering membatalkan karena fleksibilitas reservasi.
    - `Kanal Pemesanan (Distribution Channel)`: Pemesanan melalui OTA lebih sering dibatalkan dibandingkan dengan reservasi langsung.
    - `Deposit Type`: Kebijakan pembayaran Non-Refundable secara signifikan mengurangi pembatalan.
    - `Riwayat Pembatalan (Previous Cancellations)`: Pelanggan yang pernah membatalkan reservasi sebelumnya cenderung membatalkan lagi di masa mendatang.

3. **Analisis Revenue Recovery & Overbooking Cost Reduction:**
- **Revenue Recovery Rate (RRR)**: Meningkat 72.30%, menunjukkan efektivitas model dalam mengidentifikasi pembatalan berisiko tinggi.
- **Overbooking Cost Reduction (OCR)**: Berkurang 84.03%, mengurangi biaya kompensasi akibat kesalahan prediksi overbooking.

### 5.2 Tren Musiman dalam Pembatalan
- **Bulan dengan reservasi tertinggi**: Juli & Agustus → Namun juga memiliki tingkat pembatalan tinggi.
- **Bulan dengan reservasi terendah**: Desember & Januari → Perlu strategi promosi untuk meningkatkan pemesanan.

### 5.3 Strategi Bisnis untuk Mengurangi Dampak Pembatalan
1. **Tingkatkan Strategi Overbooking yang Lebih Presisi**  
    - Gunakan hasil prediksi model untuk menentukan **tingkat overbooking yang optimal** berdasarkan musim, jenis tamu, dan kanal pemesanan.  
    - Terapkan strategi **overbooking dinamis**, di mana jumlah overbooking disesuaikan dengan pola pembatalan real-time untuk menghindari risiko kompensasi berlebih.  
    - Lakukan uji coba dengan **segmen tamu tertentu** (misalnya tamu leisure dengan riwayat pembatalan tinggi) untuk melihat dampak strategi overbooking yang lebih agresif.  

2. **Optimalkan Revenue Recovery melalui Strategi Penjualan & Promosi**  
    - Gunakan **targeted promotions** untuk tamu yang berisiko tinggi membatalkan, seperti:  
    - Penawaran diskon atau upgrade kamar bagi tamu yang memilih opsi pembayaran di muka.  
    - Kampanye **last-minute deals** untuk mengisi kamar kosong akibat pembatalan mendadak.  
    - Gunakan hasil prediksi model untuk memberikan **personalized pricing & cancellation policies**, di mana tamu dengan riwayat pembatalan tinggi dikenakan **biaya pembatalan lebih besar** atau **persyaratan deposit lebih ketat**.  

3. **Perkuat Sistem Peringatan Dini untuk Pembatalan**  
     - Implementasikan sistem **notifikasi otomatis** untuk memberi peringatan kepada tim reservasi tentang pemesanan dengan risiko tinggi pembatalan.  
     - Gunakan sistem peringatan ini untuk **meningkatkan fleksibilitas rebooking**, seperti menawarkan tamu opsi untuk menjadwal ulang daripada membatalkan.  

4. **Evaluasi & Perbarui Model Secara Berkala**  
    - Pastikan model tetap akurat dengan melakukan **validasi berkala** dan memasukkan **tren eksternal** seperti perubahan kebijakan OTA atau musim wisata.  

## 6. Hasil Report
- Link Presentasi:
- Link Tableau : https://public.tableau.com/app/profile/ghaisan.rabbani5530/viz/hotelbokings-Copy/Dashboard33
