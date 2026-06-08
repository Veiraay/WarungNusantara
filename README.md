# 🍜 WarungNusantara

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-Active-success)

Warung Nusantara adalah platform e-commerce sederhana untuk UMKM lokal yang menjual kuliner tradisional Indonesia. Website ini menyediakan pengalaman berbelanja yang mudah dengan fitur keranjang belanja, konfirmasi pesanan, dan sistem pembayaran yang terintegrasi.

[🌐 Live Demo](#) • [📝 Dokumentasi](#dokumentasi) • [💬 Support](#dukungan)

---

## ✨ Fitur Utama

- 🛒 **Keranjang Belanja** - Tambah, edit, dan kelola item belanja dengan mudah
- 💳 **Proses Checkout** - Alur pembelian yang sederhana dan intuitif
- 🔄 **Konfirmasi Pesanan** - Review pesanan sebelum pembayaran
- 💰 **Integrasi Pembayaran** - Dukungan berbagai metode pembayaran
- 📱 **Responsive Design** - Optimal di desktop, tablet, dan mobile
- 🎨 **UI/UX Modern** - Desain elegan dengan warna-warna hangat tradisional
- ⚡ **Loading Cepat** - HTML/CSS/JS vanilla tanpa dependency berat
- 📦 **Mudah Dikustomisasi** - Komentar lengkap di setiap file

---

## 🏗️ Struktur Project

```
WarungNusantara/
├── index.html              # Halaman utama dengan hero section & produk
├── keranjang.html          # Halaman shopping cart
├── konfirmasi.html         # Halaman konfirmasi pesanan
├── pembayaran.html         # Halaman metode pembayaran
├── style.css               # Styling dengan CSS custom properties
├── asset/                  # Folder untuk gambar produk
│   ├── cireng.jpg
│   ├── es-dawet.jpg
│   ├── gado-gado.jpg
│   ├── gudeg.jpg
│   ├── klepon.jpg
│   └── ... (gambar produk lainnya)
└── README.md               # File dokumentasi ini
```

---

## 🔧 Tech Stack

- **HTML5** - Struktur semantic dan modern
- **CSS3** - Custom properties, Flexbox, Grid
- **JavaScript (Vanilla)** - No framework dependencies
- **Google Fonts** - Playfair Display & Lato

---

## 🚀 Quick Start

### Prasyarat
- Browser modern (Chrome, Firefox, Safari, Edge)
- Text editor (VS Code, Sublime, dll)
- Server lokal (opsional, untuk testing)

### Instalasi

1. **Clone repository**
   ```bash
   git clone https://github.com/yourusername/WarungNusantara.git
   cd WarungNusantara
   ```

2. **Buka di browser**
   - Langsung buka file `index.html` di browser, atau
   - Gunakan live server untuk development

3. **Setup Live Server (VS Code)**
   - Install extension "Live Server"
   - Klik kanan di `index.html` → "Open with Live Server"

---

## 📖 Dokumentasi

### Halaman-Halaman

| Halaman | Deskripsi |
|---------|-----------|
| **index.html** | Beranda dengan presentasi produk, fitur, dan call-to-action |
| **keranjang.html** | Menampilkan item yang ditambahkan, total harga, dan tombol checkout |
| **konfirmasi.html** | Review pesanan sebelum pembayaran |
| **pembayaran.html** | Pilihan metode pembayaran (Transfer Bank, E-wallet, COD) |

### Cara Menggunakan

#### 1️⃣ Menambah Produk Baru
Edit bagian produk di `index.html`:
```html
<div class="produk-kartu">
  <img src="asset/nama-produk.jpg" alt="Nama Produk">
  <h3>Nama Produk</h3>
  <p>Rp 25.000</p>
  <button onclick="tambahKeKeranjang('Nama Produk', 25000, 'asset/nama-produk.jpg')">
    Tambah ke Keranjang
  </button>
</div>
```

#### 2️⃣ Mengubah Warna Tema
Ubah CSS custom properties di bagian `:root` dalam `style.css`:
```css
:root {
  --warna-utama: #C0392B;      /* Warna tombol & aksen */
  --warna-sekunder: #922B21;   /* Warna hover */
  --warna-aksen: #F39C12;      /* Warna highlight */
  --warna-latar: #FFFDF7;      /* Warna background */
}
```

#### 3️⃣ Mengganti Font
Di `index.html`, ubah link Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=FONT_NAME&display=swap" rel="stylesheet">
```
Kemudian update di `style.css`:
```css
--font-judul: 'FONT_NAME', serif;
--font-isi: 'FONT_NAME', sans-serif;
```

#### 4️⃣ Mengubah Logo & Branding
Edit di navbar section di `index.html`:
```html
<a href="#" class="nav-logo">Warung<span>Nusantara</span></a>
```

---

## 🎨 Customization Guide

### Warna Tema yang Disarankan
- **Tradisional Merah**: `#C0392B` + `#F39C12` ✅ (Default)
- **Biru Modern**: `#2980B9` + `#3498DB`
- **Hijau Alami**: `#27AE60` + `#F39C12`
- **Orange Hangat**: `#E67E22` + `#E74C3C`

### Memodifikasi Responsivitas
Media queries sudah diatur di `style.css`. Sesuaikan breakpoint sesuai kebutuhan:
```css
@media (max-width: 768px) {
  /* Mobile styles */
}
```

---

## 📦 Fitur LocalStorage

Website ini menggunakan **LocalStorage** untuk menyimpan:
- 🛒 Item keranjang
- 💾 Data pesanan
- 👤 Informasi customer

Data tersimpan lokal dan tidak dikirim ke server sampai checkout selesai.

---

## 🔐 Keamanan

- ⚠️ **Development Stage**: Website ini masih tahap development
- 🔒 Input validation dilakukan pada form checkout
- 📝 Implementasi pembayaran asli perlu integrasi API provider (Midtrans, Xendit, dll)

---

## 🌐 Integrasi Payment Gateway

Untuk production, integrasikan dengan payment gateway:

### Opsi Provider:
1. **Midtrans** - Snap, CoreAPI
2. **Xendit** - Invoice, Virtual Account
3. **doku** - Payment Gateway Indonesia
4. **Wise** - International transfer

Contoh integrasi Midtrans di `pembayaran.html`:
```javascript
// Load Midtrans library
<script src="https://app.midtrans.com/snap/snap.js"></script>

// Trigger payment
snap.pay('SNAP_TOKEN', {
  onSuccess: function(result) {
    console.log('Payment successful', result);
  }
});
```

---

## 📱 Browser Support

| Browser | Support | Min Version |
|---------|---------|-------------|
| Chrome | ✅ | v90+ |
| Firefox | ✅ | v88+ |
| Safari | ✅ | v14+ |
| Edge | ✅ | v90+ |
| IE | ❌ | Not supported |

---

## 🚀 Roadmap

- [ ] Backend API integration (Node.js / Django)
- [ ] Database (MongoDB / PostgreSQL)
- [ ] Real payment gateway integration
- [ ] Admin dashboard untuk manage produk
- [ ] Customer login & order history
- [ ] Email notification
- [ ] Analytics dashboard
- [ ] Mobile app version

---

## 📸 Screenshot

### Homepage
![Homepage Screenshot Placeholder]

### Shopping Cart
![Cart Screenshot Placeholder]

### Checkout
![Checkout Screenshot Placeholder]

---

## 💡 Tips & Tricks

### Performance
- Optimize gambar: gunakan format WebP dengan fallback JPG
- Minify CSS/JS untuk production
- Lazy load images dengan `loading="lazy"`

### SEO
- Tambahkan meta description di setiap halaman
- Gunakan semantic HTML (`<article>`, `<section>`, `<nav>`)
- Struktur heading yang rapi (h1 → h2 → h3)

### Accessibility
- Alt text untuk semua gambar
- Sufficient color contrast
- Keyboard navigation support

---

## 🤝 Kontribusi

Kontribusi sangat diterima! Langkah-langkahnya:

1. Fork repository ini
2. Buat branch fitur (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buka Pull Request

---

## 📝 Lisensi

Project ini dilisensikan di bawah lisensi MIT - lihat file `LICENSE` untuk detail.

---

## 📧 Dukungan

Punya pertanyaan atau masalah? Hubungi kami:

- 📧 Email: support@warungnusantara.id
- 💬 WhatsApp: +62 xxx-xxxx-xxxx
- 🌐 Website: www.warungnusantara.id
- 📍 Instagram: [@warungnusantara](https://instagram.com)

---

## 🙏 Acknowledgment

Terima kasih kepada:
- komunitas open-source
- contributors yang telah membantu project ini
- UMKM lokal yang terinspirasi untuk go-digital

---

**Dibuat dengan ❤️ untuk UMKM Indonesia**

*Last Updated: 2024* | *Maintained by: [Your Team]*
