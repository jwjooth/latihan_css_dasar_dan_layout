# UJIAN AKHIR
## Mata Kuliah: CSS (CSS Dasar & CSS Layout)
## Program Studi: Rekayasa Perangkat Lunak

| Informasi      | Detail                                                                 |
| -------------- | ---------------------------------------------------------------------- |
| **Durasi**     | 180 menit                                                              |
| **Sifat Ujian**| Open Book & Open Internet                                              |
| **Bobot Nilai**| Bagian A: 36 poin · Bagian B: 40 poin · Bagian C: 24 poin             |
| **Prasyarat Lulus** | Nilai akhir minimal **70 / 100**                                  |

---

### 📋 Instruksi Umum

1. Seluruh jawaban **harus berupa kode HTML + CSS yang dapat dibuka dan dilihat langsung di browser**.
2. Setiap soal dikerjakan dalam satu file `.html` tersendiri dengan nama sesuai nomor soal (contoh: `soal-01.html`).
3. **Tidak diperbolehkan** menggunakan CSS framework (Bootstrap, Tailwind, dll.) kecuali soal secara eksplisit menyebutkan.
4. **Tidak diperbolehkan** menggunakan JavaScript untuk mengatur tampilan, kecuali jika soal menyebutkan.
5. Kode yang tidak dapat dibuka di browser (syntax error fatal) mendapat nilai **0** pada soal tersebut.
6. Open book dan open internet **tidak berarti copy-paste template jadi**; pengujian akan mencakup sesi tanya jawab teknis terhadap kode yang dikumpulkan.
7. Gunakan **komentar CSS** (`/* ... */`) untuk menjelaskan keputusan styling yang Anda buat pada soal bertanda 💬.

---

## BAGIAN A — Easy to Medium
> **Bobot:** 3 poin per soal × 12 soal = **36 poin**

---

### Soal 1 — CSS Selector & Cascade Spesifisitas

**Deskripsi Kasus:**
Seorang web developer menemukan bug di mana styling sebuah paragraf tidak bekerja sesuai harapan karena konflik spesifisitas selector. Anda diminta untuk memprediksi hasil akhir dan kemudian memperbaiki kode tersebut.

**Spesifikasi Teknis:**
Buat file `soal-01.html` dengan struktur HTML berikut (hardcoded, **jangan diubah**):

```html
<div id="konten" class="wrapper">
  <p class="teks" id="paragraf-utama">Teks Satu</p>
  <p class="teks">Teks Dua</p>
  <p>Teks Tiga</p>
</div>
```

Kemudian tuliskan **blok CSS** yang memenuhi seluruh requirement berikut secara **bersamaan**:

**Requirement:**
1. Semua elemen `<p>` di dalam `#konten` memiliki `font-size: 16px` dan `color: gray`.
2. Semua elemen dengan class `.teks` memiliki `font-weight: bold`.
3. Elemen dengan ID `#paragraf-utama` memiliki `color: crimson` dan `font-size: 20px`. Aturan ini harus **mengalahkan** aturan nomor 1 tanpa menggunakan `!important`.
4. Saat kursor diarahkan ke elemen `<p>` mana pun (`hover`), warna teks berubah menjadi `navy`.
5. Beri `background-color: #f0f0f0` dan `padding: 20px` pada `#konten`.

**Constraint:**
- Hanya boleh menggunakan satu blok `<style>` internal.
- **Dilarang** menggunakan `!important` untuk requirement manapun.
- **Dilarang** menggunakan inline style.
- Selector untuk setiap requirement harus se-spesifik yang diperlukan, tidak boleh lebih.

**Contoh Output yang Diharapkan di Browser:**
- "Teks Satu" tampil berwarna crimson, ukuran 20px, tebal.
- "Teks Dua" tampil berwarna gray, ukuran 16px, tebal.
- "Teks Tiga" tampil berwarna gray, ukuran 16px, tidak tebal.
- Saat di-hover, semua teks berubah ke warna navy.

---

### Soal 2 — Box Model: Padding, Margin & Border

**Deskripsi Kasus:**
Sebuah kartu informasi produk harus diimplementasikan dengan dimensi dan spasi yang presisi. Developer lain mengeluh bahwa lebar kartu berubah ketika border ditambahkan. Anda harus mengimplementasikan kartu tersebut dan menyelesaikan masalah dimensi tersebut.

**Spesifikasi Teknis:**
Buat file `soal-02.html`. Gunakan struktur HTML berikut (hardcoded):

```html
<div class="kartu">
  <h2 class="judul-kartu">Produk Unggulan</h2>
  <p class="deskripsi">Deskripsi singkat produk ini.</p>
  <span class="harga">Rp 150.000</span>
</div>
```

**Requirement CSS:**
1. `.kartu` harus memiliki lebar tepat **300px** (lebar total yang terlihat di browser, termasuk border), tinggi otomatis mengikuti konten.
2. `.kartu` memiliki `padding: 20px` di semua sisi.
3. `.kartu` memiliki `border: 2px solid #cccccc` dan `border-radius: 8px`.
4. `.kartu` memiliki `margin: 30px auto` agar berada di tengah halaman.
5. `.judul-kartu` memiliki `margin-top: 0` dan `margin-bottom: 8px`.
6. `.harga` ditampilkan sebagai block, `font-size: 18px`, `color: #e44d26`, `font-weight: bold`, dan memiliki `margin-top: 12px`.
7. Gunakan properti `box-sizing` yang tepat agar requirement nomor 1 terpenuhi dengan pasti.

**Constraint:**
- Wajib menggunakan properti `box-sizing: border-box`.
- Jelaskan dalam komentar CSS mengapa `box-sizing: border-box` dibutuhkan 💬.

**Contoh Output yang Diharapkan di Browser:**
- Kartu berada di tengah halaman.
- Total lebar kartu terlihat persis 300px di DevTools.
- Teks harga tampil di bawah deskripsi, berwarna oranye-merah.

---

### Soal 3 — Selector Kombinator & Attribute Selector

**Deskripsi Kasus:**
Sebuah halaman navigasi membutuhkan styling yang berbeda-beda berdasarkan hubungan antar elemen dan atribut link. Anda tidak diperbolehkan menambahkan class atau ID tambahan pada HTML.

**Spesifikasi Teknis:**
Buat file `soal-03.html` dengan struktur HTML berikut (hardcoded, **jangan ditambah class/id apapun**):

```html
<nav>
  <ul>
    <li><a href="/home">Beranda</a></li>
    <li><a href="/about">Tentang</a></li>
    <li><a href="https://github.com/user" target="_blank">GitHub</a></li>
    <li><a href="mailto:admin@mail.com">Email Admin</a></li>
    <li>
      <span>Dropdown</span>
      <ul>
        <li><a href="/sub1">Sub Menu 1</a></li>
        <li><a href="/sub2">Sub Menu 2</a></li>
      </ul>
    </li>
  </ul>
</nav>
```

**Requirement CSS (semua harus menggunakan selector yang tepat tanpa menambah class/id):**
1. Semua `<a>` di dalam `nav` tidak memiliki `text-decoration` dan berwarna `#333`.
2. `<a>` yang memiliki atribut `target="_blank"` (link eksternal) berwarna `steelblue` dan **setelah** teksnya tampil teks `" ↗"` menggunakan `::after` pseudo-element.
3. `<a>` yang atribut `href`-nya dimulai dengan `mailto:` berwarna `green`.
4. `<li>` yang merupakan **anak langsung** dari `<ul>` pertama (level pertama, bukan sub-menu) memiliki `padding: 8px 0`.
5. Elemen `<span>` yang **langsung diikuti** oleh `<ul>` (adjacent sibling) memiliki `font-weight: bold` dan `cursor: pointer`.
6. `<li>` dalam sub-menu (ul di dalam li) memiliki `padding-left: 20px` dan `font-size: 14px`.

**Constraint:**
- Gunakan **hanya** combinator selector, attribute selector, dan pseudo-element/class.
- Tidak boleh menambah class, ID, atau atribut HTML apapun.

---

### Soal 4 — Typography & Text Styling

**Deskripsi Kasus:**
Sebuah halaman artikel blog membutuhkan tipografi yang konsisten dan terbaca dengan baik. Implementasikan seluruh styling tipografi sesuai spesifikasi.

**Spesifikasi Teknis:**
Buat file `soal-04.html` dengan struktur HTML berikut:

```html
<article>
  <h1>Judul Artikel Utama</h1>
  <p class="meta">Ditulis oleh <strong>Andi Saputra</strong> · 20 Februari 2026</p>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore.</p>
  <blockquote>
    "Belajar CSS adalah investasi terbaik untuk seorang web developer."
  </blockquote>
  <p>Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae.</p>
  <h2>Sub Judul Bagian</h2>
  <p>Maecenas aliquet accumsan leo. Nullam dapibus fermentum ipsum.</p>
</article>
```

**Requirement CSS:**
1. `article` memiliki `max-width: 680px`, `margin: 40px auto`, dan `font-family` menggunakan **Google Font "Merriweather"** (tambahkan `@import` atau `<link>` Google Font). Fallback: `Georgia, serif`.
2. `h1` berukuran `32px`, `color: #1a1a1a`, tanpa margin atas.
3. `h2` berukuran `22px`, `color: #333`, dengan `border-bottom: 2px solid #eee` dan `padding-bottom: 6px`.
4. `.meta` berukuran `13px`, `color: #888`, menggunakan `font-style: italic`.
5. `p` memiliki `line-height: 1.8` dan `color: #444`.
6. `blockquote` memiliki `border-left: 4px solid #e44d26`, `padding-left: 20px`, `margin: 24px 0`, `font-size: 18px`, `color: #555`, dan `font-style: italic`.
7. `strong` di dalam `.meta` memiliki `color: #333` dan bukan italic.

