# Lembar Kerja Grafika Komputer

Final Project mata kuliah **Grafika Komputer** — Semester Genap 2025/2026.
Aplikasi web statis (HTML/CSS/JavaScript murni, tanpa library eksternal) yang mengimplementasikan tiga materi:

| Kode | Materi | Algoritma / Konsep |
|------|--------|---------------------|
| A | **Linear** | DDA Line, Bresenham Line, Midpoint Circle |
| B | **Transformasi 2D** | Translasi, Scaling, Rotasi, Refleksi (X/Y), Shearing (X/Y) |
| C | **Color Space** | Konversi RGB → CMYK, RGB → HSV, dan HEX |

Tersedia dalam dua tampilan dengan **logika perhitungan yang identik**:

- `index.html` — tampilan minimalis satu kolom bergaya "langkah 1-2-3", tombol pilihan besar (bukan dropdown), slider untuk warna, dan hanya satu warna aksen lembut. Dirancang supaya mudah diikuti tanpa perlu membaca dua kolom sekaligus (versi utama/default).

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
├── index.html      # Versi UI minimalis, alur langkah 1-2-3 (default)
└── README.md
```

## Teknologi

- HTML5 + CSS3 murni (tanpa framework CSS)
- JavaScript vanilla (tanpa library/dependency eksternal)
- Canvas API untuk visualisasi grafis
- Google Fonts (Inter) — dimuat via CDN

Karena tidak ada proses build, kedua file dapat langsung dibuka sebagai file statis di browser maupun di-hosting di layanan static hosting mana pun.

## Menjalankan Secara Lokal

1. Clone atau unduh repository ini.
2. Buka `index.html` 
3. Jalankan local server sederhana (opsional, untuk menghindari batasan `file://` di beberapa browser):

## Menjalankan Secara Langsung
1. klik (https://revanadha.github.io/Grafkom_218.github.io/)

## Catatan Implementasi

- Semua perhitungan (algoritma garis, lingkaran, transformasi matriks 2D, dan konversi ruang warna) berjalan sepenuhnya di sisi klien (browser), tidak ada request ke server backend.
- Kedua versi UI menggunakan fungsi perhitungan yang **sama persis**, sehingga hasil angka pada kedua tampilan akan selalu identik untuk input yang sama — perbedaannya murni pada tampilan (UI/UX).
- Grid pada canvas merepresentasikan 1 kotak = 20 piksel, dengan titik asal (0,0) berada di tengah bidang gambar.

## Lisensi

Proyek ini dibuat untuk keperluan tugas akademik (Final Project Grafika Komputer).
