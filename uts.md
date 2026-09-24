# UJIAN TENGAH SEMESTER (UTS)

## Mata Kuliah: Basis Data / Database

**Waktu:** 120 menit  
**Bentuk:** Praktik Individu  
**Total Nilai:** 100

---

# CPMK

## CPMK 1

Mampu merancang, membangun, dan mengelola basis data relasional menggunakan Microsoft Access, termasuk tabel, relasi, query, form, dan report, sesuai kaidah pengelolaan data administrasi perkantoran.

## CPMK 2

Mampu mengelola basis data pada layanan cloud **Neon.Tech/PostgreSQL** serta mengintegrasikannya dengan Microsoft Access.

---

# STUDI KASUS

Sebuah toko membutuhkan sistem database sederhana untuk mengelola:

- Barang
- Pelanggan
- Transaksi penjualan

Database terdiri dari tiga tabel berikut.

## 1. Tabel `barang`

| Field | Keterangan |
|---|---|
| `idbarang` | Kode barang |
| `namabarang` | Nama barang |
| `harga` | Harga barang |
| `stok` | Jumlah stok |
| `kategori` | Kategori barang |

## 2. Tabel `pelanggan`

| Field | Keterangan |
|---|---|
| `idpelanggan` | Kode pelanggan |
| `nama` | Nama pelanggan |
| `alamat` | Alamat pelanggan |
| `kota` | Kota pelanggan |

## 3. Tabel `transaksi`

| Field | Keterangan |
|---|---|
| `idtransaksi` | Nomor transaksi |
| `idbarang` | Barang yang dibeli |
| `idpelanggan` | Pelanggan yang melakukan transaksi |
| `jumlah` | Jumlah barang yang dibeli |
| `tanggal` | Tanggal transaksi |

---

# BAGIAN A — IMPORT DATA KE NEON.TECH

**20 poin | ±20 menit**

Dosen menyediakan file:

```text
data_penjualan.xlsx
```

File tersebut terdiri dari tiga sheet:

- `barang`
- `pelanggan`
- `transaksi`

Data pada file tersebut belum sepenuhnya memiliki struktur dan tipe data yang sesuai untuk digunakan sebagai database relasional.

## 1. Membuat Database Neon.Tech

**3 poin**

Buat sebuah project/database PostgreSQL pada Neon.Tech.

Gunakan nama database/project:

```text
uts_NIM
```

## 2. Import Data

**5 poin**

Import ketiga sheet dari file Excel ke database Neon.Tech sehingga terbentuk tiga tabel:

```text
barang
pelanggan
transaksi
```

Pastikan seluruh data berhasil diimport.

## 3. Memeriksa dan Memperbaiki Tipe Data

**12 poin**

Periksa struktur ketiga tabel setelah proses import.

Identifikasi field yang memiliki tipe data yang belum sesuai dengan karakteristik datanya.

Perbaiki tipe data setiap field agar sesuai dengan kebutuhan database dan dapat digunakan dengan baik oleh Microsoft Access.

Sebagai contoh, field yang awalnya bertipe:

```text
TEXT
```

dapat diubah menjadi tipe data yang lebih sesuai, seperti:

```text
VARCHAR(n)
INTEGER
NUMERIC
DATE
```

Gunakan pertimbangan berikut.

### Tabel `barang`

| Field | Tipe Data yang Sesuai |
|---|---|
| `idbarang` | Tipe data teks dengan panjang yang sesuai |
| `namabarang` | Tipe data teks |
| `harga` | Tipe data numerik |
| `stok` | Tipe data bilangan bulat |
| `kategori` | Tipe data teks |

### Tabel `pelanggan`

| Field | Tipe Data yang Sesuai |
|---|---|
| `idpelanggan` | Tipe data teks |
| `nama` | Tipe data teks |
| `alamat` | Tipe data teks |
| `kota` | Tipe data teks |

### Tabel `transaksi`

| Field | Tipe Data yang Sesuai |
|---|---|
| `idtransaksi` | Tipe data teks |
| `idbarang` | Tipe data teks |
| `idpelanggan` | Tipe data teks |
| `jumlah` | Tipe data bilangan bulat |
| `tanggal` | Tipe data tanggal |

> **Catatan:** Tentukan sendiri ukuran `VARCHAR(n)` yang sesuai berdasarkan karakteristik data.

---

# BAGIAN B — PRIMARY KEY, FOREIGN KEY, DAN RELATIONSHIP

**20 poin | ±20 menit**

Berdasarkan struktur dan isi data pada ketiga tabel, lakukan analisis untuk menentukan struktur database relasional yang tepat.

## 4. Menentukan Primary Key

**7 poin**

Tentukan **Primary Key** yang tepat untuk masing-masing tabel:

```text
barang
pelanggan
transaksi
```

Primary Key harus memenuhi prinsip:

- dapat mengidentifikasi record secara unik;
- tidak boleh memiliki nilai duplikat;
- tidak boleh bernilai `NULL`.

