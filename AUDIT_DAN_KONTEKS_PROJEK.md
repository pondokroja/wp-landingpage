# Laporan Eksplorasi & Konteks Brand: Pondok Roja

> **Dibuat:** 2026-07-23 | **Sumber Data:** MySQL Live DB (`roja_landingpage`) + `wp-content/` + `.env`
> **Metode:** Direct SQL query via `mysql` binary — data 100% akurat dari database.
> **Status:** Read-Only Audit - Tidak ada perubahan yang dilakukan pada data.

---

## 1. Ringkasan Konteks Bisnis & Profil Brand

| Atribut | Nilai |
|---|---|
| **Nama Brand** | Pondok Roja |
| **Nama Resmi Lengkap** | Pondok Pesantren Rooihatul Jannah Hidayatullah Sukoharjo |
| **Akronim/Nama Program** | TMQ Rooihatul Jannah (Tarbiyatul Muhafidzotil Qur'an) |
| **Tagline** | "Siapapun berhak menjadi apapun dalam bingkai Al-Qur'an" |
| **Website Live** | https://rojaa.my.id |
| **Domain Utama** | https://pondokroja.com |
| **Email** | pondok.roja@gmail.com |
| **Telepon / WhatsApp** | 0813 9210 4443 |
| **Narahubung** | Ust. Sigit: 0857 1246 5118 - Ust. Amalina: 0858 6569 3081 |
| **Lokasi** | Brumbung 03/02, Dukuh, Kec. Sukoharjo, Kabupaten Sukoharjo, Jawa Tengah 57524 |
| **Naungan** | Yayasan Hidayatullah Sukoharjo (bagian dari Ormas Hidayatullah, berpusat di Jakarta) |
| **Berdiri** | Juli 2010 |
| **Active Theme** | Divi 4.24.2 (Elegant Themes) |
| **WordPress DB Version** | 61833 (WP ~6.x) |

### Deskripsi / Fokus Utama

Pondok Roja adalah **lembaga pendidikan Islam setingkat SMP-SMA** yang berbasis pesantren modern dengan sistem pendidikan berjenjang **6 tahun + 1 tahun pengabdian**. Program utamanya adalah **Tahfidzul Qur'an** - mencetak hafidz/hafidzah Al-Qur'an mutqin minimal 20 juz. Berada di bawah naungan Yayasan Hidayatullah dengan kampus induk di Gunung Tembak, Balikpapan, Kalimantan Timur. Berdiri Juli 2010 di Sukoharjo, Jawa Tengah.

### Target Audiens

| Segmen | Detail |
|---|---|
| **Primer** | Orang tua/wali murid yang mencari pesantren putri (SMP-SMA) berbasis tahfidz |
| **Sekunder** | Calon santri perempuan usia kelas 5-6 SD / naik kelas 1 SMP |
| **Tersier** | Donatur/wakaf, alumni, komunitas Muslim pendukung pendidikan Islam |

### Value Proposition Utama

1. **Tahfidz sebagai Program Unggulan** - Target mutqin minimal 20 juz selama 6 tahun
2. **Bilingual (Arab-Inggris)** - Program percakapan intensif bahasa Arab dan Inggris
3. **Kurikulum Integral** - Perpaduan pendidikan Tauhid + Kurikulum Nasional (setara SMP-SMA)
4. **Kelas Multinasional** - Santri dari berbagai daerah di Indonesia hingga mancanegara
5. **Pengembangan Minat Bakat** - 15+ kegiatan ekstrakurikuler (Memanah, Tapak Suci, Berkuda, dll.)
6. **Biaya Terjangkau** - Syahriyah Rp 500.000/bulan (makan, asrama & SPP)

### Key Call to Actions (CTA) Utama

| CTA | URL Target | Konteks |
|---|---|---|
| **Daftar Sekarang** | https://psb.pondokroja.com | Button #FF147B di halaman Pendaftaran |
| **Selengkapnya** | /profil | Button di section hero beranda |
| **Donasi/Wakaf** | http://bit.ly/wakaf-roja | Banner GIF animasi di beranda |
| **Hubungi Kami** | /kontak | Navigasi & sidebar footer |

### Visi & Misi

**Visi:** "Lembaga pendidikan Islam pencetak kader pemimpin umat yang berakhlak mulia, berwawasan luas, dan mampu mengembangkan diri untuk tegaknya peradaban Islam."

**Misi:**
1. Membentuk generasi muslim yang unggul, berdikari, berpengetahuan luas siap menjadi da'i dan ulama yang intelek.
2. Membentuk karakter/pribadi muslim yang bertauhid, beriman dan menjalankan syariah Allah.
3. Menjadikan kampus Rooihatul Jannah sebagai lembaga berkualitas yang representatif, eksekutif & kreatif serta menjadi rujukan umat.

---

## 2. Peta Konten & SEO Footprint

### Statistik Konten (Data dari Database Langsung)

| Metrik | Jumlah |
|---|---|
| **Total Halaman (Pages) Published** | 17 |
| **Total Post Published** | 27 |
| **Total Media Attachments** | 133 file |
| **Total Users** | 3 |
| **Plugin SEO** | TIDAK ADA (Yoast/RankMath tidak terinstall - Divi built-in SEO) |
| **Permalink Structure** | `/%postname%/` |
| **Front Page** | ID 8 - Beranda |

> **Catatan SEO:** `divi_seo_home_title` dan `divi_seo_home_description` bernilai `false` di database - meta SEO custom belum dioptimasi. Migrasi ke Next.js adalah kesempatan untuk memperkuat SEO dari nol.

### Tabel Mapping Halaman (Pages) - Status: Publish (17 Halaman)

| ID | Title | Slug / URL | Catatan |
|---|---|---|---|
| 8 | **Beranda** | `/beranda/` → `/` | FRONT PAGE (homepage) |
| 10 | **Program** | `/program/` | Sistem Formal, Nonformal, Ekskul |
| 12 | **Profil** | `/profil/` | Sejarah, Visi-Misi, Struktur Organisasi |
| 14 | **Galeri** | `/galeri/` | Koleksi foto kegiatan |
| 16 | **Kegiatan** | `/kegiatan/` | Jadwal & deskripsi kegiatan |
| 18 | **Testimoni** | `/testimoni/` | Ulasan orang tua/santri |
| 20 | **Pendaftaran** | `/pendaftaran/` | Info PSB, syarat, biaya |
| 22 | **Rubik** | `/rubik/` | Halaman blog/rubrik tambahan |
| 24 | **Kontak** | `/kontak/` | Formulir & info kontak |
| 145 | **Donasi** | `/donasi/` | Info wakaf produktif |
| 488 | **Visi & Misi** | `/visi-misi/` | Halaman dedikasi Visi-Misi |
| 961 | **Amal Usaha** | `/amal-usaha/` | Program usaha pesantren |
| 964 | **Foto** | `/foto/` | Galeri foto (duplikat /galeri) |
| 966 | **Vidio** | `/vidio/` | Galeri video |
| 979 | **Informasi** | `/informasi/` | Halaman info umum |
| 1222 | **[ RAPAT KERJA TAHUNAN ]** | `/rapat-kerja-tahunan/` | Event internal (duplikat post) |
| 1451 | **UPACARA HARI SANTRI NASIONAL** | `/upacara-hari-santri-nasional/` | Event nasional (duplikat post) |

### Struktur Navigasi Utama (Primary Menu - 16 Item)

Data dari `wp_terms` → `nav_menu` → Primary Menu:

```
Menu Utama (Primary Menu - 16 item):
├── [1]  Beranda         → /beranda/          (page:8)
├── [2]  Profil          → /profil/           (page:12)
│    └── [3] Program     → /program/          (page:10)   [child of Profil?]
│    └── [4] Amal Usaha  → /amal-usaha/       (page:961)
│    └── [5] Testimoni   → /testimoni/        (page:18)
├── [6]  Galeri          → /galeri/           (page:14)
│    └── [7] Foto        → /galeri/           (custom URL, page:964-ref)
│    └── [8] Vidio       → /vidio/            (page:966)
├── [9]  Informasi       → /informasi/        (page:20 alias?)
│    └── [10] Pendaftaran → /pendaftaran/     (page:20)
│    └── [11] Kegiatan   → /kegiatan/         (page:16)
├── [12] Rubrik          → /rubik/            (page:22)
│    └── [13] Kabar Berita → /category/kabar-berita/ (taxonomy)
│    └── [14] Artikel    → /category/artikel/ (taxonomy)
├── [15] Kontak          → /kontak/           (page:24)
└── [16] Donasi          → /donasi/           (page:145)
```

### Tabel Mapping Post (Blog/Artikel) - 27 Post Published

| ID | Judul | Slug | Kategori | Tanggal |
|---|---|---|---|---|
| 123 | Islam Butuh Konsep Persatuan Umat | islam-butuh-konsep-persatuan-umat | Artikel | 2019-07-06 |
| 126 | Dapatkah Ekonomi Politik Islam Mengatasi Masalah Kemiskinan di Indonesia? | dapatkah-ekonomi-politik-islam-... | Artikel | 2019-07-06 |
| 132 | Mengkritik dan Menasihati Pemimpin Menurut Syariat Islam | mengkritik-dan-menasihati-... | Artikel | 2019-07-06 |
| 135 | Ulasan Buku "Hermeneutika Feminisme Reformasi Gender dalam Islam" | ulasan-buku-hermeneutika-... | Artikel | 2019-07-06 |
| 913 | Menangislah Sebelum Menangis Itu Di Larang | menangislah-sebelum-... | Kabar Berita | 2019-07-12 |
| 916 | Pondok Roja, Pondok Harapan | pondok-roja-pondok-harapan | Kabar Berita | 2019-07-12 |
| 918 | "Minimal Murah, Maksimal gratis" | minimal-murah-maksimal-gratis | Kabar Berita | 2019-07-12 |
| 920 | Goresan Hati Seorang Ibu Untuk Anaknya Yang Sedang Belajar Di Pondok Roja | goresan-hati-... | Kabar Berita | 2019-07-12 |
| 1089 | Santri Datang Mari Berjuang | santri-datang-mari-berjuang | Artikel | 2020-07-14 |
| 1097 | Roja Peduli Korban Banjir Bandang Masamba | roja-peduli-... | Artikel | 2020-07-22 |
| 1190 | BEGINI CARA SANTRI TMQ ROIIHATUL JANNAH SAMBUT MAULID NABI | begini-cara-... | Artikel, Kabar Berita | 2021-10-29 |
| 1231 | RAPAT KERJA TAHUNAN | rapat-kerja-tahunan | Kabar Berita, Info | 2022-07-02 |
| 1352 | HAFLAH TAKHORRUJ | haflah-takhorruj | Info | 2025-07-12 |
| 1358 | MASTA'RI (Masa Ta'aruf Santri) | mastari-masa-taaruf-santri | Artikel, Kabar Berita, Info | 2025-08-03 |
| 1371 | ROJA FRAME (HALAQOH SANTRI) | roja-frame-halaqoh-santri | Artikel, Kabar Berita, Info | 2025-08-03 |
| 1378 | INFORMASI PSB REGULER TAHUN AJARAN 2026/2027 | informasi-psb-reguler-... | Artikel, Kabar Berita, Info | 2025-08-06 |
| 1382 | WAKAF PEMBANGUNAN ASRAMA DAN RUMAH DINAS ASATIDZ PONDOK TAHFIDZUL QUR'AN | wakaf-pembangunan-... | Artikel, Kabar Berita, Info | 2025-08-06 |
| 1413 | ROJA FRAME (MUHADHOROH) | roja-frame-muhadhoroh | Artikel, Kabar Berita, Info | 2025-08-31 |
| 1416 | SERUAN DOA BERSAMA! | seruan-doa-bersama | Artikel, Info | 2025-08-31 |
| 1439 | PANEN RAYA KETAHANAN PANGAN | panen-raya-ketahanan-pangan | Artikel, Info | 2025-09-23 |
| 1442 | SAFARI TASMI' 2 | safari-tasmi-2 | Artikel, Kabar Berita, Info | 2025-09-30 |
| 1446 | LDK (Latihan Dasar Kepemimpinan) | ldk-latihan-dasar-kepemimpinan | Artikel, Info | 2025-10-19 |
| 1456 | UPACARA HARI SANTRI NASIONAL | upacara-hari-santri-nasional | Artikel, Info | 2025-11-06 |
| 1461 | [ Karya Palestina Pondok Roja di ISA Peace Exhibition ] | karya-palestina-... | Artikel, Info | 2025-11-21 |
| 1465 | [ Selamat wa baarakallah! Di ajang Lomba Kejuaraan Seni Tapak Suci Kab.Sukoharjo 2025 ] | selamat-wa-... | Artikel, Info | 2025-11-23 |
| 1469 | PRAY FOR INDONESIA | pray-for-indonesia | Artikel, Info | 2025-12-02 |
| 1485 | ssfdhsdfhs | ssfdhsdfhs | [SPAM/TEST] | 2026-01-29 |

