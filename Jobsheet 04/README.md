# Rangkuman Materi UI/UX Design (SIMPUS-Mini)

## 1. Konsep Dasar UI/UX Design

* **Perbedaan UI dan UX:**
* **UI (*User Interface*):** Fokus pada **tampilan visual** (warna, tombol, tata letak, tipografi). Contoh: styling yang dibangun lewat `style.css`.
* **UX (*User Experience*):** Fokus pada **alur dan kemudahan** pengguna dalam menyelesaikan tugas tanpa kebingungan.
* *Analogi:* UI adalah etalase dan dekorasi toko; UX adalah kemudahan mencari barang hingga membayar di kasir tanpa tersesat.


* **Urgensi Merancang Sebelum Koding:**
* Memikirkan seluruh alur tanpa terdistraksi sintaks teknis kode.
* Menemukan celah/pertanyaan logis sejak awal (mengubah teks rancangan jauh lebih murah dibanding *refactoring* kode).
* Menjadi panduan/peta acuan kerja saat tahap implementasi.


* **Dua Alat Bantu Utama:**
* **Wireframe:** Sketsa tata letak elemen pada *satu halaman*.
* **User Flow:** Diagram langkah/alur perpindahan antarhalaman untuk menyelesaikan satu tugas tertentu.

## 2. Cara Membaca Wireframe (ASCII Art)

Wireframe dibuat sederhana (tanpa warna/detail grafis) menggunakan teks karakter biasa (ASCII) agar fokus pada struktur dan posisi elemen.

### Konvensi Simbol Wireframe

| Simbol / Pola | Representasi UI | Implementasi HTML |
| --- | --- | --- |
| `+`, `-`, ` | ` (bingkai luar) | Batas halaman atau kartu/panel |
| Garis vertikal/horizontal pemisah | Pemisah section di dalam halaman | `<section>`, `<hr>` |
| `[______________]` | Kotak input teks | `<input type="text">` atau `type="password"` |
| `[ Teks ]` | Tombol aksi/klik | `<button type="submit">` atau `<a>` (link tombol) |
| Teks tanpa kurung | Label atau teks statis | `<label>`, `<h1>`, `<h2>`, `<p>` |

## 3. User Flow: Peminjaman & Pengembalian

User flow memetakan alur interaksi langkah demi langkah menggunakan format alur panah (`->`).

### A. Alur Peminjaman Buku

```text
[Petugas Login] -> [Dashboard] -> [Pilih menu "Peminjaman Baru"] 
  -> [Pilih Anggota] -> [Pilih Buku (stok > 0)] 
  -> [Simpan] -> [Stok buku berkurang 1] -> [Kembali ke Dashboard]

```

* **Poin Kunci:** Mensyaratkan login (hanya untuk aktor Petugas) dan menyertakan *business rule* berupa pengecekan stok `(stok > 0)`. Terdapat efek samping otomatis: sistem mengurangi stok buku setelah data disimpan.

### B. Alur Pengembalian Buku

```
[Dashboard] -> [Menu "Pengembalian"] -> [Cari transaksi aktif] 
  -> [Tandai "Dikembalikan"] -> [Stok buku bertambah 1] 
  -> [Kembali ke Dashboard]

```

* **Poin Kunci:** Menggunakan mekanisme pencarian data yang sudah ada (bukan form entri baru), serta menerapkan efek kebalikan dari peminjaman (stok bertambah 1).

## 4. Aktor & Otorisasi

* **Aktor:** Entitas/kategori pengguna yang dibedakan berdasarkan hak aksesnya.
* **Tamu:** Hanya dapat melihat katalog buku (Beranda, Daftar Buku) tanpa login. Halaman statis Jobsheet 1–3 merepresentasikan sudut pandang ini.
* **Petugas:** Wajib login untuk mengakses Dashboard, fitur CRUD, dan transaksi (peminjaman/pengembalian).


* **Otorisasi (*Authorization*):** Pembatasan hak akses halaman berdasarkan status pengguna (misal: Tamu yang mengakses URL Dashboard otomatis dialihkan ke halaman Login). Fitur ini membutuhkan JavaScript/backend, sehingga dirancang terlebih dahulu sebelum dikoding.

## 5. Keterhubungan Rancangan dengan Kode Eksisting

Rancangan baru merupakan kelanjutan langsung dari basis kode yang sudah dibuat pada jobsheet sebelumnya:

* **Desain & Styling Terpusat:** Elemen baru (form login, tombol, tabel transaksi) memakai ulang struktur CSS yang sudah ada di `assets/css/style.css` (tema warna `#1d5b8a`, gaya kartu putih, format tabel, form styling).
* **Fleksibilitas Navbar:** Struktur Flexbox pada menu navigasi memungkinkan penambahan menu baru ("Peminjaman") dan status login tanpa perlu merombak properti CSS.
* **Penggunaan Ulang Komponen:** Kartu statistik di Dashboard Petugas menggunakan komponen CSS Grid yang sama dengan yang ada di Beranda.
* **Pencatatan Edge Cases Sejak Dini:**
1. Validasi stok habis (`stok > 0`) pada form peminjaman.
2. Penanganan anggota yang memiliki tunggakan/keterlambatan pengembalian buku.
