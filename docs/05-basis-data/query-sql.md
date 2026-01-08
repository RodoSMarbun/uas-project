---
id: query-sql
sidebar_position: 3
title: Query SQL (Implementation)
---

# Query SQL Implementation


### 1. Menambah Anggota Baru (CREATE)
```sql
INSERT INTO anggota (nim, nama, jurusan, no_hp, password) 
VALUES ('220101099', 'Dedi Mulyadi', 'Manajemen Informatika', '081299998888', 'hashed_pass_999');
```

### 2. Update Stok Buku (UPDATE)
Mengurangi stok buku saat terjadi peminjaman.
```sql
UPDATE buku 
SET stok = stok - 1 
WHERE isbn = '978-602-1234-56-7';
```

### 3. Hapus Data Buku (DELETE)
```sql
DELETE FROM buku WHERE isbn = '978-602-1234-xx-x';
```

### 4. Pencarian Buku berdasarkan Judul (READ)
Mencari buku yang mengandung kata "Pemrograman".
```sql
SELECT judul, pengarang, stok, nama_kategori
FROM buku
JOIN kategori ON buku.id_kategori = kategori.id_kategori
WHERE judul LIKE '%Pemrograman%';
```

### 5. Daftar Buku yang Sedang Dipinjam (JOIN 3 Tabel)
Menampilkan siapa meminjam apa.
```sql
SELECT 
    p.id_peminjaman,
    a.nama AS nama_peminjam,
    b.judul AS judul_buku,
    p.tgl_jatuh_tempo
FROM peminjaman p
JOIN detail_peminjaman dp ON p.id_peminjaman = dp.id_peminjaman
JOIN buku b ON dp.isbn = b.isbn
JOIN anggota a ON p.nim = a.nim
WHERE p.status = 'Dipinjam';
```

### 6. Menghitung Total Denda per Bulan (AGGREGATION - SUM)
Laporan pendapatan denda bulan Januari 2024.
```sql
SELECT SUM(total_denda) AS total_pendapatan_denda
FROM pengembalian
WHERE MONTH(tgl_kembali) = 01 AND YEAR(tgl_kembali) = 2024;
```

### 7. Statistik Buku Paling Populer (AGGREGATION - COUNT)
Menampilkan 5 buku yang paling sering dipinjam.
```sql
SELECT 
    b.judul, 
    COUNT(dp.isbn) AS jumlah_peminjaman
FROM detail_peminjaman dp
JOIN buku b ON dp.isbn = b.isbn
GROUP BY dp.isbn, b.judul
ORDER BY jumlah_peminjaman DESC
LIMIT 5;
```

### 8. Cek Keterlambatan (DATEDIFF)
Menampilkan peminjaman yang sudah lewat jatuh tempo hari ini.
```sql
SELECT 
    id_peminjaman, 
    tgl_jatuh_tempo, 
    DATEDIFF(CURRENT_DATE, tgl_jatuh_tempo) AS telat_hari
FROM peminjaman
WHERE status = 'Dipinjam' AND tgl_jatuh_tempo < CURRENT_DATE;
```

### 9. Jumlah Peminjaman per Jurusan Mahasiswa (GROUP BY)
```sql
SELECT 
    a.jurusan, 
    COUNT(p.id_peminjaman) AS total_transaksi
FROM peminjaman p
JOIN anggota a ON p.nim = a.nim
GROUP BY a.jurusan;
```

### 10. Melihat Detail Koleksi Lengkap (LEFT JOIN)
Menampilkan semua kategori, termasuk yang belum memiliki buku (untuk evaluasi koleksi).
```sql
SELECT 
    k.nama_kategori, 
    COUNT(b.isbn) AS jumlah_judul_buku
FROM kategori k
LEFT JOIN buku b ON k.id_kategori = b.id_kategori
GROUP BY k.id_kategori, k.nama_kategori;
```
