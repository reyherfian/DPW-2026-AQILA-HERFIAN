## Rangkuman
1. Konsep Dasar
   - Tag harus memiliki pembuka dan tertutup. Tag Pembuka <tagname> dan tag penutup </tagname>. Dimana ditengah tag tersebut terdapat elemen, <tagname> elemen </tagname>.
   - Setiap halaman HTML wajib memiliki struktur yang tetap.
     ```
     <!DOCTYPE html>
     <html lang="id">
     <head>
       <meta charset="UTF-8">
       <title>SIMPUS-Mini | Beranda</title>
     </head>
     <body>
     ...
     </body>
     </html>
     ```

   | Bagian | Fungsi |
   |---|---|
   | `<!DOCTYPE html>` | Memberi tahu browser bahwa dokumen ini HTML5. **Wajib ada di baris paling atas**. |
   | `<html lang="id">` | Pembungkus utama seluruh halaman web dengan pengaturan bahasa Indonesia. |
   | `<head>` | Menyimpan informasi latar belakang (metadata, judul tab, stylesheet) yang tidak tampil langsung di layar. |
   | `<meta charset="UTF-8">` | Format encoding teks agar karakter khusus dan simbol dapat terbaca dengan benar tanpa error. |
   | `<title>` | Menentukan teks judul pada tab browser. |
   | `<body>` | Memuat semua konten utama yang tampil di halaman web (teks, gambar, tabel, formulir). |
