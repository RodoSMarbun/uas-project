---
id: hi-fi-ui
sidebar_position: 4
title: High-Fidelity & Design System
---

# High-Fidelity UI & Design System

## 1. Analisis Warna (Color Palette)
**Spesifikasi Teks**: Primary Blue (`#0056D2`), Background (`#FFFFFF` & `#F3F4F6`).

### Kondisi Visual (Mobile - Image 1, 2, 3):
Aplikasi Mobile menggunakan Full Block Blue Background yang sangat dominan. Ini membuat mata cepat lelah dan tidak sesuai dengan spesifikasi Background (Putih bersih/Abu-abu muda).

Kontras teks pada tombol kategori (Image 1 & 3) sudah cukup baik, tetapi background layar yang biru total menabrak prinsip "Clean" dari High-Fidelity.

### Kondisi Visual (Web - Image 4):
Tampilan Web sudah jauh lebih sesuai. Background utama abu-abu muda/putih, dengan aksen biru pada header. Ini terlihat profesional.

> [!WARNING]
> **Tindakan Perbaikan:**
> *   **Mobile**: Ubah background halaman Login, Register, dan Home menjadi Putih (`#FFFFFF`) atau Abu-abu sangat muda (`#F3F4F6`). Gunakan warna Biru (`#0056D2`) hanya pada Header (Navbar atas) dan Tombol (Button).

## 2. Analisis Tipografi (Typography)
**Spesifikasi Teks**: Font **Inter** atau **Roboto** (Sans-serif) untuk semua teks.

### Kondisi Visual:
Pada layar Login & Register (Image 2), tulisan "WBI Library" di bawah logo menggunakan font jenis **Serif** (mirip Times New Roman). Ini tidak konsisten dengan logo "WBI" di atasnya yang Sans-serif, dan melanggar aturan tipografi yang telah ditetapkan.

> [!WARNING]
> **Tindakan Perbaikan:**
> *   Ganti font "WBI Library" di layar Login/Register menjadi **Inter** atau **Roboto** (Sans-serif) dengan ketebalan Medium atau Semi-Bold.

## 3. Komponen UI & Layout

### A. Kartu Buku (Book Card)
**Spesifikasi Teks**: Cover di kiri, Judul di kanan (List view), ada Badge stok, ada tombol "Lihat Detail".

#### Kondisi Visual (Image 1):
Tampilan saat ini menggunakan **Grid View** (hanya cover buku berjejer). Tidak ada judul teks di kanan, tidak ada badge stok, dan tidak ada tombol "Lihat Detail".

> [!WARNING]
> **Tindakan Perbaikan:**
> *   Ubah layout "Terbaru" dari Grid menjadi **List View**.
> *   **Layout**: Gambar kecil di kiri, Judul dan Penulis di kanan, Badge status (Hijau/Merah) di pojok kanan atas kartu, dan tombol outline "Lihat Detail" di bawah judul.

### B. Form Input (Login/Register)
**Spesifikasi Teks**: Border radius 8px, Border color `#D1D5DB`.

#### Kondisi Visual (Image 2):
*   Input field terlihat kaku (radius sudut sangat kecil atau 0px).
*   Label "Email", "Kata Sandi" berada di dalam placeholder (akan hilang saat diketik), padahal deskripsi menyarankan label yang jelas (Medium, 12px).

> [!WARNING]
> **Tindakan Perbaikan:**
> *   Pindahkan label ke **atas** kolom input (bukan sebagai placeholder).
> *   Perbesar **Border Radius menjadi 8px** agar terlihat lebih modern dan ramah (sesuai spesifikasi).

### C. Navigasi & Dashboard Admin
#### Kondisi Visual (Image 4):
Halaman "Laporan" sudah terlihat sangat bagus dan paling mendekati spesifikasi. Sidebar di kiri dan konten di kanan.

**Catatan pada Status Badge**: Warna badge pada tabel ("Terlambat", "Sudah Kembali") terlihat menggunakan warna pastel (Pink/Hijau muda). Pastikan kode warnanya disinkronkan dengan palet Success Green (`#22C55E`) dan Danger Red (`#EF4444`) agar konsisten, atau gunakan varian pastel tersebut secara resmi dalam Design System.

## 4. Usability & Konsistensi
*   **Tombol Navigasi Mobile**: Pada Image 1, ikon navigasi bawah (Home, Search, Menu, Notif) terlihat agak besar dan tidak proporsional dengan area putihnya.
*   **Search Bar (Image 3)**: Ikon "X" pada search bar terlihat sedikit terpotong atau terlalu mepet ke kanan. Berikan padding yang cukup.
