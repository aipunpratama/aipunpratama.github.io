---
layout: post
date: 2025-09-07
author: "Kelompok 5 - Sistem Informasi 2023"
title: "Pengenalan Unit Testing"
categories: [Software Development, Quality Assurance]
description: Ringkasan pengantar unit testing:konsep dasar, urgensinya, pola AAA (Arrange–Act–Assert), serta framework populer seperti JUnit, Jest, dan Pytest.
tags: [Unit Testing, SDLC, Testing, QA, JUnit, Jest, Pytest, AAA]
image: /assets/pengantar-unit-testing.png
---

# Pengenalan Unit Testing

> Ingin menulis kode tanpa waswas soal bug? Mulailah dari unit testing.

Unit testing adalah pengujian pada unit terkecil dari perangkat lunak—seperti function, method, atau class—secara terisolasi. Biasanya ini merupakan lapisan pengujian paling awal yang dijalankan developer sebelum integration test atau end-to-end test, dengan tujuan memastikan tiap komponen bekerja benar tanpa ketergantungan pada bagian sistem lain.

Dalam piramida pengujian, unit test berada di dasar: paling cepat, paling murah, dan idealnya jumlahnya paling banyak.

---

## Analogi Unit Testing

Bayangkan proses merakit mobil. Sebelum seluruh mobil dirakit, komponen penting—mesin, rem, ban—diuji terpisah. Prinsipnya sama pada perangkat lunak: uji setiap “komponen” (fungsi/metode) secara individual. Jika setiap bagian lulus uji, kita lebih percaya diri terhadap kualitas keseluruhan “mobil” (aplikasi).

---

## Mengapa Unit Testing Penting?

Unit testing meningkatkan reliabilitas, kualitas, dan kemudahan perawatan kode. Manfaat utamanya antara lain:

- Deteksi dini bug: Masalah di level fungsi lebih mudah dilacak dan diperbaiki dibanding setelah sistem terintegrasi.
- Dokumentasi hidup: Test menggambarkan cara penggunaan fungsi yang benar, layaknya contoh yang dapat dieksekusi.
- Mendukung perubahan dan refactoring: Jaring pengaman test memberi kepercayaan saat memodifikasi atau merapikan kode.
- Kualitas desain lebih baik: Menulis test mendorong arsitektur yang modular dan mudah diuji (testable).
- Efisiensi waktu dan biaya: Memperbaiki sejak awal jauh lebih murah ketimbang setelah rilis.
- Kepercayaan diri pengembang: Rilis fitur baru lebih tenang karena dilindungi serangkaian unit test.

---

## Pola Dasar AAA (Arrange, Act, Assert)

Pola AAA memecah sebuah test menjadi tiga bagian jelas:

1. Arrange (Siapkan): Tetapkan kondisi awal dan data yang diperlukan (inisialisasi objek/variabel).
2. Act (Jalankan): Panggil satu fungsi/metode yang menjadi objek pengujian.
3. Assert (Verifikasi): Pastikan hasil aktual sesuai ekspektasi.

---

## Framework Populer

Berikut tiga framework umum di ekosistemnya masing-masing:

### 1) JUnit 5 (Java)
- Deskripsi: Framework de facto di ekosistem Java/JVM (termasuk Kotlin).
- Keunggulan: Integrasi kuat dengan tooling Java, ekosistem matang, serta anotasi (@Test) yang eksplisit dan rapi.

### 2) Jest (JavaScript)
- Deskripsi: Framework dari Meta yang populer untuk React, Node.js, dan TypeScript.
- Keunggulan: Zero-config, “batteries-included” (sudah ada assertion dan mocking), mendukung snapshot testing.

### 3) Pytest (Python)
- Deskripsi: Sederhana namun sangat bertenaga, cocok untuk berbagai tipe proyek Python (web, data, API).
- Keunggulan: Sintaks ringkas (minim boilerplate), fixtures yang fleksibel, dan pelaporan error yang informatif.

---

## Contoh Sederhana

Contoh unit test dengan JUnit untuk menguji fungsi penjumlahan:

```java
import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class CalculatorTest {

    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "hasil 2 + 3 harus 5");
    }
}
```

---

## Sumber Belajar

- [Dokumentasi JUnit](https://junit.org/junit5/docs/current/user-guide/)
- [Dokumentasi Jest](https://jestjs.io/docs/getting-started)
- [Dokumentasi Pytest](https://docs.pytest.org/en/stable/)

---

## Kesimpulan

Unit testing adalah fondasi kualitas—bukan sekadar mencari bug, tetapi membangun kode yang andal, mudah dipelihara, dan tahan lama. Mengadopsi pola yang tepat (mis. AAA) dan memilih framework sesuai ekosistem akan menjadi investasi awal yang menghemat banyak waktu, biaya, dan stres di masa depan.

---

## Referensi

Materi diringkas dari presentasi “Pengantar Unit Testing” oleh Kelompok 5 - Sistem Informasi 2023. Presentasi (PPT) lengkap dapat diakses di:

[Lihat Presentasi (PPT)](https://drive.google.com/file/d/1qSDpXubcQlTiRXuM2tdDO30rPo-3GkCS/view?usp=drive_link)