**Constraint:**
- Google Font harus dimuat menggunakan `@import` di dalam `<style>`.
- Seluruh requirement harus terpenuhi sekaligus (tidak ada yang saling menimpa secara tidak sengaja).

---

### Soal 5 — Background & Gradient

**Deskripsi Kasus:**
Sebuah section hero pada landing page membutuhkan background yang kompleks: kombinasi warna solid, gambar overlay, dan gradient. Anda diminta mengimplementasikan tampilan tersebut hanya dengan CSS.

**Spesifikasi Teknis:**
Buat file `soal-05.html` dengan struktur HTML berikut:

```html
<body>
  <section class="hero">
    <div class="hero-konten">
      <h1>Selamat Datang</h1>
      <p>Temukan pengalaman terbaik bersama kami.</p>
      <a href="#" class="tombol">Mulai Sekarang</a>
    </div>
  </section>
  <section class="fitur">
    <div class="fitur-item">Fitur 1</div>
    <div class="fitur-item">Fitur 2</div>
    <div class="fitur-item">Fitur 3</div>
  </section>
</body>
```

**Requirement CSS:**
1. `body` memiliki `margin: 0` dan `font-family: sans-serif`.
2. `.hero` memiliki tinggi `100vh`, `background-color: #1a1a2e` sebagai fallback.
3. `.hero` memiliki **linear-gradient** dari `rgba(26,26,46,0.85)` ke `rgba(22,33,62,0.85)` yang ditumpuk di atas `background-image` berupa URL gambar bebas (gunakan `https://picsum.photos/1920/1080` atau serupa). Keduanya dinyatakan dalam satu properti `background` shorthand dengan urutan: gradient dulu, lalu image.
4. `.hero` menggunakan `background-size: cover` dan `background-position: center`.
5. `.hero-konten` berada di tengah `.hero` secara **vertikal dan horizontal** menggunakan teknik yang **tidak menggunakan Flexbox maupun Grid** (gunakan `position` dan `transform`).
6. `h1` di dalam `.hero` berwarna `white`, ukuran `48px`.
7. `.tombol` tampil sebagai block inline dengan `padding: 12px 32px`, `background: #e44d26`, `color: white`, `text-decoration: none`, `border-radius: 4px`.
8. `.fitur` memiliki `background-color: #f8f8f8` dan `padding: 40px`.
9. Setiap `.fitur-item` memiliki `background: white`, `padding: 20px`, `border-radius: 8px`, dan tampil **berdampingan** (gunakan `display: inline-block`, lebar `calc(33.333% - 20px)`, `margin: 10px`).

**Constraint:**
- Requirement nomor 3 harus menggunakan sintaks multiple background dalam satu properti `background`.
- Requirement nomor 5 **dilarang menggunakan** Flexbox (`display: flex`) atau Grid (`display: grid`).

---

### Soal 6 — Pseudo-classes & Pseudo-elements

**Deskripsi Kasus:**
Sebuah halaman daftar artikel menggunakan pseudo-classes dan pseudo-elements untuk memberikan interaktivitas visual dan ornamen dekoratif tanpa JavaScript.

**Spesifikasi Teknis:**
Buat file `soal-06.html` dengan struktur HTML berikut:

```html
<ul class="daftar-artikel">
  <li><a href="#">Cara Belajar CSS dengan Efektif</a></li>
  <li><a href="#">Memahami Box Model Secara Mendalam</a></li>
  <li><a href="#">Flexbox vs Grid: Kapan Menggunakan Keduanya</a></li>
  <li><a href="#">Membuat Responsive Layout dengan Media Query</a></li>
  <li><a href="#">Tips dan Trik CSS untuk Pemula</a></li>
</ul>
```

**Requirement CSS:**
1. `.daftar-artikel` menghilangkan `list-style`, `padding: 0`, dan `margin: 40px auto`, `max-width: 500px`.
2. Setiap `<li>` memiliki `border-bottom: 1px solid #eee`. Elemen `<li>` **terakhir** tidak memiliki border-bottom (gunakan pseudo-class yang tepat).
3. Setiap `<li>` **ganjil** (ke-1, ke-3, ke-5) memiliki `background-color: #f9f9f9`.
4. Setiap `<a>` memiliki `display: block`, `padding: 14px 16px`, `color: #333`, `text-decoration: none`.
5. Setiap `<a>` memiliki `::before` yang menampilkan karakter `"▶ "` dengan `color: #e44d26`.
6. Saat `<a>` di-hover, background berubah ke `#fff3f0` dan warna teks menjadi `#e44d26`. Transisi ini harus **smooth** dalam `0.2s`.
7. `<a>` yang sedang dalam kondisi **focus** (navigasi keyboard) mendapat outline `2px solid steelblue` dengan `outline-offset: -2px`.

**Constraint:**
- Requirement nomor 2 (menghilangkan border-bottom terakhir) wajib menggunakan pseudo-class `:last-child` atau `:last-of-type`.
- Requirement nomor 3 wajib menggunakan pseudo-class `:nth-child()`.
- Properti `transition` harus dituliskan pada state normal (bukan pada state `:hover`).

---

### Soal 7 — Form Styling

**Deskripsi Kasus:**
Sebuah tim desain membutuhkan form registrasi yang bersih dan profesional. Form tersebut harus memberikan feedback visual yang jelas saat pengguna berinteraksi (focus, valid, invalid) menggunakan CSS murni.

**Spesifikasi Teknis:**
Buat file `soal-07.html` dengan struktur HTML berikut (hardcoded):

```html
<form class="form-registrasi">
  <h2>Daftar Akun Baru</h2>

  <div class="form-grup">
    <label for="nama">Nama Lengkap</label>
    <input type="text" id="nama" name="nama" placeholder="Masukkan nama lengkap" required minlength="3">
  </div>

  <div class="form-grup">
    <label for="email">Alamat Email</label>
    <input type="email" id="email" name="email" placeholder="contoh@email.com" required>
  </div>

  <div class="form-grup">
    <label for="password">Password</label>
    <input type="password" id="password" name="password" placeholder="Minimal 8 karakter" required minlength="8">
  </div>

  <div class="form-grup">
    <label for="peran">Peran</label>
    <select id="peran" name="peran">
      <option value="">-- Pilih Peran --</option>
      <option value="mahasiswa">Mahasiswa</option>
      <option value="dosen">Dosen</option>
    </select>
  </div>

  <button type="submit">Daftar Sekarang</button>
</form>
```

**Requirement CSS:**
1. `.form-registrasi` memiliki `max-width: 420px`, `margin: 50px auto`, `padding: 32px`, `background: white`, `border-radius: 10px`, dan `box-shadow: 0 4px 20px rgba(0,0,0,0.1)`.
2. `h2` berada di tengah (`text-align: center`), `margin-bottom: 24px`.
3. `.form-grup` memiliki `margin-bottom: 16px`.
4. `label` tampil sebagai `block`, `font-size: 14px`, `font-weight: 600`, `margin-bottom: 6px`, `color: #555`.
5. `input` dan `select` memiliki lebar `100%`, `padding: 10px 14px`, `border: 1px solid #ddd`, `border-radius: 6px`, `font-size: 15px`, `box-sizing: border-box`, dan menghilangkan `outline` default.
6. Saat `input` atau `select` dalam kondisi `:focus`, border berubah menjadi `2px solid #4a90e2` dan elemen mendapatkan `box-shadow: 0 0 0 3px rgba(74,144,226,0.2)`.
7. Saat `input` dalam kondisi `:valid` dan **bukan** `:placeholder-shown` (artinya sudah diisi dan valid), border berwarna `#27ae60`.
8. Saat `input` dalam kondisi `:invalid` dan **bukan** `:placeholder-shown` (artinya sudah diisi tapi tidak valid), border berwarna `#e74c3c`.
9. `button` memiliki `width: 100%`, `padding: 12px`, `background: #4a90e2`, `color: white`, `border: none`, `border-radius: 6px`, `font-size: 16px`, `font-weight: bold`, `cursor: pointer`. Saat di-hover, background menjadi `#357abd`.

**Constraint:**
- Requirement 7 dan 8 wajib menggunakan kombinasi pseudo-class `:valid`/`:invalid` dengan `:not(:placeholder-shown)`.
- Tidak boleh menggunakan JavaScript.

---

### Soal 8 — Table Styling

**Deskripsi Kasus:**
Sebuah halaman laporan akademik membutuhkan tabel data yang rapi, mudah dibaca, dengan efek visual yang membantu pengguna melacak baris data. Implementasikan tabel tersebut sesuai spesifikasi.

**Spesifikasi Teknis:**
Buat file `soal-08.html` dengan tabel HTML berikut (hardcoded):

```html
<div class="tabel-wrapper">
  <h3>Laporan Nilai Mahasiswa</h3>
  <table class="tabel-nilai">
    <thead>
      <tr>
        <th>NIM</th>
        <th>Nama</th>
        <th>Mata Kuliah</th>
        <th>Nilai UTS</th>
        <th>Nilai UAS</th>
        <th>Grade</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>A001</td><td>Andi</td><td>CSS Dasar</td><td>85</td><td>90</td><td>A</td></tr>
      <tr><td>A002</td><td>Bela</td><td>CSS Dasar</td><td>70</td><td>75</td><td>B</td></tr>
      <tr><td>A003</td><td>Candra</td><td>CSS Dasar</td><td>60</td><td>65</td><td>C</td></tr>
      <tr><td>A004</td><td>Dini</td><td>CSS Dasar</td><td>90</td><td>88</td><td>A</td></tr>
      <tr><td>A005</td><td>Eka</td><td>CSS Dasar</td><td>55</td><td>58</td><td>D</td></tr>
    </tbody>
  </table>
</div>
```

