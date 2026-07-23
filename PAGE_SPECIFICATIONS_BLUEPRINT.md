# 📐 Blueprint Spesifikasi Visual & Konteks Halaman (Non-Post)

> **Versi:** 2.0 — Diperkaya dari crawl HTML statis live site (23 Juli 2026).
> Sumber data: Divi shortcode DB + **17 file HTML nyata** dari `html_exports/` (via `https://pondokroja.com/wp-sitemap-posts-page-1.xml`).
> Divi versi aktif di live site: **4.27.7** (sedikit lebih baru dari DB lokal 4.24.2).

Dokumen ini adalah acuan mutlak (Source of Truth) untuk rekonstruksi UI ke dalam komponen Next.js.

---

## 📌 Komponen Global (Shared Layout)

> Data berikut adalah **factual** dari HTML live site — bukan perkiraan.

### 1. Navigation / Header

**HTML Structure:**
```html
<header id="main-header" data-height-onload="66">
  <div id="et-top-navigation" data-height="66" data-fixed-height="40">
    <nav id="top-menu-nav">
      <ul id="top-menu" class="nav">
        <!-- menu items -->
      </ul>
    </nav>
  </div>
</header>
```

- **Logo:** `<img src="https://pondokroja.com/wp-content/uploads/2019/07/Logo.png" width="164" height="63" alt="Pondok Roja" id="logo" data-height-percentage="54">` — dibungkus dalam `<div class="logo_container">`.
- **Header Height:** `66px` desktop, `40px` saat sticky/scroll.
- **Behavior:** Fixed/Sticky. CSS class `et_fixed_nav et_show_nav et_secondary_nav_enabled` pada `<body>`.

**Primary Menu Items (dari `id="top-menu"`):**

| ID Elemen | Label | URL | Sub-menu |
|---|---|---|---|
| `menu-item-38` | **Beranda** | `/` | — |
| `menu-item-32` | **Profil** | `/profil/` | Ya |
| — | ↳ Program | `/program/` | — |
| — | ↳ Amal Usaha | `/amal-usaha/` | — |
| — | ↳ Testimoni | `/testimoni/` | — |
| `menu-item-31` | **Galeri** | `/galeri/` | Ya |
| — | ↳ Foto | `/galeri/` | — |
| — | ↳ Vidio | `/vidio/` | — |
| `menu-item-1003` | **Informasi** | `/pendaftaran/` | Ya |
| — | ↳ Pendaftaran | `/pendaftaran/` | — |
| — | ↳ Kegiatan | `/kegiatan/` | — |
| `menu-item-929` | **Rubrik** | `/rubik/` | Ya |
| — | ↳ Kabar Berita | `/category/kabar-berita/` | — |
| — | ↳ Artikel | `/category/artikel/` | — |
| `menu-item-26` | **Kontak** | `/kontak/` | — |
| `menu-item-147` | **Donasi** | `/donasi/` | — |

> ⚠️ **Bug Live Site:** Menu item "Informasi" mengarah ke `/pendaftaran/` (bukan ke `/informasi/`). Di Next.js sebaiknya diperbaiki ke `/informasi/`.

> ℹ️ Item "Donasi" diberi class `nav-donation` — styling-nya sebagai **tombol hijau** yang terpisah dari link nav biasa.

**Mobile Nav:** `<div id="et_mobile_nav_menu">` → `<div class="mobile_nav closed">` dengan hamburger `<span class="mobile_menu_bar">`.

**Search Bar:** `<div id="et_top_search">` dengan form `class="et-search-form"` (tersembunyi, muncul saat ikon diklik).

**Font (Nav):** `font-family: 'Lato', Helvetica, Arial, sans-serif` — 14px, uppercase, letter-spacing.

---

### 2. Footer

