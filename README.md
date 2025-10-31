Fruits-360 Classifier

Deskripsi Umum
Aplikasi Machine Learning untuk mengklasifikasi 131 jenis buah menggunakan metode Deep Learning berbasis Convolutional Neural Network (CNN).

Fitur Utama

Arsitektur CNN dikembangkan dari awal menggunakan TensorFlow/Keras.

Antarmuka web interaktif berbasis Gradio yang mudah digunakan.

Klasifikasi hingga 131 jenis buah.

Penggunaan sederhana: unggah gambar untuk memperoleh hasil prediksi.

Akurasi tinggi (97–99%).

Kategori yang Didukung
Model dilatih untuk mengenali berbagai jenis buah, antara lain:
Apple (Braeburn, Golden, Granny Smith, dll.)
Banana
Orange
Strawberry
Mango
Pineapple
Grape (berbagai varian)
Dan lebih dari 120 jenis buah lainnya.

Panduan Menjalankan Proyek

Menggunakan Antarmuka Web (Direkomendasikan)
Jalankan perintah:
python app.py
Aplikasi akan terbuka otomatis di browser pada alamat:
http://127.0.0.1:7860

Fitur UI:

Unggah gambar dengan drag & drop atau klik.

Prediksi kategori buah muncul otomatis.

Menampilkan probabilitas lima kategori teratas.

Tampilan bersih dan responsif.

Panduan lengkap: JALANKAN_UI.md

Menjalankan Melalui Command Line

a. Instalasi Dependensi
pip install -r requirements.txt
Pastikan dataset Fruits-360 telah diunduh dan diekstraksi dari Kaggle.

b. Melatih Model
python train_model.py
Output:

fruits_classifier_model.h5 (model terlatih)

training_history.png (grafik akurasi dan loss)
Waktu pelatihan: 15–30 menit (CPU) atau 5–10 menit (GPU).

c. Prediksi Gambar Baru
python predict.py --image "path/to/your/image.jpg"

Atau gunakan kode Python berikut:
from predict import predict_fruit, load_model_and_class_names
model, class_names = load_model_and_class_names()
predicted_class, confidence = predict_fruit('sample_images/test_apple.jpg', model, class_names)
print(f"Prediksi: {predicted_class}, Keyakinan: {confidence:.2f}%")

Struktur Direktori

FruitsClassifier/
├── fruits-360/ (Dataset Training & Test)
├── sample_images/ (Contoh gambar uji)
├── requirements.txt (Dependensi Python)
│
├── app.py (Antarmuka Web)
├── train_model.py (Pelatihan model CNN)
├── predict.py (Prediksi gambar)
│
├── README.md (Dokumentasi utama)
├── JALANKAN_UI.md (Panduan UI lengkap)
└── outputs/ (Hasil pelatihan dan prediksi)
├── fruits_classifier_model.h5
└── training_history.png

Hasil Pelatihan
Akurasi Training: ±99%
Akurasi Validation: ±98%
Ukuran Model: ±15 MB

Catatan Penting

Pastikan folder fruits-360/ berada di direktori utama proyek.

Struktur dataset harus memiliki folder Training/ dan Test/.

Ukuran input gambar: 100x100 piksel.

Data augmentation tidak digunakan secara default karena dataset sudah cukup bervariasi.

Pemecahan Masalah (Troubleshooting)
Error: No module named 'tensorflow'
Solusi: pip install tensorflow

Error: Directory not found saat training
Solusi: Pastikan path dataset pada train_model.py sudah benar.

RAM tidak cukup (Out of Memory)
Solusi: Kurangi batch_size dari 32 menjadi 16 atau 8.

Contoh Hasil Prediksi
Gambar: sample_images/test_apple.jpg
Prediksi: Apple Braeburn
Keyakinan: 99.87%

Probabilitas Teratas:

Apple Braeburn - 99.87%

Apple Crimson Snow - 0.09%

Apple Red 1 - 0.02%

Pomegranate - 0.01%

Tomato - 0.01%

Kontribusi
Kontribusi sangat terbuka. Silakan ajukan pull request atau issue untuk saran dan perbaikan.

Lisensi
Proyek ini menggunakan MIT License.

Informasi Tambahan
Proyek ini dibuat untuk tujuan edukasi dalam bidang Computer Vision menggunakan CNN.

Referensi:

Dataset: Fruits-360 (Kaggle)

Framework: TensorFlow / Keras

UI Framework: Gradio

Jika proyek ini bermanfaat, silakan beri star pada repository GitHub sebagai bentuk dukungan.