**Requirement CSS:**
1. `.tabel-wrapper` memiliki `max-width: 700px`, `margin: 40px auto`, `overflow-x: auto` (untuk responsivitas horizontal).
2. `.tabel-nilai` memiliki `width: 100%`, `border-collapse: collapse`.
3. `th` dan `td` memiliki `padding: 12px 16px`, `text-align: left`, dan `border-bottom: 1px solid #e0e0e0`.
4. `thead tr` memiliki `background-color: #2c3e50` dan `color: white`.
5. `tbody tr` dengan baris **genap** (ke-2, ke-4) memiliki `background-color: #f7f7f7` (zebra striping).
6. Saat `tbody tr` di-hover, row tersebut mendapat `background-color: #fff3cd` dengan transisi `0.15s`.
7. Kolom terakhir (`td:last-child`, `th:last-child`) memiliki `text-align: center`.
8. Nilai di kolom "Grade" yang berisi teks "A" tampil dengan `color: #27ae60` dan `font-weight: bold`. Nilai "D" atau "E" tampil dengan `color: #e74c3c`. (**Hint:** Gunakan `td[...]:last-child` tidak bisa; gunakan styling class jika diperlukan — Anda diizinkan **hanya untuk requirement ini** menambahkan class pada `<td>` grade.)

**Constraint:**
- Requirement 5 harus menggunakan `tbody tr:nth-child(even)`.
- Requirement 6 wajib menggunakan `transition` pada state normal.
- `border-collapse: collapse` wajib digunakan agar border tidak dobel.

---

### Soal 9 — CSS Counter & List Styling

**Deskripsi Kasus:**
Sebuah halaman dokumentasi teknis membutuhkan daftar bernomor yang otomatis menggunakan CSS Counter, dengan format penomoran bertingkat (1.1, 1.2, 2.1, dst.) tanpa menggunakan HTML `<ol>` dengan atribut apapun.

**Spesifikasi Teknis:**
Buat file `soal-09.html` dengan struktur HTML berikut:

```html
<div class="dokumentasi">
  <h1>Panduan Instalasi</h1>
  <ul class="daftar-bab">
    <li>
      Persiapan Sistem
      <ul class="daftar-sub">
        <li>Install Node.js</li>
        <li>Install Git</li>
        <li>Install VS Code</li>
      </ul>
    </li>
    <li>
      Konfigurasi Proyek
      <ul class="daftar-sub">
        <li>Buat folder proyek</li>
        <li>Inisialisasi npm</li>
      </ul>
    </li>
    <li>
      Menjalankan Aplikasi
      <ul class="daftar-sub">
        <li>Jalankan server development</li>
        <li>Buka browser</li>
        <li>Verifikasi tampilan</li>
      </ul>
    </li>
  </ul>
</div>
```

**Requirement CSS:**
1. Hilangkan semua `list-style` default dari `<ul>` dan `<li>`.
2. Buat CSS Counter bernama `bab` yang direset pada `.daftar-bab` dan increment di setiap `li` langsung di dalamnya.
3. Buat CSS Counter bernama `sub` yang direset pada setiap `.daftar-sub` dan increment di setiap `li` di dalamnya.
4. Setiap item `.daftar-bab > li` menampilkan `::before` dengan konten format `"Bab [counter(bab)] — "` dalam `font-weight: bold`, `color: #2c3e50`.
5. Setiap item `.daftar-sub > li` menampilkan `::before` dengan konten format `"[counter(bab)].[counter(sub)] "` (contoh: "1.1 ", "1.2 ", "2.1 "), `color: #7f8c8d`.
6. `.daftar-bab > li` memiliki `font-size: 17px` dan `margin-bottom: 16px`.
7. `.daftar-sub > li` memiliki `padding-left: 20px`, `font-size: 15px`, `color: #555`, `margin-top: 6px`.

**Contoh Output yang Diharapkan:**
```
Bab 1 — Persiapan Sistem
    1.1 Install Node.js
    1.2 Install Git
    1.3 Install VS Code
Bab 2 — Konfigurasi Proyek
    2.1 Buat folder proyek
    2.2 Inisialisasi npm
Bab 3 — Menjalankan Aplikasi
    3.1 Jalankan server development
    3.2 Buka browser
    3.3 Verifikasi tampilan
```

**Constraint:**
- Wajib menggunakan properti `counter-reset` dan `counter-increment`.
- Penomoran harus terbentuk **otomatis** dari CSS, bukan ditulis manual di HTML.

---

### Soal 10 — Overflow, Opacity & Filter

**Deskripsi Kasus:**
Sebuah galeri gambar membutuhkan efek visual menggunakan properti overflow, opacity, dan filter CSS. Implementasikan galeri dengan efek hover yang menarik.

**Spesifikasi Teknis:**
Buat file `soal-10.html` dengan struktur HTML berikut:

```html
<div class="galeri">
  <div class="item-galeri">
    <img src="https://picsum.photos/seed/a/300/200" alt="Gambar 1">
    <div class="overlay">
      <p>Foto Pertama</p>
    </div>
  </div>
  <div class="item-galeri">
    <img src="https://picsum.photos/seed/b/300/200" alt="Gambar 2">
    <div class="overlay">
      <p>Foto Kedua</p>
    </div>
  </div>
  <div class="item-galeri">
    <img src="https://picsum.photos/seed/c/300/200" alt="Gambar 3">
    <div class="overlay">
      <p>Foto Ketiga</p>
    </div>
  </div>
  <div class="item-galeri">
    <img src="https://picsum.photos/seed/d/300/200" alt="Gambar 4">
    <div class="overlay">
      <p>Foto Keempat</p>
    </div>
  </div>
</div>
```

**Requirement CSS:**
1. `.galeri` menampilkan item dalam layout **baris horizontal** menggunakan `display: inline-block` (bukan Flexbox/Grid) dengan `text-align: center` pada parent, `padding: 30px`, `background: #1a1a1a`.
2. `.item-galeri` memiliki `display: inline-block`, `width: 300px`, `position: relative`, `overflow: hidden`, `margin: 8px`, `border-radius: 8px`.
3. `img` dalam `.item-galeri` memiliki `display: block`, `width: 100%`, `filter: grayscale(100%)`, transisi `filter 0.4s ease`.
4. `.overlay` diposisikan secara absolute menutupi seluruh `.item-galeri` (top, left, right, bottom: 0), memiliki `background: rgba(0,0,0,0.6)`, `opacity: 0`, transisi `opacity 0.4s ease`, menampilkan teks `<p>` di tengah secara vertikal dan horizontal menggunakan `display: flex` dan properti alignment.
5. Saat `.item-galeri` di-hover:
   - `img` kembali berwarna normal (`filter: grayscale(0%)`).
   - `.overlay` muncul (`opacity: 1`).
   - `img` membesar sedikit (`transform: scale(1.05)`).
6. `.overlay p` berwarna `white`, `font-size: 18px`, `font-weight: bold`, tanpa margin.

**Constraint:**
- Requirement 3 dan 5 wajib menggunakan `transition` yang dituliskan pada state normal.
- Requirement 4 wajib menggunakan `position: absolute`.
- `overflow: hidden` pada `.item-galeri` **wajib** digunakan agar efek scale tidak keluar batas.

---

### Soal 11 — Units: `rem`, `em`, `%`, `vh/vw`

**Deskripsi Kasus:**
Pemahaman unit CSS yang benar adalah fondasi untuk membuat layout yang scalable. Implementasikan layout yang menggunakan berbagai jenis unit dengan tujuan yang tepat.

**Spesifikasi Teknis:**
Buat file `soal-11.html` dengan struktur HTML berikut:

```html
<body>
  <header class="header-utama">
    <nav class="nav-bar">
      <span class="logo">BelajarCSS</span>
      <ul class="nav-links">
        <li><a href="#">Beranda</a></li>
        <li><a href="#">Kelas</a></li>
        <li><a href="#">Tentang</a></li>
      </ul>
    </nav>
  </header>
  <main class="konten-utama">
    <section class="hero-section">
      <h1>Belajar Web dengan Benar</h1>
      <p class="tagline">Mulai perjalanan Anda hari ini.</p>
    </section>
    <section class="info-box">
      <p class="teks-normal">Ini adalah teks dengan ukuran normal.</p>
      <p class="teks-besar">Ini adalah teks yang lebih besar dari induknya.</p>
      <p class="teks-kecil">Ini adalah teks yang lebih kecil dari induknya.</p>
    </section>
  </main>
</body>
```

**Requirement CSS (perhatikan unit yang diminta):**
1. `html` memiliki `font-size: 16px` (basis untuk kalkulasi `rem`).
2. `body` memiliki `margin: 0` dan `font-family: sans-serif`.
3. `.header-utama` memiliki tinggi `4rem`, `background: #2c3e50`, lebar `100%`.
4. `.hero-section` memiliki tinggi **setara 80% tinggi viewport** (`80vh`), `background: #ecf0f1`.
5. `h1` di dalam `.hero-section` berukuran `3rem`. Paragraf `.tagline` berukuran `1.25rem`.
6. `.konten-utama` memiliki `width: 90%` dan `max-width: 1100px`, `margin: 0 auto`.
7. `.info-box` memiliki `font-size: 18px` (basis untuk kalkulasi `em` di dalamnya).
8. `.teks-normal` berukuran `1em` (sama dengan `.info-box`).
9. `.teks-besar` berukuran `1.5em` (1.5× dari `font-size` `.info-box`).
10. `.teks-kecil` berukuran `0.75em` (0.75× dari `font-size` `.info-box`).

**Tambahan — Pertanyaan Analitis (jawab dalam komentar CSS 💬):**
Setelah mengimplementasikan kode, jawab dalam komentar CSS:
- Berapa pixel hasil kalkulasi `.teks-besar`?
- Jika `html { font-size }` diubah menjadi `20px`, berapa pixel tinggi `.header-utama` akan berubah menjadi?
- Apa perbedaan mendasar antara menggunakan `em` dan `rem` untuk `font-size`?

