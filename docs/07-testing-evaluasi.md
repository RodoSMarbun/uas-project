---
id: testing-evaluasi
sidebar_position: 7
title: Testing & Evaluasi
---

# Testing & Evaluasi Sistem

## 1. Rencana Pengujian (Functional Testing)

| ID Uji | Fitur | Skenario Pengujian | Input Data | Hasil yang Diharapkan | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TEST-01** | Login | Login dengan data valid | User: `admin`, Pass: `12345` | Masuk ke Dashboard Admin | ✅ Pass |
| **TEST-02** | Login | Login dengan password salah | User: `admin`, Pass: `salah` | Muncul pesan "Login Gagal" | ✅ Pass |
| **TEST-03** | Peminjaman | Pinjam buku melebihi kuota | User meminjam buku ke-4 | Sistem menolak dan alert "Kuota Penuh" | ✅ Pass |
| **TEST-04** | Peminjaman | Pinjam buku dengan stok 0 | Scan buku stok 0 | Sistem menolak "Stok Habis" | ✅ Pass |
| **TEST-05** | Denda | Kembalikan buku telat 2 hari | Tgl Seharusnya: 1 Jan, Kembali: 3 Jan | Sistem menghitung denda Rp 1.000 | ✅ Pass |

## 2. Rencana Evaluasi

### 2.1. Tujuan Evaluasi
Tujuan utama dari evaluasi ini adalah:
*   **Validasi Fungsional**: Memastikan seluruh fitur (login, input buku, peminjaman) berjalan tanpa error (bug).
*   **Validasi Usability (Kegunaan)**: Mengukur tingkat kemudahan dan kepuasan pengguna saat menggunakan aplikasi.

### 2.2. Ruang Lingkup & Metode
Evaluasi akan dibagi menjadi dua tahap pengujian utama:

#### Tahap A: Pengujian Fungsional (Functional Testing)
*   **Metode**: Black Box Testing (Pengujian berbasis input-output tanpa melihat kode program).
*   **Pelaksana**: Tim Pengembang / QA Tester.
*   **Fokus**: Memastikan logika sistem benar (contoh: stok buku berkurang otomatis saat dipinjam).
*   **Instrumen**: Tabel Test Case.

#### Tahap B: Pengujian Pengguna (Usability Testing)
*   **Metode**: System Usability Scale (SUS).
*   **Pelaksana**: Pengguna Akhir (End-User).
*   **Fokus**: Persepsi pengguna terhadap kemudahan antarmuka.
*   **Instrumen**: Kuesioner SUS & Skenario Tugas.

### 2.3. Detail Pelaksanaan

#### Target Responden (Untuk Tahap B)
Sesuai kebutuhan sistem perpustakaan:
*   **Pustakawan (5 Orang)**: Mewakili peran Admin/Operator.
*   **Mahasiswa (20 Orang)**: Mewakili peran Pengunjung/Peminjam.

#### Skenario Tugas (Task Scenario)
Sebelum responden mengisi kuesioner, mereka wajib melakukan simulasi penggunaan agar penilaian valid.
*   **Skenario Pustakawan**: Login -> Tambah Data Buku -> Proses Peminjaman Mahasiswa -> Cetak Laporan.
*   **Skenario Mahasiswa**: Login -> Cari Judul Buku -> Lihat Detail Buku -> Cek Riwayat Peminjaman -> Logout.
