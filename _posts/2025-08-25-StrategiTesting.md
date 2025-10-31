---
layout: post
date: 2025-08-25
author: "Kelompok 1 - Sistem Informasi 2023"
title: "Strategi Pengujian Perangkat Lunak"
categories: [Software Development, Quality Assurance]
description: Ulasan ringkas namun menyeluruh tentang strategi testing perangkat lunak:tahapan STLC, klasifikasi (Abstraksi, Fungsi, Domain, Struktur), serta urgensinya dalam SDLC modern.
tags: [Software Testing, STLC, SDLC, Unit Testing, Integration Testing, System Testing, Black Box, White Box, Quality Assurance]
image: /assets/strategi-testing.png
---

# Strategi Pengujian Perangkat Lunak

## Pengertian Software Testing

Software Testing adalah proses terstruktur untuk menilai kualitas perangkat lunak dengan cara menemukan cacat (bug/defect) serta memverifikasi bahwa produk memenuhi kebutuhan yang ditetapkan—baik fungsional maupun non-fungsional.

> Tujuan inti:
> Menemukan dan memperbaiki kesalahan sebelum produk dipakai pengguna akhir agar kualitas, keamanan, serta reliabilitas aplikasi terjaga.

### Kenapa Testing Penting?

Bayangkan aplikasi bank gagal saat transfer, atau gim tiba-tiba crash ketika naik level. Testing hadir untuk mencegah hal-hal seperti ini terjadi.

Enam manfaat utama:

| Manfaat                 | Penjelasan                                                            | Contoh Nyata                                           |
| ----------------------- | --------------------------------------------------------------------- | ------------------------------------------------------ |
| Verifikasi & Validasi   | Memastikan perangkat lunak sesuai spesifikasi dan ekspektasi pengguna | Fitur “Lupa Password” benar-benar mengirim email reset |
| Mengurangi Risiko       | Mengungkap masalah sebelum sampai ke tangan pengguna                  | Bug kritis ditemukan sebelum peluncuran                |
| Efisiensi Biaya         | Memperbaiki saat dev jauh lebih murah daripada setelah rilis          | Saat coding: ~$100 vs setelah rilis: ~$1000+           |
| Keamanan                | Menemukan celah sebelum dimanfaatkan penyerang                        | Mencegah SQL Injection, XSS                            |
| Pengalaman Pengguna     | Menjamin aplikasi nyaman digunakan                                    | Navigasi mulus, performa cepat, UI konsisten           |
| Kepercayaan Stakeholder | Membuktikan produk stabil dan siap digunakan                          | Investor/klien lebih yakin terhadap produk             |

> Catatan:
> Berbagai studi industri menunjukkan biaya perbaikan bug di produksi dapat meningkat hingga puluhan—bahkan ratusan—kali lipat dibanding saat fase pengembangan.

---

## Posisi Testing dalam SDLC

Testing bukan aktivitas di akhir proyek. Ia terintegrasi sepanjang Software Development Life Cycle (SDLC).

### Kapan Testing Dilakukan?

```
SDLC Phases:
┌──────────────────────────────────────────────────────────────┐
│  Planning → Analysis → Design → Development → Testing → Deploy │
│                          ↓           ↓          ↓            │
│                      [Unit Test]  [Integration] [System]     │
│                                                              │
│  Testing hadir di SETIAP FASE, bukan eksklusif di pengujung! │
└──────────────────────────────────────────────────────────────┘
```

Pendekatan “Shift-Left”:
- Mulai sejak Planning & Design
- Developer menulis Unit Test saat coding
- Continuous Testing pada setiap commit (CI/CD)
- Acceptance Testing sebelum rilis

---

## Software Testing Life Cycle (STLC)

STLC adalah alur kerja QA untuk melakukan pengujian secara efektif dan tertib, dengan fase yang jelas tujuan dan hasilnya.

### Fase STLC

```
Perencanaan → Perancangan → Eksekusi → Pelaporan
    ↓            ↓            ↓           ↓
 Strategi     Skenario     Jalankan     Analisis &
  & Cakup     & Data        Testing       Rekomendasi
```