**Constraint:**
- Setiap unit harus digunakan sesuai tujuannya.
- Setiap angka yang diminta dalam `rem` atau `em` harus menggunakan unit tersebut, bukan dikonversi ke `px`.

---

### Soal 12 — Cascade, Layer & `!important`

**Deskripsi Kasus:**
Seorang developer mewarisi sebuah proyek dengan CSS yang sangat berantakan: ada penggunaan `!important` sembarangan dan override yang tidak terkontrol. Anda diminta untuk merestrukturisasi CSS tersebut menggunakan fitur `@layer` dan **menghapus semua** `!important`.

**Spesifikasi Teknis:**
Diberikan kode CSS awal bermasalah berikut dan HTML-nya. Implementasikan ulang dalam file `soal-12.html`:

**HTML (hardcoded, jangan diubah):**
```html
<div class="card">
  <h2 class="card-title">Judul Kartu</h2>
  <p class="card-body">Isi dari kartu ini.</p>
  <button class="btn btn-primary">Tombol Utama</button>
</div>
```

**CSS Bermasalah (ini yang harus Anda refactor):**
```css
/* Semua !important dan konflik harus dihilangkan */
.card { background: white !important; border-radius: 8px; padding: 20px; }
.card { background: #f5f5f5; }                  /* duplikat, kalah */
.card-title { color: crimson !important; font-size: 20px; }
.card-title { color: navy; }                     /* tidak berlaku */
.btn { padding: 10px 20px; border: none; border-radius: 4px; cursor: pointer; }
.btn-primary { background: steelblue !important; color: white !important; }
.btn { background: gray; color: black; }         /* tidak berlaku */
```

**Requirement:**
1. Refactor semua CSS di atas ke dalam struktur `@layer` dengan **tiga layer**: `base`, `komponen`, `utilitas`.
2. Tempatkan styling generik (`.btn`, `.card` dasar) di layer `base`.
3. Tempatkan styling spesifik komponen (`.card-title`, `.card-body`) di layer `komponen`.
4. Tempatkan override final (`.btn-primary`) di layer `utilitas`.
5. Pastikan hasil visual **identik** dengan kode bermasalah aslinya: background kartu `white`, judul `crimson`, tombol `steelblue` dengan teks putih.
6. **Tidak ada** `!important` dalam solusi Anda.

**Tambahan — Jawab dalam komentar CSS 💬:**
- Mengapa urutan deklarasi `@layer` di awal file itu penting?
- Aturan CSS mana yang menang jika sebuah property dideklarasikan di layer `utilitas` dan juga di layer `base`?

**Constraint:**
- Wajib menggunakan `@layer` dengan minimal 3 layer bernama.
- Tidak boleh ada `!important` sama sekali dalam CSS final.

---

## BAGIAN B — Medium to Hard
> **Bobot:** 4 poin per soal × 10 soal = **40 poin**

---

### Soal 13 — Flexbox: Navigation Bar Responsif

**Deskripsi Kasus:**
Implementasikan navigation bar horizontal yang profesional menggunakan Flexbox. Navigation bar harus memiliki logo di kiri, menu di tengah (atau kanan), dan tombol aksi di kanan.

**Spesifikasi Teknis:**
Buat file `soal-13.html` dengan HTML berikut:

```html
<header class="navbar">
  <div class="navbar-brand">
    <span class="logo-teks">DevAcademy</span>
  </div>
  <nav class="navbar-menu">
    <a href="#">Beranda</a>
    <a href="#">Kelas</a>
    <a href="#">Mentor</a>
    <a href="#">Blog</a>
  </nav>
  <div class="navbar-aksi">
    <a href="#" class="btn-masuk">Masuk</a>
    <a href="#" class="btn-daftar">Daftar Gratis</a>
  </div>
</header>
```

**Requirement CSS:**
1. `.navbar` menggunakan `display: flex`, `align-items: center`, tinggi `64px`, `background: white`, `padding: 0 48px`, `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`.
2. `.navbar-brand` berada di sisi kiri. `.navbar-aksi` berada di sisi kanan. `.navbar-menu` berada di tengah. Capai ini menggunakan **satu properti** pada `.navbar-menu`: `margin: auto` (atau teknik flex setara yang membuatnya berada di tengah dengan otomatis menyesuaikan sisa ruang).
3. `.navbar-menu a` memiliki `padding: 0 16px`, `color: #555`, `text-decoration: none`, `font-size: 15px`, `height: 64px` (sama dengan navbar), `display: flex`, `align-items: center`. Saat hover, `color: #e44d26`.
4. `.logo-teks` memiliki `font-size: 22px`, `font-weight: 800`, `color: #2c3e50`.
5. `.navbar-aksi` menggunakan `display: flex`, `gap: 12px`, `align-items: center`.
6. `.btn-masuk` memiliki `padding: 8px 20px`, `color: #555`, `text-decoration: none`, `border: 1px solid #ddd`, `border-radius: 4px`.
7. `.btn-daftar` memiliki `padding: 8px 20px`, `background: #e44d26`, `color: white`, `text-decoration: none`, `border-radius: 4px`.
8. **Bonus requirement:** Saat viewport lebih kecil dari 768px (gunakan media query), `.navbar-menu` disembunyikan (`display: none`) dan `.navbar-brand` mengambil seluruh sisa lebar.

**Constraint:**
- Penempatan tengah `.navbar-menu` **wajib** menggunakan teknik Flexbox (bukan `position: absolute`).
- Wajib menggunakan `gap` untuk jarak antar tombol di `.navbar-aksi`.

---

### Soal 14 — Flexbox: Card Layout & Alignment

**Deskripsi Kasus:**
Implementasikan halaman dengan grid kartu fitur menggunakan Flexbox. Kartu harus memiliki tinggi yang sama meskipun kontennya berbeda panjang, dan tombol di setiap kartu harus selalu berada di bawah.

**Spesifikasi Teknis:**
Buat file `soal-14.html` dengan HTML berikut:

```html
<section class="fitur-section">
  <h2 class="section-title">Fitur Unggulan</h2>
  <div class="kartu-container">
    <div class="kartu-fitur">
      <div class="kartu-ikon">🎓</div>
      <h3>Belajar Fleksibel</h3>
      <p>Akses materi kapan saja dan di mana saja sesuai jadwal Anda tanpa batas waktu.</p>
      <a href="#" class="kartu-link">Pelajari Lebih Lanjut</a>
    </div>
    <div class="kartu-fitur">
      <div class="kartu-ikon">👨‍💻</div>
      <h3>Mentor Berpengalaman</h3>
      <p>Dibimbing oleh praktisi industri yang aktif bekerja di perusahaan teknologi terkemuka di Indonesia.</p>
      <a href="#" class="kartu-link">Lihat Mentor</a>
    </div>
    <div class="kartu-fitur">
      <div class="kartu-ikon">🏆</div>
      <h3>Sertifikat Resmi</h3>
      <p>Dapatkan sertifikat.</p>
      <a href="#" class="kartu-link">Info Sertifikat</a>
    </div>
    <div class="kartu-fitur">
      <div class="kartu-ikon">💬</div>
      <h3>Komunitas Aktif</h3>
      <p>Bergabung dengan ribuan pelajar aktif, diskusi, dan bantu satu sama lain dalam forum eksklusif.</p>
      <a href="#" class="kartu-link">Gabung Komunitas</a>
    </div>
  </div>
</section>
```

**Requirement CSS:**
1. `.kartu-container` menggunakan `display: flex`, `flex-wrap: wrap`, `gap: 24px`, `justify-content: center`, `padding: 0 40px`.
2. Setiap `.kartu-fitur` memiliki `flex: 1 1 220px` (dapat grow, dapat shrink, basis 220px), `max-width: 280px`.
3. **Kunci soal ini:** Setiap `.kartu-fitur` menggunakan `display: flex`, `flex-direction: column`. Elemen `.kartu-link` mendapat `margin-top: auto` sehingga **selalu berada di bawah** kartu, meskipun konten teks kartu berbeda panjang.
4. `.kartu-fitur` memiliki `background: white`, `border-radius: 12px`, `padding: 28px`, `box-shadow: 0 2px 12px rgba(0,0,0,0.08)`.
5. `.kartu-ikon` berukuran `48px`, `font-size: 32px`, `margin-bottom: 16px`.
6. `h3` di kartu berukuran `18px`, `margin: 0 0 10px`, `color: #2c3e50`.
7. `p` di kartu `color: #666`, `font-size: 14px`, `line-height: 1.6`.
8. `.kartu-link` sebagai `display: inline-block`, `margin-top: auto`, `padding: 8px 16px`, `background: #e44d26`, `color: white`, `text-decoration: none`, `border-radius: 4px`, `font-size: 14px`, `align-self: flex-start`.

**Constraint:**
- Teknik "tombol selalu di bawah" **wajib** menggunakan `margin-top: auto` pada flex item, bukan `position: absolute`.
- `flex-wrap: wrap` wajib digunakan agar kartu pindah baris di layar kecil.

---

### Soal 15 — CSS Grid: Layout Dua Dimensi

**Deskripsi Kasus:**
Implementasikan layout halaman dashboard menggunakan CSS Grid dengan area-area yang dinamai menggunakan `grid-template-areas`. Layout harus memiliki header, sidebar, konten utama, dan footer.

**Spesifikasi Teknis:**
Buat file `soal-15.html` dengan HTML berikut:

