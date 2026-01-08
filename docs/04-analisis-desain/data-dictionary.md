---
id: data-dictionary
sidebar_position: 3
title: Data Dictionary
---

# Data Dictionary (Kamus Data)

Dokumen ini menjelaskan detail metadata dari setiap entitas data yang digunakan dalam sistem, untuk memastikan konsistensi pengembangan.

### 1. Entitas: BUKU
| Atribut | Tipe Data | Size | Keterangan | Validasi / Aturan |
| :--- | :--- | :--- | :--- | :--- |
| isbn | Varchar | 20 | Primary Key | Format ISBN-13 atau ISBN-10 |
| judul | Varchar | 200 | - | Tidak boleh kosong |
| pengarang | Varchar | 100 | - | - |
| stok | Integer | - | Jumlah fisik | Minimal 0 |
| id_kategori | Integer | - | Foreign Key | Harus ada di tabel Kategori |

### 2. Entitas: ANGGOTA
| Atribut | Tipe Data | Size | Keterangan | Validasi / Aturan |
| :--- | :--- | :--- | :--- | :--- |
| nim | Varchar | 20 | Primary Key | Unik |
| nama | Varchar | 100 | - | Hanya huruf dan spasi |
| no_hp | Varchar | 15 | - | Format numerik 08... |
| status_aktif| Enum | 1 | 'Y' atau 'N' | Default 'Y' |

### 3. Entitas: PEMINJAMAN
| Atribut | Tipe Data | Size | Keterangan | Validasi / Aturan |
| :--- | :--- | :--- | :--- | :--- |
| id_peminjaman | Varchar | 20 | Primary Key | Format TRX-YYYYMMDD-XXX |
| tgl_pinjam | Date | - | - | Default Today |
| tgl_jatuh_tempo| Date | - | - | Default Today + 7 days |
| nim | Varchar | 20 | Foreign Key | Anggota harus aktif |

### 4. Entitas: DETAIL_PEMINJAMAN
| Atribut | Tipe Data | Size | Keterangan | Validasi / Aturan |
| :--- | :--- | :--- | :--- | :--- |
| id_detail | Integer | - | Primary Key | Auto Increment |
| id_peminjaman | Varchar | 20 | Foreign Key | - |
| isbn | Varchar | 20 | Foreign Key | Buku harus available saat insert |

### 5. Entitas: PENGEMBALIAN
| Atribut | Tipe Data | Size | Keterangan | Validasi / Aturan |
| :--- | :--- | :--- | :--- | :--- |
| id_pengembalian | Varchar | 20 | Primary Key | - |
| tgl_kembali | Date | - | - | - |
| total_denda | Decimal | 10,2 | - | Calculated field (TglKembali - JatuhTempo) * Tarif |
