
# Perbandingan Model ANN setelah dan sebelum Image Preprocessing dan Augmentation untuk Deteksi Pneumonia

Repositori ini berisi notebook Python (`train_comparison.ipynb`) yang membandingkan berbagai strategi pelatihan Convolutional Neural Network (CNN) untuk mendeteksi pneumonia dari citra X-ray dada. Proyek ini menggunakan dataset **Pneumonia-MNIST** yang tersedia melalui `tensorflow_datasets`.

## Daftar Isi

- Deskripsi Dataset
- Pra-pemrosesan Data
- Arsitektur ANN yang digunakan
- Teknik Augmentasi Data
- Strategi Pelatihan:
  - ANN Tanpa preprocessing dan augmentasi
  - ANN Dengan preprocessing dan augmentasi
  - Perbandingan dengan custom CNN
- Evaluasi Model
- Visualisasi Performa
- Simpan dan Muat Model

---

## Dataset

Dataset yang digunakan adalah `pneumonia_mnist`, sebuah subset dari MedMNIST, terdiri dari citra grayscale resolusi rendah (28x28 piksel) yang diklasifikasikan sebagai:
- **0**: Normal
- **1**: Pneumonia

Pembagian data:
- **Training**: 800 data
- **Validasi**: 200 data
- **Testing**: 100 data

---

## Instalasi

Pastikan Python sudah terinstal, lalu pasang pustaka berikut:

```bash
pip install tensorflow tensorflow-datasets matplotlib
```

---

## Cara Menjalankan

1. Buka file `train_comparison.ipynb` di Jupyter Notebook atau VSCode.
2. Jalankan semua sel untuk memproses data, melatih, dan mengevaluasi model.
3. Model terbaik akan disimpan secara otomatis menggunakan `ModelCheckpoint`.

---

## Arsitektur Model

Model ANN yang digunakan terdiri dari:
- Flatten
- Dense
- Fungsi aktivasi ReLU dan sigmoid untuk klasifikasi biner

Tiap eksperimen menggunakan arsitektur yang sama namun berbeda pada bagian preprocessing dan augmentasi.

---

## Strategi Pelatihan

### 1. Tanpa Preprocessing dan Augmentasi  
Model dilatih langsung dengan data asli tanpa teknik preprocessing dan augmentasi.

### 2. Preprocessing
Menambahkan preprocessing seperti:
- Black and White
- Central Crop

### 3. Augmentasi Ringan  
Menambahkan transformasi ringan seperti:
- Flip horizontal
- Translasi kecil
- Zoom kecil

---

## Evaluasi & Visualisasi

Setiap model dievaluasi menggunakan:
- Akurasi dan loss pada data validasi
- Plot kurva akurasi dan loss selama pelatihan

---

## Menyimpan & Memuat Model

Model terbaik dari setiap strategi disimpan dengan format `.h5`. Notebook juga mendukung memuat ulang model tersebut untuk evaluasi atau prediksi lanjutan.

---

## Hasil

Notebook menampilkan perbandingan visual antar model berdasarkan performa akurasi dan loss. Tujuan utamanya adalah menemukan strategi pelatihan terbaik untuk klasifikasi pneumonia yang akurat pada dataset yang kecil.

---
