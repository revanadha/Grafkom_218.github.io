# Lembar Kerja Grafika Komputer

Final Project mata kuliah **Grafika Komputer** — Semester Genap 2025/2026.
Aplikasi web statis (HTML/CSS/JavaScript murni, tanpa library eksternal) yang mengimplementasikan tiga materi:

| Kode | Materi | Algoritma / Konsep |
|------|--------|---------------------|
| A | **Linear** | DDA Line, Bresenham Line, Midpoint Circle |
| B | **Transformasi 2D** | Translasi, Scaling, Rotasi, Refleksi (X/Y), Shearing (X/Y) |
| C | **Color Space** | Konversi RGB → CMYK, RGB → HSV, dan HEX |

Tersedia dalam dua tampilan dengan **logika perhitungan yang identik**:

- `index.html` — tampilan bergaya "meja gambar teknik / blueprint" dengan navigasi tab per lembar (versi utama/default).
- `dashboard.html` — tampilan dashboard gelap dengan kartu bertumpuk (versi awal/alternatif).



---

## Demo

Buka file HTML langsung di browser (Chrome/Edge/Firefox), tidak memerlukan server atau instalasi apa pun.

## Fitur

### A. Linear
- Input titik awal/akhir garis (x1, y1, x2, y2) dan pilihan algoritma (DDA / Bresenham).
- Input pusat dan radius lingkaran (Midpoint Circle Algorithm).
- Visualisasi piksel hasil pada bidang kartesius (canvas + grid).
- Output berupa daftar koordinat piksel yang dihasilkan.

### B. Transformasi 2D
- Input tiga titik segitiga bebas (format `x,y`).
- Pilihan transformasi: Translasi, Scaling, Rotasi, Reflection X, Reflection Y, Shearing X, Shearing Y.
- Menampilkan rumus matematis yang digunakan beserta hasil perhitungan tiap titik.
- Visualisasi objek awal (garis putus-putus) vs objek hasil (garis penuh) pada canvas yang sama.

### C. Color Space
- Input nilai RGB (0–255) atau generate warna acak.
- Konversi otomatis ke CMYK, HSV, dan HEX beserta rumus yang dipakai.
- Preview warna langsung dan tabel ringkasan hasil konversi.

## Struktur Proyek

```
.
├── index.html      # Versi UI blueprint / lembar gambar teknik (default)
├── dashboard.html  # Versi UI dashboard gelap (alternatif)
└── README.md
```

## Teknologi

- HTML5 + CSS3 murni (tanpa framework CSS)
- JavaScript vanilla (tanpa library/dependency eksternal)
- Canvas API untuk visualisasi grafis
- Google Fonts (IBM Plex Mono & IBM Plex Sans) — hanya pada versi blueprint, dimuat via CDN

Karena tidak ada proses build, kedua file dapat langsung dibuka sebagai file statis di browser maupun di-hosting di layanan static hosting mana pun.

## Menjalankan Secara Lokal

1. Clone atau unduh repository ini.
2. Buka `index.html` (atau `dashboard.html`) langsung dengan browser, **atau**
3. Jalankan local server sederhana (opsional, untuk menghindari batasan `file://` di beberapa browser):

   ```bash
   # Python 3
   python -m http.server 8000

   # kemudian buka di browser:
   # http://localhost:8000/index.html
   ```

## Deploy ke GitHub Pages

1. Buat repository baru di GitHub, lalu push seluruh isi folder ini (termasuk `index.html`, `dashboard.html`, dan `README.md`).
2. File **`index.html`** sudah berada di root repository, sehingga otomatis menjadi halaman utama yang tampil saat GitHub Pages diaktifkan.
   - Jika ingin versi dashboard gelap yang tampil sebagai halaman utama, cukup tukar isi/nama kedua file (rename `dashboard.html` menjadi `index.html` dan sebaliknya).
3. Masuk ke **Settings → Pages** pada repository.
4. Pada bagian **Build and deployment**, pilih:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (atau branch utama kamu), folder `/ (root)`
5. Klik **Save**. Setelah beberapa saat, GitHub akan memberikan URL publik dengan format:

   ```
   https://<username-github>.github.io/<nama-repo>/
   ```

6. Untuk mengakses versi dashboard gelap (bukan halaman utama), tinggal tambahkan nama filenya di URL:

   ```
   https://<username-github>.github.io/<nama-repo>/dashboard.html
   ```

## Catatan Implementasi

- Semua perhitungan (algoritma garis, lingkaran, transformasi matriks 2D, dan konversi ruang warna) berjalan sepenuhnya di sisi klien (browser), tidak ada request ke server backend.
- Kedua versi UI menggunakan fungsi perhitungan yang **sama persis**, sehingga hasil angka pada kedua tampilan akan selalu identik untuk input yang sama — perbedaannya murni pada tampilan (UI/UX).
- Grid pada canvas merepresentasikan 1 kotak = 20 piksel, dengan titik asal (0,0) berada di tengah bidang gambar.

## Lisensi

Proyek ini dibuat untuk keperluan tugas akademik (Final Project Grafika Komputer). Silakan gunakan atau modifikasi sesuai kebutuhan pembelajaran.
