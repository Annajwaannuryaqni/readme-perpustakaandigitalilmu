<div align="center">

📚 Perpustakaan Digital Ilmu

Sistem informasi perpustakaan sekolah berbasis web

Mengelola buku, anggota, peminjaman, pengembalian, denda, pembayaran,
presensi, rating, komentar, notifikasi, dan laporan buku hilang.

<br>

<a href="https://perpustakaandigitalilmu.infinityfreeapp.com">🌐 Live Demo</a> ·
<a href="https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/mockup_ukk.jpg">🖼️ Mockup</a> ·
<a href="https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/usecase_diagram.jpg">📌 Use Case</a> ·
<a href="https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/flowchart.png">🔄 Flowchart</a> ·
<a href="https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/ERD-PERPUSTAKAAN.png">🗄️ ERD</a>

</div>

📋 Daftar Isi

Tentang Aplikasi

Fitur Utama

Hak Akses

Alur Sistem

Struktur Folder

Teknologi

Database

Keamanan

Instalasi Lokal

Pengelolaan Waktu

Catatan Pengembangan

📖 Tentang Aplikasi

Perpustakaan Digital Ilmu dibuat untuk membantu sekolah mengelola layanan perpustakaan secara lebih terstruktur dan terintegrasi.

Sistem memiliki 3 role utama:

Role

Fokus

Admin

Monitoring sistem dan pengelolaan akun Petugas

Petugas

Operasional buku, anggota, peminjaman, pengembalian, dan denda

Siswa

Peminjaman, pengembalian, pembayaran denda, presensi, rating, dan komentar

Teknologi yang digunakan

PHP Native · MySQL/MariaDB · PDO · HTML5 · CSS3 · JavaScript · Tailwind CSS (halaman tertentu)

✨ Fitur Utama

🏠 Beranda & Katalog

Landing page perpustakaan

Pencarian dan katalog buku

Kategori buku dan cover

Video perpustakaan

Halaman bantuan

📚 Manajemen Buku

Dikelola dari sisi Petugas:

Tambah, edit, arsip, dan pulihkan buku

Kelola kode buku, judul, pengarang, penerbit, tahun terbit, kategori, stok, lokasi rak, dan deskripsi

Upload cover buku

Buku yang diarsipkan tidak ditampilkan sebagai koleksi aktif, tetapi riwayat transaksi tetap dipertahankan

👥 Manajemen Anggota

Petugas dapat melihat dan mencari data anggota, termasuk NIS dan kelas, untuk kebutuhan transaksi.

👨‍💼 Manajemen Petugas

Admin dapat:

Menambah akun Petugas

Melihat daftar Petugas

Mengaktifkan atau menonaktifkan akun

Mengelola akun Petugas

Sistem mendukung beberapa akun Petugas dan tetap menggunakan tiga role: Admin, Petugas, dan Siswa.

📖 Peminjaman Buku

Peminjaman dapat dilakukan melalui dua jalur.

Siswa

Pilih buku → Konfirmasi peminjaman → Transaksi berhasil

Petugas

Pilih anggota → Pilih buku → Proses peminjaman

Sistem melakukan pengecekan stok, status anggota, denda belum lunas, keterlambatan aktif, dan peminjaman ganda.

Masa peminjaman: 7 hari.

Setelah transaksi berhasil, siswa dapat melihat dan mencetak bukti peminjaman dengan format untuk printer thermal 80 mm.

🔄 Pengembalian Buku

Terdapat dua jalur pengembalian.

1. Siswa mengajukan pengembalian

Siswa
  ↓
Ajukan Pengembalian
  ↓
Menunggu Konfirmasi
  ↓
Petugas memproses pengembalian

2. Siswa datang langsung ke perpustakaan

Siswa membawa buku
  ↓
Petugas membuka Pengembalian
  ↓
Pilih transaksi Dipinjam
  ↓
Proses Pengembalian

Petugas wajib memilih kondisi buku:

Kondisi

Denda Kondisi

Baik

Rp0

Rusak

Rp20.000

Hilang

Rp50.000

Ketentuan stok:

Baik → stok bertambah 1

Rusak → stok tidak otomatis bertambah

Hilang → stok tidak otomatis bertambah

💰 Denda

Denda keterlambatan: Rp1.000 per hari tanpa batas maksimum.

Denda Total = Denda Keterlambatan + Denda Kondisi

Contoh:

Kasus

Perhitungan

Total

21 hari terlambat + Rusak

Rp21.000 + Rp20.000

Rp41.000

21 hari terlambat + Hilang

Rp21.000 + Rp50.000

Rp71.000

📕 Laporan Buku Hilang

Jika Petugas memilih kondisi Hilang, sistem otomatis membuat Laporan Buku Hilang yang menyimpan informasi transaksi, anggota, buku, petugas, tanggal laporan, denda kondisi, dan catatan.

