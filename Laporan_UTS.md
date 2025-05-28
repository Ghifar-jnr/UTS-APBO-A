# Ujian Tengah Semester APBO (A) - Kelompok 1
Repositori ini berisi laporan hasil Ujian Tengah Semester (UTS) mata kuliah Analisis Pemrograman Berbasis Objek (APBO) - Kelas A

## Dosen Pengampu
Adi Wahyu Pribadi, S.Si., M.Kom

## Anggota :

|           Nama           |     NPM     |
|--------------------------|-------------|
| Aida Fitria              | 4523210007  |
| Diva Cahya Hakim         | 4523210037  |
| Ghifar Januar Abdillah   | 4523210051  |
| Mochammad Fadhila Putra  | 4523210063  |
| Priska Adriani           | 4523210085  |

## Sistem Reservasi Meja Billiard

## Buat :
### 1. Aktor / Role Yang Terlibat
### 2. Use Case
### 3. Entitas Utama
### 4. Relasi
### 5. Class Diagram
### 6. WireFrame
### 7. MockUp

## Jawab !
### 1. Aktor / Role yang terlibat : 
#### - Pelanggan
Pelanggan berperan sebagai pengguna sistem yang melakukan pemesanan meja biliard,pengisian data pribadi seperti(nama,email,no telepon),pemilihan tanggal dan waktu reservasi,melakukan pembayaran,mengecek ketersediaan meja billiard dan dapat melakukan pembatalan(atas persetujuan pegawai kasir).

#### - Pegawai Kasir
Pegawai Kasir berperan sebagai pengelola transaksi yang bekerja atau bertugas untuk memproses pesanan,mengupdate pesanan(sedang diproses,terlambat atau sudah selesai),membantu proses check in reservasi meja biliard,mengecek ketersediaan meja billiard,dan dapat menyetujui pembatalan dari pelanggan.

#### - Pemilik Biliard
Pemilik Biliard berperan sebagai mengelola data seperti (meja biliard,alat inventaris,dan data pelanggan),dan dapat melihat laporan reservasi.

### 3. Entitas Utama
### Tabel Master
#### - Tabel Pelanggan 

| Nama Atribut  | Tipe Data    | Keterangan                 |
|---------------|--------------|----------------------------|
| id_pelanggan  | Int 10 (PK)  | ID unik pelanggan          |
| nama          | Varchar 100  | Nama lengkap pelanggan     |
| no_hp         | Varchar 15   | Nomor telepon pelanggan    |
| email         | Varchar 30   | Email pelanggan            |

#### - Tabel Meja_Billiard

| Nama Atribut  | Tipe Data    | Keterangan                 |
|---------------|--------------|----------------------------|
| id_meja       | Int 5 (PK)   | ID unik Meja Billiard      |
| no_meja       | Varchar 5    | No Meja Billiard           |
| status_meja   | ENUM         | Tersedia/digunakan/rusak   |

#### - Tabel Metode_Pembayaran

| Nama Atribut  | Tipe Data    | Keterangan                 |
|---------------|--------------|----------------------------|
| id_metode     | Int 10 (PK)  | ID unik metode pembayaran  |
| nama_metode   | Varchar 50   | Tunai, Debit, Qris         |

### Tabel Transaksi
#### - Tabel Reservasi

| Nama Atribut      | Tipe Data    | Keterangan                         |
|-------------------|--------------|------------------------------------|
| id_reservasi      | Int 10 (PK)  | ID unik reservasi                  |
| id_pelanggan      | Int 10 (FK)  | Relasi ke tabel pelanggan          |
| waktu_pemesanan   | Datatime     | Waktu saat reservasi dibuat        |
| tanggal_pemesanan | Date         | Tanggal reservasi untuk bermain    |

#### - Tabel Detail_Reservasi

| Nama Atribut      | Tipe Data    | Keterangan                         |
|-------------------|--------------|------------------------------------|
| id_detail         | Int 10 (PK)  | ID detail reservasi                |
| id_ reservasi     | Int 10 (FK)  | Relasi ke tabel reservasi          |
| id_meja           | Int 5  (FK)  | Relasi ke tabel Meja_Billiard      |
| jam_mulai         | Varchar 10   | Jam mulai bermain                  |
| durasi_permainan  | Varchar 10   | Lama durasi permainan (dalam jam)  |
| total_biaya       | Varchar 20   | Total biaya sebelum pembayaran     |

#### - Tabel Bayar

| Nama Atribut      | Tipe Data    | Keterangan                         |
|-------------------|--------------|------------------------------------|
| id_bayar          | Int 10 (PK)  | ID unik pembayaran                 |
| id_reservasi      | Int 10 (FK)  | Relasi ke tabel reservasi          |
| id_metode         | Int 5  (FK)  | Relasi ke tabel Metode_Pembayaran  |
| jumlah_bayar      | Varchar 50   | Jumlah nominal pembayaran          |

#### - Tabel Pembatalan

| Nama Atribut      | Tipe Data    | Keterangan                          |
|-------------------|--------------|-------------------------------------|
| id_batal          | Int 10 (PK)  | ID unik pembatalan                  |
| id_reservasi      | Int 10 (FK)  | Relasi ke reservasi yang dibatalkan |
| alasan_pembatalan | Varchar 100  | Alasan pembatalan                   |

### 4. Relasi
![ERD UTS NEW drawio](https://github.com/user-attachments/assets/5fa0a5f9-72f8-4a6b-8f3c-be8288590304)

