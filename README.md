Perpustakaan Digital Ilmu

Aplikasi Perpustakaan Digital Ilmu merupakan aplikasi perpustakaan sekolah berbasis web untuk membantu pengelolaan buku, anggota, peminjaman, pengembalian, denda, pembayaran denda, presensi kunjungan, rating/komentar, notifikasi, dan pelaporan buku hilang.

Aplikasi dikembangkan menggunakan PHP Native, MySQL/MariaDB, PDO, HTML, CSS, JavaScript, serta Tailwind CSS pada halaman tertentu.

Live Demo: https://perpustakaandigitalilmu.infinityfreeapp.com
Mockup: https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/mockup_ukk.jpg
Use Case Diagram: https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/usecase_diagram.jpg
Flowchart: https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/flowchart.png
ERD: https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/ERD-PERPUSTAKAAN.png

1. Struktur Folder

Struktur berikut disesuaikan dengan project terbaru.

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
│   │   └── file bukti pembayaran QRIS
│   └── file cover buku
│
├── bantuan.php
├── index.php
└── rating_submit.php

Catatan: Project terbaru yang diperiksa tidak menyertakan file db_perpustakaan.sql di dalam ZIP. Jadi bagian instalasi database mengikuti database/schema yang digunakan pada project yang sudah berjalan.

2. Fitur Utama

🏠 Beranda

Landing page perpustakaan.

Pencarian dan katalog buku.

Informasi perpustakaan.

Kategori buku.

Cover buku.

Video perpustakaan.

Halaman bantuan.

📚 Manajemen Buku

Fitur pengelolaan buku berada pada sisi Petugas, meliputi:

Menambah buku.

Mengedit buku.

Mengarsipkan buku.

Memulihkan buku yang diarsipkan.

Mengelola kode buku, judul, pengarang, penerbit, tahun terbit, kategori, stok, lokasi rak, dan deskripsi.

Mengunggah cover buku.

Buku yang diarsipkan tidak ditampilkan sebagai koleksi aktif, tetapi riwayat transaksi tetap dipertahankan.

👥 Manajemen Anggota

Petugas dapat:

Melihat data anggota.

Mencari anggota.

Melihat NIS dan kelas.

Menggunakan data anggota pada proses peminjaman dan pengembalian.

👨‍💼 Manajemen Petugas

Admin dapat:

Membuat akun petugas.

Melihat daftar petugas.

Mengaktifkan atau menonaktifkan petugas.

Mengelola akun petugas.

Beberapa akun petugas dapat digunakan dalam sistem. Tidak ada role tambahan di luar Admin, Petugas, dan Siswa.

📖 Peminjaman Buku

Peminjaman dapat dilakukan melalui dua sisi:

Siswa: memilih buku dan melakukan konfirmasi peminjaman.

Petugas: memilih anggota dan buku untuk melayani peminjaman secara langsung.

Sistem melakukan pengecekan seperti stok, status anggota, denda belum lunas, keterlambatan aktif, dan peminjaman ganda.

Masa peminjaman yang digunakan adalah 7 hari.

Setelah transaksi berhasil, siswa dapat melihat bukti peminjaman dan mencetaknya dalam format yang diarahkan untuk printer thermal 80 mm.

🔄 Pengembalian Buku

Ada dua jalur pengembalian:

Jalur 1 – siswa mengajukan

Siswa → Ajukan Pengembalian → Menunggu Konfirmasi → Petugas memproses

Jalur 2 – petugas membantu langsung

Siswa datang membawa buku → Petugas → Pengembalian → pilih transaksi Dipinjam → Proses Pengembalian

Artinya siswa tetap dapat mengajukan pengembalian, tetapi pengajuan siswa tidak menjadi satu-satunya cara. Petugas aktif dapat membantu memproses transaksi yang masih Dipinjam maupun Menunggu Konfirmasi.

Saat pengembalian, petugas wajib memilih kondisi buku:

Baik

Rusak

Hilang

💰 Denda

Denda keterlambatan menggunakan aturan:

Rp1.000 per hari keterlambatan tanpa batas maksimum.

Denda kondisi buku:

Baik: Rp0

Rusak: Rp20.000

Hilang: Rp50.000

Denda total merupakan penjumlahan denda keterlambatan dan denda kondisi.

Contoh:

Terlambat 21 hari + Rusak = Rp21.000 + Rp20.000 = Rp41.000

Terlambat 21 hari + Hilang = Rp21.000 + Rp50.000 = Rp71.000

📕 Laporan Buku Hilang

Jika petugas memilih kondisi Hilang saat memproses pengembalian, sistem otomatis membuat Laporan Buku Hilang.

Laporan mencatat informasi transaksi, anggota, buku, petugas, tanggal laporan, kondisi, denda kondisi, dan catatan.

💳 Pembayaran Denda

Siswa dapat memilih metode pembayaran:

Cash

Pilih Cash → lakukan pembayaran ke Petugas → Petugas konfirmasi → Lunas

QRIS

Pilih QRIS → tampil QRIS → bayar → upload bukti → Petugas verifikasi → Lunas

Bukti pembayaran QRIS disimpan pada uploads/bukti_pembayaran/ dan QR pembayaran berada di assets/qris_pembayaran.jpeg.

Bukti QRIS dapat:

menunggu verifikasi,

diterima/diverifikasi,

ditolak dengan catatan sehingga siswa dapat mengunggah ulang bukti.

⭐ Rating dan 💬 Komentar

