---
layout: post
date: 2025-09-01
author: "Kelompok 3 - Sistem Informasi 2023"
title: "Rencana Pengujian (Test Plan)"
categories: [Software Development, Quality Assurance]
description: Uraian terstruktur tentang Test Plan:tujuan, manfaat, serta 19 komponen pokok berdasarkan IEEE 829 untuk memastikan pengujian yang sistematis dan terukur.
tags: [Software Testing, Test Plan, QA, Quality Assurance, SDLC]
image: /assets/testing-plan.png
---

# Rencana Pengujian (Test Plan)

Test Plan (Rencana Pengujian) adalah dokumen acuan resmi yang menjelaskan cara pengujian perangkat lunak akan direncanakan, dijalankan, dan dikendalikan. Dokumen ini menjadi panduan kerja tim QA agar aktivitas pengujian konsisten, fokus, dan mudah diaudit.

Di dalamnya mencakup ruang lingkup uji, pendekatan/metodologi, sumber daya (tim, alat, data uji), serta jadwal dan tonggak kegiatan.

> Tujuan inti: Memberikan arah yang jelas tentang apa yang diuji, bagaimana mengujinya, dan bagaimana memanfaatkan waktu, biaya, serta tenaga secara optimal demi mencapai kualitas yang dapat diterima pengguna.

---

## Mengapa Test Plan Penting (Tujuan)

Menyusun Test Plan yang solid membantu proyek tetap terkendali dan transparan.

- Kejelasan ruang lingkup dan pendekatan: Menjabarkan apa yang masuk/keluar cakupan dan strategi uji yang dipilih.
- Menjamin kualitas: Memaksimalkan temuan cacat secara dini sehingga kualitas produk sesuai ekspektasi.
- Optimalisasi sumber daya: Mengalokasikan waktu, biaya, dan personel secara efisien.
- Dokumentasi formal: Menjadi arsip pengetahuan (knowledge base) untuk evaluasi dan pembelajaran proyek berikutnya.

---

## Komponen Test Plan (Mengacu IEEE 829)

Standar IEEE 829-1988 merekomendasikan butir-butir yang sebaiknya ada dalam dokumen rencana pengujian. Berikut ringkasannya.

### 1) Test Plan Identifier
- Definisi: Kode/penanda unik (termasuk versi) untuk membedakan setiap rencana uji.
- Peran: Memudahkan pelacakan revisi dan referensi lintas proyek/versi.

### 2) References
- Definisi: Daftar dokumen rujukan (SRS, desain, kebijakan, standar).
- Peran: Menjaga keselarasan pengujian dengan kebutuhan dan menjadi landasan saat terjadi perbedaan tafsir.

### 3) Introduction
- Definisi: Ringkasan eksekutif berisi tujuan, cakupan, dan fokus pengujian.
- Peran: Memberi gambaran awal bagi stakeholder sebelum menelaah detail teknis.

### 4) Test Items
- Definisi: Daftar unit, fitur, modul, layanan, atau artefak yang akan diuji (apa saja yang diuji).

### 5) Software Risk Issues
- Definisi: Potensi risiko yang berasal dari produk atau proses pengujiannya.
- Contoh: Fitur kompleks, integrasi pihak ketiga, kebutuhan ambigu, area kode baru.

### 6) Features to be Tested
- Definisi: Fitur/kapabilitas yang akan diuji dari sudut pandang pengguna berikut alasan prioritas/risikonya.

### 7) Features not to be Tested
- Definisi: Fitur yang dikecualikan dari pengujian beserta alasan eksplisitnya.
- Alasan umum: Ditunda rilisnya, stabilitas tinggi, atau risiko rendah yang diterima.

### 8) Approach
- Definisi: Strategi/pedoman utama pengujian.
- Isi: Jenis uji (unit, integrasi, sistem), teknik (black/white/gray-box), metode (manual/otomasi), dan tujuan (fungsi, kinerja, keamanan, dll.).

### 9) Item Pass/Fail Criteria
- Definisi: Kriteria terukur untuk menyatakan suatu item lulus/gagal.
- Contoh Pass: Semua test case kritikal lolos, tanpa defect tingkat kritis, sesuai spesifikasi.
- Contoh Fail: Terdapat test case gagal, ditemukan defect kritis, perilaku menyimpang dari spesifikasi.

### 10) Suspension Criteria & Resumption Requirements
- Suspension: Kondisi penghentian sementara eksekusi (mis. blocker defect).
- Resumption: Syarat untuk melanjutkan (mis. perbaikan diverifikasi dan lingkungan stabil).

### 11) Test Deliverables
- Definisi: Artefak yang dihasilkan selama siklus uji.
- Contoh: Dokumen Test Plan, Test Case/Script, data uji, laporan defect, Test Execution Report, Test Summary Report.

### 12) Remaining Test Tasks
- Definisi: Daftar pekerjaan uji yang belum tuntas pada titik waktu tertentu atau prasyarat sebelum penutupan pengujian.

### 13) Environmental Needs
- Definisi: Konfigurasi lingkungan pengujian.
- Isi: Perangkat keras, perangkat lunak dan versinya, dataset uji, kredensial/akses, alat bantu, pengaturan jaringan, dan dependensi eksternal.

### 14) Staffing and Training Needs
- Definisi: Kebutuhan personel dan peningkatan kompetensi.
- Staffing: Peran (Test Manager, QA Engineer, Automation Engineer, dsb.) dan level keahlian.
- Training: Rencana pelatihan/onboarding, cheat sheet, cross-training.

### 15) Responsibilities
- Definisi: Matriks tanggung jawab yang jelas.
- Isi: Koordinasi, penulisan/eksekusi test case, verifikasi perbaikan, penetapan prioritas, dan pengambilan keputusan.

### 16) Schedule
- Definisi: Linimasa aktivitas uji.
- Isi: Tanggal mulai, periode eksekusi, milestone (review test case, dry run), jadwal re-test/regression, buffer, hingga target sign-off.

### 17) Planning Risks and Contingencies
- Definisi: Risiko pada “proyek pengujiannya” (berbeda dari risiko produk) serta rencana mitigasi/alternatif.
- Contoh: Kekurangan SDM, keterlambatan build dev, keterbatasan lisensi alat—beserta rencana cadangannya.

### 18) Approvals
- Definisi: Otorisasi formal dari pihak terkait.
- Tujuan: Menegaskan kesepakatan atas ruang lingkup, jadwal, dan sumber daya (mis. persetujuan PM, Test Manager).

### 19) Glossary
- Definisi: Daftar istilah, akronim, dan singkatan yang dipakai dalam dokumen beserta penjelasannya.
- Tujuan: Menyamakan pemahaman antar pembaca lintas fungsi.

---

## Penutup

Test Plan merupakan tumpuan disiplin QA. Tanpa rencana yang jelas, pengujian mudah kehilangan arah, boros sumber daya, dan berisiko melewatkan cacat kritis.

> Pesan utama: Susun Test Plan yang komprehensif dengan acuan standar seperti IEEE 829 agar proses pengujian berjalan efisien, terukur, dan efektif dalam menjamin kualitas perangkat lunak.

---

## Referensi

Materi dirangkum dari presentasi “Testing Plan” oleh Kelompok 3 - Sistem Informasi 2023. Unduh presentasi lengkap melalui tautan berikut:
[Presentasi (PPT)](https://drive.google.com/file/d/1Pjx6n08veg7o6P-4LjazQCGOx29xH-YS/view?usp=drive_link)