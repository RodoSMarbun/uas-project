---
id: usecase
sidebar_position: 1
title: Use Case Diagram
---

# Use Case Diagram

Analisis Use Case menggambarkan interaksi fungsional antara aktor (pengguna) dengan sistem.

## Diagram Use Case

![Use Case Diagram](/img/usecase_diagram.png)

## Deskripsi Detail Use Case

Berikut adalah spesifikasi detail untuk Use Case utama.

### UC-01: Register
**Aktor**: Anggota
**Tujuan**: Mendaftarkan akun baru bagi anggota yang belum terdaftar.
**Pre-condition**: Pengguna belum memiliki akun.
**Alur Normal**:
1.  Calon anggota memilih menu "Daftar Akun".
2.  Sistem menampilkan form registrasi.
3.  Anggota mengisi data diri (NIM/NIDN, Nama, Password).
4.  Sistem memvalidasi data.
5.  Sistem menyimpan data anggota baru.
6.  Sistem mengarahkan ke halaman Login.

### UC-02: Login (Include Reset Password)
**Aktor**: Anggota, Pustakawan, Kepala Perpus
**Tujuan**: Masuk ke dalam sistem (Otentikasi) dan akses pemulihan sandi.
**Hubungan**: Include "Reset Password".
**Alur Normal**:
1.  Aktor mengakses halaman utama.
2.  Sistem menampilkan form login.
3.  Aktor memasukkan Username dan Password.
4.  Sistem memvalidasi kredensial.
5.  Sistem memberikan akses dashboard sesuai peran (Role).
**Sub-Alur (Reset Password)**:
*   Jika aktor lupa sandi, aktor memilih fitur "Reset Password" di halaman login.
*   Sistem memverifikasi email/identitas aktor.
*   Aktor memasukkan password baru.
*   Sistem memperbarui kredensial.

### UC-03: Cari Buku
**Aktor**: Anggota
**Tujuan**: Menemukan informasi buku di katalog perpustakaan.
**Alur Normal**:
1.  Anggota memilih menu pencarian.
2.  Anggota memasukkan kata kunci judul atau pengarang.
3.  Sistem menampilkan daftar buku beserta status ketersediaannya.

### UC-04: Pinjam Buku
**Aktor**: Anggota
**Tujuan**: Mengajukan permohonan peminjaman buku (Booking/Reservasi).
**Catatan**: Berbeda dengan "Kelola Peminjaman", ini adalah aksi dari sisi Anggota.
**Alur Normal**:
1.  Anggota memilih buku yang tersedia dari hasil pencarian.
2.  Anggota menekan tombol "Pinjam".
3.  Sistem mencatat permintaan peminjaman.
4.  Sistem memberikan kode booking/batas waktu pengambilan fisik buku.

### UC-05: Kelola Peminjaman
**Aktor**: Pustakawan
**Tujuan**: Memproses serah terima fisik buku (Validasi peminjaman).
**Alur Normal**:
1.  Anggota menyerahkan buku/kode booking ke meja sirkulasi.
2.  Pustakawan memvalidasi data anggota.
3.  Pustakawan mengkonfirmasi transaksi di sistem.
4.  Sistem mengubah status buku menjadi "Dipinjam" dan mengurangi stok.

### UC-06: Kelola Pengembalian
**Aktor**: Pustakawan
**Tujuan**: Memproses pengembalian buku fisik dan cek denda.
**Alur Normal**:
1.  Pustakawan menerima buku dari anggota.
2.  Pustakawan memindai barcode buku.
3.  Sistem menampilkan rincian keterlambatan (jika ada).
4.  Pustakawan menyimpan transaksi pengembalian.
5.  Sistem memperbarui stok buku menjadi tersedia kembali.

### UC-07: Kelola Data Buku
**Aktor**: Pustakawan
**Tujuan**: Menambah, mengubah, atau menghapus data koleksi buku.
**Alur Normal**:
1.  Pustakawan masuk ke menu "Master Data".
2.  Pustakawan menginput detail buku baru (ISBN, Judul, Penerbit).
3.  Sistem memvalidasi dan menyimpan data ke database.

### UC-08: Lihat Laporan
**Aktor**: Pustakawan, Kepala Perpus
**Tujuan**: Memantau aktivitas perpustakaan melalui rekap data.
**Alur Normal**:
1.  Aktor memilih menu "Laporan".
2.  Sistem menampilkan dashboard statistik (jumlah peminjaman, buku populer, denda).
3.  Aktor dapat mengunduh laporan dalam format cetak/PDF.
