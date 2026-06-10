---
layout: post
title: "SCARE: Scar Classification and Recognition Engine — AI untuk Deteksi Bekas Luka yang Mudah Diakses"
date: 2026-06-10 09:00:00 +0700
categories: [projects, machine-learning, healthtech]
tags: [deep-learning, medical-ai, explainable-ai, tensorflow, streamlit, computer-vision, public-health]
author: aipunpratama
image: /assets/scare-banner.png
description: "SCARE adalah prototype sistem berbasis AI yang membantu publik dan tenaga kesehatan primer membedakan Keloid dan Hypertrophic Scar melalui foto, lengkap dengan heatmap interpretabilitas."
---

<div align="center">

<a href="https://scare-cc26.streamlit.app" target="_blank">
  <img src="https://img.shields.io/badge/Live_Demo-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Live Demo">
</a>
<a href="https://github.com/Kyyneko/SCARE-CC26" target="_blank">
  <img src="https://img.shields.io/badge/GitHub_Repo-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo">
</a>

<br><br>

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow">
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV">
<img src="https://img.shields.io/badge/Explainable_AI-GradCAM-46B3E6?style=for-the-badge" alt="Grad-CAM">

</div>

---

## 📌 Ringkasan Singkat

SCARE (Scar Classification and Recognition Engine) adalah prototype web app yang memanfaatkan deep learning untuk memberikan second-opinion visual kepada publik (pasien, caregiver, maupun tenaga kesehatan primer). Pengguna dapat mengunggah foto bekas luka, menerima prediksi apakah gambar lebih cenderung *Keloid* atau *Hypertrophic Scar*, serta melihat overlay heatmap (Grad‑CAM) yang menunjukkan area yang berkontribusi pada prediksi.

> Misi kami: membuat alat bantu yang mudah diakses, transparan, dan praktis — membantu masyarakat mendapatkan informasi awal sebelum berkonsultasi dengan tenaga medis resmi.

---

## 🩺 Mengapa Ini Penting?

Secara klinis, Keloid dan Hypertrophic Scar dapat terlihat mirip, terutama pada tahap awal. Kesalahan penanganan (contoh: eksisi bedah pada keloid) bisa memperparah kondisi pasien. Di banyak fasilitas primer dan layanan telemedicine, ketersediaan alat bantu objektif masih terbatas. SCARE dirancang sebagai screening awal yang cepat serta mudah digunakan oleh siapa pun.

---

## 🔧 Fitur Utama

- Prediksi klasifikasi 2 kelas: **Keloid** vs **Hypertrophic Scar**  
- Explainable AI: Grad‑CAM heatmap untuk interpretabilitas visual  
- Pipeline pra‑proses gambar: deteksi blur, cropping fokus luka, normalisasi warna, dan augmentasi  
- Web app responsive untuk unggah gambar dari ponsel & desktop  
- Model tersedia dalam format Keras / .h5 / TensorFlow Lite (opsional) untuk edge deployment

---

## 🧭 Arsitektur & Alur Kerja (High-level)

```
SCARE Workflow
├─ 1) Data Collection & Curation
│   └─ Hapus gambar blur, crop area luka, standardisasi ukuran
├─ 2) Preprocessing & Augmentation
│   └─ Rotation, Flip, Zoom, Color jitter
├─ 3) Model Training (Transfer Learning)
│   └─ EfficientFormer-L1 (fine-tune dari ImageNet)
├─ 4) Evaluation & Validation
│   └─ Confusion matrix, ROC AUC, Precision/Recall
├─ 5) Explainability
│   └─ Grad-CAM heatmap overlay
└─ 6) Web Deployment (Streamlit) → User upload → Inference + Heatmap
```

---

## 🧩 Tech Stack (Inti)

| Lapisan          |                                 Teknologi | Kegunaan                      |
| ---------------- | ----------------------------------------: | ----------------------------- |
| Bahasa           |                                    Python | Eksperimen & produksi model   |
| Deep Learning    |                        TensorFlow / Keras | Training & inference          |
| Backbone         |                        EfficientFormer‑L1 | Transfer learning             |
| Computer Vision  |                             OpenCV, NumPy | Pra‑proses citra & augmentasi |
| Interpretability |                                  Grad‑CAM | Heatmap explainability        |
| Frontend         |                     Streamlit (prototype) | UI upload & visualisasi       |
| Deployment       | Vercel / Render / Hugging Face (opsional) | Hosting web & model API       |

---

## 📊 Hasil Eksperimen (Ringkas)

- Test Accuracy: **87.36%**  
- Test Loss: **0.8986**  
- Precision: **77.35%**  
- ROC AUC: **0.8533**  
- Dataset contoh: 261 train / 86 val / 87 test

> Catatan: Hasil berasal dari uji internal pada dataset proyek. Performa di lapangan bergantung pada kualitas foto (pencahayaan, fokus, sudut).

---

## 🚀 Cara Menjalankan (Reproduksi)

1. Clone repo:
```bash
git clone https://github.com/Kyyneko/SCARE-CC26.git
cd SCARE-CC26
```

2. Buat virtual environment & install:
```bash
python -m venv venv
# Mac/Linux
source venv/bin/activate
pip install -r requirements.txt
```

3. Jalankan demo Streamlit:
```bash
streamlit run streamlit_app.py
```
atau buka demo publik: https://scare-cc26.streamlit.app

---

## 🔒 Privasi & Etika

- Foto yang diunggah hanya digunakan untuk inference; hindari mengunggah informasi identitas sensitif tanpa izin.  
- SCARE adalah alat bantu (decision support), **bukan substitusi diagnosis** profesional. Hasil harus dikonfirmasi oleh tenaga kesehatan berlisensi.  
- Kami mendorong kolaborasi validasi klinis untuk memastikan keselamatan & akurasi sebelum penggunaan skala besar.

---

## 🧭 Rencana Pengembangan Selanjutnya

- Melakukan validasi klinis bersama dokter kulit  
- Menambah dataset multi‑sumber untuk meningkatkan generalisasi  
- Optimisasi model ke TFLite / ONNX untuk integrasi mobile ringan  
- Fitur: histori anonim pengguna, batch inference, dan dashboard analytics

---

## 👥 Tim Pengembang (Coding Camp 2026 — DBS Foundation)

- Mahendra Kirana M.B — Data Science  
- Muh. Aipun Pratama — Data Science (author)  
- Rifqi Alan Maulana — AI Engineer  
- Ahmad Faizur Rahman — AI Engineer  
- Syaebatul Hamdi — Full Stack  
- Umar Faruq Manek — Full Stack

---

## 🔗 Sumber & Akses

- Live Demo: https://scare-cc26.streamlit.app  
- Repo GitHub: https://github.com/Kyyneko/SCARE-CC26  
- Model & artifacts: lihat folder Saved Models di repo atau link drive jika tersedia

---

## ✉️ Ingin Berkolaborasi atau Memberi Masukan?

Kami terbuka untuk:
- Uji coba bersama komunitas/klinik  
- Masukan dari tenaga medis terkait interpretabilitas heatmap  
- Kontribusi dataset atau kode untuk meningkatkan robustness

Silakan buka issue atau pull request di GitHub, atau hubungi via profil GitHub: https://github.com/Kyyneko

---

<sub>Proyek ini merupakan Capstone Project Coding Camp 2026 — tujuan utamanya menghadirkan solusi AI yang mudah diakses oleh masyarakat luas guna membantu deteksi awal masalah kesehatan kulit.</sub>