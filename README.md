# Child Growth & Stunting Risk Analysis
![stunting](stunting.jpeg)
## 📌 Overview

Project ini diangkat dari masalah nyata: **keterbatasan jangkauan layanan kesehatan di wilayah pelosok desa**. Di daerah seperti ini, akses ke tenaga kesehatan dan pemantauan pertumbuhan anak tidak selalu mudah, sehingga risiko stunting bisa terlambat terdeteksi. Untuk memudahkan pengecekan, project ini bertujuan membuat **dashboard perhitungan** yang dapat digunakan untuk melakukan screening stunting berdasarkan data pertumbuhan anak. Pada tahap awal, dashboard dirancang menggunakan model prediksi **K-Nearest Neighbors (KNN)**. Menurut WHO, stunting pada anak di bawah lima tahun ditandai dengan tinggi/panjang badan menurut umur yang berada di bawah **-2 SD** dari median WHO Child Growth Standards.

> Project ini untuk pembelajaran dan screening awal berbasis model mechine learning, **bukan alat diagnosis medis**. 
## 🔎 Alur Analisis

1. **Data Understanding**: dataset berisi jenis kelamin, umur, berat badan, tinggi badan, berat lahir, tinggi lahir, riwayat ASI eksklusif, dan status stunting.
2. **Preprocessing**: cek missing value dan tipe data, encoding, pemilihan fitur, standardisasi, dan train-test split.
3. **EDA**: distribusi status stunting, umur, tinggi dan berat badan, perbedaan berdasarkan jenis kelamin, serta hubungan karakteristik pertumbuhan dengan status stunting.
4. **Model awal (KNN, K = 5)**: fitur jenis kelamin, umur, berat lahir, tinggi lahir, berat badan, dan ASI eksklusif. Hasil `predict_proba()` diterjemahkan menjadi kategori risiko rendah, sedang, dan tinggi.

## 🔁 Evaluasi dan Keputusan Pendekatan

Setelah project dievaluasi kembali, untuk saat ini **lebih baik menggunakan perhitungan langsung (HAZ) tanpa model prediksi terlebih dahulu**. Alasannya:

- **KNN kurang sesuai dengan tujuan.** KNN memprediksi berdasarkan kemiripan dengan anak lain di dataset, sedangkan stunting ditentukan dengan membandingkan tinggi anak terhadap standar WHO.
- **Tinggi badan tidak dipakai sebagai fitur**, padahal itu indikator utama stunting.

Meski begitu, **ide prediksi tetap dapat dilanjutkan**. Yang perlu diganti adalah pendekatannya, bukan tujuannya: model machine learning dapat dikembangkan setelah perhitungan HAZ berjalan dengan baik, dengan algoritma yang lebih sesuai daripada KNN.

## 🚀 Pengembangan Selanjutnya

1. **Perhitungan HAZ WHO lengkap** sesuai kelompok umur, jenis kelamin, dan jenis pengukuran.
2. **Dashboard interaktif**
4. **Growth monitoring**: menyimpan riwayat pengukuran untuk melihat perubahan pertumbuhan.
5. **Penjelasan berbasis LLM** (opsional): hanya untuk menerjemahkan hasil ke bahasa sederhana, bukan menentukan status stunting.
Project ini untuk pembelajaran dan eksplorasi data. Hasilnya bukan diagnosis medis dan tidak menggantikan konsultasi dengan tenaga kesehatan.
