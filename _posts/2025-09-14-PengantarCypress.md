---
layout: post
date: 2025-09-14
author: "Kelompok 8 - Sistem Informasi 2023"
title: "Pengenalan Cypress"
categories: [Software Development, Quality Assurance, Automation]
description: Ringkasan Cypress sebagai framework E2E modern untuk aplikasi web—mencakup instalasi, perintah inti, kelebihan utama, dan contoh test case.
tags: [Cypress, Automation Testing, E2E Testing, QA, JavaScript, Web Testing]
image: /assets/pengantar-cypress.png
---

# Pengenalan Cypress

Cypress adalah framework end-to-end (E2E) testing modern yang dibuat khusus untuk menguji aplikasi web. Cypress sangat populer untuk aplikasi berbasis framework modern seperti React, Vue, maupun Angular.

Dalam piramida pengujian, Cypress terutama digunakan pada lapisan End-to-End, namun juga andal untuk Integration Testing dan bahkan Component Testing.

> Tujuan utama: Menyediakan alat uji yang cepat, mudah dikonfigurasi, dan stabil untuk memverifikasi aplikasi web dari sudut pandang pengguna akhir.

---

## Kelebihan Cypress

Apa yang membedakan Cypress dari tool otomasi lain (misalnya Selenium)?

- Arsitektur modern: Berjalan langsung di dalam browser (berbagi run loop dengan aplikasi), sehingga interaksi lebih cepat dan deterministik.
- Test Runner interaktif: Anda dapat melihat setiap perintah dieksekusi secara visual dan berinteraksi dengan aplikasi saat tes berlangsung.
- Time Travel: Lihat snapshot dari setiap langkah test untuk mempermudah penelusuran ketika terjadi kegagalan.
- Automatic Waits: Cypress menunggu elemen siap secara otomatis—tanpa perlu `wait`/`sleep` manual—membuat tes lebih stabil dan tidak mudah flaky.

---

## Setup dan Instalasi

Syarat utama: Node.js sudah terpasang.

1) Inisialisasi proyek (bila diperlukan):
```bash
npm init -y
```

2) Pasang Cypress:
```bash
npm install cypress --save-dev
```

3) Buka Test Runner:
```bash
npx cypress open
```
Perintah pertama ini akan membuka Test Runner interaktif dan membuat struktur folder default.

4) Menjalankan tes (mode headless):
```bash
npx cypress run --browser chrome
```

---

## Perintah Dasar Cypress

Sintaks Cypress ringkas dan mudah dibaca.

| Perintah              | Deskripsi                                                         |
| :-------------------- | :---------------------------------------------------------------- |
| `cy.visit('URL')`     | Membuka halaman tertentu di browser.                              |
| `cy.get('selector')`  | Mengambil elemen berdasarkan selector (ID, class, atribut, dsb.). |
| `cy.contains('text')` | Mencari elemen yang menampilkan teks tertentu.                    |
| `cy.click()`          | Melakukan klik pada elemen yang dipilih.                          |
| `cy.type('text')`     | Mengetikkan teks pada input/textarea.                             |
| `cy.url()`            | Mengambil URL aktif untuk diverifikasi.                           |

---

## Studi Kasus: Login SauceDemo

Contoh test case untuk memverifikasi proses login di `saucedemo.com`.

| ID   | Test Case                     | Steps                                                                                                 | Expected Result                                          |
| :--- | :---------------------------- | :---------------------------------------------------------------------------------------------------- | :------------------------------------------------------- |
| TC01 | Login dengan kredensial valid | 1) Buka halaman login<br>2) Username: `standard_user`<br>3) Password: `secret_sauce`<br>4) Klik login | Berpindah ke halaman inventory.                          |
| TC02 | Login dengan password salah   | 1) Buka halaman login<br>2) Username: `standard_user`<br>3) Password: `wrong_pass`<br>4) Klik login   | Muncul pesan error “Username and password do not match”. |
| TC03 | Login dengan username kosong  | 1) Buka halaman login<br>2) Kosongkan username<br>3) Password: `secret_sauce`<br>4) Klik login        | Muncul pesan error “Username is required”.               |

---

## Contoh Penggunaan

Contoh skrip Cypress sederhana untuk menguji login:

```javascript
describe('Login Test', () => {
  it('login berhasil dengan kredensial valid', () => {
    cy.visit('https://saucedemo.com');
    cy.get('input[name="user-name"]').type('standard_user');
    cy.get('input[name="password"]').type('secret_sauce');
    cy.get('input[type="submit"]').click();
    cy.url().should('include', '/inventory.html');
  });
});
```

---

## Sumber Daya Tambahan

- [Dokumentasi Cypress](https://docs.cypress.io)
- [Pencarian Tutorial Cypress di YouTube](https://www.youtube.com/results?search_query=cypress+tutorial)
- [Repositori GitHub Cypress](https://github.com/cypress-io/cypress)

---

## Kesimpulan

Cypress adalah framework testing modern untuk pengujian UI berbasis web secara end-to-end. Dengan instalasi yang sederhana, Test Runner interaktif, fitur Time Travel, dan automatic waits, Cypress membantu menyusun tes yang stabil dan merepresentasikan perilaku pengguna nyata.

> Inti pesan: Cypress meningkatkan kualitas dan keandalan aplikasi web modern melalui struktur tes yang jelas, sintaks intuitif, dan ekosistem yang mendukung produktivitas.

---

## Referensi

Materi dirangkum dari presentasi “Pengantar Cypress” oleh Kelompok 8 - Sistem Informasi 2023. Presentasi (PPT) lengkap tersedia pada tautan berikut:

[Lihat Presentasi (PPT)](https://drive.google.com/file/d/1lBwmTvmXF0iDxCIX0SbTfTBOQ7-eOLOx/view?usp=drive_link)