Terapkan Primary Key tersebut pada database PostgreSQL di Neon.Tech.

## 5. Menentukan Foreign Key

**7 poin**

Identifikasi field yang dapat digunakan sebagai **Foreign Key** berdasarkan hubungan antar data.

Tentukan Foreign Key yang diperlukan untuk membentuk database relasional yang benar.

Foreign Key harus memastikan bahwa:

- setiap transaksi mengacu pada data yang valid;
- tidak terdapat referensi ke data barang yang tidak tersedia;
- tidak terdapat referensi ke data pelanggan yang tidak tersedia;
- referential integrity tetap terjaga.

Terapkan Foreign Key tersebut pada database PostgreSQL di Neon.Tech.

> **Perhatian:** Jangan membuat field baru. Gunakan field yang sudah tersedia pada tabel.

## 6. Membuat Relationship

**6 poin**

Berdasarkan Primary Key dan Foreign Key yang telah Anda tentukan:

1. Tentukan tabel yang menjadi **parent table**.
2. Tentukan tabel yang menjadi **child table**.
3. Tentukan jenis relationship antar tabel.
4. Tentukan field yang digunakan untuk menghubungkan tabel.
5. Terapkan relationship tersebut pada database.
6. Pastikan relationship yang dibuat menjaga **referential integrity**.

Gambarkan relationship secara sederhana.

Contoh format:

```text
[TABEL A]
    │
    │ 1 : N
    │
[TABEL B]
```

> **Catatan:** Field Primary Key, Foreign Key, dan hubungan antar tabel **tidak diberikan dalam soal**. Mahasiswa harus menganalisisnya berdasarkan struktur dan makna data.

---

# BAGIAN C — INTEGRASI NEON.TECH DENGAN MICROSOFT ACCESS

**15 poin | ±15 menit**

## 7. Konfigurasi ODBC

**5 poin**

Konfigurasikan koneksi **ODBC** agar Microsoft Access dapat terhubung dengan database PostgreSQL pada Neon.Tech.

Gunakan informasi koneksi yang tersedia pada Neon.Tech.

Pastikan koneksi dapat digunakan oleh Microsoft Access.

## 8. Membuat Linked Table

**10 poin**

Buat database Microsoft Access dengan nama:

```text
UTS_NIM_Nama.accdb
```

Hubungkan tabel dari database Neon.Tech ke Microsoft Access menggunakan mekanisme **Linked Table**.

Tabel yang harus tersedia di Microsoft Access:

```text
barang
pelanggan
transaksi
```

Pastikan data yang tampil pada Microsoft Access berasal dari database PostgreSQL/Neon.Tech.

> **Penting:** Jangan membuat ulang ketiga tabel secara manual di Microsoft Access. Gunakan tabel yang terhubung dari database Neon.Tech.

---

# BAGIAN D — QUERY MICROSOFT ACCESS

**20 poin | ±25 menit**

Gunakan tabel yang telah di-link dari Neon.Tech.

## 9. Query Daftar Transaksi

**7 poin**

Buat query dengan nama:

```text
Q_DaftarTransaksi
```

Query harus menampilkan informasi:

- ID Transaksi
- Tanggal
- Nama Pelanggan
- Nama Barang
- Harga
- Jumlah
- Kategori

Gunakan relationship antar tabel untuk memperoleh data dari:

- `transaksi`
- `barang`
- `pelanggan`

## 10. Query Total Transaksi

**7 poin**

Buat query dengan nama:

```text
Q_TotalTransaksi
```

Query harus menampilkan:

- ID Transaksi
- Tanggal
- Nama Pelanggan
- Nama Barang
- Harga
- Jumlah
- Total

Hitung nilai `Total` dengan rumus:

```text
Total = Harga × Jumlah
```

Gunakan **Calculated Field** pada Microsoft Access.

## 11. Query Rekap Penjualan Barang

**6 poin**

Buat query dengan nama:

```text
Q_RekapPenjualanBarang
```

Query harus menampilkan:

- Nama Barang
- Kategori
- Total Jumlah Terjual
- Total Nilai Penjualan

Gunakan fungsi agregat:

```text
SUM()
```

Lakukan grouping berdasarkan barang.

---

# BAGIAN E — FORM MICROSOFT ACCESS

**10 poin | ±15 menit**

Buat form dengan nama:

```text
F_Transaksi
```

Form digunakan untuk menampilkan dan/atau menginput data transaksi.

Form minimal menampilkan:

- ID Transaksi
- Tanggal
- Nama Barang
- Nama Pelanggan
- Jumlah
- Harga
- Total

Jika memungkinkan, gunakan **Combo Box** untuk pemilihan:

- Barang
- Pelanggan

Form harus menggunakan data yang berasal dari database Neon.Tech melalui Linked Table.

## Penilaian

| Komponen | Nilai |
|---|---:|
| Form berhasil dibuat | 2 |
| Field sesuai kebutuhan | 2 |
| Pemilihan barang/pelanggan | 2 |
| Calculated Total | 2 |
| Kerapian tampilan | 2 |
| **Total** | **10** |