### 1) Test Planning (Perencanaan)

Tujuan: Menentukan strategi, ruang lingkup, peran, waktu, dan anggaran pengujian.

Aktivitas:
- Menetapkan Test Strategy (manual/otomasi, tools)
- Mendefinisikan scope in-scope/out-of-scope
- Menyiapkan Test Environment (server, DB, browser)
- Menetapkan peran & tanggung jawab
- Membuat estimasi timeline
- Merencanakan alokasi biaya

Output:
- Test Plan
- Test Strategy
- Estimasi effort

Contoh:
> “Aplikasi e-commerce diuji 5 tester, otomasi pakai Selenium, prioritas alur checkout dan pembayaran, estimasi 2 minggu.”

---

### 2) Test Design (Perancangan)

Tujuan: Menterjemahkan rencana menjadi artefak uji yang rinci dan siap dieksekusi.

Aktivitas:
- Menulis Test Case
- Menyusun Test Data (dummy user/produk/transaksi)
- Menentukan Expected Result
- Menyusun Requirement Traceability Matrix (RTM)
- Membuat skenario end-to-end

Output:
- Test Case & Script
- Test Data
- RTM

Contoh Test Case:

| Test Case ID    | TC_LOGIN_001                                                                          |
| --------------- | ------------------------------------------------------------------------------------- |
| Title           | Login dengan kredensial valid                                                         |
| Precondition    | User sudah terdaftar                                                                  |
| Steps           | 1) Buka halaman login<br>2) Isi email valid<br>3) Isi password valid<br>4) Klik Login |
| Expected Result | User masuk dan diarahkan ke dashboard                                                 |
| Test Data       | Email: test@example.com<br>Password: Test123!                                         |

---

### 3) Test Execution (Pelaksanaan)

Tujuan: Menjalankan test case, membandingkan hasil aktual vs harapan, dan mencatat temuan.

Aktivitas:
- Menjalankan test case sesuai rencana
- Mencatat bug di tool (Jira, Trello, dsb.)
- Regression testing setelah perubahan
- Dokumentasi (screenshot/video)
- Re-testing setelah perbaikan

Jenis pengujian yang umum dilakukan:

#### a) Unit/Component Testing
- Unit terkecil (fungsi, method, class)
- Umumnya oleh Developer
- Contoh: uji fungsi `computeDiscount()`

#### b) Integration Testing
- Interaksi antar modul/service
- API, DB, message broker, dsb.
- Contoh: Login Module → DB → Session

#### c) System Testing
- End-to-end seluruh sistem
- Umumnya oleh tim QA
- Contoh: browse → checkout → bayar → konfirmasi

#### d) Acceptance Testing (UAT)
- Dilakukan oleh user/klien
- Validasi kesesuaian dengan kebutuhan bisnis
- Hasil: persetujuan untuk go-live

Output:
- Laporan eksekusi pengujian
- Laporan bug
- Log pengujian

Status test case:
- Passed / Failed / Blocked / Skipped

---

### 4) Test Reporting & Analysis (Pelaporan)

Tujuan: Merangkum, menganalisis, dan menyajikan hasil pengujian untuk pengambilan keputusan.

Aktivitas:
- Menghasilkan metrik (pass rate, bug count, dsb.)
- Analisis bug (severity/priority)
- Penilaian kualitas produk
- Menyusun laporan akhir
- Memberikan rekomendasi ke tim dev

Contoh metrik:

| Metrik         | Penjelasan                        | Contoh                                    |
| -------------- | --------------------------------- | ----------------------------------------- |
| Test Coverage  | Persentase requirement yang diuji | 95% (190/200)                             |
| Pass Rate      | Persentase test case lulus        | 85% (170 pass, 30 fail)                   |
| Bug Count      | Total bug ditemukan               | 45                                        |
| Bug Severity   | Tingkat keparahan                 | Critical: 5, High: 15, Medium: 20, Low: 5 |
| Defect Density | Bug per 1000 LOC                  | 2,5/KLOC                                  |

Severity vs Priority:

