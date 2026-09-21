# ✨ SVG Purifier

SVG Purifier adalah sebuah aplikasi web ringan berbasis browser (single-file) yang berfungsi untuk membersihkan file SVG (Scalable Vector Graphics) dari metadata yang tidak perlu, atribut proteksi, dan kode sisa (*bloat*) bawaan editor desain. Aplikasi ini memastikan file SVG Anda bersih, berukuran lebih kecil, dan hanya berisi elemen bentuk (shapes) murni.

Aplikasi ini berjalan sepenuhnya di sisi klien (browser) tanpa memerlukan server, sehingga menjamin privasi dan keamanan file Anda.

## 🚀 Fitur Utama

- **Drag & Drop Interface:** Antarmuka pengguna yang ramah, memungkinkan Anda untuk cukup menarik dan melepas (drag & drop) file SVG ke area yang disediakan, atau klik untuk menelusuri file.
- **Deteksi Otomatis:** Secara otomatis mendeteksi dan menampilkan Versi SVG dan *Character Encoding* (misalnya UTF-8, UTF-16).
- **Pembersihan Ekstensif (Purify):**
  - **Menghapus Editor Bloat:** Menghapus *namespace* dan *prefix* dari aplikasi desain populer seperti Inkscape, Adobe Illustrator, Figma, Sketch, CorelDraw, dll.
  - **Menghapus Elemen Sampah:** Membuang elemen seperti `<metadata>`, grid editor, *guide*, deskripsi, dan *title* otomatis.
  - **Menghapus Atribut Proteksi:** Menghapus atribut seperti `locked`, `protected`, `pointer-events: none`, dan tag lain yang mengunci elemen.
  - **Optimasi Struktur:** Menyederhanakan *wrapper groups* (mengangkat anak `<g>` ke induknya jika tidak perlu) dan menghapus *container* kosong (`<defs>`, `<g>`).
- **Analisis & Statistik:** Menampilkan ukuran file asli, ukuran setelah dibersihkan, total byte yang dihapus, dan persentase pengurangan ukuran file.
- **Perbandingan Kode (Before & After):**
  - Tampilan perbandingan kode secara *inline* (*collapsible panel*) dengan menyoroti baris mana saja yang dihapus (warna merah) dan ditambahkan (warna hijau).
  - Tab terpisah untuk melihat kode Asli (Original) dan kode yang sudah dibersihkan (Purified).
- **Pratinjau (Preview) SVG:** Melihat langsung hasil visual dari SVG yang telah dibersihkan untuk memastikan tidak ada bentuk desain yang rusak.
- **Salin Kode (Copy Code):** Tombol sekali klik untuk menyalin kode SVG langsung ke *clipboard*.
- **Ekspor/Unduh:** Tombol dedikasi untuk mengunduh langsung file SVG yang sudah bersih dengan nama file berakhiran `_purified.svg`.

## 🛠️ Teknologi yang Digunakan

Proyek ini dibangun sebagai aplikasi **Single-File** (semua dalam `index.html`) dengan menggunakan:
- **HTML5:** Struktur semantik.
- **CSS3:** Styling modern menggunakan *CSS Custom Properties (Variables)*, *Flexbox*, dan *CSS Animations* tanpa library eksternal.
- **Vanilla JavaScript:** Logika aplikasi sepenuhnya menggunakan JS murni (ES6+), memanfaatkan `DOMParser`, `XMLSerializer`, dan `FileReader` API.

## 📖 Cara Penggunaan

1. **Buka Aplikasi:**
   Karena proyek ini adalah file HTML statis tunggal, Anda cukup membuka file `index.html` langsung menggunakan browser web modern apa saja (Chrome, Firefox, Edge, Safari).
2. **Pilih File SVG:**
   Tarik dan lepas file `.svg` Anda ke kotak bergaris putus-putus, atau klik kotak tersebut untuk memilih file dari komputer Anda.
3. **Mulai Proses Purify:**
   Setelah file berhasil dimuat dan info file muncul, klik tombol **"Purify"**.
4. **Lihat Hasil:**
   Lihat statistik pengurangan ukuran file. Anda bisa memeriksa tab **"Before & After"** untuk melihat perubahan kode, atau tab **"Preview"** untuk memastikan gambar tetap aman.
5. **Simpan/Ekspor:**
   Klik tombol **"Export Purified SVG"** untuk mengunduh hasil akhirnya, atau gunakan fitur salin pada tab kode jika ingin menempelkannya langsung ke proyek pengembangan Anda.

## 🤝 Kontribusi

Aplikasi ini dapat dimodifikasi dengan mudah karena semuanya berada dalam satu file `index.html`. Jika Anda ingin menambahkan aturan *parsing* baru untuk menghapus tag tertentu, Anda bisa mencari dan mengubah variabel `junkNS`, `junkPrefixes`, `removeElements`, atau `removeAttrs` di dalam kode JavaScript.