# Rangkuman Konsep & Implementasi Responsive Web Design (RWD)

## 1. Konsep Dasar RWD
* **Definisi:** Pendekatan pembuatan tata letak web agar otomatis menyesuaikan resolusi atau lebar layar perangkat (HP, tablet, desktop) menggunakan satu berkas HTML/CSS yang sama.
* **`<meta name="viewport">`:**
  * Sintaks: `<meta name="viewport" content="width=device-width, initial-scale=1">`
  * Fungsi: Mencegah browser mobile memakai *default layout viewport* (±980px) yang menyebabkan tampilan mengecil (*zoom out* otomatis). Menyelaraskan 1px CSS dengan ukuran layar fisik.
* **Media Query (`@media`):** Mekanisme CSS untuk menerapkan styling bersyarat tanpa bantuan JavaScript.
* **Breakpoint:** Batas lebar layar target pengaktif media query (pada modul ini: `768px` untuk tablet dan `480px` untuk mobile).
* **Pendekatan Desktop-First:**
  * Styling default ditulis untuk layar monitor besar terlebih dahulu.
  * Blok `@media (max-width: ...)` diletakkan di **paling bawah berkas CSS** agar aturan di layar kecil berhasil menimpa (*override*) gaya default sesuai aturan spesifisitas.

## 2. Perubahan pada Berkas HTML
1. **Tag Meta Viewport:** Disisipkan di bagian `<head>` seluruh dokumen HTML.
2. **Struktur Checkbox Hack:** Ditambahkan elemen `<input type="checkbox" id="nav-toggle" class="nav-toggle">` dan `<label for="nav-toggle" class="nav-toggle-label">&#9776;</label>` sejajar di dalam `<header>` tepat sebelum `<nav>`.
3. **Pembungkus Tabel:** Elemen `<table>` dibungkus menggunakan `<div class="table-responsive">` sebagai pengontrol overflow.


