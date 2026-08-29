<h4>Aqila Herfian F.S/TI-2F/04<h4>

## PROGRESS

- [x] index.htmml
- [ ] buku list.html
- [ ] buku tambah.html
- [ ] anggota list.html
- [ ] anggota tambah.html
- [ ] style.css
- [ ] latihan tambahan

## DAFTAR ISI
1. [`index.html`](index.html)
2. [`buku/list.html`](buku/list.html)
3. [`buku/tambah.html`](buku/tambah.html)
4. [`anggota/list.html`](anggota/list.html)
5. [`anggota/tambah.html`](anggota/tambah.html)
   
### 10.4 Ide Latihan Tambahan
1. Ubah skema warna
   - semua warna berubah karena memiliki hex yang sama.
2. tambah kolom keempat
   - menambah kolom keempat pada tabel statistik yang ada di beranda dengan menambahkan kode pada css dan index.html.

     | No | Kode | letak |
     |:--:|:---|:---|
     | 1 | `grid-template-columns: repeat(4, 1fr)` | CSS |
     | 2 | `<h3>Buku Terlambat</h3>` | index.html |
     
3. Buat tombol ketiga di tabel buku/list
   - menambahkan button pada html terlebih dahulu dengan menggunakan kode
     `<button type="button">Detail</button> `
   - kemudian merapihkan warna pada css karena penambahan button membuat warna bergeser.
     |button ke-| Kode |
     |:--:|:---|
     | 1 | <pre><code>td button:nth-child(1) {<br>  background-color: #f0ad4e;<br>  color: #fff;<br>}</code></pre> |
     | 2 | <pre><code>td button:nth-child(2) {<br>  background-color: #d9534f;<br>  color: #fff;<br>}</code></pre> |
     | 3 | <pre><code>td button:nth-child(3) {<br>  background-color: #4f96d9;<br>  color: #fff;<br>}</code></pre> |