### Kategori Post (Taxonomy)

| ID | Nama | Slug | Jumlah Post |
|---|---|---|---|
| 1 | **Artikel** | artikel | 20 |
| 10 | **Info** | info | 15 |
| 9 | **Kabar Berita** | kabar-berita | 12 |

### Media Library Stats (133 Attachments)

| Tahun | Jumlah File |
|---|---|
| 2019 | 50 |
| 2020 | 6 |
| 2021 | 18 |
| 2022 | 24 |
| 2023 | 2 |
| 2025 | 29 |
| 2026 | 4 |
| **Total** | **133** |

---

## 3. Brand Identity & Design Guidelines (Reverse-Engineering dari DB & CSS)

### Palette Warna Utama

| Peran | Hex | Keterangan |
|---|---|---|
| **Primary (Orange)** | `#F86E01` | Dominan: header section, top bar, hero background, footer social icons |
| **Accent Green (CTA Primer)** | `#7CDA24` | Button "Selengkapnya", label Visi/Misi, nav Donasi, active slider |
| **Accent Pink/Magenta (CTA Konversi)** | `#FF147B` | "Daftar Sekarang", hover state, scroll-to-top, blog hover |
| **Dark Magenta (Section BG)** | `#E30083` | Background section Program di homepage |
| **Dark Blue (Accent)** | `#3c39e6` | Border-top card di halaman Profil |
| **Background Page** | `#F7F9FB` | Background konten halaman dalam |
| **Background Input** | `#F9FAFD` | Input form (komentar/kontak) |
| **White** | `#FFFFFF` | Card content, body background |
| **Text Default Nav** | `rgba(32,41,47,0.6)` | Menu navigation text |
| **Border/Divider** | `#DDDDDD` | Border input, divider footer |
| **Footer Text** | `#666666` | Widget text footer |
| **Footer Link/Accent** | `#ff147b` | Link di footer widget |

