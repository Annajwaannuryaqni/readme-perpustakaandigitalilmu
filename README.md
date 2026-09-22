📚 Perpustakaan Digital Ilmu

Sistem Informasi Perpustakaan Sekolah Berbasis Web

Aplikasi ini digunakan untuk mengelola kegiatan perpustakaan sekolah, mulai dari buku, anggota, peminjaman, pengembalian, denda, pembayaran, presensi, rating, komentar, notifikasi, hingga laporan buku hilang.

🔗 Daftar Tautan

🌐 Live Demo
https://perpustakaandigitalilmu.infinityfreeapp.com

🖼️ Mockup
https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/mockup_ukk.jpg

📌 Use Case Diagram
https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/usecase_diagram.jpg

🔄 Flowchart
https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/flowchart.png

🗄️ ERD
https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/ERD-PERPUSTAKAAN.png

📖 1. Tentang Aplikasi

1.1 Tujuan

Perpustakaan Digital Ilmu dibuat untuk membantu sekolah mengelola layanan perpustakaan secara lebih terstruktur.

1.2 Role Sistem

No.

Role

Fokus Utama

1

Admin

Monitoring sistem dan pengelolaan akun Petugas

2

Petugas

Operasional buku, anggota, peminjaman, pengembalian, dan denda

3

Siswa

Peminjaman, pengembalian, pembayaran denda, presensi, rating, dan komentar

1.3 Teknologi Utama

PHP Native

MySQL / MariaDB

PDO

HTML

CSS

JavaScript

Tailwind CSS pada halaman tertentu

✨ 2. Fitur Utama

2.1 Beranda dan Katalog

Landing page perpustakaan.

Pencarian dan katalog buku.

Kategori buku.

Cover buku.

Video perpustakaan.

Halaman bantuan.

2.2 Manajemen Buku

Dikelola dari sisi Petugas.

Menambah buku.

Mengedit data buku.

Mengarsipkan buku.

Memulihkan buku yang diarsipkan.

Mengelola kode buku.

Mengelola judul buku.

Mengelola pengarang.

Mengelola penerbit.

Mengelola tahun terbit.

Mengelola kategori.

Mengelola stok.

Mengelola lokasi rak.

Mengelola deskripsi.

Mengunggah cover buku.

Buku yang diarsipkan tidak ditampilkan sebagai koleksi aktif.

Riwayat transaksi buku tetap dipertahankan.

2.3 Manajemen Anggota

Petugas dapat:

Melihat data anggota.

Mencari data anggota.

Melihat NIS anggota.

Melihat kelas anggota.

Menggunakan data anggota dalam proses transaksi.

2.4 Manajemen Petugas

Admin dapat:

Menambah akun Petugas.

Melihat daftar Petugas.

Mengaktifkan akun Petugas.

Menonaktifkan akun Petugas.

Mengelola akun Petugas.

Sistem mendukung beberapa akun Petugas dengan tiga role utama:

Admin

Petugas

Siswa

📚 3. Peminjaman Buku

3.1 Peminjaman oleh Siswa

Alur:

1. Pilih buku
2. Konfirmasi peminjaman
3. Transaksi berhasil

3.2 Peminjaman oleh Petugas

Alur:

1. Pilih anggota
2. Pilih buku
3. Proses peminjaman

3.3 Validasi Peminjaman

Sistem melakukan pengecekan:

Stok buku.

Status anggota.

Denda yang belum lunas.

Keterlambatan aktif.

Peminjaman ganda.

3.4 Lama Peminjaman

Masa peminjaman adalah 7 hari.

Batas pengembalian dihitung dari tanggal peminjaman.

3.5 Bukti Peminjaman

Setelah transaksi berhasil:

Siswa dapat melihat bukti peminjaman.

Siswa dapat mencetak bukti peminjaman.

Format disiapkan untuk printer thermal 80 mm.

🔄 4. Pengembalian Buku

Sistem menyediakan dua jalur pengembalian.

4.1 Siswa Mengajukan Pengembalian

1. Siswa
2. Ajukan Pengembalian
3. Menunggu Konfirmasi
4. Petugas memproses pengembalian

4.2 Siswa Datang Langsung ke Perpustakaan

1. Siswa membawa buku
2. Petugas membuka menu Pengembalian
3. Pilih transaksi Dipinjam
4. Proses Pengembalian

4.3 Kondisi Buku

Saat pengembalian, Petugas wajib memilih kondisi buku.

No.

Kondisi

Denda Kondisi

1

Baik

Rp0

2

Rusak

Rp20.000

3

Hilang

Rp50.000