| Severity | Deskripsi                      | Contoh                          |
| -------- | ------------------------------ | ------------------------------- |
| Critical | Crash, kehilangan data, breach | Pembayaran gagal, data terhapus |
| High     | Fitur inti tidak berfungsi     | Login gagal, checkout error     |
| Medium   | Masalah minor, ada workaround  | Filter tidak akurat             |
| Low      | Kosmetik/typo                  | Warna tombol salah, typo label  |

Output:
- Test Summary Report
- Bug Status Report
- Dashboard Quality Metrics
- Rekomendasi perbaikan

---

## Ringkasan Aktivitas per Fase (Versi Singkat)

- Menentukan kasus uji prioritas
- Estimasi waktu & biaya
- Menetapkan hasil uji dan targetnya
- Membagi peran & tanggung jawab
- Review dan approval rencana pengujian

Perancangan:
- Mengidentifikasi dan menulis test case
- Membuat data & skenario uji
- Menetapkan expected result
- Review & validasi
- Memutakhirkan RTM

Eksekusi:
- Jalankan test case sesuai rencana
- Catat selisih aktual vs ekspektasi sebagai bug
- Level: Komponen → Integrasi → Sistem → Acceptance

Pelaporan:
- Ringkasan hasil (pass/fail/not run)
- Daftar bug, severity, status perbaikan
- Evaluasi kualitas (fungsional & non-fungsional)
- Grafik tren dan rekomendasi

---

## Klasifikasi Strategi Testing

Empat sudut pandang untuk meliput aspek perangkat lunak secara komprehensif:

```
┌─────────────────────────────────────────────────────────┐
│                KLASIFIKASI STRATEGI TESTING             │
├─────────────────────────────────────────────────────────┤
│  1. Level Abstraksi → Unit / Integrasi / Sistem / UAT   │
│  2. Fungsi → Fungsional vs Non-Fungsional               │
│  3. Domain → Kinerja / Keamanan / Kegunaan / dst.       │
│  4. Struktur → Black-Box vs White-Box (Gray-Box)        │
└─────────────────────────────────────────────────────────┘
```

---

### 1) Berdasarkan Level Abstraksi (Testing Pyramid)

Dari unit terkecil hingga sistem utuh.

```
        ┌─────────────┐
       │     UAT      │  ← paling sedikit, paling lambat
      ├───────────────┤
     │ System Testing │
    ├─────────────────┤
   │ Integration Test │
  ├───────────────────┤
 │    Unit Testing   │  ← paling banyak, paling cepat
└────────────────────┘
```

#### Unit Testing

Definisi: Menguji unit terkecil (fungsi/metode/kelas) secara terisolasi.

Karakteristik:
- Cepat (ms)
- Cakupan kecil dan spesifik
- Oleh developer, sering otomatis
- Terisolasi dari DB/API/file system

Tools populer:
- Java: JUnit, TestNG
- JS: Jest, Mocha, Jasmine
- Python: pytest, unittest
- C#: NUnit, xUnit

Contoh:

```javascript
// Fungsi yang diuji
function computeDiscount(price, pct) {
  if (price < 0 || pct < 0) return 0;
  return price * (pct / 100);
}

// Unit test
test('computeDiscount menghitung nilai dengan benar', () => {
  expect(computeDiscount(100, 10)).toBe(10);
  expect(computeDiscount(200, 25)).toBe(50);
  expect(computeDiscount(-100, 10)).toBe(0); // harga negatif
});
```

Kapan dipakai:
- Logika bisnis
- Validasi input
- Perhitungan matematis
- Transformasi data

---

#### Integration Testing

Definisi: Memvalidasi interaksi antar modul/komponen.

Karakteristik:
- Fokus pada komunikasi antarbagian
- Oleh dev atau QA
- Melibatkan API, DB, eksternal service
- Lebih lambat dari unit tetapi lebih cepat dari sistem

Pendekatan:

