---
layout: post
title: "SCARE: Scar Classification and Recognition Engine — Accessible AI for Scar Screening"
date: 2026-06-10 09:05:00 +0700
categories: [projects, machine-learning, healthtech]
tags: [deep-learning, medical-ai, tensorflow, computer-vision, public-health]
author: aipunpratama
image: /assets/scare-banner.jpg
description: "SCARE is a web prototype that helps the public differentiate Keloid and Hypertrophic Scars from photos — accessible from any browser."
---

<div align="center">

<a href="https://scare-cc-26-full-stack-front-end.vercel.app/" target="_blank">
  <img src="https://img.shields.io/badge/Live_App-Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Live App">
</a>
<a href="https://github.com/Kyyneko/SCARE-CC26" target="_blank">
  <img src="https://img.shields.io/badge/GitHub_Repo-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo">
</a>

<br><br>

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow">
<img src="https://img.shields.io/badge/EfficientFormer-L1-7C4DFF?style=for-the-badge" alt="EfficientFormer-L1">
<img src="https://img.shields.io/badge/React-TBD-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="React">

</div>

---

## 📌 Quick Summary

SCARE (Scar Classification and Recognition Engine) is a web prototype leveraging deep learning to provide an accessible second opinion for the public — patients, caregivers, and primary health workers — to distinguish between **Keloid** and **Hypertrophic Scar** from photos. The frontend is available at: https://scare-cc-26-full-stack-front-end.vercel.app/

> Goal: provide a fast, easy-to-use screening tool that helps users make informed next steps prior to clinical consultation.

---

## 🩺 Why This Matters

Keloids and hypertrophic scars can look very similar in early stages. Incorrect treatment (e.g., surgery on a keloid) may worsen the condition. Many primary-care settings and telemedicine platforms lack objective visual tools. SCARE aims to fill that gap by offering an easy-to-access screening service to the general public.

---

## 🔧 Main Features

- Two-class prediction: **Keloid** vs **Hypertrophic Scar**  
- Image preprocessing pipeline: blur detection, crop to lesion area, normalization, and augmentation  
- Responsive web app (mobile & desktop) accepting photo uploads from smartphones  
- Model artifacts available in Keras / .h5 (TFLite optional for edge)  
- Note: This project currently does NOT include explainability techniques such as Grad‑CAM — interpretability features are planned for future releases.

---

## 🧭 Architecture & Workflow (High-level)

```
SCARE Workflow
├─ 1) Data Curation (filter blur, crop lesion)
├─ 2) Preprocessing & Augmentation (rotation, flip, zoom, color jitter)
├─ 3) Model Training (Transfer Learning: EfficientFormer‑L1)
├─ 4) Evaluation (Accuracy, Precision, Recall, ROC-AUC)
├─ 5) Model Serving (REST API)
└─ 6) Frontend (React/Vercel) → User upload → Inference → Result
```

---

## 🧩 Core Tech Stack

| Layer           |                  Technology | Purpose                                 |
| --------------- | --------------------------: | --------------------------------------- |
| Language        |                      Python | Experimentation & model training        |
| Deep Learning   |          TensorFlow / Keras | Training & inference                    |
| Backbone        |          EfficientFormer‑L1 | Transfer learning                       |
| Computer Vision |               OpenCV, NumPy | Image preprocessing                     |
| Frontend        |  React (deployed on Vercel) | UI & public hosting                     |
| Backend         | FastAPI / Flask (model API) | Serving model endpoints                 |
| Storage         |     Supabase / Cloud Bucket | Artifacts & optional anonymized history |

---

## 📊 Experimental Results (Summary)

- Test Accuracy: **87.36%**  
- Test Loss: **0.8986**  
- Precision: **77.35%**  
- ROC AUC: **0.8533**  
- Example dataset split: 261 train / 86 val / 87 test

> These results are from internal experiments. Field performance depends on photo quality (lighting, focus, angle).

---

## 🚀 How to Reproduce (Short)

1. Clone repository:
```bash
git clone https://github.com/Kyyneko/SCARE-CC26.git
cd SCARE-CC26
```
2. Follow the repository README for training and serving instructions (notebooks & scripts are included).  
3. To run frontend locally (if developing):
```bash
cd frontend
npm install
npm run dev
```
4. To run the model API (example FastAPI):
```bash
cd api
pip install -r requirements.txt
uvicorn app:app --reload
```

---

## 🔒 Privacy & Ethics

- Uploaded photos are used for inference only. Do not upload sensitive personally-identifiable information.  
- SCARE is a public-facing screening tool, **not a substitute for professional medical diagnosis**. Always consult licensed healthcare providers for medical decisions.  
- We welcome clinical validation partnerships to ensure safety and reliability before large-scale adoption.

---

## 🛠 Roadmap

- Clinical validation with dermatologists  
- Expand dataset diversity to improve generalization  
- Optimize and release TFLite / ONNX models for edge deployment  
- Add interpretability (e.g., Grad‑CAM or other explainability methods)  
- Implement anonymized history and analytics features

---

## 👥 Project Team (Coding Camp 2026 — DBS Foundation)

- Mahendra Kirana M.B — Data Science  
- Muh. Aipun Pratama — Data Science (author)  
- Rifqi Alan Maulana — AI Engineer  
- Ahmad Faizur Rahman — AI Engineer  
- Syaebatul Hamdi — Full Stack  
- Umar Faruq Manek — Full Stack

---

## 🔗 Links & Access

- Live App (frontend): https://scare-cc-26-full-stack-front-end.vercel.app/  
- GitHub Repo: https://github.com/Kyyneko/SCARE-CC26

---

## ✉️ Collaborate or Give Feedback

We are open to:
- Field trials with clinics / community groups  
- Feedback from medical professionals on model validity  
- Contributions to datasets or code for robustness improvements

Create an issue or pull request on GitHub, or contact us via the repository profile: https://github.com/Kyyneko

---

<sub>This project is a Capstone Project from Coding Camp 2026 — the aim is to provide an accessible AI screening tool that helps communities detect potential skin scar issues early.</sub>