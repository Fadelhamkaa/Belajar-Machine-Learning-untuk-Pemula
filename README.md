# Belajar Machine Learning untuk Pemula: Clustering dan Klasifikasi Data Lingkungan NYC

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue.svg)](https://www.linkedin.com/in/fadelhamka/)

Proyek ini mendemonstrasikan penerapan teknik *unsupervised clustering* dan *supervised classification* pada data lingkungan dari New York City (NYC). Dataset awal bersumber dari [NYC Department of Health Environment Data](http://nyc.gov/health/environmentdata), dan menjadi fondasi untuk menciptakan cluster yang terpisah dengan baik serta membangun model klasifikasi yang robust.

---

## 🎯 Tujuan

- Melakukan segmentasi data lingkungan menjadi kelompok (cluster) yang berbeda.
- Membangun model klasifikasi yang mampu memprediksi keanggotaan cluster dengan akurat.
- Mendapatkan *insight* mengenai faktor-faktor lingkungan di seluruh NYC.
- Mengevaluasi performa model untuk potensi aplikasi di dunia nyata.

## ✨ Sorotan Utama

- **Clustering:** Setelah menerapkan Principal Component Analysis (PCA), skor Silhouette tertinggi yang dicapai adalah **0.54**, mengindikasikan pemisahan cluster yang cukup baik.
- **Klasifikasi:** Mengembangkan tiga model klasifikasi (Decision Tree, Random Forest, dan SVM) yang semuanya mencapai akurasi 100% setelah *hyperparameter tuning*.
- **Ketidakseimbangan Data:** Meskipun terdapat ketidakseimbangan yang signifikan antar cluster, model berhasil mengklasifikasikan kedua kelompok dengan sempurna, memerlukan investigasi lebih lanjut untuk memastikan generalisasi.

---

## 💾 Sumber Data

Dataset ini awalnya diperoleh dari [NYC Department of Health Environment Data](http://nyc.gov/health/environmentdata). Dataset ini berisi berbagai ukuran dan indikator lingkungan yang memberikan wawasan tentang kesehatan perkotaan dan kualitas lingkungan.

---

## ⚙️ Alur Kerja Proyek

1. **Pemuatan dan Pra-pemrosesan Data:**
   - Memuat dataset dan menghapus kolom yang tidak diperlukan (misalnya, ID, label redundan).
   - Memisahkan fitur dan variabel target (`cluster_label_after_featureSelection`).
   - Membagi data menjadi set pelatihan dan pengujian menggunakan *stratified sampling*.
   - Menerapkan Principal Component Analysis (PCA) untuk reduksi dimensi sebelum clustering.

2. **Clustering:**
   - Menerapkan teknik clustering (K-Means) pada data yang telah direduksi dimensinya menggunakan PCA.
   - Mengevaluasi jumlah cluster optimal menggunakan Elbow Method dan Silhouette Score.
   - Skor Silhouette tertinggi yang diperoleh adalah **0.54**.
   - Memvisualisasikan hasil clustering untuk analisis karakteristik setiap cluster.

3. **Klasifikasi:**
   - Membangun model klasifikasi menggunakan Decision Tree, Random Forest, dan Support Vector Machine (SVM).
   - Mengembangkan *pipeline* untuk memproses data (menggunakan OneHotEncoder dan StandardScaler jika diperlukan).
   - Mengevaluasi model menggunakan metrik seperti Akurasi, Presisi, Recall, dan F1-Score.

4. **Hyperparameter Tuning:**
   - Melakukan GridSearchCV untuk mengoptimalkan parameter model.
   - Mengevaluasi kembali model setelah *tuning*, dengan semua model mencapai akurasi 100% pada set pengujian.

5. **Evaluasi Model:**
   - Membandingkan metrik evaluasi sebelum dan sesudah *tuning*.
   - Memvisualisasikan performa model menggunakan *confusion matrix*.
   - Mendiskusikan potensi *overfitting* dan dampak ketidakseimbangan data.

---

## 📊 Hasil Akhir dan Insight

- **Hasil Clustering:**
  Setelah menerapkan PCA untuk reduksi dimensi, fase clustering menghasilkan kelompok dengan skor Silhouette tertinggi sebesar **0.54**. Ini mengindikasikan pemisahan cluster yang cukup baik setelah transformasi data. Jumlah cluster optimal yang teridentifikasi adalah [**Di sini perlu diisi jumlah cluster optimal berdasarkan kode Anda**].

- **Analisis Kluster:**
  Berikut adalah ringkasan karakteristik untuk setiap cluster yang teridentifikasi (berdasarkan data setelah PCA):
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
  Ketiga model (Decision Tree, Random Forest, dan SVM) mencapai akurasi 100% setelah *tuning*, dengan presisi, recall, dan F1-score yang sempurna untuk kedua cluster.

- **Analisis dan Rekomendasi ke Depan:**
  - **Pengaruh PCA:** Penerapan PCA membantu dalam mereduksi dimensi data sebelum clustering, dan menghasilkan pemisahan cluster dengan skor Silhouette **0.54**. Eksperimen lebih lanjut dengan jumlah komponen PCA yang berbeda dapat dilakukan untuk melihat dampaknya terhadap kualitas cluster.
  - **Generalisasi Model:** Meskipun skor sempurna, performa tinggi memerlukan validasi lebih lanjut (misalnya, *cross-validation* atau pengujian pada data eksternal) untuk memastikan model tidak mengalami *overfitting*.
  - **Mengatasi Ketidakseimbangan:** Dengan perbedaan signifikan dalam jumlah sampel per cluster, teknik tambahan seperti *oversampling* atau *cost-sensitive learning* perlu dieksplorasi.
  - **Eksplorasi Algoritma:** Pertimbangkan untuk menguji algoritma yang lebih canggih (misalnya, Gradient Boosting atau Neural Networks) untuk memverifikasi apakah performa serupa dapat dicapai dengan kondisi pemodelan yang berbeda.

---

## 🛠️ Teknologi yang Digunakan

- **Bahasa Pemrograman:** Python
- **Pustaka (Libraries):**
  - Pandas
  - NumPy
  - Scikit-Learn
  - Matplotlib
  - Seaborn

---

Jangan ragu untuk terhubung dengan saya di [LinkedIn](https://www.linkedin.com/in/fadelhamka/) untuk diskusi lebih lanjut atau kolaborasi pada proyek ilmu data serupa!
