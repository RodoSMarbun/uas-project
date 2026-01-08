---
id: konteks-sistem
sidebar_position: 2
title: Konteks & Kebutuhan Sistem
---

# Konteks & Kebutuhan Sistem

## 1. Latar Belakang dan Konteks Bisnis
Pengembangan Sistem Informasi Perpustakaan ini bertujuan untuk menunjang efisiensi operasional perpustakaan di lingkungan kampus. Sistem dirancang untuk menggantikan atau menyempurnakan proses manual menjadi proses digital yang terintegrasi.

Secara teknis, sistem ini dibangun dengan arsitektur yang memungkinkan pertukaran data secara *loose-coupled*. Salah satu implementasi kuncinya adalah integrasi dengan data Biro Administrasi Akademik (BAA). Integrasi ini berfungsi untuk memvalidasi status keaktifan mahasiswa secara otomatis (simulasi), memastikan bahwa layanan sirkulasi hanya dapat diakses oleh civitas akademika yang berstatus aktif.

## 2. Profil Singkat Lingkungan / Organisasi Pengguna
Sistem akan diimplementasikan di Politeknik Wilmar Bisnis Indonesia (PWBI). Lingkungan operasional mencakup:

*   **Unit Perpustakaan**: Sebagai pusat pengelolaan data buku fisik dan transaksi harian.
*   **Civitas Akademika**: Terdiri dari Mahasiswa dan Dosen sebagai pengguna layanan utama yang membutuhkan akses cepat terhadap katalog dan status peminjaman.
*   **Lingkungan Transaksional**: Berfokus pada meja sirkulasi (*circulation desk*) dimana interaksi peminjaman, pengembalian, dan pembayaran denda tunai terjadi.

## 3. Stakeholder Utama
Pihak-pihak yang memiliki kepentingan dan pengaruh langsung terhadap kesuksesan pengembangan sistem ini meliputi:

*   **Project Sponsor**: Wakil Direktur Bidang Akademik (Penanggung jawab keselarasan sistem dengan tujuan akademik).
*   **Process Owner**: Kepala Perpustakaan PWBI (Pemilik kebijakan operasional, seperti aturan denda dan durasi peminjaman).
*   **User Representative**: Himpunan Mahasiswa / HIMA (Mewakili kebutuhan dan pengalaman pengguna akhir).

## 4. Scope (Batasan Sistem)
Untuk memastikan pengembangan yang terarah, berikut adalah batasan ruang lingkup fungsional sistem:

### A. In-Scope (Fokus Pengembangan)
Sistem mencakup modul-modul esensial berikut:

*   ✅ **Manajemen Katalog (Inventory)**: Pengelolaan data pustaka fisik meliputi input, edit, dan hapus data buku.
*   ✅ **Manajemen Keanggotaan**: Pengelolaan data induk anggota (Mahasiswa dan Dosen) dengan kemampuan Create, Read, Update, Delete (CRUD).
*   ✅ **Modul Sirkulasi**: Penanganan siklus transaksi peminjaman dan pengembalian buku fisik.
*   ✅ **Logika Bisnis Denda**: Kalkulasi otomatis biaya denda berdasarkan keterlambatan pengembalian sesuai aturan perpustakaan.
*   ✅ **OPAC (Online Public Access Catalog)**: Fitur pencarian katalog buku yang dapat diakses secara mandiri oleh anggota.
*   ✅ **Pelaporan Dasar**: Penyediaan laporan rekapitulasi jumlah peminjaman bulanan untuk keperluan manajerial.

### B. Out-of-Scope (Tidak Termasuk Pengembangan)
Fitur-fitur berikut berada di luar cakupan rilis saat ini:

*   ❌ **Digital Library Reader**: Sistem tidak menyediakan fitur membaca konten digital (e-book/pdf) di dalam aplikasi.
*   ❌ **Payment Gateway**: Pembayaran denda dilakukan secara tunai (*cash-only*) di meja petugas; sistem hanya mencatat perubahan status pembayaran.
*   ❌ **Hardware Integration (RFID)**: Belum mendukung integrasi dengan sensor keamanan gerbang (*gate*) maupun tagging buku berbasis RFID.
*   ❌ **Modul Pengadaan (Procurement)**: Proses bisnis pembelian buku dari vendor ke perpustakaan tidak ditangani oleh sistem ini.
