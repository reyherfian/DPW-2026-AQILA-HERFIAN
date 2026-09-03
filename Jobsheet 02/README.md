# Ringkasan: Konsep Dasar CSS 

### 1. Definisi & Peran CSS
- **HTML vs CSS**: HTML menentukan struktur dan isi konten, sedangkan CSS (*Cascading Style Sheets*) mengatur aspek tampilan (warna, ukuran font, jarak, dan tata letak).

### 2. Anatomi Aturan CSS (*CSS Rule*)
Setiap baris kode CSS tersusun dari bagian-bagian berikut:
- **Selector**: Target elemen HTML yang diberi gaya (contoh: `header`).
- **Declaration Block**: Blok kurung kurawal `{ ... }` pembungkus aturan gaya.
- **Property**: Aspek tampilan yang diatur (contoh: `background-color`, `color`).
- **Value**: Nilai dari properti tersebut (contoh: `#1d5b8a`, `#fff`).

### 3. Menghubungkan CSS ke HTML
- Menggunakan metode *External CSS* dengan tag `<link rel="stylesheet" href="...">` di dalam `<head>`.
- **Keuntungan**: Satu file `style.css` dapat digunakan bersama oleh banyak file HTML sekaligus (efisien dan modular).

### 4. Ragam Jenis Selector
- **Tag/Elemen**: Memilih seluruh tag tertentu (contoh: `body`, `table`).
- **Universal (`*`)**: Memilih semua elemen tanpa terkecuali.
- **Descendant (Turunan)**: Memilih elemen di dalam elemen lain berdasarkan hierarki (contoh: `header nav ul`).
- **Pseudo-class State (`:hover`)**: Memilih elemen saat kondisi tertentu (contoh: `a:hover`, `tbody tr:hover`).
- **Pseudo-class Posisi (`:nth-child`, `:nth-of-type`)**: Memilih elemen berdasarkan urutan posisinya (contoh: `tr:nth-child(even)`).
- **Attribute Selector**: Memilih elemen berdasarkan atribut spesifiknya (contoh: `button[type="submit"]`).

### 5. Konsep CSS Box Model
Setiap elemen HTML diperlakukan sebagai kotak berlapis (dari luar ke dalam):
- **Margin**: Ruang kosong transparan di luar kotak (jarak ke elemen lain).
- **Border**: Garis pembatas di sekeliling padding dan konten.
- **Padding**: Ruang kosong di dalam kotak (jarak antara border dan konten).
- **Content**: Isi teks atau media sebenarnya.

### 6. Satuan Ukuran & Format Warna
- **Satuan**: `px` (nilai absolut/tetap), `rem` (relatif terhadap ukuran font akar HTML), `%` (relatif terhadap pembungkus), dan `fr` (pecahan ruang pada CSS Grid).
- **Warna Hex**: Menggunakan format heksadesimal `#RRGGBB` (contoh: `#1d5b8a`) atau bentuk ringkas 3 digit (contoh: `#fff`).


# Ringkasan: Perubahan File HTML & Path CSS 

### 1. Perubahan Minimalis pada Dokumen HTML
- Struktur HTML dari Jobsheet 1 tidak diubah sama sekali; perubahan hanya berupa penambahan satu baris tag `<link>` di dalam `<head>`.

### 2. Penyesuaian Path Relatif `href`
Nilai `href` disesuaikan dengan kedalaman posisi file HTML terhadap file stylesheet:
- **Di Root Folder (`index.html`)**: `href="assets/css/style.css"` (langsung masuk ke subfolder).
- **Di Subfolder (`buku/*.html`, `anggota/*.html`)**: `href="../assets/css/style.css"` (naik satu level folder terlebih dahulu).

### 3. Prinsip *Separation of Concerns*
- Memisahkan tanggung jawab secara tegas: HTML fokus mengelola struktur semantik konten, sedangkan CSS sepenuhnya mengontrol visual antarmuka tanpa perlu mengubah markup.


# Ringkasan: CSS Reset & Gaya Dasar Body 

