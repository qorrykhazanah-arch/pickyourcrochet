# Pick Your Crochet 🧶

Website e-commerce untuk toko rajutan (crochet) handmade, dibangun sepenuhnya dengan HTML, CSS, dan JavaScript murni (tanpa framework, tanpa backend/server).

## 🎓 Latar Belakang

Project ini dibuat untuk memenuhi Ujian Akhir Semester (UAS) mata kuliah **KAIT**.

## 👤 Identitas

| | |
|---|---|
| **Nama** | Qorry Khazanah |
| **NIM** | 209250223 |
| **Kelas** | Administrasi Bisnis 3 |
| **Dosen Pengampu** | Yoki Oktorian Sukardi, S.Kom., M.A.B. |

---

# BAGIAN 1 — DOKUMENTASI BISNIS

## 1.1 Ringkasan Eksekutif

**Pick Your Crochet** adalah platform toko online yang menjual produk rajutan (crochet) handmade dengan konsep *"made with love"* — setiap produk dibuat dan dikemas dengan penuh perhatian. Website ini mensimulasikan pengalaman belanja online end-to-end: mulai dari melihat katalog, menambah ke keranjang, checkout, memilih metode pembayaran, hingga pengelolaan pesanan dari sisi pemilik toko (admin).

## 1.2 Profil Bisnis

| | |
|---|---|
| **Nama Brand** | Pick Your Crochet |
| **Jenis Usaha** | UMKM / toko online produk kerajinan tangan (handicraft) |
| **Kategori Produk** | Amigurumi, Aksesoris, Pakaian rajut, Dekorasi rumah |
| **Target Pasar** | Remaja–dewasa muda (khususnya perempuan) yang menyukai produk handmade, estetik, dan personal; juga pembeli yang mencari hadiah unik |
| **Value Proposition** | 100% handmade, material berkualitas & ramah lingkungan, dikemas cantik, cocok dijadikan hadiah |

## 1.3 Kategori & Contoh Produk

| Kategori | Contoh Produk |
|---|---|
| 🧸 Amigurumi | Beruang Amigurumi, Kucing Amigurumi |
| 🎀 Aksesoris | Gantungan Kunci Rajut, Dompet Rajut, Tas Tote Rajut |
| 👗 Pakaian (Wearable) | Cardigan Rajut, Tas Granny Square |
| 🏠 Dekorasi Rumah | Selimut Bayi Rajut, Bantal Hias Rajut, Set Coaster Rajut |

## 1.4 Alur Bisnis (Customer Journey)

```
Pelanggan browsing katalog
        ↓
Filter/cari produk (kategori, harga, rating)
        ↓
Lihat detail produk → Tambah ke keranjang
        ↓
Buka keranjang → Checkout
        ↓
Isi data pengiriman (nama, alamat, kontak)
        ↓
Pilih metode pengiriman (Reguler / Express / Same Day)
        ↓
Pilih metode pembayaran (QRIS / Transfer Bank / COD)
        ↓
Konfirmasi pesanan → Notifikasi "Pembayaran Berhasil"
        ↓
[Sisi Admin] Pesanan masuk ke panel Admin
        ↓
Admin memproses: ubah status pesanan
  (Menunggu Pembayaran → Diproses → Dikirim → Selesai)
```

## 1.5 Metode Pengiriman

| Metode | Estimasi | Biaya |
|---|---|---|
| Regular | 3–5 hari | Rp 15.000 |
| Express | 1–2 hari | Rp 25.000 |
| Same Day | Hari yang sama | Rp 40.000 |

## 1.6 Metode Pembayaran

| Metode | Keterangan |
|---|---|
| **QRIS** | Scan QR, mendukung GoPay/OVO/DANA/ShopeePay, dll |
| **Transfer Bank** | Virtual Account — pilihan BCA, Mandiri, BNI, atau BRI |
| **COD** | Bayar tunai ke kurir saat barang diterima |

> Catatan: pembayaran di project ini bersifat **simulasi** untuk keperluan demo/akademik — belum terhubung ke payment gateway sungguhan (mis. Midtrans/Xendit).

## 1.7 Kanal Pemasaran & Kontak

