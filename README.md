# BERKAH ELEKTRONIK Management System
1. DASHBOARD
![alt text](screenshots/Dashboard.png)
2. DATA PENJUALAN
![alt text](<screenshots/Data penjualan.png>)
3. DATA SUPPLIER
![alt text](<screenshots/Data supplier.png>)
4. KATEGORI
![alt text](screenshots/Kategori.png)
5. KELOLA BARANG
![alt text](<screenshots/Kelola barang.png>)
6. LAPORAN PENJUALAN
![alt text](<screenshots/Laporan penjualan.png>)
7. LOGIN ADMIN
![alt text](<screenshots/Login admin.png>)
8. LOGIN STAFF
![alt text](<screenshots/Login staff.png>)
9. TRANSAKSI PEMBELIAN
![alt text](<screenshots/Transaksi pembelian.png>)

## 1. Deskripsi Proyek

BERKAH ELEKTRONIK Management System adalah aplikasi berbasis web yang dibuat untuk membantu mengelola data barang, kategori, supplier, pembelian, dan penjualan. Aplikasi ini dibuat menggunakan Laravel dan MySQL sebagai database.

Dengan aplikasi ini, pengelolaan stok barang dan pencatatan transaksi dapat dilakukan dengan lebih mudah, rapi, dan teratur.

## 2. Tujuan Proyek

Tujuan pembuatan aplikasi ini adalah:
- Memudahkan pengelolaan data barang dan stok.
- Memudahkan pencatatan transaksi pembelian dan penjualan.
- Membantu memantau stok barang yang mulai menipis.
- Memudahkan melihat laporan penjualan.
- Membatasi akses pengguna sesuai dengan perannya.

## 3. Teknologi yang Digunakan

- **Bahasa pemrograman:** PHP
- **Framework:** Laravel
- **Database:** MySQL
- **Web server lokal:** XAMPP
- **Editor kode:** Visual Studio Code
- **Bahasa tampilan:** HTML dan CSS

## 4. Fitur Aplikasi

### A. Login dan Logout
Pengguna harus login terlebih dahulu untuk masuk ke aplikasi. Pengguna juga dapat logout setelah selesai menggunakan aplikasi.

### B. Dashboard
Menampilkan ringkasan data, yaitu:
- Total barang.
- Total stok barang.
- Jumlah barang dengan stok menipis.
- Total supplier.

### C. Kelola Barang
Digunakan untuk melihat, menambah, mengedit, dan menghapus data barang sesuai hak akses pengguna. Data barang mencakup nama barang, kategori, harga, stok, dan stok minimum.

### D. Kelola Kategori
Digunakan untuk mengelola kategori barang agar data lebih teratur.

### E. Kelola Supplier
Digunakan untuk melihat, menambah, mengedit, dan menghapus data supplier. Informasi supplier meliputi nama, nomor telepon, email, dan alamat.

### F. Pembelian
Digunakan untuk mencatat transaksi pembelian barang dari supplier. Admin dapat mengedit dan menghapus data pembelian, sedangkan Staff dapat melihat dan membuat transaksi pembelian.

### G. Penjualan
Digunakan untuk mencatat transaksi penjualan barang. Sistem menghitung total transaksi dan mengurangi stok barang secara otomatis setelah penjualan berhasil disimpan.

### H. Laporan Penjualan
Menampilkan data transaksi penjualan, total transaksi, total omzet, dan ringkasan barang terjual. Laporan juga dapat difilter berdasarkan tanggal awal dan tanggal akhir.

### I. Data Pengguna
Admin dapat mengelola akun pengguna dan mengatur peran pengguna, yaitu Admin dan Staff.

## 5. Hak Akses Pengguna

| Fitur | Admin | Staff |
|---|---|---|
| Dashboard | Ya | Ya |
| Melihat barang | Ya | Ya |
| Menambah, mengedit, menghapus barang | Ya | Tidak |
| Mengelola kategori | Ya | Tidak |
| Mengelola supplier | Ya | Tidak |
| Melihat dan membuat pembelian | Ya | Ya |
| Mengedit dan menghapus pembelian | Ya | Tidak |
| Melihat dan membuat penjualan | Ya | Ya |
| Melihat laporan penjualan | Ya | Ya |
| Mengelola data pengguna | Ya | Tidak |
| Logout | Ya | Ya |

## 6. Struktur Folder Utama

```text
uts-inventory-sales/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   └── Middleware/
│   └── Models/
├── database/
│   └── migrations/
├── public/
├── resources/
│   └── views/
├── routes/
│   └── web.php
├── .env
├── artisan
├── composer.json
└── README.md
```

## 7. Cara Menjalankan Aplikasi

### Persiapan
Pastikan perangkat sudah memiliki:
- XAMPP dengan MySQL aktif.
- PHP yang sesuai dengan versi Laravel proyek.
- Composer.

### Langkah menjalankan

1. Jalankan Apache dan MySQL melalui XAMPP.
2. Pastikan database `inventory_uts` sudah tersedia dan berisi tabel aplikasi.
3. Buka terminal di folder proyek.
4. Pastikan pengaturan database pada file `.env` sesuai dengan database lokal.

Contoh pengaturan database:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=inventory_uts
DB_USERNAME=root
DB_PASSWORD=
```

5. Jika dependensi proyek belum terpasang, jalankan:

```bash
composer install
```

6. Jalankan aplikasi dengan perintah:

```bash
D:/php83/php.exe artisan serve
```

7. Buka browser dan akses:

```text
http://127.0.0.1:8000
```

8. Login menggunakan akun Admin atau Staff yang sudah dibuat di database.

**Catatan:** Jika PHP 8.3 pada perangkatmu perlu dipanggil melalui lokasi khusus, gunakan perintah berikut:

```powershell
D:\php83\php.exe artisan serve
```

## 8. Database

Database yang digunakan bernama `inventory_uts` dengan MySQL. Database menyimpan data pengguna, barang, kategori, supplier, pembelian, dan penjualan beserta detail transaksinya.

Untuk memindahkan aplikasi ke perangkat lain, ekspor database ke file SQL terlebih dahulu, lalu impor file tersebut ke MySQL pada perangkat tujuan.

## 9. Keamanan dan Validasi

Aplikasi memiliki beberapa pengamanan, yaitu:
- Login diperlukan untuk mengakses halaman utama.
- Hak akses Admin dan Staff dibedakan.
- Halaman khusus Admin dilindungi oleh middleware.
- Password pengguna disimpan dalam bentuk hash.
- Form barang memvalidasi data wajib serta menolak harga dan stok negatif.

## 10. Penutup

BERKAH ELEKTRONIK Management System dibuat untuk membantu pengelolaan barang dan transaksi dalam satu aplikasi. Diharapkan aplikasi ini dapat mempermudah pencatatan stok, pembelian, penjualan, serta pemantauan laporan penjualan.

Proyek ini juga menjadi sarana pembelajaran dalam menerapkan Laravel, database MySQL, pengelolaan data, dan pengaturan hak akses pengguna.