### Divi Color Palette (Tersimpan di Theme Settings)

```
#000000 | #FFFFFF | #e02b20 | #e09900 | #edf000 | #7cda24 | #0c71c3 | #8300e9
```

### Tipografi

| Peran | Font | Weight | Size | Keterangan |
|---|---|---|---|---|
| **Heading (H1-H5)** | **Raleway** | 100-900 | variabel | Google Fonts |
| **Body** | **Raleway** | 400 | 16px, lh:2 | Google Fonts |
| **Navigasi Utama** | **Lato** | 600 | 14px | Uppercase, letter-spacing: 1px |
| **Top Bar / Secondary Nav** | **Lato** | 400 | 14px | Google Fonts |
| **Testimonial Kutipan** | **EB Garamond** | 400 | 16px | Italic, Google Fonts |
| **Blog Post Labels** | **Montserrat** | 500 | 16px | Uppercase, letter-spacing: 2px |

> Icon: **Font Awesome 4.7** via StackPath CDN.

### Visual Style Notes

| Elemen | Detail |
|---|---|
| **Border Radius Button** | `5px` - tegas, tidak terlalu rounded |
| **Border Radius Card** | `20px` - soft & modern |
| **Border Radius Image Blog** | `10px` |
| **Border Radius Image Post** | `20px` |
| **Border Radius Social Icons** | `4px` |
| **Box Shadow Cards** | `0 5px 20px 0 rgba(0,0,0,0.1), 0 13px 24px -11px rgba(0,0,0,0)` |
| **Box Shadow Header** | `0 5px 10px rgba(7,51,84,0.10)` (sticky) |
| **Box Shadow CTA Button** | `0 14px 26px -12px rgba(233,30,99,.42), 0 4px 23px 0 rgba(0,0,0,.12)` |
| **Header Style** | Left-aligned, Sticky/Fixed, top-bar kontak aktif |
| **Letter Spacing** | body: `0.5px`, nav: `1px`, blog title: `2px`, section header: `4px` |
| **Section Dividers** | `ramp2` style, flip horizontal (efek gelombang antar section) |
| **Section Padding** | Besar: `90px-120px`, Medium: `50px-70px` |
| **Animation** | Slide from bottom pada blurb/card, `transition: 0.2s ease-in-out` |
| **Max Width** | `1440px` pada card kustom |
| **Breakpoints** | Tablet: 768px, Mobile: 980px |

