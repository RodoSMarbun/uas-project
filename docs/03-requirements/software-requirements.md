---
id: software-requirements
sidebar_position: 4
title: Software Requirements (FR & NFR)
---

# Software Requirements

Dokumen ini menjelaskan **Kebutuhan Perangkat Lunak** (Software Requirements) untuk Sistem Informasi Perpustakaan PWBI. Kebutuhan dibagi menjadi Fungsional (Functional Requirements) dan Non-Fungsional (Non-Functional Requirements).

## 1. Functional Requirements (FR)

Kebutuhan fungsional mendefinisikan fitur dan fungsi spesifik yang harus dapat dilakukan oleh sistem.

| ID | Kategori | Deskripsi Kebutuhan | Prioritas |
| :--- | :--- | :--- | :--- |
| **FR-AUTH-01** | Autentikasi | Sistem harus memungkinkan pengguna (Admin, Pustakawan, Mahasiswa) untuk masuk (login) menggunakan NIM/NIDN dan kata sandi. | **Must Have** |
| **FR-AUTH-02** | Autentikasi | Sistem harus membatasi hak akses fitur berdasarkan peran pengguna (Role-based Access Control). | **Must Have** |
| **FR-AUTH-03** | Autentikasi | Sistem harus memiliki fitur logout untuk mengakhiri sesi pengguna dengan aman. | **Must Have** |
| **FR-BOOK-01** | Manajemen Buku | Admin/Pustakawan dapat menambah, mengubah, dan menghapus data buku (Judul, Pengarang, Penerbit, Tahun, ISBN, Stok). | **Must Have** |
| **FR-BOOK-02** | Manajemen Buku | Sistem dapat menampilkan status ketersediaan buku secara *real-time* kepada pengguna. | **Must Have** |
| **FR-BOOK-03** | Manajemen Buku | Admin/Pustakawan dapat mengelola kategori buku dan lokasi rak penyimpanan. | **Should Have** |
| **FR-SCH-01** | Pencarian | Pengguna dapat mencari buku berdasarkan Judul, Pengarang, atau Kategori. | **Must Have** |
| **FR-TRANS-01** | Peminjaman | Pustakawan dapat mencatat transaksi peminjaman buku dengan memindai ID Anggota dan ID Buku / ISBN. | **Must Have** |
| **FR-TRANS-02** | Peminjaman | Sistem harus memvalidasi batas maksimal buku yang dipinjam (Maksimal 3 buku untuk mahasiswa). | **Must Have** |
| **FR-TRANS-03** | Peminjaman | Sistem harus mencegah peminjaman jika anggota memiliki denda yang belum dibayar. | **Should Have** |
| **FR-RET-01** | Pengembalian | Pustakawan dapat mencatat pengembalian buku dan sistem otomatis menghitung keterlambatan. | **Must Have** |
| **FR-DND-01** | Denda | Sistem harus menghitung denda secara otomatis (Rp 500,- per hari) jika pengembalian melewati tanggal jatuh tempo. | **Must Have** |
| **FR-REP-01** | Laporan | Admin dapat mengunduh laporan peminjaman bulanan dalam format PDF atau Excel. | **Could Have** |
| **FR-REP-02** | Laporan | Sistem menampilkan dashboard statistik jumlah buku dipinjam dan buku populer. | **Could Have** |
| **FR-USR-01** | Profil Anggota | Anggota dapat melihat riwayat peminjaman dan status denda mereka sendiri melalui dashboard. | **Should Have** |

## 2. Non-Functional Requirements (NFR)

Kebutuhan non-fungsional mendefinisikan atribut kualitas sistem, seperti keandalan, efisiensi, dan keamanan.

| ID | Kategori | Deskripsi Kebutuhan | Prioritas |
| :--- | :--- | :--- | :--- |
| **NFR-PERF-01** | Performa | Waktu respons sistem untuk pencarian buku tidak boleh lebih dari 3 detik. | **Should Have** |
| **NFR-SEC-01** | Keamanan | Kata sandi pengguna harus disimpan dalam database menggunakan enkripsi (hashing) yang aman (seperti bcrypt). | **Must Have** |
| **NFR-SEC-02** | Keamanan | Sistem otomatis *logout* jika tidak ada aktivitas selama 30 menit. | **Should Have** |
| **NFR-AVL-01** | Ketersediaan | Sistem harus dapat diakses 24/7 kecuali saat pemeliharaan terjadwal. | **Must Have** |
| **NFR-UI-01** | Usability | Antarmuka pengguna harus responsif (*mobile-friendly*) untuk akses melalui smartphone mahasiswa. | **Should Have** |
