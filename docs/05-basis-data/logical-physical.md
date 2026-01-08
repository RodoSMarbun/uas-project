---
id: logical-physical
sidebar_position: 2
title: Logical & Physical Design
---

# Logical & Physical Design

## Tabel Master

### 1. Tabel `anggota`
Menyimpan data mahasiswa atau dosen yang menjadi anggota perpustakaan.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `nim` | VARCHAR(20) | PK | Nomor Induk Mahasiswa (Unik) |
| `nama` | VARCHAR(100) | NOT NULL | Nama lengkap anggota |
| `jurusan` | VARCHAR(50) | NOT NULL | Program studi |
| `no_hp` | VARCHAR(15) | | Nomor WhasApp/Telepon |
| `password` | VARCHAR(255) | NOT NULL | Kata sandi (Hashed) |
| `status_aktif` | ENUM('Y','N')| DEFAULT 'Y' | Status keanggotaan |

### 2. Tabel `pustakawan`
Menyimpan data petugas perpustakaan.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_pegawai` | VARCHAR(10) | PK | ID Pustakawan |
| `nama` | VARCHAR(100) | NOT NULL | Nama petugas |
| `jabatan` | VARCHAR(50) | | Jabatan struktural |
| `password` | VARCHAR(255) | NOT NULL | Kata sandi (Hashed) |

### 3. Tabel `buku`
Menyimpan data koleksi buku.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `isbn` | VARCHAR(20) | PK | International Standard Book Number |
| `judul` | VARCHAR(200) | NOT NULL | Judul buku |
| `pengarang` | VARCHAR(100) | | Nama pengarang |
| `penerbit` | VARCHAR(100) | | Nama penerbit |
| `tahun_terbit` | YEAR | | Tahun terbit buku |
| `stok` | INT | DEFAULT 0 | Jumlah buku fisik tersedia |
| `id_kategori` | INT | FK | Referensi ke tabel kategori |
| `id_rak` | INT | FK | Referensi ke tabel rak |

## Tabel Referensi

### 4. Tabel `kategori`
| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_kategori` | INT | PK, AUTO_INCREMENT | ID Kategori |
| `nama_kategori` | VARCHAR(50) | NOT NULL | Contoh: Teknologi, Ekonomi, Fiksi |

### 5. Tabel `rak`
| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_rak` | INT | PK, AUTO_INCREMENT | ID Rak |
| `lokasi` | VARCHAR(50) | NOT NULL | Contoh: Lantai 1 - A01 |

## Tabel Transaksi

### 6. Tabel `peminjaman`
Header transaksi peminjaman.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_peminjaman` | VARCHAR(20) | PK | No Transaksi (misal: TRX-20231001-001) |
| `tgl_pinjam` | DATE | NOT NULL | Tanggal buku diambil |
| `tgl_jatuh_tempo`| DATE | NOT NULL | Tanggal wajib kembali (biasanya H+7) |
| `status` | ENUM('Dipinjam','Selesai') | DEFAULT 'Dipinjam' | Status keseluruhan transaksi |
| `nim` | VARCHAR(20) | FK | Peminjam |
| `id_pegawai` | VARCHAR(10) | FK | Petugas yang melayani |

### 7. Tabel `detail_peminjaman`
Detail buku apa saja yang dipinjam dalam satu transaksi.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_detail` | INT | PK, AUTO_INCREMENT | ID Detail |
| `id_peminjaman` | VARCHAR(20) | FK | Referensi ke header |
| `isbn` | VARCHAR(20) | FK | Buku yang dipinjam |

### 8. Tabel `pengembalian`
Transaksi pengembalian buku.

| Field | Tipe Data | Constraint | Deskripsi |
| :--- | :--- | :--- | :--- |
| `id_pengembalian`| VARCHAR(20) | PK | No Pengembalian |
| `tgl_kembali` | DATE | NOT NULL | Tanggal aktual kembali |
| `total_denda` | DECIMAL(10,2)| DEFAULT 0 | Denda keterlambatan |
| `id_peminjaman` | VARCHAR(20) | FK | Referensi ke peminjaman awal |
| `id_pegawai` | VARCHAR(10) | FK | Petugas yang menerima |
