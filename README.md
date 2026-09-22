# **<font size="6">📚 Perpustakaan Digital Ilmu</font>**

> **<font size="3">Sistem Informasi Perpustakaan Sekolah Berbasis Web</font>**

Aplikasi pengelolaan layanan perpustakaan sekolah secara terintegrasi (buku, anggota, transaksi, denda, presensi, hingga laporan).

---

## **<font size="5">🔗 Tautan Penting</font>**

* 🌐 **Live Demo:** [<font color="#0066cc">perpustakaandigitalilmu.infinityfreeapp.com</font>](https://perpustakaandigitalilmu.infinityfreeapp.com)
* 🖼️ **Mockup:** [<font color="#0066cc">Lihat Gambar</font>](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/mockup_ukk.jpg)
* 📌 **Use Case Diagram:** [<font color="#0066cc">Lihat Diagram</font>](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/usecase_diagram.jpg)
* 🔄 **Flowchart:** [<font color="#0066cc">Lihat Flowchart</font>](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/flowchart.png)
* 🗄️ **ERD:** [<font color="#0066cc">Lihat ERD</font>](https://raw.githubusercontent.com/Annajwaannuryaqni/readme-perpustakaandigitalilmu/refs/heads/main/ERD-PERPUSTAKAAN.png)

---

## **<font size="5">👥 Hak Akses & Role</font>**

| Role | Akses Utama |
|---|---|
| **Admin** | Monitoring sistem, rekapitulasi, dan manajemen akun Petugas. |
| **Petugas** | Pengelolaan buku, anggota, peminjaman, pengembalian, denda, serta laporan buku hilang. |
| **Siswa** | Peminjaman buku, pengajuan pengembalian, pembayaran denda, presensi, serta pemberi rating & komentar. |

---

## **<font size="5">✨ Fitur Utama</font>**

### **<font size="4">📖 Katalog & Anggota</font>**
* Katalog buku digital, pencarian, kategori, dan detail lokasi rak.
* Pengarsipan buku tanpa menghapus riwayat transaksi.
* Pencarian dan verifikasi data anggota (NIS & Kelas).

### **<font size="4">📚 Peminjaman & Pengembalian</font>**
* **Masa Pinjam:** Default 7 hari (format struk mendukung printer thermal 80mm).
* **Validasi Otomatis:** Pengecekan stok, status anggota, denda aktif, dan peminjaman ganda.
* **Opsi Pengembalian:** Pengajuan via akun siswa atau pemrosesan langsung oleh Petugas.
* **Dampak Kondisi Buku terhadap Stok:**
  * **Baik:** Stok bertambah (+1).
  * **Rusak / Hilang:** Stok tidak otomatis bertambah, dikenakan denda kondisi, dan otomatis membuat **Laporan Buku Hilang** (khusus status hilang).

### **<font size="4">💰 Denda & Pembayaran</font>**
* **Rumus Denda:** `Denda Keterlambatan (Rp1.000/hari) + Denda Kondisi`
* **Tarif Denda Kondisi:**
  * Baik: Rp0
  * Rusak: Rp20.000
  * Hilang: Rp50.000
* **Metode Pembayaran:** Cash (konfirmasi Petugas) & QRIS (upload bukti transfer dengan fitur *Approve/Reject* oleh Petugas).

### **<font size="4">🏫 Presensi & Fitur Lainnya</font>**
* **Presensi Kunjungan:** Validasi jam operasional (Senin–Kamis: 07:30–15:30 WIB, Jumat: 07:30–14:00 WIB) & pencegahan presensi ganda harian.
* **Rating & Komentar:** Khusus untuk siswa yang telah menyelesaikan transaksi peminjaman.
* **Notifikasi:** Realtime/In-app notification dengan efek suara.

---

## **<font size="5">🗂️ Struktur Folder</font>**

<details>
<summary><strong>Klik untuk melihat struktur direktori proyek</strong></summary>

```text
Perpustakaan_digital_ilmu-main/
│
├── admin/            # Panel & fitur khusus Admin
├── api/              # Endpoint API (notifications, dll)
├── assets/           # Style, scripts, gambar, dan media
├── config/           # Konfigurasi database & konstanta
├── includes/         # Layout & helper (navbar, sidebar, auth)
├── petugas/          # Panel & operasional Petugas
├── siswa/            # Panel & fitur transaksi Siswa
├── uploads/          # Direktori penyimpanan file & bukti transfer
├── bantuan.php
├── index.php
└── rating_submit.php
🛠️ Teknologi & Keamanan
Tech Stack
Backend: PHP Native (PDO, PHP Session)

Database: MySQL / MariaDB (db_perpustakaan)

Frontend: HTML5, CSS3, JavaScript, Tailwind CSS (halaman tertentu)

Timezone: Asia/Jakarta (WIB)

Keamanan
Password Hashing dengan PASSWORD_BCRYPT.

Prepared Statements (PDO) untuk mencegah SQL Injection.

Proteksi CSRF & Pembatasan percobaan login (rate limiting).

Proteksi transaksi database (Database Transaction & Locking) pada proses peminjaman/pengembalian.

🚀 Instalasi Lokal
Clone / pindahkan folder ke direktori web server (misal: htdocs).

Jalankan Apache & MySQL.

Buat database baru bernama db_perpustakaan dan import struktur tabel yang dibutuhkan.

Buka file config/database.php untuk menyesuaikan kredensial koneksi.

Akses aplikasi melalui browser:

Plaintext
http://localhost/Perpustakaan_digital_ilmu-main/
👩‍💻 Kontributor
Najwa — Pengembang Aplikasi