## 3. Komponen Tabel Responsif (`table-responsive`)
* **Masalah:** Tabel dengan jumlah kolom banyak mendesak layout dan terpotong di layar berukuran sempit.
* **Solusi CSS:**
  ```css
  .table-responsive {
      overflow-x: auto;
  }

# Rangkuman Materi Bootstrap: Konsep, Komponen, dan Grid

## 1. Konsep Dasar & Filosofi Bootstrap
* **Pengertian:** Framework CSS dan JavaScript yang menyediakan kumpulan *utility classes*, komponen antarmuka siap pakai (navbar, card, modal), serta sistem grid 12-kolom responsif.
* **Filosofi Utility-First:** Styling diterapkan langsung di HTML melalui penamaan class (misal: `.text-center`, `.mb-3`, `.shadow-sm`) alih-alih menulis deklarasi CSS manual dari nol.
* **Metode Pemuatan (CDN):**
  * `<link>` CSS di dalam tag `<head>`: Memuat semua pustaka styling class.
  * `<script>` JS (`bundle.min.js`) di akhir `<body>`: Menjalankan fungsi interaktif (animasi toggle menu, dropdown, modal) dan sudah mengemas pustaka *Popper.js*.
* **Spacing Scale:** Menggunakan format penamaan arah + level ukuran (contoh: `mb-0` sampai `mb-5`, `p-3`, `mt-*`, `ms-*`).

## 2. Sistem Breakpoint & Grid 12-Kolom
Bootstrap mengadopsi pendekatan **Mobile-First** (`min-width`): gaya dasar berlaku untuk layar terkecil, lalu breakpoint menambahkan penyesuaian saat layar melebar.

### Tabel Standar Breakpoint
| Breakpoint | Infix | Lebar Layar |
| :--- | :--- | :--- |
| Extra small | *(tanpa infix)* | `< 576px` |
| Small | `sm` | `≥ 576px` |
| Medium | `md` | `≥ 768px` |
| Large | `lg` | `≥ 992px` |
| Extra large | `xl` | `≥ 1200px` |
| Extra extra large | `xxl` | `≥ 1400px` |

### Aturan Grid System
* Setiap kelompok kolom wajib dibungkus oleh elemen beralas `.row` (`display: flex` internal).
* Total pembagian lebar virtual per baris adalah **12 kolom**.
* Penulisan `.col-12 .col-md-4` berarti: elemen selebar layar penuh (12/12) di smartphone (<768px), lalu berubah menjadi sepertiga layar (4/12) di breakpoint `md` (≥768px) ke atas.
* Pengaturan jarak antar-kolom diatur otomatis menggunakan class *gutter* seperti `.g-3`.

## 3. Komponen Antarmuka Utama

### A. Navbar Responsif
* Menggantikan teknik *CSS Checkbox Hack* dengan fungsionalitas JavaScript bawaan.
* **`.navbar-expand-{breakpoint}`:** Menentukan batas lebar layar kapan menu tampil terbuka horizontal dan kapan menciut menjadi menu hamburger.
* **`.navbar-toggler`:** Tombol pemicu yang dihubungkan ke target menu menggunakan atribut `data-bs-toggle="collapse"` dan `data-bs-target="#idTarget"`.
* **`.collapse.navbar-collapse`:** Kontainer menu navigasi yang melipat/membuka dengan animasi transisi halus.

### B. Komponen Card
* **`.card`:** Kontainer pembungkus visual dengan gaya border, latar putih, dan sudut membulat.
* **`.card-body`:** Elemen pembungkus internal wajib untuk memberikan padding konten.
* **`.card-title`:** Penataan tipografi heading khusus area kartu.

### C. Tabel Responsif
* **`.table`:** Class dasar untuk reset layout, padding sel, dan *border-bottom*.
* **`.table-striped` & `.table-hover`:** Pengganti selektor manual `:nth-child(even)` dan `:hover`.
* **`.align-middle`:** Menjaga teks dan tombol di tiap baris sel sejajar secara vertikal.
* **`<div class="table-responsive">`:** Pembungkus tabel agar menghasilkan *overflow horizontal scroll* saat dibuka pada perangkat berlayar sempit.

### D. Formulir & Tombol
* **Form Control:** Penggunaan `.form-label`, `.form-control` (untuk `<input>`), dan `.form-select` memberikan ukuran, outline saat fokus, serta padding yang seragam tanpa mengubah atribut fungsional native (`required`, `type`, `name`).
* **Tombol Semantik:** Class tombol berbasis tugas, seperti `.btn-warning` (kuning/peringatan) untuk Edit, `.btn-danger` (merah/destruktif) untuk Hapus, dan modifier ukuran seperti `.btn-sm`.

## 4. Perbandingan: CSS Murni vs Bootstrap

| Kategori | Pendekatan CSS Murni | Pendekatan Bootstrap 5 |
| :--- | :--- | :--- |
| **Penyusunan Gaya** | Menulis selektor & aturan manual di berkas `.css`. | Memasang kombinasi class utility langsung di elemen HTML. |
| **Responsive Logic** | Sering memakai strategi *desktop-first* (`max-width`). | Sepenuhnya memakai strategi *mobile-first* (`min-width`). |
| **Hamburger Menu** | Memanfaatkan trik `:checked` pada elemen `<input type="checkbox">` tanpa JS. | Komponen resmi berbasis manipulasi class dinamis lewat JavaScript (`bootstrap.bundle.min.js`). |
| **Ketergantungan** | Mandiri, tidak butuh koneksi luar maupun file library eksternal. | Bergantung pada koneksi CDN atau instalasi pustaka pihak ketiga. |
| **Warna Custom** | Dikelola bebas lewat variabel atau kode HEX manual. | Memerlukan *inline style* khusus atau penimpaan CSS jika warna di luar palet bawaan Bootstrap. |