**HTML Structure:**
```html
<footer id="main-footer">
  <div id="footer-widgets" class="clearfix">
    <!-- 4 widget columns -->
  </div>
  <div id="footer-bottom">
    <ul class="et-social-icons"> ... </ul>
    <div id="footer-info">Copyright 2019 - <a href="https://pondokroja.com">Pondok Roja</a>. All Rights Reserved.</div>
  </div>
</footer>
```

**Widget 1 — About (Logo + Deskripsi):**
- Logo `Logo.png` diulang di footer.
- Teks: *"Pesantren Tahfidz Putri Rooihatul Jannah (Pondok Roja) adalah lebaga pendidikan Islam setingkat SMP-SMA..."*

**Widget 2 — Hubungi Kami:** (`<h4 class="title">Hubungi Kami</h4>`)
- HP/WhatsApp: `0813 9210 4443`
- Ust. Sigit: `0857 1246 5118`
- Ust. Amalina: `0858 6569 3081`
- Email: `pondok.roja@gmail.com` *(Cloudflare-obfuscated di HTML)*
- Alamat: *Brumbung, Dukuh, Kec. Sukoharjo, Kab. Sukoharjo, Jawa Tengah 57524*

**Widget 3 — Pintasan:** (`<h4 class="title">Pintasan</h4>`) → `<ul id="menu-secondary-menu" class="menu">`
- Beranda, Kegiatan, Program, Profil, Testimoni, Galeri, Pendaftaran, Kontak

**Widget 4 — Informasi:** (`<h4 class="title">Informasi</h4>`) → 5 recent posts terbaru dengan tanggal (`<span class="post-date">`)

**Footer Bottom Bar:**
- Social icons: `<ul class="et-social-icons">`
  - Facebook → `https://www.facebook.com/pondok.roja/` (class: `et-social-facebook`)
  - Twitter/X → `https://twitter.com/pondok_roja` (class: `et-social-twitter`)
  - Instagram → `https://www.instagram.com/pondok_roja/` (class: `et-social-instagram`)
  - RSS → `https://pondokroja.com/feed/` (class: `et-social-rss`)
- Copyright: `<div id="footer-info">Copyright 2019 - Pondok Roja. All Rights Reserved.</div>`

---

### 3. Floating & Shared UI Elements

**Back-to-Top Button (semua halaman):**
```html
<span class="et_pb_scroll_top et-pb-icon"></span>
```
CSS (dari inline style `et-critical-inline-css`):
```css
.et_pb_scroll_top.et-pb-icon {
  border-radius: 50px;
  right: 10px;
  background-color: #FF147B;
  box-shadow: 0 10px 30px rgba(51,73,90,.38);
}
```

**Monarch Social Sidebar (semua inner page):**
```html
<div class="et_social_sidebar_networks et_social_visible_sidebar et_social_slideright
            et_social_animated et_social_rounded et_social_sidebar_flip et_social_mobile_on">
```
Muncul di sisi kiri/kanan layar — berisi tombol share Facebook, Twitter, Pinterest, Google+.

**WhatsApp Button (khusus halaman `/donasi/`):**
Bukan floating — berada di dalam konten halaman:
```html
<a href="https://api.whatsapp.com/send?phone=6282223095818" target="_blank">
  <img src=".../WhatsApp.png" width="330" height="46" />
</a>
```
> Tidak ada global floating WA button — ini hanya ada di halaman Donasi.

---

## 📄 Detail Spesifikasi Per Halaman

### 1. Beranda (URL: `/`)
- **Tujuan Halaman:** Landing page utama untuk menarik calon pendaftar, menampilkan program unggulan, dan ajakan berdonasi.
- **SEO Metadata:** Meta Title & Desc bawaan WP (unoptimized).

#### Seksi 1: Hero Slider
- **Tipe Layout:** Fullwidth Slider (Carousel).
- **Teks / Copywriting:**
  - **Heading (H1):** "Menghafal Al-Qur'an dengan Ceria"
  - **Body Teks:** "Pesantren Tahfidz Putri Rooihatul Jannah (Pondok Roja) adalah lembaga pendidikan islam setingkat SMP-SMA yang menerapkan kurikulum integral..."