```html
<div class="dashboard">
  <header class="db-header">Header Dashboard</header>
  <aside class="db-sidebar">
    <nav>
      <ul>
        <li>Menu 1</li>
        <li>Menu 2</li>
        <li>Menu 3</li>
      </ul>
    </nav>
  </aside>
  <main class="db-konten">
    <div class="widget">Widget A</div>
    <div class="widget">Widget B</div>
    <div class="widget">Widget C</div>
    <div class="widget">Widget D</div>
  </main>
  <footer class="db-footer">Footer Dashboard</footer>
</div>
```

**Requirement CSS:**
1. `.dashboard` menggunakan `display: grid` dengan `grid-template-columns: 240px 1fr` dan `grid-template-rows: 64px 1fr 50px`, `min-height: 100vh`.
2. `.dashboard` menggunakan `grid-template-areas` sebagai berikut:
   ```
   "header  header"
   "sidebar konten"
   "footer  footer"
   ```
3. Masing-masing area dihubungkan ke elemen yang tepat menggunakan `grid-area`.
4. `.db-header` memiliki `background: #2c3e50`, `color: white`, `display: flex`, `align-items: center`, `padding: 0 24px`, `font-size: 20px`, `font-weight: bold`.
5. `.db-sidebar` memiliki `background: #34495e`, `color: white`, `padding: 20px`. `ul` di dalamnya tidak memiliki list-style dan padding 0. `li` memiliki `padding: 10px 12px`, `border-radius: 4px`, `cursor: pointer`. Saat `li` di-hover, `background: rgba(255,255,255,0.1)`.
6. `.db-konten` memiliki `background: #ecf0f1`, `padding: 24px`. Di dalamnya, `.widget` ditampilkan menggunakan **CSS Grid** dengan 2 kolom sama lebar (`repeat(2, 1fr)`), `gap: 16px`. Setiap `.widget` memiliki `background: white`, `padding: 20px`, `border-radius: 8px`, `box-shadow: 0 1px 4px rgba(0,0,0,0.1)`.
7. `.db-footer` memiliki `background: #2c3e50`, `color: #aaa`, `display: flex`, `align-items: center`, `justify-content: center`, `font-size: 13px`.

**Constraint:**
- Wajib menggunakan `grid-template-areas` dan `grid-area` untuk penempatan elemen utama.
- Nested grid di dalam `.db-konten` wajib menggunakan `repeat()` dan `1fr`.

---

### Soal 16 — CSS Grid: Item Spanning & Alignment

**Deskripsi Kasus:**
Implementasikan layout majalah (magazine layout) menggunakan CSS Grid di mana beberapa artikel menempati lebih dari satu kolom atau baris (grid spanning).

**Spesifikasi Teknis:**
Buat file `soal-16.html` dengan HTML berikut:

```html
<div class="majalah">
  <article class="artikel featured">
    <img src="https://picsum.photos/seed/m1/600/400" alt="">
    <h2>Artikel Utama: Revolusi AI di 2026</h2>
    <p>Kecerdasan buatan semakin mengubah cara kita bekerja dan belajar setiap harinya.</p>
  </article>
  <article class="artikel">
    <img src="https://picsum.photos/seed/m2/300/200" alt="">
    <h2>Berita Teknologi</h2>
    <p>Update terbaru dari dunia teknologi dan inovasi digital global.</p>
  </article>
  <article class="artikel">
    <img src="https://picsum.photos/seed/m3/300/200" alt="">
    <h2>Tips Produktivitas</h2>
    <p>Cara efektif mengatur waktu dan meningkatkan produktivitas harian Anda.</p>
  </article>
  <article class="artikel wide">
    <img src="https://picsum.photos/seed/m4/600/200" alt="">
    <h2>Laporan Khusus: Industri Kreatif Indonesia</h2>
    <p>Menelusuri pertumbuhan ekonomi kreatif dan potensi yang belum tereksplor.</p>
  </article>
  <article class="artikel">
    <img src="https://picsum.photos/seed/m5/300/200" alt="">
    <h2>Review Gadget</h2>
    <p>Ulasan mendalam produk teknologi terbaru untuk Anda.</p>
  </article>
</div>
```

**Requirement CSS:**
1. `.majalah` menggunakan `display: grid`, `grid-template-columns: repeat(3, 1fr)`, `gap: 20px`, `padding: 30px`, `background: #f0f0f0`.
2. `.artikel.featured` (artikel utama) menempati **2 kolom dan 2 baris**: `grid-column: span 2` dan `grid-row: span 2`.
3. `.artikel.wide` (artikel lebar) menempati **seluruh 3 kolom**: `grid-column: 1 / -1`.
4. Setiap `.artikel` memiliki `background: white`, `border-radius: 8px`, `overflow: hidden`, `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`.
5. `img` di dalam `.artikel` memiliki `width: 100%`, `height: 200px`, `object-fit: cover`.
6. `h2` dan `p` di dalam `.artikel` memiliki `padding: 0 16px`. `h2` berukuran `16px`, `margin: 12px 0 6px`. `p` berukuran `13px`, `color: #666`.
7. `.artikel.featured img` memiliki `height: 280px`.

**Constraint:**
- Wajib menggunakan `grid-column: span` atau `grid-column: start / end` untuk spanning.
- `object-fit: cover` wajib digunakan pada gambar.
- `grid-column: 1 / -1` atau `span 3` wajib digunakan untuk `.wide`.

---

### Soal 17 — Positioning: Z-index & Stacking Context

**Deskripsi Kasus:**
Implementasikan komponen modal (popup dialog) dan tooltip menggunakan CSS positioning. Komponen ini menguji pemahaman tentang z-index, stacking context, dan koordinasi `position: absolute/fixed`.

**Spesifikasi Teknis:**
Buat file `soal-17.html` dengan HTML berikut:

```html
<body>
  <div class="halaman-konten">
    <h1>Halaman Utama</h1>
    <p>Ini adalah konten halaman biasa.</p>

    <div class="tooltip-wrapper">
      <button class="btn-info">Hover untuk Info ℹ️</button>
      <div class="tooltip">Ini adalah teks tooltip yang informatif!</div>
    </div>

    <button class="btn-buka-modal" onclick="document.getElementById('modal').style.display='flex'">
      Buka Modal
    </button>
  </div>

  <div class="overlay-modal" id="modal" style="display:none;">
    <div class="modal-kotak">
      <button class="modal-tutup" onclick="document.getElementById('modal').style.display='none'">✕</button>
      <h2>Judul Modal</h2>
      <p>Ini adalah isi dari modal dialog. Konten di belakang modal harus terlihat teredup.</p>
      <button class="btn-konfirmasi">Konfirmasi</button>
    </div>
  </div>
</body>
```

> *Catatan: Penggunaan `onclick` inline di soal ini diizinkan untuk tujuan demonstrasi CSS. Fokus evaluasi ada pada CSS, bukan JavaScript.*

**Requirement CSS:**
1. `.overlay-modal` menggunakan `position: fixed`, menutupi seluruh layar (top/left/right/bottom: 0), `background: rgba(0,0,0,0.5)`, `z-index: 1000`, `display: flex`, `align-items: center`, `justify-content: center`.
2. `.modal-kotak` memiliki `background: white`, `border-radius: 12px`, `padding: 32px`, `max-width: 480px`, `width: 90%`, `position: relative`.
3. `.modal-tutup` diposisikan `position: absolute`, `top: 12px`, `right: 12px`, `background: none`, `border: none`, `font-size: 20px`, `cursor: pointer`.
4. `.btn-konfirmasi` memiliki `padding: 10px 24px`, `background: #27ae60`, `color: white`, `border: none`, `border-radius: 4px`, `cursor: pointer`.
5. `.tooltip-wrapper` menggunakan `position: relative`, `display: inline-block`.
6. `.tooltip` menggunakan `position: absolute`, `bottom: calc(100% + 8px)`, `left: 50%`, `transform: translateX(-50%)`, `background: #2c3e50`, `color: white`, `padding: 8px 14px`, `border-radius: 4px`, `white-space: nowrap`, `font-size: 13px`, `opacity: 0`, transisi `opacity 0.2s`. **Saat `.tooltip-wrapper` di-hover**, `.tooltip` muncul (`opacity: 1`).
7. `.tooltip::after` menambahkan panah segitiga ke bawah: `content: ""`, `position: absolute`, `top: 100%`, `left: 50%`, `transform: translateX(-50%)`, `border: 6px solid transparent`, `border-top-color: #2c3e50`.

**Constraint:**
- `.overlay-modal` wajib menggunakan `position: fixed` (bukan absolute).
- `.modal-tutup` wajib menggunakan `position: absolute` relatif terhadap `.modal-kotak`.
- Tooltip wajib muncul melalui `:hover` pada `.tooltip-wrapper`, bukan JavaScript.

---

### Soal 18 — Sticky & Fixed Positioning

**Deskripsi Kasus:**
Implementasikan halaman artikel panjang dengan header yang `fixed`, sidebar Table of Contents yang `sticky`, dan tombol "Kembali ke Atas" yang `fixed` di pojok kanan bawah.

**Spesifikasi Teknis:**
Buat file `soal-18.html` dengan HTML berikut:

```html
<body>
  <header class="fixed-header">
    <span>📚 Portal Belajar</span>
  </header>

  <div class="layout-artikel">
    <aside class="toc">
      <h3>Daftar Isi</h3>
      <ul>
        <li><a href="#bab1">1. Pengenalan</a></li>
        <li><a href="#bab2">2. Konsep Dasar</a></li>
        <li><a href="#bab3">3. Implementasi</a></li>
        <li><a href="#bab4">4. Kesimpulan</a></li>
      </ul>
    </aside>

    <article class="isi-artikel">
      <h1 id="bab1">1. Pengenalan</h1>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>

      <h2 id="bab2">2. Konsep Dasar</h2>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>

      <h2 id="bab3">3. Implementasi</h2>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>

      <h2 id="bab4">4. Kesimpulan</h2>
      <p><!-- Isi 5 kalimat lorem ipsum --></p>
    </article>
  </div>

  <a href="#" class="tombol-atas">↑ Atas</a>
</body>
```

