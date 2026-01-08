---
id: erd
sidebar_position: 1
title: Entity Relationship Diagram (ERD)
---

# Entity Relationship Diagram (ERD)


## Diagram ERD

![ER Diagram](/img/erd_diagram.png)

## Penjelasan Kardinalitas

1.  **Anggota - Peminjaman (1:N)**
    *   Satu anggota dapat melakukan banyak transaksi peminjaman.
    *   Satu transaksi peminjaman hanya milik satu anggota.
2.  **Peminjaman - Detail Peminjaman (1:N)**
    *   Satu struk peminjaman bisa terdiri dari banyak buku (Detail).
3.  **Buku - Detail Peminjaman (1:N)**
    *   Satu buku bisa muncul di banyak riwayat detail peminjaman.
4.  **Kategori - Buku (1:N)**
    *   Satu kategori memiliki banyak buku.
    *   Satu buku hanya memiliki satu kategori utama.
5.  **Peminjaman - Pengembalian (1:N)**
    *   *Catatan*: Biasanya 1:1 jika dikembalikan sekaligus, namun 1:N jika pengembalian dicicil. Dalam desain ini diasumsikan 1 peminjaman terkait dengan record pengembalian.