💳 Pembayaran Denda

Sistem menyediakan Cash dan QRIS.

💵 Cash

Siswa memilih Cash
      ↓
Pembayaran kepada Petugas
      ↓
Petugas mengonfirmasi
      ↓
Status Lunas

📱 QRIS

Pilih QRIS
   ↓
Tampilkan QRIS
   ↓
Lakukan pembayaran
   ↓
Upload bukti pembayaran
   ↓
Petugas melakukan verifikasi
   ↓
Diterima / Ditolak

Komponen

Lokasi

QR pembayaran

assets/qris_pembayaran.jpeg

Bukti pembayaran

uploads/bukti_pembayaran/

Status verifikasi

Diterima / Ditolak

Jika bukti QRIS ditolak, siswa dapat mengunggah bukti baru.

⭐ Rating & 💬 Komentar

Siswa dapat memberikan rating dan komentar setelah memiliki transaksi buku yang sudah selesai dikembalikan.

🏫 Presensi Kunjungan

Siswa dapat melakukan presensi kunjungan dengan validasi jadwal operasional dan pencegahan presensi ganda pada hari yang sama.

Hari

Jam Operasional

Senin–Kamis

07:30–15:30 WIB

Jumat

07:30–14:00 WIB

Sabtu–Minggu

Tutup

🔔 Notifikasi

Notifikasi dalam aplikasi

Status sudah/belum dibaca

Notifikasi berdasarkan aktivitas sistem

Suara notifikasi

Endpoint: api/notifications.php

👤 Hak Akses

Fitur

Admin

Petugas

Siswa

Dashboard

✅

✅

✅

Manajemen Petugas

✅

—

—

Data Buku

—

✅

Lihat

Data Anggota

—

✅

—

Peminjaman

Lihat

✅

✅

Pengembalian

—

✅

Ajukan

Denda

Lihat

✅

Lihat/Bayar

Verifikasi Pembayaran

—

✅

—

Laporan Buku Hilang

—

✅

—

Presensi

Lihat

Lihat

✅

Rating & Komentar

Lihat

Lihat

✅

Notifikasi

✅

✅

✅

🔄 Alur Sistem

LOGIN
  │
  ▼
Hak Akses sesuai Role
  │
  ├───────────────┬───────────────┐
  ▼               ▼               ▼
SISWA           PETUGAS         ADMIN
  │               │               │
  ├─ Peminjaman   ├─ Peminjaman   ├─ Monitoring
  ├─ Pengembalian ├─ Pengembalian └─ Kelola Petugas
  ├─ Pembayaran   ├─ Denda
  └─ Presensi     └─ Verifikasi

Pengembalian
      │
      ▼
 Pilih Kondisi Buku
      │
 ┌────┼─────┐
 ▼    ▼     ▼
Baik Rusak Hilang
 │    │       │
 │    └───┐   └──→ Laporan Buku Hilang
 │        │
 └────────┴────→ Hitung Denda
                    │
              ┌─────┴─────┐
              ▼           ▼
            Cash         QRIS
              │           │
              │      Upload Bukti
              │           │
              └─────┬─────┘
                    ▼
            Verifikasi Petugas
                    │
                    ▼
                  Lunas

🗂️ Struktur Folder

Struktur berikut mengikuti project terbaru yang digunakan.

<details>
<summary><strong>📁 Klik untuk melihat struktur lengkap</strong></summary>

Perpustakaan_digital_ilmu-main/
│
├── admin/
│   ├── dashboard.php
│   ├── kunjungan.php
│   ├── login.php
│   ├── logout.php
│   ├── petugas.php
│   └── transaksi.php
│
├── api/
│   └── notifications.php
│
├── assets/
│   ├── css/
│   │   └── notification.css
│   ├── js/
│   │   └── notification.js
│   ├── sounds/
│   │   └── notification.mp3
│   ├── video/
│   │   └── perpustakaan.mp4
│   ├── logo-sekolah.png
│   ├── qris_pembayaran.jpeg
│   └── style.css
│
├── config/
│   ├── constants.php
│   └── database.php
│
├── includes/
│   ├── auth.php
│   ├── navbar_notification.php
│   ├── notification_helper.php
│   ├── petugas_sidebar.php
│   └── siswa_sidebar.php
│
├── petugas/
│   ├── aktivitas.php
│   ├── bayar_denda.php
│   ├── buku_terlambat.php
│   ├── dashboard.php
│   ├── data_anggota.php
│   ├── data_buku.php
│   ├── denda.php
│   ├── edit_buku.php
│   ├── hapus_buku.php
│   ├── laporan_buku_hilang.php
│   ├── login.php
│   ├── logout.php
│   ├── peminjaman.php
│   ├── pengembalian.php
│   ├── profil.php
│   ├── proses_kembali.php
│   ├── proses_pinjam.php
│   ├── pulihkan_buku.php
│   ├── riwayat_peminjaman.php
│   └── tambah_buku.php
│
├── siswa/
│   ├── bukti_peminjaman.php
│   ├── daftar.php
│   ├── dashboard.php
│   ├── kembali.php
│   ├── login.php
│   ├── logout.php
│   ├── pembayaran_denda.php
│   ├── pinjam.php
│   ├── pinjam_konfirmasi.php
│   ├── presensi.php
│   ├── proses_kembali.php
│   ├── proses_pembayaran_denda.php
│   └── proses_rating.php
│
├── uploads/
│   ├── bukti_pembayaran/
│   └── file cover buku
│
├── bantuan.php
├── index.php
└── rating_submit.php