- **Elemen UI / CTA:** Tombol [Tentang Kami -> `/profil`] dengan icon panah. Background Hijau (`#7CDA24`), Hover Pink (`#FF147B`).
- **Visual & Style:** Overlay teks putih, `border-radius` tombol `5px`.
- **Media Assets:** `Slide-02.jpg`, `Slide-03.jpg`, `Slide-04.jpg`.

#### Seksi 2: Berita / Post Carousel Terbaru
- **Tipe Layout:** Fullwidth Post Slider.
- **Elemen UI:** Menampilkan kategori "Kabar Berita". Tombol CTA [Baca Selengkapnya].

#### Seksi 3: Banner Wakaf (Donasi)
- **Tipe Layout:** 2-Column Grid.
- **Visual & Style:** Menampilkan 2 gambar GIF animasi berdampingan tanpa jarak (`custom_margin="-8px||"`).
- **Media Assets:** `wp-content/uploads/2019/09/WAKAF.gif` (Link ke `http://bit.ly/wakaf-roja`).

#### Seksi 4: Program Unggulan (Fitur Grid)
- **Tipe Layout:** 2-Column Grid bersusun (4 Item).
- **Teks & Elemen:**
  - 1. **Tahfidzul Qur'an** (Mutqin minimal 20 Juz)
  - 2. **Bilingual (Arab-Inggris)**
  - 3. **Pengembangan Minat Bakat**
  - 4. **Kelas Multinasional**
- **Visual & Style:** Menggunakan komponen 'Blurb' Divi. Ikon berada di atas teks (alignment center). Animasi "Slide from bottom". Warna Ikon Pink (`#FE147B`).

#### Seksi 5: Tentang Pondok (Section Magenta/Orange)
- **Tipe Layout:** Centered Content. Background solid Orange (`#F86E01`) dengan Divider gelombang atas-bawah (`ramp2` style).
- **Teks / Copywriting:**
  - **Sub-heading:** "Pondok Pesantren"
  - **Heading (H1):** "Rooihatul Jannah Hidayatullah"
  - **Body:** Deskripsi singkat pesantren modern berjenjang 6 tahun + 1 tahun pengabdian.
- **Elemen UI / CTA:** Tombol [Selengkapnya -> `/profil`] bergaya Pink (`#FF147B`) dengan `box-shadow` melayang.

#### Seksi 6: Visi & Misi
- **Tipe Layout:** 1/3 (Visi) dan 2/3 (Misi) Column Grid.
- **Teks / Copywriting:**
  - Visi: "Lembaga pendidikan islam pencetak kader pemimpin umat..."
  - Misi: List 1-3 (Membentuk generasi muslim yang unggul...).
- **Visual & Style:** Label "VISI" & "MISI" menggunakan desain asimetris: Background Hijau (`#7CDA24`), border-radius: `20px 0px 20px 0px`, teks Uppercase putih.

#### Seksi 7: Highlight Program Formal & Non Formal
- **Tipe Layout:** 2-Column Grid (Cards).
- **Visual & Style:** Background seksi Magenta (`#E30083`). Card konten berwarna Putih melayang (negative margin `-102px` agar overlapping dengan section sebelumnya), `border-radius: 20px`, `box-shadow`.
- **Elemen UI / CTA:**
  - Kiri: "Sistem Pendidikan Formal" -> Tombol Hijau [Selengkapnya -> `/program/#sistem-pendidikan-formal`]
  - Kanan: "Sistem Pendidikan Non Formal" -> Tombol Orange [Selengkapnya -> `/program/#sistem-pendidikan-nonformal`]

#### Seksi 8: Informasi / Blog Grid Terakhir
- **Tipe Layout:** Centered Header + 3-Column Blog Grid.
- **Teks / Copywriting:** "Informasi" - "Dapatkan informasi menarik tentang Islam yang tentunya sangat bermanfaat untuk Anda."

---

