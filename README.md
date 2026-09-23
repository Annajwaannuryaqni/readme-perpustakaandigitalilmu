# 📚 Perpustakaan Digital Ilmu

> **Sistem Informasi Perpustakaan Sekolah Berbasis Web**

Aplikasi pengelolaan layanan perpustakaan sekolah secara terintegrasi — mulai dari pencarian buku, transaksi peminjaman, pembayaran denda, presensi pengunjung, hingga pelaporan.

---

## 📑 Daftar Isi

- [Tautan Penting](#-tautan-penting)
- [Hak Akses & Role](#-hak-akses--role)
- [Fitur Utama](#-fitur-utama)
- [Teknologi & Keamanan](#️-teknologi--keamanan)
- [Struktur Folder Utama](#️-struktur-folder-utama)
- [Instalasi Lokal](#-instalasi-lokal)
- [Kontributor](#-kontributor)

---

## 🔗 Tautan Penting

| Tautan | Deskripsi |
| :--- | :--- |
| 🌐 [Live Demo](https://perpustakaandigitalilmu.infinityfreeapp.com) | Coba langsung aplikasinya |
| 🌐 [REPOSITORY ](https://github.com/Annajwaannuryaqni/Perpustakaan_digital_ilmu.git) | REPOSITORY GITHUB |
| 🖼️ [Mockup](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/mockup_ukk.jpg) | Tampilan antarmuka aplikasi |
| 📌 [Use Case Diagram](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/usecase_diagram.jpg) | Diagram interaksi pengguna |
| 🔄 [Flowchart](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/flowchart.png) | Alur proses sistem |
| 🗄️ [ERD](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/ERD-PERPUSTAKAAN.png) | Rancangan struktur basis data |

---

## 👥 Hak Akses & Role

| Role | Fungsi Utama |
| :--- | :--- |
| **Admin** | Monitoring sistem, rekapitulasi data, dan manajemen akun Petugas. |
| **Petugas** | Pengelolaan data buku, anggota, peminjaman, pengembalian, verifikasi denda, dan laporan buku hilang. |
| **Siswa** | Katalog buku, peminjaman, pengajuan pengembalian, pembayaran denda, presensi, serta ulasan buku. |

---

## ✨ Fitur Utama

### 📖 Katalog & Manajemen Buku

- Katalog digital dengan pencarian, pemfilteran kategori, lokasi rak, dan status ketersediaan.
- Fitur pengarsipan buku — buku yang diarsipkan tidak muncul di katalog aktif, tetapi riwayat transaksi tetap tersimpan.

### 📚 Peminjaman & Pengembalian

- **Masa Pinjam:** batas waktu 7 hari, dengan opsi cetak bukti peminjaman (mendukung printer thermal 80mm).
- **Validasi Otomatis:** pengecekan stok, status aktif anggota, denda yang belum dibayar, dan peminjaman ganda.
- **Proses Pengembalian:** mendukung pengajuan lewat akun Siswa maupun pemrosesan langsung oleh Petugas.
- **Dampak Kondisi Buku terhadap Stok:**
  - **Baik** → stok bertambah (+1).
  - **Rusak / Hilang** → stok tidak bertambah otomatis, dikenakan denda kondisi, dan (khusus status hilang) otomatis memicu pembuatan **Laporan Buku Hilang**.

### 💰 Denda & Pembayaran

**Perhitungan denda total:**

$$\text{Denda Total} = \text{Denda Keterlambatan (Rp1.000/hari)} + \text{Denda Kondisi}$$

**Tarif denda kondisi:**

| Kondisi Buku | Denda |
| :--- | ---: |
| Baik | Rp0 |
| Rusak | Rp20.000 |
| Hilang | Rp50.000 |

**Metode pembayaran:**

- **Cash** — konfirmasi langsung oleh Petugas.
- **QRIS** — unggah bukti transfer, dengan fitur verifikasi (*Approve* / *Reject*) oleh Petugas.

### 🏫 Presensi & Fitur Pendukung

- **Presensi Kunjungan:** validasi jam operasional sekolah (Senin–Kamis: 07.30–15.30 WIB, Jumat: 07.30–14.00 WIB) dan pencegahan presensi ganda harian.
- **Rating & Komentar:** ulasan terbuka khusus untuk siswa yang telah menyelesaikan transaksi peminjaman buku terkait.
- **Notifikasi Sistem:** in-app notification realtime beserta indikator suara.

---

## 🛠️ Teknologi & Keamanan

### Tech Stack

| Komponen | Teknologi |
| :--- | :--- |
| Backend | PHP Native (PDO, PHP Session) |
| Database | MySQL / MariaDB (`db_perpustakaan`) |
| Frontend | HTML5, CSS3, JavaScript, Tailwind CSS |
| Timezone | Asia/Jakarta (WIB) |

### Keamanan

- Password hashing menggunakan `PASSWORD_BCRYPT`.
- Prepared Statements (PDO) untuk perlindungan dari SQL Injection.
- Proteksi CSRF & *rate limiting* percobaan login.
- *Database transaction & locking* pada alur peminjaman dan pengembalian, untuk mencegah bentrok/pemrosesan ganda.

---

## 🗂️ Struktur Folder Utama

```text
Perpustakaan_digital_ilmu-main/
├── admin/          # Panel kontrol Admin
├── api/            # API endpoint (Notifikasi, dll)
├── assets/         # CSS, JS, media, logo, QRIS
├── config/         # Konfigurasi database & konstanta
├── includes/       # Komponen reusable (Sidebar, Auth, Notification)
├── petugas/        # Panel operasional Petugas
├── siswa/          # Panel layanan Siswa
└── uploads/        # Penyimpanan file bukti pembayaran & cover buku
```

---

## 🚀 Instalasi Lokal

1. Clone atau ekstrak repositori ke direktori web server Anda (misalnya `htdocs` di XAMPP).
2. Jalankan service **Apache** dan **MySQL**.
3. Buat database baru dengan nama `db_perpustakaan`, lalu impor skema database Anda.
4. Sesuaikan konfigurasi database pada file `config/database.php`.
5. Buka browser dan akses:

   ```text
   http://localhost/Perpustakaan_digital_ilmu-main/
   ```

---

## 👩‍💻 Kontributor

- **Najwa** — Pengembang Utama

---

<p align="center"><sub>Perpustakaan Digital Ilmu • Dokumentasi Project</sub></p>
