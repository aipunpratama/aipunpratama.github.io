---
layout: post
date: 2025-09-01
author: "Kelompok 4 - Sistem Informasi 2023"
title: "Skenario Uji, Kasus Uji, dan Laporan Bug"
categories: [Software Development, Quality Assurance]
description: Panduan praktis untuk membedakan Skenario Uji (apa yang diuji), Kasus Uji (cara mengujinya), dan Laporan Bug (cara melaporkan temuan) agar proses QA lebih terstruktur.
tags: [Test Scenario, Test Case, Bug Report, QA, Quality Assurance, Testing]
image: /assets/test-scenario-test-case-and-bug-report.png
---

# Skenario Uji, Kasus Uji, dan Laporan Bug

Tiga artefak ini—test scenario, test case, dan bug report—adalah fondasi pengujian perangkat lunak. Ketiganya saling menyambung untuk memastikan aplikasi bekerja sesuai ekspektasi dan bebas dari cacat kritis.

> Tujuan utama: Memastikan aplikasi berfungsi sesuai harapan dengan mendefinisikan apa yang diuji (Scenario), bagaimana mengujinya (Case), serta cara melaporkan masalah secara jelas (Bug Report).

---

## Test Scenario vs Test Case

Perbedaan utamanya terletak pada pertanyaan yang dijawab masing-masing artefak.

### Test Scenario: Apa yang diuji?
- Definisi: Gambaran tingkat tinggi tentang area/fungsi yang akan diuji untuk memvalidasi kebutuhan dari sudut pandang pengguna, biasanya bersifat end-to-end.
- Komponen inti:
  - ID Skenario: Penanda unik.
  - Deskripsi: Ringkasan tujuan skenario.
  - Modul/Fitur: Area aplikasi yang dicakup.

### Test Case: Bagaimana pengujiannya?
- Definisi: Rangkaian langkah detail untuk mengeksekusi pengujian, termasuk input, kondisi awal, dan hasil yang diharapkan.
- Komponen inti:
  - ID Test Case: Penanda unik.
  - Deskripsi: Ringkasan singkat maksud pengujian.
  - Precondition: Kondisi awal yang harus dipenuhi.
  - Test Steps: Langkah-langkah rinci eksekusi.
  - Test Data: Data yang digunakan selama uji.
  - Expected Result: Hasil yang seharusnya muncul.
  - Actual Result: Hasil nyata saat eksekusi.
  - Status: Pass/Fail (atau status lain yang relevan).

---

## Bug Report: Laporan Resmi Temuan Cacat

Ketika Actual Result tidak sesuai dengan Expected Result pada sebuah test case, QA membuat Bug Report untuk dikomunikasikan kepada developer. Laporan ini menjelaskan detail masalah dan langkah reproduksinya.

Dua atribut penting dalam bug report: Severity dan Priority.

### Bug Severity: Dampak terhadap sistem
Menggambarkan seberapa parah pengaruh bug ke fungsionalitas.
- Critical: Mengakibatkan kegagalan total, hilangnya data, atau ketidaktersediaan fungsi vital.
- Major (High): Fitur utama tidak bekerja benar, walau sistem tidak sepenuhnya crash.
- Minor (Medium): Gangguan non-kritis yang mengurangi kenyamanan, namun fungsi inti tetap berjalan.
- Low: Masalah kosmetik atau gangguan kecil tanpa dampak berarti.

### Bug Priority: Urgensi perbaikan
Menentukan seberapa cepat bug harus ditangani, biasanya terkait dampak bisnis.
- P1 (Urgent/Critical): Harus diperbaiki segera.
- P2 (High): Penting dan memengaruhi banyak pengguna; segera ditangani namun tidak segenting P1.
- P3 (Medium): Dapat dijadwalkan pada rilis berikutnya; tidak menyentuh fungsi inti.
- P4 (Low): Perbaikan minor/kosmetik; fleksibel waktunya.

### Komponen utama dalam Bug Report
Laporan bug yang efektif umumnya mencakup:
- Bug Title dan Bug ID
- Steps to Reproduce (langkah reproduksi)
- Actual Result (hasil nyata)
- Expected Result (hasil yang diharapkan)
- Severity dan Priority
- Assignee (developer penanggung jawab) dan Reporter (pelapor/QA)
- Informasi lingkungan: Build Number, platform pengujian (mis. Android/iOS, browser/OS)

---

## Praktik untuk Meminimalkan Bug

Mencegah bug adalah upaya lintas tahapan SDLC, bukan hanya tugas saat testing.

- Pahami Kebutuhan: Seluruh tim harus memiliki pemahaman yang sama terhadap requirement.
- Unit Testing: Deteksi kesalahan lebih dini di level kode.
- Code Review: Perspektif kedua membantu menemukan celah yang luput.
- Test Plan yang Jelas: Rencana pengujian komprehensif sebagai kompas eksekusi.
- Otomasi Pengujian: Percepat deteksi regresi dan uji berulang.
- Kolaborasi yang Baik: Komunikasi aktif antara developer, QA, dan stakeholder.

---

## Kesimpulan

Test Scenario menjawab “apa yang diuji”, Test Case menerjemahkannya menjadi “bagaimana mengujinya”, dan Bug Report menjadi sarana komunikasi formal ketika terjadi penyimpangan hasil.

> Pesan utama: Penguasaan penyusunan skenario uji, kasus uji, dan laporan bug yang baik akan meningkatkan kualitas rilis, menekan risiko di produksi, serta memastikan kesesuaian dengan kebutuhan pengguna.

---

## Referensi

Konten dirangkum dari presentasi “Test Scenario, Test Case, dan Bug Report” oleh Kelompok 4 - Sistem Informasi 2023. Materi lengkap dapat diakses di:

[Presentasi (PPT)](https://drive.google.com/file/d/1er2wwoA69y6OFqgGZCR4S9YeQEx0rM6z/view?usp=drive_link)