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

*(Catatan: Jobsheet ini berfokus murni pada kerangka/struktur dokumen, sehingga belum menggunakan CSS/JS).*
