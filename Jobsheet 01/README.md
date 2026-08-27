<h4>Nama        : Aqila Herfian F.S<h4>
<h4>NIM         : 254107020041<h4>
<h4>Kelas       : TI-2F<h4>
<h4>Absen       : 04<h4>

## PROGRESS
| No | Task / Modul | Status | Keterangan |
|:--:|:---|:---:|:---|
| 1 | Index html | ✅ Selesai | Beranda |
| 2 | Buku list | ✅ Selesai | Tampilan daftar buku |
| 3 | Buku tambah | ✅ Selesai | Form input buku baru |
| 4 | Anggota list | ✅ Selesai | Tampilan daftar anggota |
| 5 | Anggota tambah | ✅ Selesai | Form input anggota |
| 6 | Latihan reflektif | ⏳ On Progress | Pending |
| 7 | Latihan opsional | ❌ Belum | Pending |

### 3.3 Data yang Ditampilkan (Dummy)
Menambah isi tabel yang berisikan judul buku, pengarang, tahun dan stok ke dalam HTML statis.
```

    <table>
        <thead>
            <tr>
                <th>Judul</th>
                <th>Pengarang</th>
                <th>Tahun Terbit</th>
                <th>Stok</th>
                <th>Aksi</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Laskar Pelangi</td>
                <td>Andrea Hirata</td>
                <td>2008</td>
                <td>4</td>
                <td>
                    <button type="button">Edit</button>
                    <button type="button">Hapus</button>
                </td>
            </tr>
            <tr>
                <td>Bumi Manusia</td>
                <td>Pramoedya Ananta Toer</td>
                <td>1980</td>
                <td>2</td>
                <td>
                    <button type="button">Edit</button>
                    <button type="button">Hapus</button>
            <tr>
                <td>Negeri 5 Menara</td>
                <td>Ahmad Fuadi</td>
                <td>2009</td>
                <td>0</td>
                <td>
                    <button type="button">Edit</button>
                    <button type="button">Hapus</button>
            <tr>
                <td>Filosofi Teras</td>
                <td>Henry Manampiring</td>
                <td>2018</td>
                <td>5</td>
                <td>
                    <button type="button">Edit</button>
                    <button type="button">Hapus</button>
                </td>
            <tr>
                <td>Ronggeng Dukuh Paruk</td>
                <td>Ahmad Tohari</td>
                <td>1982</td>
                <td>1</td>
                <td>

                    <button type="button">Edit</button>
                    <button type="button">Hapus</button>
                </td>
            </tr>
```

### 6.5 Latihan Reflektif
1. Kenapa field "Alamat" dan "No. HP" tidak diberi `requiered`, sedangkan "Nama" dan "No. Anggota" diberi?
   - karena "Nama" dan "No. Anggota" bersifat wajib yang berfungsi sebagai primary kry atau pengenal unik agar sistem dapat membedakan tiap baris data tanpa duplikasi. Sedangkan "Alamat" dan "No. HP" dibuat opsional. Nomor telepon dan alamat rumah tergolong data sensitif (Personally Identifiable Information.
2. Apa yang akan terjadi (di browser) kalau kamu klik tombol "Simpan" tanpa mengisi field "Nama"? Coba buka filenya di browser dan praktikkan.
   - form batal terkirim/submit dan pop-up peringatan wajib mengisi.
3. Form ini juga belum punya action pada tag <form>-nya — apa dampaknya saat tombol "Simpan" ditekan?
   - browser akan menerapkan default. 