> *Isi paragraf dapat diisi dengan teks lorem ipsum yang cukup untuk membuat halaman dapat di-scroll.*

**Requirement CSS:**
1. `body` memiliki `margin: 0`, `padding-top: 60px` (untuk mengimbangi `fixed-header`).
2. `.fixed-header` menggunakan `position: fixed`, `top: 0`, `left: 0`, `right: 0`, `height: 60px`, `background: #2c3e50`, `color: white`, `display: flex`, `align-items: center`, `padding: 0 24px`, `z-index: 100`.
3. `.layout-artikel` menggunakan `display: flex`, `max-width: 1000px`, `margin: 0 auto`, `padding: 40px 20px`, `gap: 40px`.
4. `.toc` menggunakan `position: sticky`, `top: 80px` (20px di bawah fixed-header), `width: 220px`, `flex-shrink: 0`, `align-self: flex-start`, `background: #f8f8f8`, `padding: 16px`, `border-radius: 8px`.
5. `.isi-artikel` menggunakan `flex: 1`, `min-width: 0`.
6. `.tombol-atas` menggunakan `position: fixed`, `bottom: 30px`, `right: 30px`, `background: #e44d26`, `color: white`, `padding: 12px 16px`, `border-radius: 50%`, `text-decoration: none`, `font-weight: bold`, `z-index: 99`.

**Tambahan — Jawab dalam komentar CSS 💬:**
- Mengapa `.toc` membutuhkan `align-self: flex-start`? Apa yang terjadi jika properti ini dihapus?
- Mengapa `min-width: 0` diperlukan pada `.isi-artikel`?

**Constraint:**
- Wajib menggunakan `position: sticky` untuk TOC, bukan `fixed`.
- Wajib menggunakan `position: fixed` untuk header dan tombol kembali ke atas.

---

### Soal 19 — Media Query: Responsive Layout

**Deskripsi Kasus:**
Implementasikan halaman yang **sepenuhnya responsif** menggunakan pendekatan **mobile-first**. Halaman yang sama harus tampil berbeda di tiga ukuran layar: mobile (<600px), tablet (600px–1024px), dan desktop (>1024px).

**Spesifikasi Teknis:**
Buat file `soal-19.html` dengan HTML berikut:

```html
<body>
  <header class="header-resp">
    <div class="brand">MyApp</div>
    <nav class="nav-resp">
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Contact</a>
    </nav>
  </header>
  <main class="main-resp">
    <section class="konten-resp">
      <h1>Responsive Design</h1>
      <p>Halaman ini berubah layout tergantung ukuran layar.</p>
    </section>
    <section class="kartu-resp-wrapper">
      <div class="kartu-resp">Kartu 1</div>
      <div class="kartu-resp">Kartu 2</div>
      <div class="kartu-resp">Kartu 3</div>
      <div class="kartu-resp">Kartu 4</div>
      <div class="kartu-resp">Kartu 5</div>
      <div class="kartu-resp">Kartu 6</div>
    </section>
  </main>
</body>
```

**Requirement CSS — Mobile First (default, no media query):**
1. `.header-resp` menggunakan `display: flex`, `flex-direction: column`, `align-items: flex-start`, `padding: 16px`, `background: #2c3e50`, `color: white`, `gap: 12px`.
2. `.nav-resp` menampilkan link secara vertikal (`display: flex`, `flex-direction: column`, `gap: 8px`). Link berwarna `rgba(255,255,255,0.8)`, `text-decoration: none`.
3. `.kartu-resp-wrapper` menggunakan `display: grid`, `grid-template-columns: 1fr` (1 kolom), `gap: 16px`, `padding: 16px`.
4. `.kartu-resp` memiliki `background: steelblue`, `color: white`, `padding: 24px`, `border-radius: 8px`, `text-align: center`.

**Requirement CSS — Tablet (`@media (min-width: 600px)`):**
5. `.header-resp` berubah menjadi `flex-direction: row`, `justify-content: space-between`, `align-items: center`.
6. `.nav-resp` berubah menjadi `flex-direction: row`, `gap: 20px`.
7. `.kartu-resp-wrapper` berubah menjadi `grid-template-columns: repeat(2, 1fr)` (2 kolom).

**Requirement CSS — Desktop (`@media (min-width: 1024px)`):**
8. `.header-resp` memiliki `padding: 0 48px`, tinggi `64px`.
9. `.kartu-resp-wrapper` berubah menjadi `grid-template-columns: repeat(3, 1fr)` (3 kolom), `padding: 30px 48px`.
10. `.main-resp` memiliki `max-width: 1200px`, `margin: 0 auto`.

**Constraint:**
- Wajib menggunakan pendekatan **mobile-first** (default styles untuk mobile, kemudian media query untuk breakpoint yang lebih besar).
- Wajib menggunakan `min-width` dalam media query (bukan `max-width`).
- Verifikasikan dengan mengubah ukuran browser window.

---

### Soal 20 — Flexbox Advanced: Flex Grow, Shrink & Basis

**Deskripsi Kasus:**
Implementasikan layout sidebar-konten yang memanfaatkan properti `flex-grow`, `flex-shrink`, dan `flex-basis` secara eksplisit untuk mengatur distribusi ruang yang dinamis.

**Spesifikasi Teknis:**
Buat file `soal-20.html` dengan HTML berikut:

```html
<div class="app-layout">
  <aside class="sidebar-kiri">
    <h3>Sidebar Kiri</h3>
    <p>Navigasi utama aplikasi.</p>
  </aside>
  <main class="konten-tengah">
    <h2>Konten Utama</h2>
    <p>Area ini harus mengambil seluruh sisa ruang yang tersedia.</p>
  </main>
  <aside class="sidebar-kanan">
    <h3>Sidebar Kanan</h3>
    <p>Widget dan informasi tambahan.</p>
  </aside>
</div>

<hr>

<div class="progress-bar-demo">
  <div class="progress-label">JavaScript</div>
  <div class="progress-track">
    <div class="progress-fill" style="--persen: 85%"></div>
  </div>
  <div class="progress-persen">85%</div>
</div>
<div class="progress-bar-demo">
  <div class="progress-label">CSS</div>
  <div class="progress-track">
    <div class="progress-fill" style="--persen: 92%"></div>
  </div>
  <div class="progress-persen">92%</div>
</div>
```

**Requirement CSS — App Layout:**
1. `.app-layout` menggunakan `display: flex`, `height: 400px`, `gap: 16px`, `padding: 20px`, `background: #f0f0f0`.
2. `.sidebar-kiri` menggunakan `flex: 0 0 200px` (tidak grow, tidak shrink, basis tetap 200px). `background: #2c3e50`, `color: white`, `padding: 20px`, `border-radius: 8px`.
3. `.konten-tengah` menggunakan `flex: 1 1 auto` (grow sebanyak mungkin, dapat shrink, basis auto). `background: white`, `padding: 20px`, `border-radius: 8px`.
4. `.sidebar-kanan` menggunakan `flex: 0 1 160px` (tidak grow, dapat shrink, basis 160px). `background: #ecf0f1`, `padding: 20px`, `border-radius: 8px`.

**Requirement CSS — Progress Bar:**
5. `.progress-bar-demo` menggunakan `display: flex`, `align-items: center`, `gap: 12px`, `padding: 8px 20px`.
6. `.progress-label` menggunakan `flex: 0 0 80px`, `font-weight: bold`.
7. `.progress-track` menggunakan `flex: 1`, `height: 12px`, `background: #ddd`, `border-radius: 6px`, `overflow: hidden`.
8. `.progress-fill` menggunakan `height: 100%`, `width: var(--persen)`, `background: linear-gradient(to right, #27ae60, #2ecc71)`, `border-radius: 6px`.
9. `.progress-persen` menggunakan `flex: 0 0 40px`, `font-size: 13px`, `color: #555`, `text-align: right`.

**Tambahan — Jawab dalam komentar CSS 💬:**
- Apa arti dari `flex: 0 0 200px`? Sebutkan masing-masing nilai `flex-grow`, `flex-shrink`, `flex-basis`.
- Mengapa `.sidebar-kanan` menggunakan `flex-shrink: 1` tapi `.sidebar-kiri` tidak?

**Constraint:**
- Wajib menggunakan shorthand `flex: [grow] [shrink] [basis]` untuk ketiga sidebar/konten.
- `var(--persen)` wajib digunakan untuk lebar progress fill (demonstrasi CSS Custom Properties).

---

### Soal 21 — Grid Advanced: `fr`, `minmax()` & `auto-fill`

**Deskripsi Kasus:**
Implementasikan layout grid responsif yang secara otomatis menyesuaikan jumlah kolom menggunakan `auto-fill` dan `minmax()`, tanpa media query apapun.

**Spesifikasi Teknis:**
Buat file `soal-21.html` dengan HTML berikut:

```html
<div class="galeri-produk">
  <div class="produk-item">
    <img src="https://picsum.photos/seed/p1/280/200" alt="Produk 1">
    <div class="produk-info">
      <h3>Produk Alpha</h3>
      <p class="harga-produk">Rp 250.000</p>
      <button>Beli Sekarang</button>
    </div>
  </div>
  <div class="produk-item">
    <img src="https://picsum.photos/seed/p2/280/200" alt="Produk 2">
    <div class="produk-info">
      <h3>Produk Beta</h3>
      <p class="harga-produk">Rp 175.000</p>
      <button>Beli Sekarang</button>
    </div>
  </div>
  <div class="produk-item">
    <img src="https://picsum.photos/seed/p3/280/200" alt="Produk 3">
    <div class="produk-info">
      <h3>Produk Gamma</h3>
      <p class="harga-produk">Rp 320.000</p>
      <button>Beli Sekarang</button>
    </div>
  </div>
  <div class="produk-item">
    <img src="https://picsum.photos/seed/p4/280/200" alt="Produk 4">
    <div class="produk-info">
      <h3>Produk Delta</h3>
      <p class="harga-produk">Rp 95.000</p>
      <button>Beli Sekarang</button>
    </div>
  </div>
  <div class="produk-item">
    <img src="https://picsum.photos/seed/p5/280/200" alt="Produk 5">
    <div class="produk-info">
      <h3>Produk Epsilon</h3>
      <p class="harga-produk">Rp 450.000</p>
      <button>Beli Sekarang</button>
    </div>
  </div>
</div>
```