---

# BAGIAN F — REPORT MICROSOFT ACCESS

**15 poin | ±20 menit**

Buat report dengan nama:

```text
R_LaporanPenjualan
```

Gunakan:

```text
Q_TotalTransaksi
```

sebagai sumber data report.

## Judul Report

Gunakan judul:

```text
LAPORAN PENJUALAN
```

Report minimal menampilkan:

- ID Transaksi
- Tanggal
- Nama Pelanggan
- Nama Barang
- Jumlah
- Harga
- Total

## Grouping

Report dikelompokkan berdasarkan:

```text
Kategori Barang
```

## Footer

Tambahkan:

```text
Total Nilai Penjualan
```

Gunakan fungsi agregat yang sesuai.

## Penilaian

| Komponen | Nilai |
|---|---:|
| Report berhasil dibuat | 3 |
| Data sesuai query | 3 |
| Grouping | 3 |
| Total penjualan | 3 |
| Header/footer dan kerapian | 3 |
| **Total** | **15** |

---

# REKAPITULASI NILAI

| Bagian | Materi | CPMK | Nilai | Waktu |
|---|---|---|---:|---:|
| A | Import & perbaikan tipe data Neon | CPMK 2 | 20 | 20 menit |
| B | Primary Key, Foreign Key & Relationship | CPMK 2 | 20 | 20 menit |
| C | ODBC & Linked Table | CPMK 2 | 15 | 15 menit |
| D | Query Access | CPMK 1 | 20 | 25 menit |
| E | Form Access | CPMK 1 | 10 | 15 menit |
| F | Report Access | CPMK 1 | 15 | 20 menit |
| **TOTAL** | | | **100** | **115 menit** |

**Sisa waktu:** 5 menit untuk pengecekan dan pengumpulan.

**Total waktu UTS: 120 menit**

---

# ALUR PENGERJAAN

Mahasiswa wajib mengikuti tahapan berikut:

```text
DATA EXCEL
    │
    ▼
IMPORT KE NEON.TECH
    │
    ▼
PERIKSA TIPE DATA
    │
    ▼
PERBAIKI TIPE DATA
    │
    ├── TEXT → VARCHAR(n)
    ├── TEXT → INTEGER
    ├── TEXT → NUMERIC
    └── TEXT → DATE
    │
    ▼
ANALISIS PRIMARY KEY
    │
    ▼
ANALISIS FOREIGN KEY
    │
    ▼
BUAT RELATIONSHIP
    │
    ▼
VERIFIKASI REFERENTIAL INTEGRITY
    │
    ▼
KONEKSI ODBC
    │
    ▼
LINK TABLE KE MICROSOFT ACCESS
    │
    ▼
BUAT QUERY
    │
    ├── Q_DaftarTransaksi
    ├── Q_TotalTransaksi
    └── Q_RekapPenjualanBarang
    │
    ▼
BUAT FORM
    │
    └── F_Transaksi
    │
    ▼
BUAT REPORT
    │
    └── R_LaporanPenjualan
```

---

# PENGUMPULAN

Pada akhir ujian, mahasiswa mengumpulkan **2 item**.

## 1. Link Database Neon.Tech

Kumpulkan **link database Neon.Tech** yang dapat digunakan dosen untuk melakukan pemeriksaan.

Informasi akses yang diperlukan untuk pemeriksaan juga harus disertakan, termasuk **password/database credential** sesuai instruksi dosen.

Pastikan database masih aktif dan dapat diakses saat proses pemeriksaan.

> **Saran:** Gunakan credential khusus untuk keperluan UTS, bukan password akun pribadi yang digunakan untuk layanan lain.

## 2. Database Microsoft Access

Kumpulkan database:

```text
UTS_NIM_Nama.accdb
```

dalam bentuk ZIP:

```text
UTS_NIM_Nama.zip
```

File ZIP harus berisi database Microsoft Access yang telah selesai dikerjakan.

---

# KETENTUAN UJIAN

1. UTS dikerjakan secara **individu**.
2. Gunakan akun Neon.Tech masing-masing.
3. Gunakan file data yang diberikan oleh dosen.
4. Jangan mengubah isi data sumber kecuali diperlukan untuk memperbaiki tipe atau struktur database.
5. Jangan membuat ulang tabel secara manual di Microsoft Access.
6. Microsoft Access harus menggunakan **Linked Table** dari database Neon.Tech.
7. Primary Key dan Foreign Key harus ditentukan berdasarkan analisis mahasiswa.
8. Relationship harus dibuat berdasarkan struktur dan makna data.
9. Pastikan database Neon.Tech dapat diakses oleh dosen pada saat pemeriksaan.
10. Pastikan file Microsoft Access dapat dibuka setelah diekstrak dari ZIP.
11. Nama file harus mengikuti format:

```text
UTS_NIM_Nama.zip
```

12. Gunakan waktu ujian secara efektif.