### Pattern Visual Identitas Khas Pondok Roja

- **Badge/Label Asimetris** - `border-top-left-radius: 20px; border-bottom-right-radius: 20px` dengan warna berbeda per section
- **Dual-CTA System** - CTA Primer = Hijau (#7CDA24), CTA Konversi/Urgent = Pink (#FF147B), hover saling bertukar
- **Card Bordered** - Card profil: `border-top: 18px solid #3c39e6` + `border-bottom: 10px solid #7CDA24`
- **Wave Dividers** - Setiap major section dipisah gelombang ramp2
- **GIF Banner Donasi** - 2x WAKAF.gif berdampingan sebagai CTA wakaf di beranda

---

## 4. Daftar Asset Penting

### Logo & Brand Identity

| File | Path Lokal | Keterangan |
|---|---|---|
| **Logo Utama** | `wp-content/uploads/2019/07/Logo.png` | PNG transparan, 18KB, header nav |
| **Logo Thumbnail** | `wp-content/uploads/2019/07/Logo-150x63.png` | Versi resize |
| **Brand Asset** | `wp-content/uploads/2019/07/Brand.png` | 5.7KB - alternatif logo |
| **Favicon Original** | `wp-content/uploads/2019/07/Favicon.png` | 3.1KB |
| **Favicon Cropped** | `wp-content/uploads/2019/07/cropped-Favicon.png` | 80KB - versi WordPress |
| **Favicon 32x32** | `wp-content/uploads/2019/07/cropped-Favicon-32x32.png` | Browser tab |
| **Site Icon ID** | Post ID: 593 di database | Referensi wp_options site_icon |

### Hero / Slider Images (Beranda)

| File | Path | Ukuran |
|---|---|---|
| **Slide 01** | `wp-content/uploads/2019/07/Slide-01.jpg` | 307KB |
| **Slide 02** | `wp-content/uploads/2019/07/Slide-02.jpg` | 298KB |
| **Slide 03** | `wp-content/uploads/2019/07/Slide-03.jpg` | 226KB |
| **Slide 04** | `wp-content/uploads/2019/07/Slide-04.jpg` | 222KB |
| **Cover Image** | `wp-content/uploads/2019/07/Cover.jpg` | 154KB |

### Video Asset

| File | Path | Ukuran |
|---|---|---|
| **Video Wisuda 2025** | `wp-content/uploads/2025/07/wisuda.mp4` | 30.4MB |
| **Video Wisuda Alt** | `wp-content/uploads/2025/07/wisuda-1.mp4` | 30.4MB |
| **Photo Wisuda 2025** | `wp-content/uploads/2025/07/photo_2025-07-12_10-56-01.jpg` | 211KB |
| **Video Profil 2019** | `wp-content/uploads/2019/07/Video.mp4` | 9.1MB |

### Background & Decorative Assets

| File | Path | Keterangan |
|---|---|---|
| **Page Background** | `wp-content/uploads/2019/07/Bg.png` | Background halaman Profil (dekoratif) |
| **Quote Ornament** | `wp-content/uploads/2019/07/Quote.png` | Ornamen kutipan testimonial |
| **Separator Ornament** | `wp-content/uploads/2019/07/Group-2.png` | Pembatas dekoratif blog |
| **Wakaf GIF** | `wp-content/uploads/2019/09/WAKAF.gif` | Banner animasi CTA donasi di beranda |
| **WhatsApp Button** | `wp-content/uploads/2019/07/WhatsApp.png` | Tombol WhatsApp sidebar |

### Galeri Foto (133 Media Total)

Tersebar di `wp-content/uploads/YYYY/MM/`:
- 2019: 50 file (termasuk slide, galeri kegiatan, artikel awal)
- 2020-2022: 48 file (kegiatan & blog reguler)
- 2025: 29 file (terbaru: Haflah Takhorruj Juli 2025, kegiatan harian)
- 2026: 4 file (terbaru)

---

## 5. Rekomendasi & Readiness Check Migrasi

### Kekuatan Yang Perlu Dipertahankan

1. **Konten Aktif & Terkini** - Post terakhir Desember 2025, 27 posts + 17 pages, konten masih diupdate
2. **Brand Identity Konsisten** - Palet warna, tipografi, dan pola desain jelas → siap jadi design system Next.js
3. **Media Library Terorganisir** - 133 attachment, tersusun per tahun/bulan
4. **Navigasi yang Jelas** - 16 item menu utama dengan hierarki yang logis
5. **SEO Slug Bersih** - Permalink `/%postname%/` dengan slug bahasa Indonesia yang deskriptif

### Catatan Teknis Kritis Sebelum Migrasi

| No. | Masalah | Dampak | Rekomendasi |
|---|---|---|---|
| 1 | **Konten Divi Shortcode** | TINGGI - Semua page content adalah `[et_pb_section...]`, tidak bisa langsung render sebagai HTML | Re-write konten halaman di Next.js secara manual |
| 2 | **No SEO Plugin** | TINGGI - Tidak ada Yoast/RankMath, `og:` tags tidak terverifikasi | Implementasi `next/metadata` API per-halaman |
| 3 | **URL Asset Absolute ke Domain Lama** | SEDANG - Gambar masih referensikan `https://pondokroja.com/wp-content/uploads/` | Putuskan: keep WP as headless CMS, atau migrate ke CDN/Next.js public |
| 4 | **Duplikasi Page vs Post** | SEDANG - `/rapat-kerja-tahunan/` dan `/upacara-hari-santri-nasional/` ada sebagai page DAN post | Konsolidasi sebelum build |
| 5 | **Post Spam/Test Published** | RENDAH - Post ID 1485 (`ssfdhsdfhs`) berstatus publish | Filter dari API atau hapus dari DB |
| 6 | **Video Besar (2x 30.4MB)** | SEDANG - File wisuda.mp4 tidak efisien untuk self-host | Upload ke YouTube/Vimeo, embed di Next.js |
| 7 | **Branding Ganda** | RENDAH - "Pondok Roja" vs "TMQ Rooihatul Jannah Hidayatullah" | Standardisasi: Pondok Roja (brand populer) untuk frontend |
| 8 | **Database Name di .env Berbeda** | RENDAH - `.env` DB_NAME=`roja_landingpage`, SQL dump file berbeda | Sudah confirmed: DB live bernama `roja_landingpage` |

### Struktur Halaman Next.js yang Direkomendasikan

```
app/
├── page.tsx                    → / (Beranda - Landing Page Utama)
├── profil/
│   └── page.tsx                → /profil (Tentang + Sejarah + Struktur + Visi-Misi)
├── program/
│   └── page.tsx                → /program (Formal + Nonformal + Ekskul)
├── pendaftaran/
│   └── page.tsx                → /pendaftaran (PSB - halaman konversi utama)
├── informasi/
│   ├── page.tsx                → /informasi (Blog list - Artikel + Kabar Berita + Info)
│   └── [slug]/
│       └── page.tsx            → /informasi/[slug] (Detail artikel)
├── galeri/
│   └── page.tsx                → /galeri (Foto + Video)
├── testimoni/
│   └── page.tsx                → /testimoni
├── donasi/
│   └── page.tsx                → /donasi (Wakaf Produktif)
└── kontak/
    └── page.tsx                → /kontak (Formulir & info)
```

### Design System Tokens untuk Next.js (CSS Variables)

```css
:root {
  /* === COLOR PALETTE === */
  --color-primary:        #F86E01;  /* Orange - brand utama */
  --color-accent-green:   #7CDA24;  /* Hijau - CTA primer */
  --color-accent-pink:    #FF147B;  /* Pink - CTA konversi/urgent */
  --color-accent-magenta: #E30083;  /* Magenta - section background */
  --color-accent-blue:    #3c39e6;  /* Biru tua - dekoratif card */

  --color-bg-page:        #F7F9FB;  /* Background halaman */
  --color-bg-card:        #FFFFFF;  /* Background card */
  --color-bg-input:       #F9FAFD;  /* Background input form */
  --color-bg-light:       #F1F1F1;  /* Background pembatas */

  --color-text-primary:   rgba(32,41,47,1);
  --color-text-nav:       rgba(32,41,47,0.6);
  --color-text-footer:    #666666;
  --color-text-link:      #FF147B;
  --color-border:         #DDDDDD;

  /* === TYPOGRAPHY === */
  --font-heading: 'Raleway', Helvetica, Arial, sans-serif;
  --font-body:    'Raleway', Helvetica, Arial, sans-serif;
  --font-nav:     'Lato', Helvetica, Arial, sans-serif;
  --font-quote:   'EB Garamond', Georgia, 'Times New Roman', serif;

  --font-size-body:   16px;
  --font-size-nav:    14px;
  --line-height-body: 2;

  --letter-spacing-body:    0.5px;
  --letter-spacing-nav:     1px;
  --letter-spacing-blog:    2px;
  --letter-spacing-heading: 4px;

  /* === BORDER RADIUS === */
  --radius-btn:    5px;
  --radius-card:   20px;
  --radius-img-sm: 10px;
  --radius-img-lg: 20px;
  --radius-social: 4px;
  --radius-badge-tl: 20px 5px 20px 5px; /* asimetris khas Pondok Roja */

  /* === BOX SHADOWS === */
  --shadow-card:    0 5px 20px 0 rgba(0,0,0,0.1), 0 13px 24px -11px rgba(0,0,0,0);
  --shadow-header:  0 5px 10px rgba(7,51,84,0.10);
  --shadow-btn-cta: 0 14px 26px -12px rgba(233,30,99,.42), 0 4px 23px 0 rgba(0,0,0,.12), 0 8px 10px -5px rgba(233,30,99,.2);

  /* === SPACING === */
  --section-padding-lg: 120px;
  --section-padding-md: 70px;
  --section-padding-sm: 40px;

  /* === TRANSITIONS === */
  --transition-base: all 0.2s ease-in-out 0s;
}
```

### Social Media Links

| Platform | URL |
|---|---|
| Facebook | https://www.facebook.com/pondok.roja/ |
| Twitter/X | https://twitter.com/pondok_roja |
| Instagram | https://www.instagram.com/pondok_roja/ |

### Koneksi Database untuk Development

```env
DB_TYPE=mysql
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=root
DB_NAME=roja_landingpage
```

> MySQL binary: `C:\Program Files\MySQL\MySQL Server 8.0\bin\mysql.exe`

---

*Laporan ini dihasilkan dari query langsung ke database MySQL live (`roja_landingpage`) dan analisis direktori `wp-content/`. Tidak ada data yang dimodifikasi.*
