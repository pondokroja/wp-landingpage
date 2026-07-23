MASTER CONTEXT & SYSTEM INSTRUCTIONS

Project Code: Roja Web Revamp (Phase 1)
Stack: Astro (Frontend) + WordPress REST API (Headless CMS)
Date: July 2026
Target Audience of this Document: AI Coding Agent / LLM Assistant

1. PROJECT OVERVIEW & BUSINESS DOMAIN

Brand: Pondok Roja (Pondok Pesantren Rooihatul Jannah Hidayatullah)

Domain: Pendidikan Islam (Pesantren Putri setingkat SMP-SMA). Program unggulan Tahfidzul Qur'an (target 20 juz).

Target Audience: Orang tua/wali calon santri, calon santri perempuan (kelas 5-6 SD), dan donatur/wakaf.

Primary CTA: Pendaftaran Santri Baru (PSB) via tombol "Daftar Sekarang" (mengarahkan ke https://psb.pondokroja.com) dan Donasi/Wakaf.

Goal Phase 1: Mengganti frontend monolithic WordPress (tema Divi) dengan Astro yang super cepat (0 KB JS untuk statis), menyelesaikan masalah SEO/Sitemap, sambil tetap membiarkan admin non-teknis mengisi blog/berita melalui dashboard WordPress lama.

2. PROBLEM STATEMENT (MENGAPA MIGRASI?)

Vendor Lock-in (Divi Bloat): Saat ini, 17 halaman dan 27 post terbungkus shortcode [et_pb_section...]. Output HTML sangat kotor dan lambat.

SEO & Sitemap Failures: Website tidak memiliki plugin SEO. Beban client-side dan SSR bawaan Divi membuat crawler Google sering timeout, sehingga sitemap gagal terindeks.

Performa Aset: 133 aset media (termasuk video 30MB) membebani server lokal VPS.

3. ARCHITECTURE DECISION (PHASE 1)

Frontend Framework: Astro (versi 4+). Pendekatan "Islands Architecture".

Rendering Mode: hybrid (Mayoritas halaman di-generate statis / SSG saat build, sedangkan halaman blog tunggal menggunakan on-demand rendering atau SSR).

Backend/CMS: WordPress REST API (Read-Only). Admin tetap login ke pondokroja.com/wp-admin. Frontend baru (Astro) akan dipublikasikan di domain utama nantinya.

Sitemap Strategy: Menggunakan @astrojs/sitemap untuk halaman statis, dan dynamic route sitemap-posts.xml.ts yang me-fetch WP API untuk konten dinamis.

4. ROUTING & FILE STRUCTURE STRATEGY (ASTRO)

Agen HARUS mengikuti struktur direktori Astro berikut saat menulis kode:

src/
├── components/          # Reusable UI (Astro/Preact/React)
│   ├── Atoms/           # Button, Badge, WaveDivider, Icons
│   ├── Molecules/       # CardProfil, TestimoniItem, PostCard
│   └── Organisms/       # HeroSlider, Navbar, Footer, FeatureGrid
├── layouts/
│   └── MainLayout.astro # Base HTML, Head, Meta SEO, Navigation
├── lib/
│   └── wp.ts            # Fungsi fetch ke WordPress REST API
├── pages/
│   ├── index.astro      # (SSG) Beranda (/)
│   ├── profil.astro     # (SSG) Profil & Visi Misi (/profil)
│   ├── program.astro    # (SSG) Program & Ekskul (/program)
│   ├── pendaftaran.astro# (SSG) Info PSB (/pendaftaran)
│   ├── kegiatan.astro   # (SSG) Jadwal (/kegiatan)
│   ├── testimoni.astro  # (SSG) (/testimoni)
│   ├── kontak.astro     # (SSG) Form Kontak (/kontak)
│   ├── donasi.astro     # (SSG) Wakaf & Rekening (/donasi)
│   └── informasi/
│       ├── index.astro  # (SSG/SSR) Daftar berita (/informasi)
│       └── [slug].astro # (SSR/On-demand) Detail post WP
└── styles/
    └── global.css       # Tailwind config / CSS Variables


Penting: Halaman seperti profil, program, dan pendaftaran HARUS DI-HARDCODE struktur HTML/datanya di Astro. Jangan di-fetch dari page WordPress lama karena kontennya penuh shortcode Divi dan desain tata letaknya terlalu spesifik. API WordPress HANYA digunakan untuk /informasi (Blog/Berita).

5. DESIGN SYSTEM & TOKENS (CSS VARIABLES)

Agen harus menggunakan token warna dan tipografi ini secara konsisten (bisa diadaptasi ke tailwind.config.mjs):

Warna Utama:

--color-primary: #F86E01 (Orange - untuk Header Banner, Footer icons)

--color-accent-green: #7CDA24 (Hijau - CTA Sekunder, Slider aktif, Label Visi/Ekskul)

--color-accent-pink: #FF147B (Pink/Magenta - CTA Primer "Daftar", Hover states)

--color-section-bg: #E30083 (Magenta Tua - Background section khusus)

--color-bg-body: #F7F9FB (Abu-abu sangat terang - Background halaman utama)

Tipografi:

Heading (H1-H5): Raleway (Google Fonts)

Body: Raleway, 16px, line-height: 2, letter-spacing: 0.5px.

Navigasi Utama: Lato, 14px, Uppercase, letter-spacing: 1px.

Border Radius Khas (Wajib Direplikasi):

Tombol (Button): 5px

Card General: 20px

Asymmetrical Badge (Khas Pondok Roja): border-radius: 20px 5px 20px 5px (Digunakan di judul section Visi-Misi, Program, dll).

Shadow:

Card Shadow: 0 5px 20px 0 rgba(0,0,0,0.1)

6. DATA FETCHING (WORDPRESS REST API)

Agen akan menulis fungsi di src/lib/wp.ts untuk menarik data. Skema endpoint:

Get All Posts: GET /wp-json/wp/v2/posts?_embed&per_page=10

Gunakan parameter _embed untuk mendapatkan URL Featured Image (wp:featuredmedia) dan Author.

Get Single Post by Slug: GET /wp-json/wp/v2/posts?slug={slug}&_embed

Sanitisasi Konten: Konten post (content.rendered) masih merupakan HTML. Agen harus merendernya di Astro menggunakan <Fragment set:html={post.content.rendered} />.

7. AI AGENT DIRECTIVES (RULES OF ENGAGEMENT)

Saat menerima instruksi untuk membangun komponen atau halaman, ikuti aturan ketat berikut:

Astro First: Gunakan .astro files untuk 90% komponen (Zero JS). Gunakan framework UI client (Preact/React/Svelte) HANYA untuk interaktivitas berat (misal: Form Kontak, Image Gallery Slider).

No Divi Trash: Jangan pernah mencoba me-render shortcode Divi ([et_pb...]) ke dalam UI Astro. Konversi visualnya menjadi HTML/Tailwind murni.

Responsive by Default: Pastikan semua tata letak mobile-first. Pengguna (orang tua santri) mayoritas mengakses via HP.

SEO Implementation: Setiap file layout MainLayout.astro wajib menerima props berupa title, description, canonicalURL, dan ogImage.

Wave Dividers: Pondok Roja identik dengan pembatas seksi bergelombang (Divi ramp2). Agen harus menggunakan elemen SVG (wave) sebagai komponen mandiri <WaveDivider /> untuk mereplikasi desain ini.

Card Registration UI: Di halaman pendaftaran, perhatikan bahwa ikon CTA menjorok keluar batas kotak (absolute positioning left: -65px). Desain ikonik ini wajib direplikasi secara pixel-perfect.