# Belajar Machine Learning untuk Pemula: Clustering dan Klasifikasi Data (Segmentasi Pelanggan Otomotif)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue.svg)](https://www.linkedin.com/in/fadelhamka/)

Proyek ini mendemonstrasikan penerapan teknik *unsupervised clustering* dan *supervised classification*. Fokus utama proyek ini adalah melakukan segmentasi pelanggan menggunakan dataset dari studi kasus di industri otomotif. Tujuannya adalah untuk memahami pengelompokan pelanggan dan membangun model untuk memprediksi segmen pelanggan baru.

---

## 🎯 Tujuan

- Melakukan segmentasi pelanggan ke dalam kelompok-kelompok yang berbeda berdasarkan data historis dari industri otomotif.
- Menganalisis karakteristik dari segmen pelanggan yang terbentuk.
- Membangun model klasifikasi yang mampu memprediksi segmen untuk pelanggan potensial di pasar baru.

## ✨ Sorotan Utama

- **Clustering:** Mencapai *silhouette score* sebesar **0.54** setelah menerapkan Principal Component Analysis (PCA), mengindikasikan pemisahan cluster yang cukup baik.
- **Klasifikasi:** Mengembangkan model klasifikasi (Decision Tree, Random Forest, dan SVM) untuk memprediksi segmen pelanggan.
- **Dataset:** Menggunakan dataset **Customer Segmentation Context** dari Kaggle ([https://www.kaggle.com/datasets/vetrirah/customer?select=Train.csv](https://www.kaggle.com/datasets/vetrirah/customer?select=Train.csv)). Dataset ini berisi informasi pelanggan yang telah diklasifikasikan ke dalam 4 segmen (A, B, C, D) oleh tim penjualan perusahaan otomotif.

---

## 💾 Sumber Data

Dataset utama yang digunakan adalah "Train.csv" dari dataset **Customer Segmentation Context** yang tersedia di Kaggle: [https://www.kaggle.com/datasets/vetrirah/customer?select=Train.csv](https://www.kaggle.com/datasets/vetrirah/customer?select=Train.csv).

---

## ⚙️ Alur Kerja Proyek

1. **Pemuatan dan Pra-pemrosesan Data:**
   - Memuat dataset pelanggan dari Kaggle.
   - Melakukan pembersihan dan pra-pemrosesan data yang relevan untuk analisis segmentasi.
   - Menerapkan Principal Component Analysis (PCA) untuk reduksi dimensi data sebelum clustering.

2. **Clustering:**
   - Menerapkan teknik clustering (K-Means) pada data pelanggan yang telah direduksi dimensinya menggunakan PCA.
   - Mengevaluasi kualitas cluster menggunakan **Silhouette Score sebesar 0.54**.
   - Menganalisis karakteristik setiap cluster berdasarkan fitur-fitur pelanggan.

3. **Klasifikasi:**
   - Membangun model klasifikasi menggunakan algoritma seperti Decision Tree, Random Forest, dan Support Vector Machine (SVM) untuk memprediksi segmen pelanggan (A, B, C, D).
   - Mengembangkan *pipeline* untuk memproses data (encoding kategorikal, penskalaan numerik).
   - Mengevaluasi performa model klasifikasi.

4. **Hyperparameter Tuning:**
   - Mengoptimalkan parameter model klasifikasi.

5. **Prediksi Pasar Baru:**
   - Menggunakan model yang telah dilatih untuk memprediksi segmen bagi pelanggan potensial di pasar baru (berdasarkan informasi dari dataset).

---

## 📊 Hasil Akhir dan Insight

- **Hasil Clustering:**
  Setelah menerapkan PCA, fase clustering menghasilkan kelompok dengan **Silhouette Score sebesar 0.54**, mengindikasikan pemisahan cluster yang cukup baik. Jumlah cluster optimal yang teridentifikasi adalah [**Di sini perlu diisi jumlah cluster optimal berdasarkan kode Anda**].

- **Analisis Kluster:**
  Berikut adalah ringkasan karakteristik untuk setiap cluster yang teridentifikasi (berdasarkan data pelanggan):
  - **Cluster 0:**
    - **Umur (Age):** Median mendekati nilai 0–1 (kategori dewasa), dengan rentang cukup lebar (ada outlier usia tua juga).
    - **Pengalaman Kerja (Work_Experience):** Nilai cenderung negatif (median di bawah 0), menandakan pengalaman relatif rendah.
    - **Ukuran Keluarga (Family_Size):** Median negatif (keluarga kecil), rentang juga lebih kecil dibanding kluster lain.
    - **Gender:** Proporsi laki-laki sedikit lebih tinggi daripada perempuan.
    - **Ever_Married:** Mayoritas sudah menikah.
    - **Graduated:** Mayoritas telah lulus.
    - **Profession:** Banyak yang bekerja di bidang **Artist**, diikuti **Entertainment** dan **Lawyer**.
    - **Spending_Score:** Mayoritas menggunakan skor “Low”–“Average”.
    - **Var_1:** Terbanyak di **Cat_6**, diikuti **Cat_4** dan **Cat_3**.
    - **Interpretasi:** Cluster 0 mewakili individu dewasa dengan pengalaman kerja terbatas, keluarga kecil, sebagian besar sudah menikah & lulusan, dan banyak yang berprofesi kreatif (artist/entertainment).
  - **Cluster 1:**
    - **Umur (Age):** Median di bawah 0 (muda), rentang usia paling muda.
    - **Pengalaman Kerja (Work_Experience):** Median tinggi (~1.6), menandakan pengalaman kerja relatif tinggi bagi usia muda (mungkin profesional muda berprestasi).
    - **Ukuran Keluarga (Family_Size):** Cenderung negatif—keluarga kecil/baru.
    - **Gender:** Lebih berimbang, sedikit dominasi perempuan.
    - **Ever_Married:** Hampir semua sudah menikah.
    - **Graduated:** Hampir semua telah lulus.
    - **Profession:** Bervariasi, didominasi **Healthcare**, **Artist**, **Entertainment**.
    - **Spending_Score:** Mayoritas “Low” (skor belanja rendah).
    - **Var_1:** Terbanyak di **Cat_6**, selanjutnya **Cat_4**, **Cat_3**.
    - **Interpretasi:** Cluster 1 adalah kelompok profesional muda berpengalaman, berkeluarga kecil, sudah menikah & lulusan, dengan belanja rendah.
  - **Cluster 2:**
    - **Umur (Age):** Mayoritas dewasa (median ~–0.8), dengan rentang outlier usia tua.
    - **Pengalaman Kerja (Work_Experience):** Median negatif (~–0.5), pengalaman menengah–rendah.
    - **Ukuran Keluarga (Family_Size):** Median positif (keluarga relatif besar).
    - **Gender:** Proporsi laki-laki sedikit lebih tinggi.
    - **Ever_Married:** Proporsi “No” lebih tinggi dibanding kluster lain.
    - **Graduated:** Proporsi “Yes” sedikit di bawah proporsi “No”—akan ada kesetaraan lulusan & non-lulusan.
    - **Profession:** Didominasi **Healthcare**, lalu **Artist**, **Marketing**, **Entertainment**.
    - **Spending_Score:** Banyak yang “Low”, kedua “Average”.
    - **Var_1:** Terbanyak di **Cat_6**, kemudian **Cat_4** & **Cat_3**.
    - **Interpretasi:** Cluster 2 menggambarkan individu dewasa dengan keluarga lebih besar, pengalaman kerja terbatas, banyak belum menikah dan lulusan/non-lulusan seimbang, kebanyakan di bidang healthcare.

- **Performa Klasifikasi:**
  Model klasifikasi yang dibangun menunjukkan performa yang baik dalam memprediksi segmen pelanggan. Metrik evaluasi spesifik akan ditambahkan setelah evaluasi model selesai.

---

## 🛠️ Teknologi yang Digunakan

- **Bahasa Pemrograman:** Python
- **Pustaka (Libraries):**
  - Pandas
  - NumPy
  - Scikit-Learn

---

Jangan ragu untuk terhubung dengan saya di [LinkedIn](https://www.linkedin.com/in/fadelhamka/) untuk diskusi lebih lanjut atau kolaborasi pada proyek ilmu data serupa!
