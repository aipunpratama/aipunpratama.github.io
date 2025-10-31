---
layout: post
date: 2025-09-14
author: "Kelompok 7 - Sistem Informasi 2023"
title: "Pengenalan Selenium WebDriver"
categories: [Software Development, Quality Assurance, Automation]
description: Ringkasan Selenium WebDriver—alat otomasi browser open‑source untuk pengujian aplikasi web, keunggulannya, serta contoh skenario dan test case praktis.
tags: [Selenium, WebDriver, Automation Testing, QA, Python, Java, Web Testing]
image: /assets/pengantar-selenium-webdriver.png
---

# Pengenalan Selenium WebDriver

Selenium adalah framework otomasi browser open‑source yang populer untuk menguji aplikasi web dengan menirukan interaksi pengguna pada berbagai browser seperti Chrome, Firefox, Edge, dan Safari.

> Tujuan utama: Mengotomatiskan pengujian fungsional aplikasi web lintas browser dan platform, sehingga memastikan perilaku aplikasi sesuai harapan.

---

## Apa itu Selenium WebDriver?

WebDriver adalah inti API Selenium yang bertindak sebagai penghubung antara kode uji (misalnya ditulis dengan Python atau Java) dan browser. Melalui WebDriver, skrip uji dapat:

- Membuka halaman web
- Mengklik tombol atau tautan
- Mengisi formulir (input teks)
- Melakukan navigasi (back, forward, refresh)
- Membaca dan memverifikasi konten halaman

---

## Mengapa Memilih Selenium?

Beberapa alasan Selenium menjadi standar industri untuk otomasi web:

- Open‑source dan gratis: Tidak memerlukan lisensi.
- Multi‑bahasa: Mendukung Python, Java, C#, JavaScript, dan lainnya.
- Multi‑platform: Berjalan di Windows, macOS, dan Linux.
- Multi‑browser: Kompatibel dengan browser modern utama (Chrome, Firefox, Safari, Edge).
- Mudah diintegrasikan: Bekerja baik dengan Pytest, JUnit, TestNG untuk pelaporan dan manajemen uji.
- Komunitas besar: Dokumentasi lengkap dan ekosistem yang matang memudahkan pemecahan masalah.

---

## Langkah Dasar Berinteraksi dengan Selenium

Tiga fondasi untuk mulai mengotomasi pengujian dengan Selenium:

1) Instalasi
- Pasang pustaka Selenium untuk bahasa yang dipakai (contoh Python):
  ```bash
  pip install selenium
  ```

2) Membuka browser
- Inisialisasi WebDriver dan arahkan ke URL target.

3) Berinteraksi dengan elemen
- Temukan elemen HTML (tombol, input, tautan) menggunakan locator yang tepat, lalu lakukan aksi yang diinginkan.

Tips:
- Gunakan locator yang stabil (By.ID, By.NAME, By.CSS_SELECTOR, By.XPATH).
- Manfaatkan eksplisit wait untuk elemen dinamis agar tes lebih andal.

---

## Contoh Skenario dan Test Case

Studi kasus: Pengujian login di situs SauceDemo.

### Test Scenario (Apa yang diuji)
- TS‑001: Login berhasil di SauceDemo.
- TS‑002: Login gagal dengan kredensial tidak valid.
- TS‑003: Menambah produk ke keranjang setelah login sukses.

### Test Case (Bagaimana mengujinya)

| ID     | Deskripsi             | Steps                                                                                                     | Expected Result                                                   |
| :----- | :-------------------- | :-------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------- |
| TC‑001 | Login sukses          | 1) Buka halaman login<br>2) Username: `standard_user`<br>3) Password: `secret_sauce`<br>4) Klik Login     | Dialihkan ke halaman inventory.                                   |
| TC‑002 | Login gagal           | 1) Buka halaman login<br>2) Username: `user_salah`<br>3) Password: `secret_sauce`<br>4) Klik Login        | Tetap di halaman login dan muncul pesan error terkait kredensial. |
| TC‑003 | Tambah produk ke cart | 1) Jalankan TC‑001 (login sukses)<br>2) Pada halaman inventory, klik “Add to cart” pada salah satu produk | Badge keranjang bertambah menjadi 1.                              |

---

## Contoh Kode (Python, Selenium 4)

Berikut contoh sederhana pengujian login menggunakan Selenium WebDriver dengan locator modern:

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Inisialisasi WebDriver (Selenium 4.6+ memiliki Selenium Manager untuk mengelola driver)
driver = webdriver.Chrome()
driver.implicitly_wait(5)

try:
    # Buka halaman
    driver.get("https://saucedemo.com")

    # Isi form login
    driver.find_element(By.NAME, "user-name").send_keys("standard_user")
    driver.find_element(By.NAME, "password").send_keys("secret_sauce")
    driver.find_element(By.CSS_SELECTOR, "input[type='submit']").click()

    # Verifikasi URL mengarah ke inventory
    assert "inventory.html" in driver.current_url, "Login gagal: tidak masuk ke halaman inventory"
finally:
    driver.quit()
```

Catatan:
- Metode `find_element_by_*` sudah deprecated pada Selenium 4; gunakan `find_element(By.…)`.
- Pertimbangkan `WebDriverWait` untuk elemen yang muncul dinamis.

---

## Sumber Belajar Tambahan

- [Dokumentasi Selenium](https://www.selenium.dev/documentation/en/)
- [Tutorial Selenium di YouTube](https://www.youtube.com/results?search_query=selenium+tutorial)
- [Repositori GitHub Selenium](https://github.com/SeleniumHQ/selenium)

---

## Kesimpulan

Selenium WebDriver adalah alat penting dalam otomasi pengujian aplikasi web. Dengan dukungan lintas bahasa, platform, dan browser, Selenium membantu tim QA mengotomatiskan pengujian berulang sehingga kualitas rilis lebih konsisten dan waktu pengujian lebih efisien.

> Inti pesan: Menguasai Selenium WebDriver mempercepat, menstabilkan, dan memperluas cakupan pengujian otomasi—keterampilan kunci bagi praktisi QA dan automasi testing.

---

## Referensi

Konten dirangkum dari presentasi “Pengantar Selenium WebDriver” oleh Kelompok 7 - Sistem Informasi 2023. Presentasi lengkap dapat diakses melalui tautan berikut:

[Lihat Presentasi (PPT)](https://drive.google.com/file/d/1G8XP7xVKPqGMZah4RyEfYVi3NrzOKuCo/view?usp=drive_link)