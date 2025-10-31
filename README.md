# Fruits-360 Classifier

Aplikasi Machine Learning ini dirancang untuk melakukan **klasifikasi terhadap 131 jenis buah** menggunakan pendekatan **Deep Learning berbasis Convolutional Neural Network (CNN)**.

---

## 🧠 Ringkasan
Proyek ini menyiapkan model CNN sederhana yang dilatih pada dataset **Fruits-360** untuk mengenali 131 kategori buah. Cocok untuk demo, pembelajaran *Computer Vision*, dan integrasi cepat lewat *Gradio UI*.

---

## 🚀 Fitur Utama
- **Model CNN Klasik** — Arsitektur dibangun dari awal menggunakan TensorFlow / Keras.
- **Antarmuka Modern** — Web UI interaktif berbasis Gradio (unggah gambar, lihat lima prediksi teratas).
- **Klasifikasi Luas (131 Kategori)** — Dari apel hingga tomat ceri.
- **Kemudahan Penggunaan** — Unggah gambar dan dapatkan hasil instan.
- **Akurasi Tinggi** — 97–99%, didukung dataset bersih dan terstruktur.

---

## 🍎 Kategori Buah yang Dikenali
Model mengenali lebih dari 131 kategori buah, termasuk:
- Apple (Braeburn, Golden, Granny Smith, Crimson Snow, dll.)
- Banana
- Orange
- Strawberry
- Mango
- Pineapple
- Grape (berbagai varian)
- Tomato Cherry
- dan lebih dari 120 jenis lainnya.

---

## ⚙️ Panduan Menjalankan Proyek

### 1️⃣ Menggunakan Antarmuka Web *(Direkomendasikan)*
```bash
python app.py
```
Setelah dijalankan, aplikasi akan terbuka otomatis di browser:
```
http://127.0.0.1:7860
```
**Fitur Web UI:**
- Unggah gambar dengan *drag & drop* atau klik.
- Menampilkan lima probabilitas teratas.
- Tampilan bersih, modern, dan responsif.

Panduan lengkap tersedia di **JALANKAN_UI.md**.

### 2️⃣ Menjalankan via Command Line
**Instal dependensi:**
```bash
pip install -r requirements.txt
```
**Latih model:**
```bash
python train_model.py
```
Hasil:
```
fruits_classifier_model.h5
training_history.png
```
**Prediksi gambar:**
```bash
python predict.py --image "path/to/image.jpg"
```
Atau secara manual:
```python
from predict import predict_fruit, load_model_and_class_names

model, class_names = load_model_and_class_names()
predicted_class, confidence = predict_fruit('sample_images/test_apple.jpg', model, class_names)

print(f"Prediksi: {predicted_class}, Keyakinan: {confidence:.2f}%")
```

---

## 📁 Struktur Direktori
```
FruitsClassifier/
├── fruits-360/              # Dataset (Training & Test)
├── sample_images/           # Contoh gambar uji
├── requirements.txt         # Dependensi Python
├── app.py                   # Antarmuka Web (Gradio)
├── train_model.py           # Skrip pelatihan model CNN
├── predict.py               # Skrip prediksi gambar
├── README.md                # Dokumentasi utama
├── JALANKAN_UI.md           # Panduan UI lengkap
└── outputs/                 # Hasil pelatihan & prediksi
    ├── fruits_classifier_model.h5
    └── training_history.png
```

---

## 📊 Hasil Pelatihan
| Metric | Nilai (±) |
|:--|:--:|
| Akurasi Training | 99% |
| Akurasi Validation | 98% |
| Ukuran Model | ~15 MB |

---

## 🧾 Contoh Hasil Prediksi
**Gambar:** `sample_images/test_apple.jpg`
```
Prediksi: Apple Braeburn
Keyakinan: 99.87%

Top-5 Probabilities:
Apple Braeburn        99.87%
Apple Crimson Snow     0.09%
Apple Red 1            0.02%
Pomegranate            0.01%
Tomato                 0.01%
```

---

## 🧩 Pemecahan Masalah
- **Error:** `No module named 'tensorflow'`
  → Jalankan `pip install tensorflow`
- **Error:** *Directory not found* saat pelatihan
  → Periksa path dataset di `train_model.py`
- **Masalah RAM (Out of Memory)**
  → Ubah `batch_size` dari 32 → 16 atau 8.

---

## 🤝 Kontribusi & Lisensi
Kontribusi terbuka. Silakan ajukan *pull request* atau *issue* untuk perbaikan.

Lisensi: **[MIT License](LICENSE)**

---

## 📚 Informasi Tambahan
Proyek ini dikembangkan untuk tujuan edukasi di bidang **Computer Vision** dengan penerapan **CNN (Convolutional Neural Network)**.

**Referensi:**
- Dataset: [Fruits-360 (Kaggle)](https://www.kaggle.com/moltean/fruits)
- Framework: TensorFlow / Keras
- Antarmuka: Gradio

Jika proyek ini bermanfaat, mohon beri ⭐ di repositori GitHub Anda!
