🍎 Fruits-360 Classifier 🥝
Aplikasi Machine Learning untuk mengklasifikasi 131 jenis buah-buahan menggunakan Deep Learning (Convolutional Neural Network - CNN).

🎯 Fitur Utama
🤖 Model CNN Klasik - Arsitektur CNN yang dibangun dari awal dengan TensorFlow/Keras. 🎨 Modern UI - Interface web interaktif yang dibuat dengan Gradio. 📊 131 Kategori - Mampu mengenali berbagai jenis buah, mulai dari Apel hingga Tomat Ceri. 🚀 Mudah Digunakan - Cukup upload gambar buah dan dapatkan prediksi secara instan. 📈 Sangat Akurat - Akurasi mencapai 97-99% berkat dataset yang bersih dan terstruktur.

📦 Kategori yang Diklasifikasi
Model ini dilatih untuk mengenali 131 kategori buah yang berbeda, di antaranya:

Apple (beberapa varian: Braeburn, Golden, Granny Smith, dll.)

Banana

Orange

Strawberry

Mango

Pineapple

Grape (beberapa varian)

... dan 120+ jenis buah lainnya!

🚀 Cara Menjalankan Proyek
⭐ CARA TERMUDAH: Gunakan UI Modern

Langsung jalankan aplikasi web interaktif dengan satu perintah:

Bash

python app.py
Browser akan otomatis terbuka di alamat http://127.0.0.1:7860.

Fitur UI:

Upload gambar dengan drag & drop atau klik.

Prediksi kategori buah ditampilkan secara otomatis.

Lihat probabilitas untuk 5 kategori teratas.

Interface yang bersih dan responsif.

📖 Lihat JALANKAN_UI.md untuk panduan lengkap.

📊 Langkah Alternatif (Command Line)

Langkah 1: Install Dependencies

Bash

pip install -r requirements.txt
Pastikan Anda sudah mengunduh dan mengekstrak dataset Fruits-360 dari Kaggle.

Langkah 2: Melatih Model

Jalankan skrip untuk melatih model CNN dari awal.

Bash

python train_model.py
Output yang dihasilkan:

fruits_classifier_model.h5 - File model Keras yang sudah dilatih.

training_history.png - Grafik akurasi dan loss selama pelatihan.

Waktu pelatihan: ~15-30 menit di CPU / 5-10 menit dengan GPU.

Langkah 3: Uji Prediksi via Command Line

Gunakan model yang sudah dilatih untuk memprediksi gambar baru.

Bash

python predict.py --image "path/to/your/image.jpg"
Atau gunakan fungsi prediksi secara manual di dalam skrip Python:

Python

from predict import predict_fruit, load_model_and_class_names

model, class_names = load_model_and_class_names()

# Prediksi satu gambar
predicted_class, confidence = predict_fruit(
    'sample_images/test_apple.jpg',
    model,
    class_names
)
print(f"Prediksi: {predicted_class}, Keyakinan: {confidence:.2f}%")
📁 Struktur File
FruitsClassifier/
├── fruits-360/          # Folder dataset (Training & Test)
├── sample_images/       # Contoh gambar untuk prediksi
├── requirements.txt     # Dependencies Python
│
├── app.py               # 🚀 UI Modern dengan Gradio
├── train_model.py       # Skrip untuk melatih model CNN
├── predict.py           # Skrip untuk melakukan prediksi
│
├── README.md            # Dokumentasi ini
├── JALANKAN_UI.md       # Panduan lengkap UI
└── outputs/             # Hasil dari eksekusi skrip
    ├── fruits_classifier_model.h5
    └── training_history.png
🎯 Hasil yang Diharapkan
Akurasi Training: ~99%

Akurasi Validation: ~98%

Model Size: ~15MB (CNN Sederhana)

📝 Catatan Penting
Pastikan folder dataset fruits-360/ berada di direktori utama proyek.

Struktur dataset harus berisi folder Training dan Test, yang masing-masing berisi subfolder per kategori buah.

Model menggunakan ukuran input gambar 100x100 piksel.

Data augmentation tidak digunakan secara default karena dataset sudah cukup bervariasi dalam hal rotasi.

🔧 Troubleshooting
Error: "No module named 'tensorflow'"

Bash

pip install tensorflow
Error: "Directory not found" saat training Pastikan path ke folder fruits-360/Training dan fruits-360/Test di dalam train_model.py sudah benar.

RAM tidak cukup (Out of Memory) Kurangi batch_size di train_model.py dari 32 menjadi 16 atau 8.

📊 Contoh Output
📸 Gambar: sample_images/test_apple.jpg 🎯 Prediksi: Apple Braeburn 📊 Keyakinan: 99.87%

Probabilitas Top 5:

Apple Braeburn: 99.87%

Apple Crimson Snow: 0.09%

Apple Red 1: 0.02%

Pomegranate: 0.01%

Tomato: 0.01%

🤝 Contributing
Kontribusi sangat diterima! Silakan buat pull request atau open issue untuk saran dan perbaikan.

📄 License
Proyek ini menggunakan MIT License.

👨‍💻 Author
Proyek ini dibuat untuk tujuan edukasi dalam bidang Computer Vision menggunakan CNN.

📚 Referensi
Dataset: Fruits 360 on Kaggle

Framework: TensorFlow/Keras

UI Framework: Gradio

⭐ Star History
Jika proyek ini membantu Anda belajar, jangan lupa berikan ⭐ di repository GitHub!