| Pendekatan | Deskripsi                       | Kelebihan                         | Kekurangan                    |
| ---------- | ------------------------------- | --------------------------------- | ----------------------------- |
| Big Bang   | Integrasi semua modul sekaligus | Cepat untuk sistem sederhana      | Sulit deteksi sumber error    |
| Top-Down   | Dari level atas ke bawah        | Deteksi isu arsitektur lebih dini | Perlu stub untuk modul bawah  |
| Bottom-Up  | Dari bawah ke atas              | Modul kritikal diuji lebih awal   | Perlu driver untuk modul atas |
| Sandwich   | Kombinasi keduanya              | Seimbang                          | Lebih kompleks                |

Contoh:

```python
# Integration Test: Alur Login
def test_login_integration():
    # 1. Submit form login
    response = client.post('/login', data={
        'email': 'test@example.com',
        'password': 'password123'
    })

    # 2. Query ke DB berjalan
    assert user_exists_in_db('test@example.com') is True

    # 3. Session terbentuk
    assert session.get('user_id') is not None

    # 4. Redirect ke dashboard
    assert response.status_code == 302
    assert response.location == '/dashboard'
```

Kapan dipakai:
- Integrasi API
- Koneksi database
- Layanan pihak ketiga (pembayaran, email)
- Komunikasi antar microservice

---

#### System Testing

Definisi: Uji end-to-end pada sistem yang sudah terintegrasi penuh.

Karakteristik:
- Ruang lingkup seluruh sistem
- Lingkungan mirip produksi
- Oleh tim QA independen
- Mengacu pada SRS

Jenis:
- Functional, Performance, Security, Usability, Compatibility

Contoh skenario e-commerce:

```
Test Case: Complete Purchase Flow
1. Jelajah produk
2. Tambah ke cart
3. Terapkan kupon
4. Checkout
5. Isi alamat
6. Pilih metode bayar
7. Konfirmasi & bayar
8. Sistem kirim email konfirmasi
9. Stok berkurang
10. User mendapat nomor resi

Ekspektasi: Pesanan berhasil dibuat
```

---

#### Acceptance Testing (UAT)

Definisi: Validasi oleh pengguna/klien sebelum go-live untuk memastikan kesesuaian kebutuhan bisnis.

Karakteristik:
- Pelaku: end user, klien, stakeholder
- Tujuan: persetujuan akhir
- Basis: kebutuhan pengguna dan skenario bisnis
- Fokus: UX dan value

Jenis:
- Alpha, Beta, Contract Acceptance, Regulation Acceptance

Contoh UAT:

```
Skenario: HR Manager merekrut karyawan baru
Given: HR Manager login
When: Membuat lowongan → kandidat melamar → review & shortlist → jadwal interview → offering
Then: Kandidat menerima offer via email
 And: Profile karyawan tercipta
 And: Notifikasi ke IT untuk akun

Kriteria:
- Selesai ≤ 5 langkah
- Email notifikasi otomatis
- Data karyawan tersimpan
```

---

### 2) Berdasarkan Fungsi (Apa vs Bagaimana)

#### Functional Testing

Definisi: Memeriksa apakah fitur bekerja sesuai kebutuhan fungsional (WHAT).

Karakteristik:
- Berbasis dokumen kebutuhan fungsional
- Fokus pada fitur dan hasil
- Biasanya dengan pendekatan black-box
- Perspektif pengguna

Contoh:

| Fitur           | Test Case        | Expected                          |
| --------------- | ---------------- | --------------------------------- |
| Login           | Kredensial valid | Redirect ke dashboard             |
| Search          | Cari “laptop”    | Produk relevan tampil             |
| Add to Cart     | Tambah produk    | Jumlah +1, total harga berubah    |
| Payment         | Bayar CC         | Pembayaran sukses, order tercipta |
| Forgot Password | Minta reset      | Email terkirim                    |

Tools: Selenium, Cypress, Appium, Postman, Katalon

---

#### Non-Functional Testing

Definisi: Menilai bagaimana sistem bekerja (HOW), seperti kinerja, keamanan, kegunaan, reliabilitas, skalabilitas.

Jenis umum:
- Performance (Load/Stress/Spike/Endurance)
- Security (Pentest/Scan/Audit)
- Usability
- Compatibility
- Reliability
- Scalability