4.4 Pengaruh Kondisi terhadap Stok

Baik → stok bertambah 1.

Rusak → stok tidak otomatis bertambah.

Hilang → stok tidak otomatis bertambah.

💰 5. Denda

5.1 Denda Keterlambatan

Tarif denda adalah Rp1.000 per hari.

Tidak ada batas maksimum denda keterlambatan.

5.2 Denda Kondisi

Buku Baik → Rp0.

Buku Rusak → Rp20.000.

Buku Hilang → Rp50.000.

5.3 Rumus Denda

Denda Total = Denda Keterlambatan + Denda Kondisi

5.4 Contoh Perhitungan

No.

Kondisi

Perhitungan

Total

1

21 hari terlambat + Rusak

Rp21.000 + Rp20.000

Rp41.000

2

21 hari terlambat + Hilang

Rp21.000 + Rp50.000

Rp71.000

📕 6. Laporan Buku Hilang

Jika Petugas memilih kondisi Hilang, sistem otomatis membuat laporan buku hilang.

Data laporan mencakup:

Informasi transaksi.

Data anggota.

Data buku.

Data Petugas.

Tanggal laporan.

Denda kondisi.

Catatan.

💳 7. Pembayaran Denda

Sistem menyediakan dua metode pembayaran.

7.1 Pembayaran Cash

1. Siswa memilih Cash
2. Siswa melakukan pembayaran kepada Petugas
3. Petugas mengonfirmasi pembayaran
4. Status menjadi Lunas

7.2 Pembayaran QRIS

1. Pilih QRIS
2. Tampilkan QRIS
3. Lakukan pembayaran
4. Upload bukti pembayaran
5. Petugas melakukan verifikasi
6. Status Diterima atau Ditolak

7.3 File Pembayaran

QR pembayaran: assets/qris_pembayaran.jpeg

Bukti pembayaran: uploads/bukti_pembayaran/

Bukti QRIS dapat diterima.

Bukti QRIS dapat ditolak dengan catatan.

Jika ditolak, siswa dapat mengunggah bukti baru.

⭐ 8. Rating dan Komentar

Siswa dapat memberikan:

Rating.

Komentar.

Pemberian rating dan komentar dilakukan setelah memiliki transaksi buku yang sudah selesai dikembalikan.

🏫 9. Presensi Kunjungan

Siswa dapat melakukan presensi kunjungan dengan:

Validasi jadwal operasional.

Pencegahan presensi ganda pada hari yang sama.

9.1 Jam Operasional

No.

Hari

Jam Operasional

1

Senin–Kamis

07:30–15:30 WIB

2

Jumat

07:30–14:00 WIB

3

Sabtu–Minggu

Tutup

🔔 10. Notifikasi

Sistem memiliki:

Notifikasi dalam aplikasi.

Status sudah / belum dibaca.

Notifikasi berdasarkan aktivitas sistem.

Suara notifikasi.

Endpoint notifikasi pada api/notifications.php.

👤 11. Hak Akses

11.1 Admin

Dashboard Admin.

Melihat data transaksi.

Melihat data kunjungan.

Mengelola akun Petugas.

Memantau statistik dan informasi penting pada dashboard.

11.2 Petugas

Dashboard Petugas.

Data buku.

Data anggota.

Peminjaman.

Pengembalian.

Buku terlambat.

Denda.

Verifikasi pembayaran Cash / QRIS.

Laporan buku hilang.

Aktivitas transaksi.

Riwayat peminjaman.

Profil Petugas.

11.3 Siswa

Registrasi dan login.

Dashboard pribadi.

Katalog dan pencarian buku.

Peminjaman buku.

Bukti peminjaman.

Pengajuan pengembalian.

Pembayaran denda Cash / QRIS.

Upload bukti pembayaran QRIS.

Rating dan komentar.

Presensi kunjungan.

🗂️ 12. Struktur Folder

Struktur berikut mengikuti project terbaru yang digunakan.

<details>
<summary><strong>Klik untuk melihat struktur lengkap</strong></summary>

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

🛠️ 13. Teknologi yang Digunakan

No.

Teknologi

Penggunaan

1

PHP Native

Backend dan proses aplikasi

2

MySQL / MariaDB

Penyimpanan data

3

PDO

Koneksi dan query database

4

HTML5

Struktur halaman

5

CSS3

Tampilan dan responsive layout

6

Tailwind CSS

Digunakan pada halaman tertentu

7

JavaScript

Interaksi, modal, jam realtime, dan notifikasi

8

PHP Session

Autentikasi dan hak akses

9

bcrypt

Hashing password dengan PASSWORD_BCRYPT