**Requirement CSS:**
1. `.galeri-produk` menggunakan `display: grid`, `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))`, `gap: 24px`, `padding: 30px`.
2. `.produk-item` menggunakan `display: flex`, `flex-direction: column`, `background: white`, `border-radius: 10px`, `overflow: hidden`, `box-shadow: 0 2px 10px rgba(0,0,0,0.1)`, transisi `transform 0.2s, box-shadow 0.2s`. Saat hover: `transform: translateY(-4px)`, `box-shadow: 0 8px 24px rgba(0,0,0,0.15)`.
3. `img` di `.produk-item` memiliki `width: 100%`, `height: 180px`, `object-fit: cover`.
4. `.produk-info` memiliki `padding: 16px`, `display: flex`, `flex-direction: column`, `flex: 1`.
5. `h3` di `.produk-info` berukuran `16px`, `margin: 0 0 8px`.
6. `.harga-produk` memiliki `color: #e44d26`, `font-weight: bold`, `font-size: 18px`, `margin: 0 0 12px`.
7. `button` di `.produk-info` menggunakan `margin-top: auto`, `padding: 10px`, `width: 100%`, `background: #2c3e50`, `color: white`, `border: none`, `border-radius: 6px`, `cursor: pointer`. Saat hover: `background: #34495e`.

**Tambahan — Jawab dalam komentar CSS 💬:**
- Apa perbedaan antara `auto-fill` dan `auto-fit` dalam konteks `repeat()`?
- Mengapa tidak diperlukan media query sama sekali untuk layout ini?

**Constraint:**
- Wajib menggunakan `repeat(auto-fill, minmax(...))` — tidak boleh diganti dengan media query.
- `object-fit: cover` wajib digunakan pada gambar.

---

### Soal 22 — Float, Multiple Column & Display None

**Deskripsi Kasus:**
Implementasikan halaman artikel majalah menggunakan teknik `float` untuk drop cap, `column-count` untuk teks multi-kolom, dan `display: none` yang dikendalikan pseudo-class `:focus-within` untuk menampilkan konten tersembunyi.

**Spesifikasi Teknis:**
Buat file `soal-22.html` dengan HTML berikut:

```html
<article class="artikel-majalah">
  <h1 class="judul-majalah">Mengenal Teknologi Web Modern</h1>

  <p class="artikel-konten">
    <span class="drop-cap">T</span>eknologi web telah berkembang pesat dalam satu dekade terakhir.
    Dari HTML statis hingga aplikasi web yang kompleks, perjalanan ini dipenuhi
    inovasi yang mengubah cara kita berinteraksi dengan internet setiap harinya.
    CSS Layout seperti Flexbox dan Grid telah merevolusi cara developer membuat tampilan.
    Kini membuat layout yang responsif jauh lebih mudah dibanding era float-based layout.
    Media query memungkinkan satu halaman tampil sempurna di berbagai ukuran layar.
  </p>

  <div class="teks-multi-kolom">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum ante ipsum
    primis in faucibus orci. Sed do eiusmod tempor incididunt ut labore et dolore magna.
    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip.
    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu.
    Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt.
    Nullam dapibus fermentum ipsum. Maecenas aliquet accumsan leo. Vivamus condimentum.
    Proin commodo diam. Pellentesque habitant morbi tristique senectus et netus malesuada.</p>
  </div>

  <div class="spoiler">
    <button class="spoiler-tombol" tabindex="0">🔍 Klik untuk Lihat Fakta Menarik</button>
    <div class="spoiler-konten">
      <p>CSS pertama kali diusulkan oleh Håkon Wium Lie pada Oktober 1994.
         Grid Layout baru menjadi standard browser pada tahun 2017.</p>
    </div>
  </div>
</article>
```

**Requirement CSS:**
1. `.artikel-majalah` memiliki `max-width: 760px`, `margin: 40px auto`, `padding: 0 20px`, `font-family: Georgia, serif`.
2. `.drop-cap` menggunakan `float: left`, `font-size: 72px`, `line-height: 0.8`, `padding-right: 8px`, `padding-top: 4px`, `color: #e44d26`, `font-weight: bold`. Pastikan teks di sampingnya mengalir melingkari huruf besar tersebut.
3. `.artikel-konten` memiliki `line-height: 1.7`, `margin-bottom: 24px`. Tambahkan `overflow: hidden` atau `clearfix` agar container tidak kolaps akibat float.
4. `.teks-multi-kolom` menggunakan `column-count: 3`, `column-gap: 24px`, `column-rule: 1px solid #ddd`, `font-size: 14px`, `line-height: 1.6`, `color: #555`.
5. `.spoiler-tombol` memiliki `display: block`, `width: 100%`, `padding: 12px`, `background: #ecf0f1`, `border: none`, `border-radius: 6px`, `cursor: pointer`, `text-align: left`, `font-size: 15px`.
6. `.spoiler-konten` secara default `display: none`.
7. Saat elemen `.spoiler` dalam kondisi `:focus-within` (ketika tombol di dalamnya di-focus/diklik), `.spoiler-konten` berubah menjadi `display: block` dan mendapat `background: #fff3cd`, `padding: 16px`, `border-radius: 6px`, `margin-top: 8px`.

**Constraint:**
- Requirement 2 wajib menggunakan `float: left`.
- Requirement 4 wajib menggunakan `column-count`, `column-gap`, dan `column-rule`.
- Requirement 7 wajib menggunakan pseudo-class `:focus-within` pada `.spoiler`.

---

## BAGIAN C — Hard / Applied Problem
> **Bobot:** 6 poin per soal × 4 soal = **24 poin**

---

### Soal 23 — Mini Project: Landing Page Responsif Penuh

**Deskripsi Kasus:**
Implementasikan halaman landing page satu halaman (*single-page*) yang responsif penuh, mengintegrasikan seluruh teknik CSS yang telah dipelajari. Ini adalah soal capstone yang menguji kemampuan sintesis.

**Spesifikasi Teknis:**
Buat file `soal-23.html`. HTML-nya **Anda buat sendiri** sesuai spesifikasi berikut. Tidak ada HTML yang diberikan.

**Section yang harus dibuat (dengan urutan vertikal):**
1. **Navbar Sticky** — Logo di kiri, menu di kanan. Sticky di atas saat scroll. Menggunakan Flexbox.
2. **Hero Section** — Tinggi 100vh, background gradient atau gambar, judul besar, subteks, dan tombol CTA (Call-to-Action) di tengah secara vertikal-horizontal.
3. **Fitur Section** — Grid 3 kolom (responsif ke 1 kolom di mobile). Minimal 3 kartu fitur dengan ikon (bisa emoji), judul, deskripsi.
4. **Pricing Section** — Flexbox dengan 3 paket harga. Paket tengah ("Recommended") harus memiliki tampilan yang menonjol (warna berbeda, `transform: scale(1.05)` atau border tebal).
5. **Footer** — Background gelap, teks tengah, copyright.

**Responsive Breakpoints yang wajib diimplementasikan:**
- Mobile (<600px): Semua section satu kolom, navbar menu disembunyikan.
- Desktop (≥600px): Layout seperti spesifikasi di atas.

**Requirement Teknis Minimum:**
- Minimal 5 jenis selector yang berbeda (type, class, id, pseudo-class, pseudo-element atau attribute).
- Minimal menggunakan: Flexbox, Grid, `position: sticky`, `@media`, `transition`, `::before` atau `::after`, `box-shadow`, `border-radius`, gradient.
- Seluruh teks, warna, dan konten boleh bebas sesuai kreativitas.
- Wajib ada file yang dapat dibuka dan dilihat di browser tanpa error.

**Constraint:**
- Tidak boleh menggunakan CSS framework apapun.
- Tidak boleh menggunakan JavaScript untuk styling atau layout.
- HTML dan CSS boleh dalam satu file `.html`.

---

### Soal 24 — CSS Animation & Transition: Loading & Skeleton Screen

**Deskripsi Kasus:**
Implementasikan dua jenis efek animasi yang umum digunakan dalam aplikasi web modern: loading spinner dan skeleton screen (placeholder loading). Keduanya harus diimplementasikan hanya dengan CSS tanpa JavaScript.

**Spesifikasi Teknis:**
Buat file `soal-24.html` dengan HTML berikut:

```html
<body>
  <h2>Loading Spinner</h2>
  <div class="spinner-wrapper">
    <div class="spinner"></div>
    <p class="loading-teks">Memuat data...</p>
  </div>

  <hr>

  <h2>Skeleton Screen</h2>
  <div class="skeleton-card">
    <div class="skeleton skeleton-img"></div>
    <div class="skeleton-body">
      <div class="skeleton skeleton-judul"></div>
      <div class="skeleton skeleton-teks"></div>
      <div class="skeleton skeleton-teks pendek"></div>
    </div>
  </div>

  <div class="skeleton-card">
    <div class="skeleton skeleton-img"></div>
    <div class="skeleton-body">
      <div class="skeleton skeleton-judul"></div>
      <div class="skeleton skeleton-teks"></div>
      <div class="skeleton skeleton-teks pendek"></div>
    </div>
  </div>
</body>
```

