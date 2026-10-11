# Analisis Tingkat Kecemasan Pemain Game Daring (Online Gaming Anxiety - Machine Learning Project)

Repositori ini berisi proyek praktikum *Machine Learning* yang bertujuan untuk menganalisis dan memprediksi tingkat kecemasan (`GADE`) pada pemain gim daring berdasarkan profil demografi serta pola kebiasaan bermain.

## 📋 Daftar Isi
1. [Tentang Proyek](#-tentang-proyek)
2. [Struktur Dataset](#-struktur-dataset)
3. [Alur Kerja (Workflow)](#-alur-kerja-workflow)
4. [Instalasi & Kebutuhan Sistem](#-instalasi--kebutuhan-sistem)
5. [Cara Menjalankan Proyek](#-cara-menjalankan-proyek)
6. [Hasil & Evaluasi Model](#-hasil--evaluasi-model)
7. [Kontributor](#-kontributor)

---

## 🎯 Tentang Proyek

Aktivitas bermain game daring secara intensif memiliki keterkaitan erat dengan kondisi kesehatan mental, salah satunya adalah tingkat kecemasan pemain. Proyek ini menerapkan pendekatan *Supervised Learning* (Klasifikasi) menggunakan algoritma *Decision Tree* dan *Random Forest* untuk memprediksi tingkat kecemasan (`GADE`) individu berdasarkan variabel demografi dan pola perilaku bermain mereka.

---

## 📊 Struktur Dataset

Dataset yang digunakan dalam proyek ini adalah `GamingStudy_data.csv` yang terdiri dari 13.464 baris dan 55 kolom, mencakup:
* **Fitur Demografi / Identitas:** Usia (`Age`), Jenis Kelamin (`Gender`), Status Pekerjaan (`Work`), dll.
* **Fitur Perilaku Bermain:** Durasi waktu bermain per minggu (`Hours`), frekuensi bermain, dll.
* **Fitur Psikologis:** Skor total gangguan kecemasan umum (`GAD_T`), kecemasan sosial (`SPIN_T`), dll.
* **Variabel Target (`GADE`):** Kategori tingkat kesulitan kecemasan akibat bermain gim (*Not difficult at all*, *Somewhat difficult*, *Very difficult*, dll.) yang ditransformasikan ke dalam format biner.

---

## 🔄 Alur Kerja (Workflow)

Eksperimen ini disusun secara sistematis melalui beberapa tahapan utama:
1. **Pengumpulan & Pengenalan Data (*Data Collecting*):** Memuat dataset dari berkas CSV, memeriksa dimensi, tipe data, serta memastikan pengaturan *encoding* yang sesuai.
2. **Prapemrosesan Data (*Data Processing*):** 
   * Pembersihan nilai kosong (*missing values* / `NaN`).
   * Seleksi fitur independen (`Age`, `Hours`) dan variabel target (`GADE`).
   * Transformasi label target berbentuk teks menjadi format numerik biner (`0` dan `1`).
3. **Pembagian Data (*Data Splitting*):** Membagi dataset menjadi data pelatihan (80%) dan data pengujian (20%) menggunakan fungsi `train_test_split` dengan parameter `random_state=42`.
4. **Pemodelan & Evaluasi (*Model Training & Evaluation*):**
   * Melatih model klasifikasi menggunakan algoritma *Decision Tree* dan *Random Forest*.
   * Menguji performa model berdasarkan metrik *Accuracy*, *Confusion Matrix*, dan *Classification Report* (*Precision*, *Recall*, *F1-Score*).
   * Menganalisis tingkat kepentingan fitur (*Feature Importance*).