🗄️ 14. Database

Project menggunakan database db_perpustakaan.

14.1 Tabel

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

14.2 Relasi Utama

kategori
   │
   └──< buku
           │
           └──< transaksi >── anggota
                    │
                    └── petugas

buku ───< rating >── anggota

buku ───< komentar >── anggota

anggota ───< kunjungan

transaksi ───< pembayaran_denda

transaksi ───< laporan_buku_hilang

14.3 Data Pengembalian pada Tabel Transaksi

Tabel transaksi juga mencakup:

kondisi_buku

catatan_kondisi

denda_kondisi

14.4 Data Pembayaran

Tabel pembayaran_denda menyimpan:

Metode pembayaran.

Bukti pembayaran.

Status verifikasi.

Informasi verifikasi.

🔄 15. Alur Sistem

1. LOGIN
      ↓
2. Hak akses sesuai role
      ↓
3. SISWA / PETUGAS / ADMIN
      ↓
4. Proses sesuai hak akses
      ↓
5. Peminjaman
      ↓
6. Pengembalian
      ↓
7. Pemeriksaan kondisi buku
      ↓
8. Baik / Rusak / Hilang
      ↓
9. Perhitungan denda
      ↓
10. Pembayaran Cash / QRIS
      ↓
11. Verifikasi Petugas
      ↓
12. Status Lunas

15.1 Alur Kondisi Buku

1. Baik
   → Denda kondisi Rp0
   → Stok bertambah

2. Rusak
   → Denda kondisi Rp20.000
   → Stok tidak otomatis bertambah

3. Hilang
   → Denda kondisi Rp50.000
   → Stok tidak otomatis bertambah
   → Laporan Buku Hilang dibuat

🔐 16. Keamanan

Aplikasi menerapkan beberapa mekanisme keamanan dasar:

Password hashing dengan PASSWORD_BCRYPT.

Verifikasi password dengan password_verify().

Prepared statement melalui PDO.

CSRF protection.

Session authentication berdasarkan role.

Session regeneration setelah login.

Pembatasan percobaan login pada masing-masing role.

Pemeriksaan akses halaman melalui fungsi autentikasi.

Transaction database pada proses penting seperti peminjaman dan pengembalian.

Penguncian transaksi saat proses pengembalian untuk membantu mencegah pemrosesan ganda.

🚀 17. Instalasi Lokal

17.1 Persyaratan

XAMPP / Laragon atau web server sejenis.

PHP 8.2 atau versi yang kompatibel.

MySQL / MariaDB.

Browser modern.

17.2 Langkah Instalasi

Letakkan folder project ke dalam htdocs jika menggunakan XAMPP.

Jalankan Apache dan MySQL.

Buat database dengan nama db_perpustakaan.

Sesuaikan konfigurasi koneksi pada config/database.php.

Pastikan seluruh tabel yang dibutuhkan aplikasi tersedia.

Pastikan tabel pembayaran_denda dan laporan_buku_hilang tersedia.

Buka aplikasi melalui browser:

http://localhost/Perpustakaan_digital_ilmu-main/

Login menggunakan akun yang tersedia pada database.

Catatan: Project terbaru yang diperiksa tidak menyertakan dump SQL db_perpustakaan.sql, sehingga file SQL perlu disediakan dari database/schema project yang digunakan.

🕒 18. Pengelolaan Waktu

Aplikasi menggunakan timezone Asia/Jakarta (WIB) pada proses PHP yang berkaitan dengan tanggal dan waktu.

Beberapa proses menggunakan:

date('Y-m-d') untuk tanggal.

date('H:i:s') untuk waktu.

strtotime('+7 days') untuk menentukan batas pengembalian.

JavaScript setInterval(..., 1000) pada halaman presensi untuk memperbarui jam realtime di browser.

📌 19. Catatan Pengembangan

Versi saat ini menggunakan satu alur operasional Petugas untuk menangani transaksi dari peminjaman sampai pengembalian.

Pengembangan lanjutan yang masih dapat dilakukan:

Export laporan yang lebih lengkap.

Statistik dan analitik tambahan.

Pencetakan laporan transaksi.

Penguatan validasi dan keamanan file upload.

Pengembangan manajemen Petugas jika kebutuhan sistem bertambah.

👩‍💻 20. Kontributor

Najwa

Project ini dikembangkan sebagai aplikasi perpustakaan digital sekolah untuk membantu proses pengelolaan layanan perpustakaan secara terintegrasi.

<p align="center">
  <sub>Perpustakaan Digital Ilmu • Dokumentasi Project</sub>
</p>