---

### 3) Berdasarkan Domain (Spesifik Non-Fungsional)

#### Performance Testing

Definisi: Mengukur kecepatan, responsivitas, dan stabilitas.

Empat jenis:

| Jenis     | Tujuan                   | Skenario                   | Tools              |
| --------- | ------------------------ | -------------------------- | ------------------ |
| Load      | Beban normal/target      | 1000 pengguna bersamaan    | JMeter, LoadRunner |
| Stress    | Batas maksimal           | Naikkan beban hingga crash | Gatling, k6        |
| Spike     | Lonjakan tiba-tiba       | Flash sale                 | JMeter             |
| Endurance | Ketahanan jangka panjang | 24/7 seminggu              | LoadRunner         |

Metrik:
- Response Time (< 2–3 detik)
- Throughput (req/s)
- CPU (< 70%)
- Memori (< 80%)
- Error Rate (< 1%)

Contoh:

```
Load Test: Flash Sale 12.12
- 5000 concurrent users
- 30 menit, ramp-up 1000/5 menit

Target:
- Response time < 3s
- Error rate < 0,5%
- Uptime 100%
- DB connection stabil

Hasil:
- Rata-rata 1,8s
- Puncak 10.000 req/menit
- 0 crash
- Error rate 0,2%
```

---

#### Security Testing

Definisi: Mengidentifikasi celah keamanan dan melindungi data.

Tujuan:
- Mencegah akses tak sah
- Mengurangi risiko serangan
- Kepatuhan (mis. GDPR, ISO 27001)
- Privasi pengguna

OWASP Top Risks (contoh 5 teratas):

| Peringkat | Kerentanan                | Contoh Serangan             | Pencegahan                          |
| --------- | ------------------------- | --------------------------- | ----------------------------------- |
| 1         | Broken Access Control     | User biasa bisa akses admin | Otorisasi ketat, least privilege    |
| 2         | Cryptographic Failures    | Password plain text         | Hashing kuat (bcrypt), enkripsi     |
| 3         | Injection                 | SQLi, XSS                   | Validasi input, parameterized query |
| 4         | Insecure Design           | Tanpa rate limiting         | Security by design, threat modeling |
| 5         | Security Misconfiguration | Default password aktif      | Hardening, secure default           |

Bentuk pengujian:

```
Security Testing
- Vulnerability Scanning (Nessus, OpenVAS)
- Penetration Testing (Burp Suite, Metasploit)
- Security Auditing (review code/config/log)
- Risk Assessment (identifikasi & prioritas risiko)
```

Contoh test case:

| Test Case         | Attack                      | Expected                           |
| ----------------- | --------------------------- | ---------------------------------- |
| SQL Injection     | `' OR '1'='1`               | Ditolak, error terlog              |
| XSS               | `<script>alert(1)</script>` | Disanitasi, tidak dieksekusi       |
| Brute Force       | 100 kali gagal login        | Akun terkunci (mis. 5 percobaan)   |
| Session Hijacking | Curian cookie session       | Session invalid saat logout/rotasi |

---

#### Usability Testing

Definisi: Menilai kemudahan, efisiensi, dan kepuasan penggunaan dari sudut pandang pengguna.

Fokus:
- Kemudahan belajar
- Kecepatan menyelesaikan tugas
- Kesalahan yang terjadi
- Kepuasan

Metode:
- Hallway Testing
- A/B Testing
- Eye Tracking
- Think Aloud
- Survei

Five-second test:
```
Tampilkan landing page 5 detik → tutup
Tanya: Apa yang diingat?
Hasil baik: pesan utama melekat
```

Metrik:
- Task Success Rate (> 80%)
- Time on Task (≤ target)
- Error Rate (< 5%)
- Satisfaction (> 4/5)

---

### 4) Berdasarkan Struktur (The “Box” Approach)

Tingkat pengetahuan tester terhadap internal sistem:

```
 Black Box     Gray Box      White Box
   No Code     Partial        Full Code
  Knowledge    Knowledge      Knowledge

   QA Tester   QA + Dev       Developer
```

