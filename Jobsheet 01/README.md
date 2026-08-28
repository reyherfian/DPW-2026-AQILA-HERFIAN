# Ringkasan: Konsep Dasar HTML (Jobsheet 1)

### 1. Tag vs Elemen
- **Tag**: Sintaks pembuka (`<tag>`) dan penutup (`</tag>`).
- **Elemen**: Keseluruhan isi dari tag pembuka sampai tag penutup (contoh: `<h1>SIMPUS-Mini</h1>`).

### 2. Struktur Dasar Dokumen HTML
- `<!DOCTYPE html>`: Deklarasi standar dokumen HTML5.
- `<html lang="id">`: Pembungkus utama halaman dan penentu bahasa konten (Bahasa Indonesia).
- `<head>`: Memuat metadata halaman (tidak tampil di layar), seperti:
  - `<meta charset="UTF-8">`: Standar encoding karakter.
  - `<title>`: Judul halaman pada tab browser.
- `<body>`: Memuat seluruh konten visual yang tampil di browser (teks, tautan, form, tabel).

### 3. Tag Semantik HTML5
Tag semantik digunakan untuk memberi arti/makna struktural pada konten (bukan sekadar pembungkus polos seperti `<div>`), sehingga mempermudah pembacaan kode, SEO, dan aksesibilitas (*screen reader*):
- `<header>`: Bagian kepala halaman/navigasi atas.
- `<nav>`: Area menu atau daftar tautan navigasi.
- `<main>`: Area konten utama (hanya 1 per halaman).
- `<section>`: Pengelompokan bagian konten berdasarkan tema tertentu.
- `<article>`: Blok konten mandiri (contoh: kartu statistik).
- `<footer>`: Bagian kaki halaman (hak cipta/informasi penutup).

### 4. Navigasi & Path Relatif (`<a>`)
Tautan antar-halaman menggunakan atribut `href` dengan path relatif berdasarkan lokasi file:
- **Turun folder**: `buku/list.html` (masuk ke subfolder).
- **Naik folder**: `../index.html` (naik satu tingkat folder).
- **Satu folder**: `tambah.html` (langsung nama file).

# Ringkasan: Struktur Halaman Beranda (`index.html`)

### 1. Fungsi File
- Berperan sebagai **halaman utama (entry point)** aplikasi SIMPUS-Mini yang otomatis dimuat browser saat mengakses direktori root.

### 2. Bedah Komponen Halaman
- **`<header>` & `<nav>`**: 
  - `<h1>`: Judul utama aplikasi (hanya ada 1 per halaman).
  - Menu navigasi menggunakan kombinasi `<ul>`, `<li>`, dan `<a>`. 
  - Tautan mengarah ke subfolder langsung tanpa `../` (contoh: `buku/list.html`) karena `index.html` berada di root.
- **`<main>` (Konten Utama)**:
  - **Section Sambutan**: Memuat judul sub-bagian (`<h2>`) dan deskripsi singkat sistem (`<p>`).
  - **Section Ringkasan**: Menampilkan kartu statistik dummy (*Total Buku*, *Total Anggota*, *Sedang Dipinjam*). Masing-masing dibungkus elemen semantik `<article>` (berisi `<h3>` dan `<p>`) karena informasinya bersifat mandiri (*self-contained*).
- **`<footer>`**:
  - Memuat informasi hak cipta.
  - Menggunakan **HTML Entities** untuk karakter khusus agar aman dirender browser: `&copy;` untuk simbol `©` dan `&mdash;` untuk tanda pisah panjang `—`.

### 3. Pola Template Standar
File ini menjadi acuan struktur seragam untuk halaman lainnya:  
`Header (Navigasi)` $\rightarrow$ `Main (Konten Spesifik)` $\rightarrow$ `Footer (Hak Cipta)`.

# Ringkasan: Struktur Halaman Daftar Buku (`buku/list.html`)

### 1. Fungsi File
- Menampilkan data katalog buku perpustakaan dalam bentuk **tabel HTML statis** (data dummy 5 baris).

### 2. Penyesuaian Path Navigasi
Karena file berada di dalam subfolder `buku/`, penulisan tautan navigasi (`href`) disesuaikan:
- `../index.html`: Naik satu folder ke direktori root untuk membuka Beranda.
- `list.html` & `tambah.html`: Langsung nama file (berada di folder yang sama).
- `../anggota/list.html`: Naik ke root lalu masuk ke folder `anggota/`.