### 1. Reset Global (`*`)
- `margin: 0; padding: 0;`: Menghilangkan margin dan padding default bawaan browser untuk menyamakan tampilan awal.
- `box-sizing: border-box;`: Mengunci perhitungan total lebar/tinggi elemen agar mencakup padding dan border tanpa menambah ukuran fisik kotak keluar.

### 2. Gaya Dasar Dokumen (`body`)
- `font-family`: Menetapkan susunan font prioritas bertingkat (`"Segoe UI", Arial, sans-serif`).
- `color: #2b2b2b;`: Warna teks abu-abu gelap agar tidak terlalu kontras dan ramah di mata.
- `background-color: #f5f6f8;`: Warna latar belakang utama bernuansa abu-abu sangat muda.
- `line-height: 1.5;`: Mengatur jarak tinggi baris teks agar teks paragraf mudah dibaca.
- **Pewarisan (*Inheritance*)**: Nilai font, warna, dan spasi baris otomatis diturunkan ke seluruh elemen teks anak di dalam `<body>`.

### 3. Tampilan Tautan (`<a>`)
- `color: #1d5b8a;`: Mengubah warna default tautan menjadi biru tema.
- `text-decoration: none;`: Menghapus garis bawah tautan agar tampilan bersih.
- `a:hover { text-decoration: underline; }`: Menampilkan garis bawah kembali saat kursor diarahkan ke tautan sebagai indikator visual klik.


# Ringkasan: Header & Navbar dengan Flexbox 

### 1. Flexbox pada Kontainer Utama (`header`)
- `display: flex;`: Mengubah elemen `<header>` menjadi *flex container* sehingga elemen di dalamnya berjejer horizontal.
- `align-items: center;`: Meratakan judul (`<h1>`) dan navigasi (`<nav>`) sejajar di tengah secara vertikal.
- `justify-content: space-between;`: Mendorong judul ke ujung kiri dan menu navigasi ke ujung kanan.
- `flex-wrap: wrap;`: Mengizinkan elemen turun ke baris baru saat ukuran layar menyempit.

### 2. Flexbox Bertingkat pada Menu (`header nav ul`)
- `list-style: none;`: Menghilangkan bullet point bawaan list HTML.
- `display: flex;`: Menyusun tautan menu menjadi sejajar secara horizontal.
- `gap: 1.25rem;`: Memberikan jarak seragam antartautan menu tanpa perlu mengatur margin manual.

### 3. Styling Menu & Spesifisitas CSS
- `header nav a`: Mengubah teks menu menjadi putih (`#fff`) dengan ketebalan sedang (`font-weight: 500`).
- **Spesifisitas**: Aturan `header nav a` mengalahkan aturan umum `a` karena selektornya lebih panjang dan bertingkat.


# Ringkasan: Layout Konten & Kartu Section 

### 1. Pembatas Konten Utama (`main`)
- `max-width: 1000px;`: Membatasi lebar konten agar tidak melar berlebihan di layar monitor besar.
- `margin: 2rem auto;`: Mengatur jarak vertikal dan memanfaatkan nilai `auto` untuk menengahkan kontainer secara horizontal.
- `padding: 0 1.5rem;`: Memberi jarak aman di sisi kiri dan kanan agar konten tidak menempel ke tepi layar ponsel.

### 2. Desain Tampilan Kartu (`section`)
- `background-color: #fff;`: Memberikan warna latar putih bersih yang kontras dengan latar abu-abu halaman.
- `border-radius: 8px;`: Membulatkan keempat sudut kotak kartu.
- `padding: 1.5rem;` & `margin-bottom: 1.5rem;`: Memberi ruang napas internal dan jarak pemisah antarkartu.
- `box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);`: Menambahkan efek bayangan halus dengan format warna RGBA transparan agar kartu tampak terangkat.

### 3. Penataan Judul Kartu (`section h2`)
- Menggunakan warna biru tema (`#1d5b8a`) dan jarak bawah (`margin-bottom: 1rem;`) agar serasi di seluruh halaman.


# Ringkasan: Kartu Statistik dengan CSS Grid 

### 1. Selektor Berbasis Urutan (`:nth-of-type(2)`)
- `main section:nth-of-type(2)`: Menargetkan elemen `<section>` urutan kedua (Ringkasan) secara spesifik tanpa perlu atribut `class` tambahan pada HTML.