**Requirement CSS:**

**Spinner:**
1. `.spinner` adalah sebuah `div` berbentuk lingkaran (`border-radius: 50%`), berukuran `48px × 48px`. Memiliki `border: 5px solid #e0e0e0`. Sisi atas border berwarna `steelblue` (`border-top-color`). Dianimasikan untuk berputar penuh dalam `0.8s` secara linear dan infinite menggunakan `@keyframes`.
2. `.loading-teks` memiliki animasi `opacity` yang berkedip (0.4 → 1 → 0.4) dalam `1.5s` ease-in-out infinite.

**Skeleton Screen:**
3. `.skeleton-card` menggunakan `display: flex`, `gap: 16px`, `padding: 20px`, `background: white`, `border-radius: 10px`, `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`, `max-width: 500px`, `margin: 16px auto`.
4. `.skeleton` (base class) memiliki `background: #e0e0e0`, `border-radius: 4px`, `position: relative`, `overflow: hidden`.
5. `.skeleton::after` mengimplementasikan efek **shimmer** (kilap berjalan): sebuah gradien `linear-gradient(90deg, transparent, rgba(255,255,255,0.6), transparent)` yang diposisikan `absolute` dan bergerak dari kiri ke kanan menggunakan animasi `@keyframes` dalam `1.5s` linear infinite.
6. `.skeleton-img` berukuran `80px × 80px`, `border-radius: 8px`, `flex-shrink: 0`.
7. `.skeleton-judul` memiliki `height: 18px`, `width: 60%`, `margin-bottom: 10px`.
8. `.skeleton-teks` memiliki `height: 12px`, `width: 100%`, `margin-bottom: 8px`.
9. `.skeleton-teks.pendek` memiliki `width: 45%`.

**Constraint:**
- Wajib mendefinisikan minimal 2 `@keyframes` yang berbeda (satu untuk spinner, satu untuk shimmer/opacity).
- Animasi shimmer wajib menggunakan `::after` pseudo-element.
- Tidak boleh menggunakan JavaScript.

---

### Soal 25 — CSS Custom Properties (Variables) & Theme Switching

**Deskripsi Kasus:**
Implementasikan sistem tema gelap/terang (*dark/light mode*) menggunakan CSS Custom Properties (`var()`) tanpa JavaScript. Penggantian tema dilakukan menggunakan checkbox HTML dan selector CSS.

**Spesifikasi Teknis:**
Buat file `soal-25.html` dengan HTML berikut:

```html
<body>
  <input type="checkbox" id="tema-toggle" class="tema-checkbox">

  <div class="app-wrapper">
    <header class="app-header">
      <h1>CSS Theme Demo</h1>
      <label for="tema-toggle" class="tema-label">
        <span class="tema-icon">🌙</span>
        <span class="tema-teks">Dark Mode</span>
      </label>
    </header>

    <main class="app-konten">
      <div class="app-card">
        <h2>Kartu Informasi</h2>
        <p>Ini adalah contoh konten kartu yang akan berubah warnanya berdasarkan tema yang dipilih.</p>
        <button class="app-btn">Tombol Aksi</button>
      </div>
      <div class="app-card">
        <h2>Kartu Kedua</h2>
        <p>Seluruh elemen menggunakan CSS Custom Properties agar perubahan tema berlaku secara konsisten.</p>
        <button class="app-btn">Tombol Aksi</button>
      </div>
    </main>
  </div>
</body>
```

**Requirement CSS:**

**Definisi Tema:**
1. Definisikan variabel tema light pada `:root`: `--bg-page: #f0f2f5`, `--bg-surface: #ffffff`, `--bg-header: #2c3e50`, `--text-primary: #1a1a1a`, `--text-secondary: #555`, `--accent: #3498db`, `--border: #e0e0e0`.
2. Saat `#tema-toggle:checked`, override semua variabel pada `.app-wrapper` menjadi tema dark: `--bg-page: #121212`, `--bg-surface: #1e1e1e`, `--bg-header: #0d0d0d`, `--text-primary: #f0f0f0`, `--text-secondary: #aaa`, `--accent: #64b5f6`, `--border: #333`.

**Penggunaan Variabel:**
3. `.tema-checkbox` disembunyikan (`display: none`).
4. `.app-wrapper` menggunakan `background: var(--bg-page)`, `min-height: 100vh`, `transition: background 0.3s`.
5. `.app-header` menggunakan `background: var(--bg-header)`, `color: white`, `padding: 16px 32px`, `display: flex`, `justify-content: space-between`, `align-items: center`.
6. `.app-konten` menggunakan `display: grid`, `grid-template-columns: repeat(auto-fill, minmax(280px, 1fr))`, `gap: 20px`, `padding: 30px`.
7. `.app-card` menggunakan `background: var(--bg-surface)`, `color: var(--text-primary)`, `border: 1px solid var(--border)`, `border-radius: 10px`, `padding: 24px`, `transition: background 0.3s, color 0.3s, border-color 0.3s`.
8. `p` di `.app-card` menggunakan `color: var(--text-secondary)`.
9. `.app-btn` menggunakan `background: var(--accent)`, `color: white`, `border: none`, `padding: 10px 20px`, `border-radius: 6px`, `cursor: pointer`.
10. `.tema-label` menggunakan `cursor: pointer`, `display: flex`, `align-items: center`, `gap: 8px`, `color: white`.
11. Saat `#tema-toggle:checked` (dark mode aktif), `.tema-teks` berubah kontennya tidak bisa diubah secara CSS, tapi `.tema-icon::before` dapat menampilkan emoji matahari menggunakan `content: "☀️"` dan menyembunyikan `🌙` asli.

**Tambahan — Jawab dalam komentar CSS 💬:**
- Apa keuntungan menggunakan CSS Custom Properties dibanding menuliskan nilai warna langsung di setiap selector?
- Mengapa selector `#tema-toggle:checked ~ .app-wrapper` (general sibling combinator) dibutuhkan untuk melakukan perubahan dari checkbox ke elemen lain?

**Constraint:**
- Wajib menggunakan minimal 6 CSS Custom Properties yang berbeda.
- Semua perubahan warna antar tema wajib melalui variabel (`var()`), bukan nilai hardcoded.
- Penggantian tema wajib menggunakan CSS `~` sibling combinator dengan checkbox, tanpa JavaScript.

---

### Soal 26 — Integrasi Total: Profile Card Component

**Deskripsi Kasus:**
Implementasikan komponen **Profile Card** yang kompleks dan interaktif hanya dengan HTML dan CSS. Komponen ini harus menggabungkan positioning, flexbox/grid, pseudo-elements, animasi, dan custom properties dalam satu komponen yang kohesif dan siap produksi.

**Spesifikasi Teknis:**
Buat file `soal-26.html`. HTML-nya **Anda buat sendiri**. Komponen harus memiliki struktur logis yang mencerminkan komponen kartu profil yang nyata.

**Komponen yang harus dibuat:**

**Profile Card (satu kartu utama + 3 kartu mini dalam grid):**

Kartu profil utama harus memiliki:
- Bagian **header** dengan background gradient dan foto avatar (bisa gunakan `https://i.pravatar.cc/120`).
- Badge status (online/offline) yang diposisikan menggunakan `position: absolute` di sudut avatar.
- Nama, jabatan, dan bio singkat.
- Statistik dalam 3 kolom (Posts, Followers, Following) menggunakan Grid.
- Dua tombol aksi (Follow dan Message) menggunakan Flexbox.
- Saat kartu di-hover: efek elevasi (`transform: translateY(-4px)`, `box-shadow` lebih dalam).

**Tiga kartu mini** di bawah kartu utama (dalam satu baris menggunakan Grid) menampilkan skill/badge:
- Setiap kartu mini memiliki ikon (emoji), nama skill, dan level (persentase ditampilkan sebagai progress bar CSS murni).

**Requirement Teknis Minimum yang Harus Ada:**
1. Minimal 2 CSS Custom Properties (`--warna-utama`, `--warna-aksen`, dll.).
2. Minimal 1 penggunaan `position: absolute` untuk elemen yang di-overlay.
3. Minimal 1 penggunaan `::before` atau `::after` untuk ornamen dekoratif.
4. Gradient pada header kartu menggunakan `linear-gradient`.
5. Semua transisi interaktif menggunakan `transition` (bukan JavaScript).
6. Layout responsif: di mobile (<500px) semua kartu menumpuk vertikal.
7. Foto avatar berbentuk lingkaran sempurna dengan `border-radius: 50%` dan `border: 4px solid white`.

**Constraint:**
- Tidak boleh menggunakan CSS framework.
- Tidak boleh menggunakan JavaScript.
- Kode harus dapat dibuka dan dilihat di browser tanpa error.
- Dilarang menggunakan `!important`.
- Kreativitas desain adalah bagian dari penilaian (10% bobot soal ini).

---

*— Selamat Mengerjakan —*

> *Ujian ini dirancang untuk mengukur pemahaman konseptual dan kemampuan implementasi nyata. Berpikirlah secara logis, gunakan referensi dengan bijak, dan kerjakan sendiri.*

---

## Lampiran: Rubrik Penilaian

| Kriteria | Bobot |
|---|---|
| Kode dapat dibuka di browser tanpa error | 25% |
| Output visual sesuai spesifikasi | 35% |
| Penggunaan teknik CSS yang diminta secara tepat | 25% |
| Keterbacaan kode, penamaan class, dan komentar | 10% |
| Kreativitas dan polish (khusus Soal 23 & 26) | 5% |

---

*Dokumen ujian ini dibuat untuk keperluan akademik mata kuliah CSS.*
*Dilarang menyebarluaskan tanpa izin dosen pengampu.*