Siswa dapat memberikan rating dan komentar setelah memiliki transaksi buku yang sudah selesai dikembalikan.

🏫 Presensi Kunjungan

Siswa dapat melakukan presensi kunjungan dengan validasi jadwal operasional dan pencegahan presensi ganda pada hari yang sama.

Jadwal yang diterapkan pada aplikasi:

Senin–Kamis: 07:30–15:30 WIB

Jumat: 07:30–14:00 WIB

Sabtu–Minggu: tutup

🔔 Notifikasi

Notifikasi dalam aplikasi.

Status sudah/belum dibaca.

Notifikasi berdasarkan aktivitas.

Suara notifikasi.

Endpoint notifikasi melalui api/notifications.php.

3. Peran Pengguna

1. Admin

Admin berfungsi sebagai pengelola dan pemantau sistem.

Akses utama:

Dashboard Admin.

Melihat data transaksi.

Melihat data kunjungan.

Mengelola akun petugas.

Memantau statistik perpustakaan dan informasi penting pada dashboard.

2. Petugas

Petugas berfokus pada operasional perpustakaan.

Akses utama:

Dashboard Petugas.

Data buku.

Data anggota.

Peminjaman.

Pengembalian.

Buku terlambat.

Denda.

Verifikasi pembayaran Cash/QRIS.

Laporan buku hilang.

Aktivitas transaksi.

Riwayat peminjaman.

Profil petugas.

3. Siswa / Anggota

Siswa menggunakan layanan perpustakaan.

Akses utama:

Registrasi dan login.

Dashboard pribadi.

Katalog dan pencarian buku.

Peminjaman buku.

Bukti peminjaman.

Pengembalian / pengajuan pengembalian.

Pembayaran denda Cash atau QRIS.

Upload bukti pembayaran QRIS.

Rating dan komentar.

Presensi kunjungan.

4. Teknologi

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

Digunakan pada halaman tertentu seperti beranda dan bantuan

JavaScript

Interaksi, jam realtime, modal, dan notifikasi

PHP Session

Autentikasi dan hak akses

bcrypt (PASSWORD_BCRYPT)

Hashing password

5. Struktur Database

Project menggunakan database db_perpustakaan.

Tabel yang digunakan oleh aplikasi antara lain:

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

Relasi Utama

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

Kolom tambahan pada transaksi untuk kondisi pengembalian mencakup:

kondisi_buku

catatan_kondisi

denda_kondisi

Pembayaran denda mencatat metode pembayaran dan status verifikasi bukti.

6. Alur Sistem Singkat

LOGIN
  ↓
Hak akses sesuai role
  ↓
┌───────────────┬────────────────┬─────────────────┐
│     SISWA     │    PETUGAS     │      ADMIN      │
└───────────────┴────────────────┴─────────────────┘
        ↓               ↓                  ↓
     Pinjam          Operasional        Monitoring
        ↓               ↓                  ↓
     Kembali ←──────── Pengembalian ───────┘
        ↓
  Cek kondisi buku
    ↓      ↓       ↓
  Baik   Rusak   Hilang
           ↓       ↓
        Denda   Laporan Hilang
           \      /
             Denda
               ↓
        Cash atau QRIS
               ↓
        Verifikasi Petugas
               ↓
             Lunas

7. Keamanan

Aplikasi menerapkan beberapa mekanisme keamanan, antara lain:

Password hashing menggunakan PASSWORD_BCRYPT.

password_verify() untuk verifikasi password.

Prepared statement PDO.

CSRF protection.

Autentikasi session berdasarkan role.

Session regeneration setelah login.

Pembatasan percobaan login pada masing-masing role.

Pemeriksaan akses halaman melalui fungsi autentikasi.

Transaction database pada proses penting seperti peminjaman dan pengembalian.

Penguncian transaksi saat proses pengembalian untuk membantu mencegah pemrosesan ganda.

8. Instalasi

Persyaratan

XAMPP/Laragon atau web server PHP.

PHP 8.2 atau versi yang kompatibel.

MySQL/MariaDB.

Browser modern.

Langkah Dasar

Letakkan folder project pada htdocs jika menggunakan XAMPP.

Jalankan Apache dan MySQL.

Buat database dengan nama db_perpustakaan.

Pastikan konfigurasi koneksi pada config/database.php sesuai dengan server lokal.

Pastikan struktur tabel yang dibutuhkan aplikasi tersedia, termasuk pembayaran_denda dan laporan_buku_hilang.

Buka project melalui browser, misalnya:
http://localhost/Perpustakaan_digital_ilmu-main/

Login menggunakan akun yang tersedia pada database.

Catatan: ZIP project terbaru yang diperiksa tidak menyertakan dump SQL db_perpustakaan.sql, sehingga file SQL perlu disediakan dari database/schema project yang digunakan.

9. Catatan Pengembangan

Aplikasi masih dapat dikembangkan lebih lanjut, misalnya:

laporan dan export data yang lebih lengkap,

pencetakan laporan transaksi,

statistik dan analitik tambahan,

penguatan keamanan file upload,

pengembangan lebih lanjut pada manajemen petugas.

Untuk versi saat ini, satu petugas dapat menangani operasional transaksi dari peminjaman sampai pengembalian. Pemisahan tanggung jawab petugas berdasarkan fungsi dapat menjadi pengembangan berikutnya jika sistem diperbesar.

10. Kontributor

Najwa

Project ini dikembangkan sebagai aplikasi perpustakaan digital sekolah untuk membantu proses pengelolaan layanan perpustakaan secara terintegrasi.