### 2. Profil (URL: `/profil`)
- **Tujuan Halaman:** Menampilkan detail sejarah, visi-misi lengkap, struktur kepengurusan, fasilitas, dan prestasi.

#### Seksi 1: Header
- **Tipe Layout:** Fullwidth Header. Background Orange (`#F86E01`), Bottom Divider `ramp2` warna putih. Judul: "Profil Kami".

#### Seksi 2: Identitas Utama & Visi Misi
- **Tipe Layout:** 1 Column Centered. Background Gradient (`#ffffff` ke `#e1eafb`) + Image Pattern di bawah (`Bg.png`).
- **Teks / Copywriting:** "Pondok Pesantren TMQ Rooihatul Jannah Hidayatullah".
- **Visual & Style:** Card Visi & Misi menggunakan desain khusus: Label Title berwarna Pink (`#FF147B`) dengan `position: absolute; left: 40px; top: -27.5px`. Kotak konten berwarna Putih dengan `border-radius: 20px 5px 20px 5px`.

#### Seksi 3: Sejarah Singkat & Kepengurusan
- **Tipe Layout:** Teks Sejarah (Centered) -> Diikuti 5-Column Grid untuk Pengurus.
- **Teks Pengurus:** Pembina, Pengawas, Ketua, Sekretaris, Bendahara.
- **Visual & Style:** Grid pengurus berada di dalam container khusus dengan `border-top: 18px solid #3c39e6` (Biru tua) dan `border-bottom: 10px solid #7CDA24` (Hijau), background putih, `border-radius: 15px`, dan shadow sangat tebal (`0px 39px 80px -6px rgba(0,0,0,0.1)`).

#### Seksi 4: Fasilitas & Prestasi
- **Tipe Layout:** 2/5 (Fasilitas) dan 3/5 (Prestasi) Grid. Background Magenta Gradient (`#FF147B` ke `#ffffff`).
- **Elemen UI:** Card putih melayang. Ikon Fasilitas (Listik centang), Prestasi menggunakan teks cetak tebal dan miring untuk daftar kejuaraan.

---

### 3. Program (URL: `/program`)
- **Tujuan Halaman:** Menjelaskan secara rinci kurikulum, sistem formal, non-formal, dan ekstrakurikuler.

#### Seksi 1: Header
- **Tipe Layout:** Fullwidth Header Orange (`#F86E01`). Judul: "Program". Divider `ramp2` warna abu muda (`#F7F9FB`).