#### Black-Box Testing

Definisi: Penguji tidak mengetahui struktur internal; fokus pada input-output.

Teknik umum:
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table
- State Transition
- Error Guessing

Kelebihan:
- Tidak perlu akses/source code
- Perspektif pengguna
- Skala besar untuk fungsional

Kekurangan:
- Coverage kode tidak terjamin penuh
- Logika tersembunyi bisa terlewat

Contoh:

```
Black-Box: Form Login
Input: email, password
Output: sukses/pesan error

Kasus:
- valid@test.com / valid123 → sukses
- invalid / valid123 → error email
- valid@test.com / salah → error password
- (kosong) / valid123 → wajib diisi
- test@test.com / (kosong) → wajib diisi
```

---

#### White-Box Testing

Definisi: Penguji memahami struktur internal, algoritma, dan alur kode.

Teknik:
- Statement/Branch/Path/Condition Coverage
- Loop Testing

Contoh coverage:

```javascript
function computeGrade(score) {
  if (score >= 90) {
    return "A"; // Branch 1
  } else if (score >= 80) {
    return "B"; // Branch 2
  } else if (score >= 70) {
    return "C"; // Branch 3
  } else {
    return "F"; // Branch 4
  }
}

// 100% branch coverage:
computeGrade(95) // A
computeGrade(85) // B
computeGrade(75) // C
computeGrade(60) // F
```

Kelebihan:
- Coverage tinggi
- Menemukan bug logika tersembunyi
- Meningkatkan kualitas kode
- Mengungkap isu keamanan

Kekurangan:
- Butuh kemampuan coding
- Waktu dan biaya bisa tinggi
- Tidak mencakup UX

Tools:
- Coverage: JaCoCo, coverage.py, Istanbul
- Static analysis: SonarQube, ESLint, Pylint
- Code quality: CodeClimate, Codacy

---

#### Gray-Box Testing

Definisi: Kombinasi black-box dan white-box; penguji punya pengetahuan terbatas (mis. skema DB, API spec).

Contoh:

```
Uji Pendaftaran Pengguna
Black-Box:
- Isi form → submit → pesan sukses

Gray-Box:
- Verifikasi data masuk DB
- Password tersimpan ter-enkripsi
- Token verifikasi email terbentuk

White-Box (tidak dilakukan):
- Tidak menelaah detail algoritma enkripsi
```

---

## Kesimpulan

Testing adalah fondasi kualitas perangkat lunak. Bukan sekadar mencari bug, melainkan:
- Membangun kepercayaan pengguna dan stakeholder
- Menghemat biaya dengan mencegah masalah di produksi
- Meningkatkan pengalaman pengguna
- Menjaga keamanan dan privasi
- Menjamin reliabilitas produk

### Hal-Hal Penting

| Aspek        | Ringkasan                                                   |
| ------------ | ----------------------------------------------------------- |
| STLC         | Alur terstruktur: Planning → Design → Execution → Reporting |
| Test Pyramid | Banyakkan unit test, minimalisir UI test yang lambat        |
| Klasifikasi  | 4 dimensi: Level, Fungsi, Domain, Struktur                  |
| Keseimbangan | Kombinasikan Black-Box (user) & White-Box (kode)            |
| Kontinu      | Testing berkelanjutan, bukan fase penutup semata            |

### Praktik Terbaik

```
Golden Rules
1) Mulai dini (shift-left)
2) Otomatiskan yang repetitif
3) Tulis test case yang jelas
4) Gunakan skenario data realistis
5) Dokumentasikan semuanya
6) Regression test setiap perubahan
7) Kolaborasi erat dengan developer
8) Terus belajar & update skill
```

### Rekomendasi Pembelajaran

| Level        | Jalur                                     | Sumber           |
| ------------ | ----------------------------------------- | ---------------- |
| Beginner     | Dasar manual testing, penulisan test case | ISTQB Foundation |
| Intermediate | Otomasi (Selenium, Cypress)               | Kursus online    |
| Advanced     | Performance & Security testing            | JMeter, OWASP    |
| Expert       | Test strategy, integrasi DevOps           | CI/CD, Jenkins   |

