# <p align="center" style="margin-bottom: 0px;">SIPAGI</p>
## <p align="center" style="margin-top: 0;">SISTEM PENJADWALAN GUDANG GABAH TERINTEGRASI</p>

<p align="center">
  <img src="Logo Unsulbar.png" width="300" alt="Deskripsi gambar" />
</p>

### <p align="center">AHMAD KHANIF IZZAH ARIFIN</p>
### <p align="center">D0223511</p></br>
### <p align="center">Framework Web Based</p>
### <p align="center">2025</p>


## Role dan fitur-fiturnya

### 1. Admin
- CRUD (tambah, lihat, ubah, hapus) data buku
- CRUD (tambah, lihat, ubah, hapus) data petugas
- Melihat laporan peminjaman

### 2. Petugas
- CRUD (tambah, lihat, ubah, hapus) data anggota
- CRUD (tambah, lihat, ubah, hapus) data peminjaman dan pengembalian buku

### 3. Anggota
- Melihat daftar buku
- Melihat riwayat peminjaman
- Update profil sendiri (lihat, edit)

## Tabel-tabel database beserta field dan tipe datanya

### Tabel: anggota

| Field       | Tipe Data     | Keterangan       |
|-------------|---------------|------------------|
| id_anggota  | INT           | Primary Key      |
| nama        | VARCHAR(100)  | Nama anggota     |
| username    | VARCHAR(50)   | Login            |
| password    | VARCHAR(100)  | Password login   |

### Tabel: buku

| Field     | Tipe Data     | Keterangan       |
|-----------|---------------|------------------|
| id_buku   | INT           | Primary Key      |
| judul     | VARCHAR(100)  | Judul buku       |
| stok      | INT           | Jumlah tersedia  |

### Tabel: petugas

| Field       | Tipe Data     | Keterangan       |
|-------------|---------------|------------------|
| id_petugas  | INT           | Primary Key      |
| nama        | VARCHAR(100)  | Nama petugas     |
| username    | VARCHAR(50)   | Login            |
| password    | VARCHAR(100)  | Password login   |

### Tabel: peminjaman

| Field           | Tipe Data   | Keterangan             |
|------------------|-------------|-------------------------|
| id_pinjam        | INT         | Primary Key            |
| id_anggota       | INT         | FK ke tabel anggota    |
| id_buku          | INT         | FK ke tabel buku       |
| tanggal_pinjam   | DATE        | Tanggal peminjaman     |
| tanggal_kembali  | DATE        | Tanggal pengembalian   |

## Jenis relasi dan tabel yang berelasi

| Tabel 1  | Relasi | Tabel 2     | Keterangan                             |
|----------|--------|-------------|----------------------------------------|
| anggota  | 1 : N  | peminjaman  | Satu anggota bisa meminjam banyak buku |
| buku     | 1 : N  | peminjaman  | Satu buku bisa dipinjam berkali-kali   |
| petugas  | 1 : N  | anggota     | Satu petugas bisa mengelola banyak anggota (opsional) |