### 2. Tata Letak Kisi (CSS Grid)
- `display: grid;`: Mengubah kontainer menjadi tata letak kisi 2 dimensi.
- `grid-template-columns: repeat(3, 1fr);`: Membagi kartu secara presisi menjadi 3 kolom dengan lebar proporsional sama besar.
- `gap: 1rem;`: Memberi jarak seragam antarkolom kartu statistik.

### 3. Hierarki Visual Kartu Statistik (`<article>`)
- **Kotak Kartu**: Diberi latar biru muda (`#eef4fa`), sudut membulat, dan teks rata tengah (`text-align: center;`).
- **Label (`h3`)**: Dibuat kecil (`0.95rem`) dan berwarna redup (`#55677a`) sebagai teks sekunder.
- **Angka Data (`p`)**: Dibuat besar (`1.8rem`), tebal (`font-weight: 700`), dan berwarna biru tema sebagai pusat perhatian utama visual.


# Ringkasan: Styling Tabel Data 

### 1. Pengaturan Dasar Tabel (`table`)
- `width: 100%;`: Memaksa tabel melebar penuh mengikuti kontainer pembungkusnya.
- `border-collapse: collapse;`: Menyatukan garis pembatas antarsel menjadi garis tunggal yang rapi.

### 2. Sel Header & Data (`th, td`)
- Disatukan dengan perataan teks rata kiri (`text-align: left;`) dan garis pembatas bawah tipis (`border-bottom: 1px solid #e2e6ea;`).
- `thead`: Diberi latar belakang biru tema (`#1d5b8a`) dengan teks putih solid.

### 3. Zebra Stripes & Efek Hover
- `tbody tr:nth-child(even)`: Memberikan latar abu-abu terang pada baris genap untuk memudahkan pembacaan data horizontal.
- `tbody tr:hover`: Memberikan warna sorotan biru muda saat kursor melintas di atas baris data.

### 4. Tombol Aksi Kolom Tabel (`td button`)
- **Format Dasar**: Menghilangkan border default (`border: none;`), sudut sedikit membulat, ukuran teks proporsional, dan kursor berbentuk tangan (`cursor: pointer;`).
- **Pembedaan Posisi**:
  - `button:first-of-type`: Tombol pertama (Edit) diberi warna kuning/oranye (`#f0ad4e`).
  - `button:last-of-type`: Tombol terakhir (Hapus) diberi warna merah (`#d9534f`).


# Ringkasan: Styling Form Isian

### 1. Spasi & Label Form
- `form p`: Memberikan jarak pemisah vertikal (`margin-bottom: 1rem;`) di bawah setiap grup isian.
- `form label`: Dibuat menjadi elemen blok (`display: block;`) agar input otomatis turun ke baris baru, serta ditebalkan (`font-weight: 600;`) dengan warna abu gelap.

### 2. Kotak Input & Pilihan (`input`, `select`)
- `width: 100%; max-width: 400px;`: Melebar fleksibel mengikuti layar sempit namun dibatasi maksimal 400px pada layar lebar agar tetap rapi.
- Diberi garis batas abu tipis (`border: 1px solid #cdd4da;`), sudut membulat, dan ruang padding yang proporsional.

### 3. Tombol Submit Form
- `button[type="submit"]`: Target khusus tombol kirim menggunakan *attribute selector*, berlatar biru tema dan teks putih.
- `button[type="submit"]:hover`: Mengubah warna tombol menjadi biru lebih gelap (`#164869`) saat kursor mouse berada di atasnya.


# Ringkasan: Footer Halaman (Jobsheet 2 - Bab 9)

### 1. Penataan Kaki Halaman (`footer`)
- `text-align: center;`: Memposisikan teks hak cipta tepat di tengah secara horizontal.
- `padding: 1.25rem;`: Memberi jarak ruang yang seragam di sekeliling teks.

### 2. Bobot Visual Teks Pelengkap
- `color: #7a8794;`: Menggunakan warna abu-abu pudar agar tidak mencolok.
- `font-size: 0.9rem;`: Menggunakan ukuran font lebih kecil dari teks normal guna menegaskan fungsinya sebagai informasi penutup/sekunder.
