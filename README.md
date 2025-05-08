# Klasifikasi Gambar menggunakan CNN dengan Inferensi TFLite

Proyek ini melibatkan pelatihan Jaringan Syaraf Tiruan Konvolusional (CNN) untuk mengklasifikasikan varietas padi. ​​Kumpulan data awalnya berisi 75.000 gambar dan telah dibagi secara manual menjadi set pelatihan, validasi, dan pengujian untuk kinerja yang lebih baik dengan sumber daya yang terbatas.

## Project Overview

- **Dataset**: Dataset terdiri dari gambar dari 5 kelas beras: Arborio, Basmati, Ipsala, Jasmine, dan Karacadag.
- **Data Split**: Data telah direduksi dan dipecah secara manual menjadi:
- **Train**: 2.000 gambar
- **Validation**: 400 gambar
- **Test**: 200 gambar
- **Model Architecture**: Model CNN digunakan untuk mengklasifikasikan gambar.
- **Saved Models**: Model disimpan dalam beberapa format: SavedModel, TFLite, dan TFJS.
- **Inference**: Inferensi dilakukan menggunakan model TFLite, memastikan bahwa gambar yang digunakan dalam inferensi belum menjadi bagian dari dataset pelatihan.

## Setup

Untuk menjalankan proyek ini di Google Colab, ikuti langkah-langkah berikut:

### 1. Buka Google Colab

Kunjungi [Google Colab](https://colab.research.google.com/) dan buat notebook baru atau buka notebook yang sudah ada yaitu notebook.ipynb.

### 2. Unggah File `requirements.txt`

Pastikan file `requirements.txt` ada di folder proyek ini. Unggah file tersebut ke Colab dengan cara klik ikon folder di sebelah kiri, lalu pilih tombol "Upload" untuk mengunggah file `requirements.txt`.

### 3. Install Dependensi

Setelah mengunggah file `requirements.txt`, jalankan perintah berikut di sel notebook Colab untuk menginstall semua dependensi yang diperlukan:

```python
!pip install -r '/content/requirements.txt'
```

### 4. Jalankan Kode

Setelah dependensi terinstall, Anda dapat menjalankan kode lainnya di notebook sesuai kebutuhan.

## Usage

### 1. Training the Model

Model ini dilatih menggunakan gambar dari direktori `train` dan `val`. Pelatihan ini mencakup early stopping untuk menghindari overfitting.

### 2. Saving the Model

Model yang dilatih disimpan dalam beberapa format:

- **SavedModel**: Untuk memuat model dalam TensorFlow.
- **TFLite**: Untuk diterapkan pada perangkat seluler atau edge.
- **TFJS**: Untuk diterapkan di web.

### 3. Inferensi menggunakan TFLite

Untuk inferensi, model dimuat dalam format TFLite dan dijalankan pada gambar baru yang tidak digunakan selama pelatihan. Gambar diproses terlebih dahulu, dan model memprediksi kelasnya.

## Kesimpulan

Proyek ini menunjukkan cara melatih model CNN untuk klasifikasi varietas padi dan menerapkan model dalam berbagai format untuk berbagai kasus penggunaan (TensorFlow, TFLite, TFJS). Model dievaluasi menggunakan data uji terpisah yang belum pernah digunakan dalam pelatihan, untuk memastikan integritas prediksi.

## References

- TensorFlow Documentation: https://www.tensorflow.org
- TFLite Documentation: https://www.tensorflow.org/lite