### 3. Anatomi Tabel HTML (`<table>`)
Data disajikan menggunakan tag semantik tabel agar ramah aksesibilitas (*screen reader*) dan memiliki relasi baris-kolom yang jelas:
- `<table>`: Pembungkus utama seluruh komponen tabel.
- `<thead>`: Bagian kepala tabel untuk mendefinisikan label kolom.
- `<tbody>`: Bagian tubuh tabel yang memuat baris data aktual.
- `<tr>` (*table row*): Mendefinisikan baris horizontal.
- `<th>` (*table header cell*): Sel judul kolom (otomatis tebal dan rata tengah).
- `<td>` (*table data cell*): Sel data biasa di dalam baris.

### 4. Elemen Aksi & Tombol
- Setiap baris memiliki kolom "Aksi" berisi tombol **Edit** dan **Hapus**.
- Menggunakan atribut `type="button"` secara eksplisit untuk menandakan tombol reguler (bukan tombol submit form).
- *Catatan*: Tombol dan data bersifat statis/dummy (belum terhubung ke JavaScript atau database).

# Ringkasan: Struktur Halaman Tambah Buku (`buku/tambah.html`)

### 1. Fungsi File
- Menyediakan antarmuka formulir input (`<form>`) untuk menambahkan data buku baru ke sistem perpustakaan.

### 2. Komponen Dasar Form
- **`<form>`**: Pembungkus seluruh field input yang akan dikirim secara bersamaan. *(Catatan: Atribut `action` dan `method` sengaja belum diisi karena pemrosesan data backend akan dipelajari pada jobsheet berikutnya).*
- **Relasi `<label>` dan `<input>`**: 
  - Menggunakan atribut `for` pada label yang nilainya sama dengan `id` pada input (contoh: `<label for="judul">` $\rightarrow$ `<input id="judul">`).
  - Meningkatkan aksesibilitas dan kemudahan klik (memilih label langsung mengarahkan kursor ke kotak input).
- **Perbedaan `id` vs `name`**:
  - `id`: Pengenal unik elemen di dokumen HTML (untuk relasi label/CSS/JS).
  - `name`: Kunci/parameter data yang dikirim ke server saat form di-*submit*.

### 3. Ragam Elemen Input & Validasi Bawaan HTML5
Validasi dasar diterapkan langsung di browser tanpa perlu JavaScript:
- **Teks Bebas (`type="text"`)**:
  - Judul & Pengarang: Menggunakan atribut `required` (wajib diisi).
  - ISBN: Bersifat opsional (tanpa `required`).
- **Angka (`type="number"`)**:
  - Tahun Terbit: Dibatasi dengan rentang `min="1900"` dan `max="2026"`.
  - Stok: Dibatasi nilai minimal `min="0"` (mencegah stok negatif).
- **Dropdown Pilihan (`<select>` & `<option>`)**:
  - Menyediakan opsi terbatas: *Fiksi*, *Non-Fiksi*, dan *Referensi*.
  - Atribut `value` menentukan data aktual yang dikirim ke server, sedangkan teks di dalam tag menentukan tampilan di layar.

### 4. Tombol Submit (`<button>`)
- Menggunakan `type="submit"` untuk memicu pengiriman form (berbeda dengan `type="button"` yang hanya bertindak sebagai tombol statis biasa).

# Ringkasan: Struktur Halaman Daftar Anggota (`anggota/list.html`)

### 1. Fungsi File
- Menampilkan data tabel anggota perpustakaan secara statis sebagai penerapan mandiri dari konsep tabel HTML (`<table>`).

### 2. Kesamaan Struktur dengan `buku/list.html`
- Menggunakan hierarki tabel semantik yang identik: `<table>` $\rightarrow$ `<thead>` (judul kolom `<th>`) $\rightarrow$ `<tbody>` (baris `<tr>` & data `<td>`).
- Menyediakan kolom **Aksi** dengan tombol reguler `<button type="button">` (Edit & Hapus) yang belum diberi logika JavaScript.

### 3. Penyesuaian Data & Kolom
- **Struktur Kolom**: Disesuaikan untuk entitas anggota, yaitu *No. Anggota*, *Nama*, *Alamat*, *No. HP*, dan *Aksi*.
- **Data Dummy**: Berisi 2 baris data contoh (A001 & A002). Penggunaan format nomor telepon dummy (seperti `0812xxxx`) diterapkan sebagai praktik baik keamanan data pribadi.

### 4. Navigasi & Tugas Konsistensi Menu
- **Path Relatif Folder `anggota/`**:
  - `../index.html`: Naik ke root untuk menuju Beranda.
  - `../buku/list.html`: Naik ke root lalu masuk ke folder `buku/`.
  - `list.html` & `tambah.html`: Langsung nama file (sesama folder `anggota/`).
- **Catatan Konsistensi Navigasi**: Menu pada file ini sudah memuat tautan ke `tambah.html` (*Tambah Anggota*), sehingga menu di file lainnya (`index.html`, `buku/*.html`) perlu disinkronkan agar navigasi di seluruh aplikasi konsisten.