#### Seksi 2: Detail Program (Formal, Non-formal, Ekskul)
- **Tipe Layout:** 1 Column List (Tumpukan Card).
- **Teks / Copywriting:**
  - **Sistem Pendidikan Formal:** Deskripsi jam KBM (07.30 s/d 11.50 WIB), tahfidz, dll.
  - **Sistem Pendidikan Nonformal:** List a-k (Ta'lim, Organisasi Santri, Kepanduan, Club Bahasa, dll).
  - **Ekstra Kulikuler:** List 1-15 (Pandu, Muhadhoroh, Memanah, Berkuda, dll).
- **Visual & Style:** Menggunakan desain Card dengan Absolute Badge Title. Badge "Formal" & "Nonformal" warna Pink (`#FF147B`), sedangkan "Ekstra Kulikuler" warna Hijau (`#7CDA24`). Kotak deskripsi putih, `border-radius: 20px 5px 20px 5px`. Terdapat Anchor Link (`id="sistem-pendidikan-formal"`) untuk navigasi dari beranda.

---

### 4. Pendaftaran (URL: `/pendaftaran`)
- **Tujuan Halaman:** Pusat konversi untuk penerimaan santri baru (PSB).

#### Seksi 1: Header
- **Tipe Layout:** Fullwidth Header Orange (`#F86E01`). Judul: "Pendaftaran".

#### Seksi 2: Informasi PSB
- **Tipe Layout:** 2-Column Grid (Grid 2x2). Background halaman abu-abu muda (`#F7F9FB`).
- **Cards:**
  1. **Syarat Pendaftaran:** (Icon Hijau di kiri, bulat absolute) -> Pendaftaran Online, FC KK.
  2. **Waktu Pendaftaran:** (Icon Pink) -> 5 Des - 30 Mar.
  3. **Biaya Pendidikan:** (Icon Hijau) -> Rincian Syahriyah Rp 750k, Pendaftaran 300k, Wakaf 4jt, dll.
  4. **Tes Seleksi:** (Icon Pink) -> Hafalan, PAI, Matematika, IPA, B.Indo, B.Inggris.
- **Visual & Style:** Setiap card berwarna putih (`border-radius: 20px`). Ikon berada di dalam lingkaran ber-border putih tebal (`5px solid #FFFFFF`), posisinya menjorok keluar ke sebelah kiri (`left: -65px; position: absolute`). Desain ini sangat ikonik dan harus direplikasi.

#### Seksi 3: CTA Utama
- **Tipe Layout:** 1 Column Centered.
- **Elemen UI:** Tombol Lebar [Daftar Sekarang -> `https://psb.pondokroja.com`] warna Pink (`#FF147B`). Melayang dengan negative margin.

---

### 5. Kegiatan (URL: `/kegiatan`)
- **Tujuan Halaman:** Tabel jadwal harian santri (waktu & aktifitas).

#### Seksi 1: Header & Judul
- **Tipe Layout:** Fullwidth Header Orange -> Diikuti Teks Judul Centered "JADWAL KEGIATAN TARBIYATUL MUHAFIDZOTIL QUR'AN".

#### Seksi 2: Jadwal Harian & Pekan
- **Tipe Layout:** Card Putih besar (`border-radius: 20px`, shadow). Di dalamnya terdapat Tag `<table>` HTML mentah.
- **Teks / Konten:**
  - **A. Harian:** Tabel 20 item (03.30 Sholat tahajud s/d 22.00 Tidur).
  - **B. Pekan:** Tabel 7 item (Senin/Kamis Puasa, Ahad Tapak Suci, dll).

---

### 6. Testimoni (URL: `/testimoni`)
- **Tujuan Halaman:** Social proof dari wali santri.

#### Seksi 1: Header
- **Tipe Layout:** Fullwidth Header Orange. Judul: "Testimoni".

#### Seksi 2: Masonry / 2-Column Grid Testimonial
- **Tipe Layout:** 2-Column Grid. Terdapat ornamen kutipan ganda (`Quote.png`) berukuran besar dengan negative margin di awal setiap kolom.
- **Elemen UI:** Modul Testimonial Divi (Teks Quote, Nama Author, Kelas, Nama Wali, dan Avatar/Foto Bundar).
- **Teks / Copywriting:** Kutipan dari wali santri (Aliya Husna, Olivia Zubaidah, dll) yang memuji hafalan, kemandirian, dan kenyamanan.

---

### 7. Kontak (URL: `/kontak`)
- **Tujuan Halaman:** Alamat, Google Maps, dan Form Kirim Pesan.

#### Seksi 1: Header & Map
- **Tipe Layout:** Fullwidth Header Orange (Teks: "Kami sangat terbuka...") -> Dilanjutkan dengan iframe Google Maps Fullwidth (Tanpa border/padding).

#### Seksi 2: Info & Form Grid
- **Tipe Layout:** 2-Column Grid (Kiri: Info Kontak teks, Kanan: Form).
- **Kiri (Info Kontak):**
  - Nomor Roja 1, 2, 3.
  - Email.
  - Alamat Lengkap.
- **Kanan (Form):**
  - Input: Name, Email Address, Message (Textarea).
  - Tombol Submit: [Kirim Pesan] warna Hijau (`#7CDA24`). Style input kotak dengan border abu-abu (`#ddd`) dan background abu sangat terang (`#F9FAFD`).

---

### 8. Donasi (URL: `/donasi`)
- **Tujuan Halaman:** Menggalang wakaf dan sedekah untuk pembangunan dan operasional.

#### Seksi 1: Header
- **Tipe Layout:** Fullwidth Header Orange. Judul: "Donasi".

#### Seksi 2: Penjelasan & Galeri Mini
- **Tipe Layout:** Teks Centered (Deskripsi Penyaluran Infaq untuk masjid, saung, asrama, dll) -> Diikuti Galeri 4 gambar berderet (Gambar desain pembangunan/kegiatan).

#### Seksi 3: Rekening Bank (Cards)
- **Tipe Layout:** 3-Column Grid.
- **Visual & Style:** Container grid melayang (negative margin) dengan background Hijau (`#7CDA24`), sudut asimetris yang ekstrim (`border-radius: 50px 0 50px 0`), serta `border-top: 18px solid`. Teks di dalamnya putih.
- **Teks / Konten (3 Bank):**
  1. BNI Syariah (0820-7561-67 a.n. Yayasan Hidayatullah Sukoharjo)
  2. Bank Syariah Mandiri (7080-2428-61)
  3. Bank Muamalat Indonesia (5210-0726-97)

#### Seksi 4: Kontak Cepat & Map Mini
- **Tipe Layout:** 1-Column Box melayang di atas Footer.
- **Visual & Style:** Container putih border biru tua (`#3c39e6`). Di dalamnya ada teks nomor HP (+62 822...), Ikon/Tombol WhatsApp besar `WhatsApp.png` (link ke `api.whatsapp.com`), alamat, dan iframe Google Maps berukuran kecil dengan radius di bagian bawah.

---

## 🛠 Target Rekomendasi Komponen Next.js (Dekomposisi UI)

Berdasarkan analisis struktur desain di atas, berikut adalah arsitektur komponen React/Next.js yang direkomendasikan untuk pembuatan ulang:

### Global UI Components
- `MainLayout.tsx` (Membungkus Header, Main Content, Footer, & Floating WA)
- `Header.tsx` (Sticky nav, transparansi saat scroll)
- `Footer.tsx` (Multi-column links)
- `PageHeader.tsx` (Banner Orange `#F86E01` dengan divider ombak putih di bagian bawah, digunakan di hampir semua halaman)
- `WaveDivider.tsx` (SVG untuk mereplikasi efek Divi `ramp2` di bawah section)

### Atoms & Molecules (Design System)
- `Button.tsx` (Prop variant: `primary` untuk Hijau, `secondary` untuk Pink, `outline`)
- `BadgeCard.tsx` (Card putih melayang dengan label/title asimetris absolute di sudut kiri atas - *Digunakan di halaman Profil & Program*)
- `FloatingIconCard.tsx` (Card putih dengan lingkaran ikon yang menjorok keluar ke kiri - *Digunakan di halaman Pendaftaran*)
- `TestimonialItem.tsx` (Berisi kutipan, avatar bundar, nama, dan detail wali)

### Section Blocks (Organisms)
- `HeroSlider.tsx` (Carousel di Beranda dengan teks dan tombol Pink/Hijau)
- `FeatureGrid.tsx` (Grid 2x2 atau 4 kolom untuk Program Unggulan di Beranda)
- `DonationBanner.tsx` (2 GIF animasi Jejer)
- `BankAccountsGrid.tsx` (Grid 3 bank dengan background hijau asimetris - *Halaman Donasi*)
- `ScheduleTable.tsx` (Wrapper responsive untuk tabel jadwal harian & pekan - *Halaman Kegiatan*)
- `ContactForm.tsx` (Formulir validasi sederhana - *Halaman Kontak*)
- `TeamGrid.tsx` (Card besar dengan border atas biru & bawah hijau untuk menampilkan pengurus - *Halaman Profil*)

---
*Blueprint ini disusun berdasarkan data aseli Divi Builder (JSON/Shortcode) per 23 Juli 2026. Layout bersifat pixel-perfect reference.*