> "Testing shows the presence, not the absence of bugs." — Edsger Dijkstra
> Dengan strategi yang tepat, kita bisa meminimalkan risiko dan memaksimalkan kualitas.

---

## Referensi & Sumber

### Sumber Materi
Konten dirangkum dari presentasi “Strategi Testing” oleh Kelompok 1 - Sistem Informasi 2023. Presentasi lengkap:
[ Lihat Presentasi (PPT) ](https://drive.google.com/file/d/1bNFmdW8ePz_z0VM0660SZU4meSBaxc9c/view?usp=drive_link)

### Belajar Lebih Lanjut

- Buku: “Software Testing Fundamentals” (Rex Black), “The Art of Software Testing” (Glenford Myers), “Agile Testing” (Lisa Crispin & Janet Gregory)
- Online: [ISTQB Certification](https://www.istqb.org/), [Test Automation University](https://testautomationu.applitools.com/), [Ministry of Testing](https://www.ministryoftesting.com/)
- Tools: TestRail/Zephyr/qTest (manual), Selenium/Cypress/Playwright (otomasi), JMeter/Gatling/k6 (kinerja), OWASP ZAP/Burp Suite (keamanan), Postman/SoapUI/REST Assured (API)
- Latihan: [The Internet](https://the-internet.herokuapp.com/), [Restful Booker](https://restful-booker.herokuapp.com/), [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/)

---

## FAQ

<details>
<summary><strong>Kapan waktu terbaik memulai testing?</strong></summary>
<br>
Seawal mungkin. Di tahap <b>Requirements & Design</b> sudah bisa:
<ul>
<li>Review kebutuhan untuk mengurangi ambiguitas</li>
<li>Menetapkan test strategy</li>
<li>Menulis test case</li>
</ul>
Itulah esensi “Shift-Left Testing”.
</details>

<details>
<summary><strong>Berapa target test coverage yang ideal?</strong></summary>
<br>
Tidak ada angka baku. Rekomendasi umum:
<ul>
<li><b>Unit:</b> 70–80% code coverage</li>
<li><b>Integrasi:</b> jalur kritikal tercakup</li>
<li><b>E2E:</b> perjalanan pengguna utama tercakup</li>
</ul>
<b>Kualitas mengalahkan kuantitas.</b>
</details>

<details>
<summary><strong>Manual vs Automation: mana yang lebih baik?</strong></summary>
<br>
Keduanya penting—gunakan sesuai konteks.
<table>
<tr>
<th>Manual</th>
<th>Automation</th>
</tr>
<tr>
<td>Exploratory, Usability, Ad-hoc, One-off</td>
<td>Regression, Load, Repetitif, CI/CD</td>
</tr>
</table>
<b>Pendekatan terbaik:</b> Hybrid (kombinasi).
</details>

<details>
<summary><strong>Skill apa yang dibutuhkan QA/Tester?</strong></summary>
<br>
<b>Teknis:</b>
<ul>
<li>Menulis test case & bug report</li>
<li>Basic programming (otomasi)</li>
<li>SQL (uji DB)</li>
<li>Tools: Jira, Selenium, Postman</li>
</ul>
<b>Non-teknis:</b>
<ul>
<li>Ketelitian</li>
<li>Analitis & komunikasi</li>
<li>Berpikir kritis</li>
<li>Sabar & konsisten</li>
</ul>
</details>

<details>
<summary><strong>Bagaimana prioritas testing jika waktu terbatas?</strong></summary>
<br>
Terapkan <b>Risk-Based Testing</b>:
<ol>
<li><b>High:</b> fungsi inti (login, pembayaran, checkout)</li>
<li><b>Medium:</b> fitur sekunder (search, filter)</li>
<li><b>Low:</b> nice-to-have (animasi, tooltip)</li>
</ol>
Fokus pada fitur yang paling sering dipakai dan paling vital bagi bisnis.
</details>

---

“Quality is not an act, it is a habit.” — Aristotle