- 📧 Email: pickyourcrochet@gmail.com
- 📱 WhatsApp: +62 895-2492-7373
- 📸 Instagram: [@pick.yourcrochet](https://instagram.com/pick.yourcrochet)
- 🎵 TikTok: [@pick.yourcrochet](https://tiktok.com/@pick.yourcrochet)

## 1.8 Model Operasional (Admin)

Pemilik toko mengelola bisnis lewat **Panel Admin** di website tanpa perlu tools tambahan:
- Menambah, mengedit, menghapus produk (termasuk upload foto asli produk)
- Memantau stok setiap produk (otomatis berkurang saat ada pesanan masuk)
- Melihat detail tiap pesanan yang masuk (barang, alamat, kontak pembeli)
- Mengubah status pesanan sesuai progres pengerjaan/pengiriman
- Melihat ringkasan statistik (jumlah produk, total stok, nilai stok, jumlah pesanan, total pendapatan)

---

# BAGIAN 2 — DOKUMENTASI TEKNIS

## 2.1 Tech Stack

| Komponen | Teknologi |
|---|---|
| Struktur | HTML5 |
| Styling | CSS3 murni (custom properties/variables, flexbox, grid, animation) — tanpa framework CSS |
| Logika | JavaScript (vanilla, ES5-style) — tanpa library/framework eksternal |
| Ikon | [Font Awesome 6](https://fontawesome.com/) (CDN) |
| Font | [Google Fonts](https://fonts.google.com/) — Quicksand & Pacifico (CDN) |
| Penyimpanan Data | Browser `localStorage` (tidak ada backend/database server) |

## 2.2 Struktur File

```
├── index.html      # Struktur/markup seluruh halaman (SPA — single page, multi-section)
├── style.css        # Seluruh styling & animasi
├── script.js         # Seluruh logika aplikasi (state, render, event handling)
└── README.md        # Dokumentasi project
```

Ketiga file inti (`index.html`, `style.css`, `script.js`) saling terhubung lewat `<link>` dan `<script src>` dengan path relatif, sehingga **wajib berada dalam satu folder yang sama**.

## 2.3 Arsitektur Aplikasi

Website ini adalah **client-side only single page application (SPA)** — semua "halaman" (Katalog, Checkout, Admin, dsb.) sebenarnya adalah section/overlay dalam satu `index.html` yang ditampilkan/disembunyikan lewat JavaScript (`display:block/none`), bukan navigasi antar file HTML terpisah. Tidak ada request ke server backend; seluruh data disimpan dan dibaca dari `localStorage` browser pengguna.

**Karena tidak ada backend/database**, project ini cocok untuk keperluan demo/simulasi/akademik, namun punya keterbatasan yang perlu dipahami (lihat bagian 2.9).

## 2.4 Model Data

### Produk (Product)
```js
{
  id: 1,
  nm: { id: 'Beruang Amigurumi', en: 'Amigurumi Bear' },  // nama, bilingual
  cat: 'amigurumi',                                        // amigurumi | accessories | wearable | home-decor
  pr: 85000,                                                // harga (Rupiah)
  ds: { id: '...', en: '...' },                             // deskripsi, bilingual
  rt: 4.9,                                                  // rating (0–5)
  st: 12,                                                   // stok
  customImg: 'data:image/jpeg;base64,...'                   // opsional, foto upload admin
}
```
Jika `customImg` tidak ada, gambar produk digenerate otomatis sebagai SVG placeholder (`mkSVG()`) berdasarkan kategori & nama produk.

### Keranjang (Cart Item)
```js
{ id: 1, qty: 2 }   // referensi ke id produk + jumlah
```

### Pesanan (Order)
```js
{
  id: 'PYC12345678',
  name, email, phone, address, city, zip,   // data pengiriman
  items: [{ id: 1, qty: 2 }, ...],
  subtotal, shipping, total,
  payMethod: 'qris' | 'bank' | 'cod',
  bankLabel: 'Bank BCA',                    // hanya jika payMethod === 'bank'
  status: 'pending' | 'processing' | 'shipped' | 'completed' | 'cancelled',
  date: '2026-07-14T...'                    // ISO timestamp
}
```

## 2.5 Modul / Fitur Utama

| Modul | Fungsi Kunci | Deskripsi |
|---|---|---|
| **Katalog Produk** | `renderProducts()`, `filterCat()` | Render grid produk, filter kategori/harga, pencarian, sortir |
| **Keranjang** | `addCart()`, `updCartQty()`, `rmCart()`, `renderCart()` | Kelola isi keranjang, hitung total, sidebar keranjang |
| **Checkout** | `goCheck()`, `validateForm()`, `doPay()` | Form data pengiriman + validasi, ringkasan pesanan, proses pembayaran |
| **Simulasi Pembayaran** | `mkQRIS()`, `generateVA()`, `BANK_INFO` | Generate tampilan QRIS (SVG) & nomor Virtual Account per bank secara dinamis |
| **Panel Admin** | `renderAdm()`, `savePF()`, `openOrd()`, `updOrdStatus()` | CRUD produk (+ upload foto), lihat detail pesanan, ubah status pesanan |
| **Multi-bahasa (i18n)** | `applyLang()`, objek `L` | Toggle ID/EN, semua teks statis diambil dari kamus terjemahan |
| **Autentikasi Admin** | `doLog()`, `doLogout()` | Login sederhana (client-side, bukan sistem auth sungguhan) |

## 2.6 Strategi Persistensi Data (localStorage)

| Key | Isi |
|---|---|
| `pyc_products` | Daftar produk (termasuk hasil edit/tambah admin) |
| `pyc_products_ver` | Nomor versi skema data produk (lihat 2.7) |
| `pyc_orders` | Daftar seluruh pesanan yang masuk |
| `pyc_profile` | Data pengiriman terakhir (auto-fill saat checkout berikutnya) |

Foto produk yang diupload admin **dikompres otomatis** (resize maks. ±700px, kualitas JPEG ~75%) sebelum disimpan sebagai base64 di `localStorage`, untuk menghindari cepat penuhnya kuota penyimpanan (`saveProducts()` dibungkus `try/catch` untuk menangani error kuota).

## 2.7 Sistem Versi Data Produk

Karena daftar produk default (`defaultP`) bisa berubah seiring pengembangan, ada mekanisme sederhana berbasis `PRODUCTS_VERSION`: jika versi data yang tersimpan di browser tidak cocok dengan versi terbaru di kode, data lama otomatis di-reset dan diganti dengan data default terbaru (`loadProducts()`). Ini mencegah pengguna "terjebak" melihat data lama setelah ada pembaruan produk di kode.

## 2.8 Alur Render Utama

```
DOMContentLoaded
   → loadProducts()   // baca localStorage / fallback ke defaultP
   → loadOrders()      // baca localStorage
   → renderProducts()  // tampilkan grid produk awal
   → renderCart()       // tampilkan status keranjang (kosong/isi)
   → pasang seluruh event listener (search, filter, sort, navbar, dll)
```
Setiap perubahan state (tambah ke keranjang, ubah filter, edit produk, dll) memicu fungsi `render*()` terkait untuk re-render bagian DOM yang relevan — pendekatan render manual tanpa Virtual DOM/reactive framework.

## 2.9 Keterbatasan (Known Limitations)

- **Tidak ada backend/database sungguhan** — semua data tersimpan lokal di browser (`localStorage`), tidak sinkron antar device/browser, dan akan hilang jika cache dibersihkan.
- **Autentikasi admin tidak aman** — kredensial (`admin` / `admin123`) tertulis langsung di kode client-side, tidak cocok untuk produksi sungguhan.
- **Pembayaran hanya simulasi tampilan** — QRIS & Virtual Account digenerate secara visual, tidak terhubung ke payment gateway/bank sungguhan.
- **Kapasitas foto produk terbatas** oleh kuota `localStorage` (umumnya ±5–10MB per origin browser).

## 2.10 Cara Menjalankan

1. Pastikan `index.html`, `style.css`, dan `script.js` berada dalam satu folder.
2. Buka folder tersebut di **VS Code**.
3. Install extension **Live Server** (by Ritwick Dey).
4. Klik kanan `index.html` → **Open with Live Server**.
5. Website akan terbuka di browser lewat `http://127.0.0.1:5500/...`.

> Disarankan menggunakan Live Server (bukan membuka file HTML langsung lewat `file://`) agar CSS dan JS ter-load dengan benar.

## 2.11 Login Admin

- **Username:** `admin`
- **Password:** `admin123`

## 2.12 Potensi Pengembangan Lanjutan

- Integrasi backend & database sungguhan (mis. Node.js + MongoDB/MySQL) agar data tersimpan di server dan bisa diakses dari device manapun
- Integrasi payment gateway sungguhan (Midtrans/Xendit) untuk pembayaran real
- Sistem autentikasi admin yang aman (hashing password, session/token di server)
- Fitur ulasan & rating dari pembeli sungguhan
- Notifikasi email/WhatsApp otomatis saat status pesanan berubah

  ---
  Dibuat untuk keperluan Tugas Besar KAIT. Semua transaksi pembayaran pada prototype ini bersifat simulasi.