</details>

Catatan: Project terbaru yang diperiksa tidak menyertakan db_perpustakaan.sql.

🛠️ Teknologi

Teknologi

Penggunaan

PHP Native

Backend dan proses aplikasi

MySQL / MariaDB

Penyimpanan data

PDO

Koneksi dan query database

HTML5

Struktur halaman

CSS3

Tampilan dan responsive layout

Tailwind CSS

Digunakan pada halaman tertentu

JavaScript

Interaksi, modal, jam realtime, dan notifikasi

PHP Session

Autentikasi dan hak akses

bcrypt

Hashing password menggunakan PASSWORD_BCRYPT

🗄️ Database

Project menggunakan database db_perpustakaan.

Tabel utama

admin
anggota
buku
kategori
petugas
transaksi
rating
komentar
kunjungan
notifications
pembayaran_denda
laporan_buku_hilang

Relasi utama

kategori
   └──< buku
           └──< transaksi >── anggota
                    └── petugas

buku ───< rating >── anggota
buku ───< komentar >── anggota
anggota ───< kunjungan
transaksi ───< pembayaran_denda
transaksi ───< laporan_buku_hilang

Data pengembalian pada transaksi juga mencakup:

kondisi_buku

catatan_kondisi

denda_kondisi

Tabel pembayaran_denda menyimpan metode pembayaran, bukti pembayaran, status verifikasi, dan informasi verifikasi.

🔐 Keamanan

Aplikasi menerapkan beberapa mekanisme keamanan dasar:

Password hashing dengan PASSWORD_BCRYPT

Verifikasi password dengan password_verify()

Prepared statement melalui PDO

CSRF protection

Session authentication berdasarkan role

Session regeneration setelah login

Pembatasan percobaan login pada masing-masing role

Pemeriksaan akses halaman melalui fungsi autentikasi

Transaction database pada proses penting seperti peminjaman dan pengembalian

Penguncian transaksi saat proses pengembalian untuk membantu mencegah pemrosesan ganda

🚀 Instalasi Lokal

Persyaratan

XAMPP / Laragon atau web server sejenis

PHP 8.2 atau versi yang kompatibel

MySQL / MariaDB

Browser modern

Langkah

1. Letakkan folder project di htdocs jika menggunakan XAMPP.

2. Jalankan Apache dan MySQL.

3. Buat database:

Nama database: db_perpustakaan

4. Sesuaikan konfigurasi koneksi pada:

config/database.php

5. Pastikan seluruh tabel yang dibutuhkan aplikasi tersedia, termasuk:

pembayaran_denda
laporan_buku_hilang

6. Buka aplikasi:

http://localhost/Perpustakaan_digital_ilmu-main/

7. Login menggunakan akun yang tersedia pada database.

Catatan: Project terbaru yang diperiksa tidak menyertakan dump SQL db_perpustakaan.sql, sehingga file SQL perlu disediakan dari database/schema project yang digunakan.

🕒 Pengelolaan Waktu

Aplikasi menggunakan timezone Asia/Jakarta (WIB) pada proses PHP yang berkaitan dengan tanggal dan waktu.

Implementasi

Fungsi

date('Y-m-d')

Mengambil tanggal

date('H:i:s')

Mengambil waktu

strtotime('+7 days')

Menentukan batas pengembalian

setInterval(..., 1000)

Memperbarui jam realtime pada halaman presensi

📌 Catatan Pengembangan

Versi saat ini menggunakan satu alur operasional Petugas untuk menangani transaksi dari peminjaman sampai pengembalian.

Pengembangan lanjutan yang masih dapat dilakukan:

Export laporan yang lebih lengkap

Statistik dan analitik tambahan

Pencetakan laporan transaksi

Penguatan validasi dan keamanan file upload

Pengembangan manajemen Petugas sesuai kebutuhan sistem

👩‍💻 Kontributor

Najwa

Project ini dikembangkan sebagai aplikasi perpustakaan digital sekolah untuk membantu proses pengelolaan layanan perpustakaan secara terintegrasi.

<div align="center">

📚 Perpustakaan Digital Ilmu
Dokumentasi Project

</div>
