# Laporan SEO Readiness Mulkan Mimba'un

Tanggal audit dan implementasi: 24 Juni 2026  
URL production: https://mulkanmimbaun.dekatlokal.com/

Pemeriksaan live pada tanggal audit: homepage, `robots.txt`, dan `sitemap.xml` production aktif melalui HTTPS dan masing-masing mengembalikan status 200. Metadata live masih versi lama karena perubahan dalam laporan ini belum dideploy.

## Ringkasan audit awal

- Homepage sudah berupa HTML statis sehingga konten utama tersedia pada respons awal.
- Canonical, robots meta, `robots.txt`, sitemap dasar, dan metadata sosial dasar sudah tersedia serta memakai domain production.
- Title dan meta description masih generik dan belum memuat positioning serta produk utama secara memadai.
- Structured data baru mencakup `WebSite` dan `Organization`; belum ada `LocalBusiness`, `WebPage`, `BreadcrumbList`, `Product`, `OfferCatalog`, atau `FAQPage`.
- FAQ dan lima produk sudah tampil di halaman sehingga layak direpresentasikan dalam structured data.
- Foto utama berukuran sekitar 2,3–2,6 MB per file. Sebagian besar gambar belum memiliki dimensi intrinsik, lazy loading, decoding hint, atau alt text yang cukup deskriptif.
- Pesan CTA WhatsApp belum konsisten dengan sumber DekatLokal dan konteks produk.
- Deskripsi GULJACO serta jawaban FAQ halal perlu dibuat lebih aman agar tidak menyiratkan manfaat kesehatan atau sertifikasi yang belum terverifikasi.
- Sitemap belum memiliki `lastmod`.

## File yang diubah atau ditambahkan

- `index.html`: metadata, JSON-LD, semantik, image SEO, CTA, aksesibilitas, dan performance hints.
- `sitemap.xml`: penambahan `lastmod`.
- `vercel.json`: cache header, content type, dan header keamanan dasar.
- `SEO-READINESS.md`: laporan audit, status readiness, risiko, dan SOP Google Search Console.
- `assets/hero-section2.jpg` dan `assets/og-mulkan-mimbaun.jpg`: hero terkompresi dan social preview 1200×630.
- `assets/abon-tuna-panggang.jpg`, `assets/keripik-tempe.jpg`, `assets/otak-otak.jpg`, `assets/guljaco.jpg`, `assets/kopi.jpg`, dan `assets/cerita-kami.jpg`: foto konten terkompresi.
- `assets/logo-mulkan-mimbaun-optimized.png`, `assets/rumah-bumn-optimized.png`, dan `assets/bank-bri-optimized.png`: logo beresolusi web.
- `robots.txt`: diverifikasi sudah benar sehingga tidak perlu diubah.

## Implementasi

### Metadata dan indexing

- Title: `Mulkan Mimba’un | Oleh-Oleh Makanan dan Minuman Lokal Makassar - DekatLokal`
- Meta description berisi nama bisnis, Makassar, dan lima kelompok produk utama secara natural.
- Canonical tetap satu versi dan mengarah ke URL HTTPS production.
- Robots meta mengizinkan index/follow dan preview gambar besar.
- Open Graph dan Twitter Card memakai judul/deskripsi khusus serta gambar preview 1200×630.
- `robots.txt` telah diverifikasi mengizinkan crawling dan menunjuk sitemap production.
- Sitemap berisi homepage production dan `lastmod` yang sesuai perubahan halaman.

### Structured data

Satu graph JSON-LD sekarang memuat:

- `Organization`
- `LocalBusiness` tanpa alamat pusat yang belum terverifikasi
- `WebSite`
- `WebPage`
- `ImageObject`
- `BreadcrumbList`
- `OfferCatalog`
- Lima `Product`: Abon Tuna Panggang, Keripik Tempe, Otak-Otak Ikan, GULJACO, dan Kopi Para Raja
- `AggregateOffer.lowPrice` untuk merepresentasikan harga "mulai dari" tanpa membuat harga final, stok, atau variasi palsu
- `FAQPage` untuk enam FAQ yang benar-benar terlihat di halaman

Structured data sengaja tidak memuat rating/review, alamat pusat, jam operasional, availability, SKU/GTIN, sertifikasi, atau klaim legal yang belum dapat diverifikasi.

### Image SEO dan performa

- Hero memakai versi JPEG terkompresi, diprioritaskan dengan preload dan `fetchpriority="high"`.
- Preview sosial dibuat dari visual hero pada ukuran 1200×630.
- Foto produk dan cerita dikonversi ke JPEG terkompresi tanpa mengubah komposisi visual.
- Logo besar yang digunakan di halaman dibuatkan versi PNG teroptimasi.
- Seluruh gambar memiliki width, height, alt text, dan decoding hint.
- Gambar di bawah fold menggunakan lazy loading; hero tetap eager.
- Aset foto yang sebelumnya sekitar 2,3–2,6 MB turun menjadi sekitar 0,23–0,34 MB per file.
- Konten tetap terlihat ketika JavaScript tidak tersedia; animasi reveal hanya diaktifkan saat JavaScript aktif.
- Header cache aset dan header keamanan dasar ditambahkan melalui konfigurasi Vercel.

### Link, CTA, dan keamanan klaim

- CTA utama dan per produk memakai `wa.me` dengan nomor internasional serta pesan yang menyebut DekatLokal, Mulkan Mimba'un, dan produk terkait.
- Link Google Maps dan Shopee dipertahankan, diberi label aksesibel, dan teks CTA dibuat deskriptif.
- Link ke domain utama DekatLokal tetap tersedia.
- Klaim "stamina harian" pada GULJACO diubah menjadi bahasa pengalaman rasa yang aman.
- Jawaban FAQ bahan pengawet dan halal tidak lagi menyiratkan status yang belum terverifikasi.

## Status readiness

- Technical indexing: siap di level code.
- Product snippets: siap diuji, dengan catatan homepage berisi beberapa produk dan harga "mulai dari".
- Merchant listings: belum dapat dianggap lengkap sebelum tersedia harga final per variasi, availability, kebijakan pengiriman/pengembalian, identifier produk, dan landing page produk yang stabil.
- LocalBusiness rich result: schema dasar tersedia, tetapi alamat utama tidak ditambahkan karena belum ada data pusat yang terverifikasi.
- Google Search Console: siap didaftarkan dan menerima sitemap setelah deploy.

## Checklist pascadeploy Google Search Console

1. Buka https://mulkanmimbaun.dekatlokal.com/ dan pastikan status homepage 200.
2. Pastikan HTTPS valid dan tidak ada mixed content.
3. Buka https://mulkanmimbaun.dekatlokal.com/robots.txt dan pastikan dapat diakses.
4. Buka https://mulkanmimbaun.dekatlokal.com/sitemap.xml dan pastikan dapat diakses.
5. Cek source HTML, bukan hanya DOM hasil render.
6. Pastikan title sesuai laporan ini.
7. Pastikan meta description sesuai laporan ini.
8. Pastikan canonical mengarah ke homepage production.
9. Pastikan robots meta berisi index/follow.
10. Pastikan Open Graph dan Twitter Card memakai URL production.
11. Pastikan `og:image` dan `twitter:image` mengembalikan status 200.
12. Pastikan JSON-LD tersedia pada source HTML.
13. Jalankan Rich Results Test untuk homepage dan periksa error Product/FAQ/Breadcrumb.
14. Buat atau gunakan Domain Property `dekatlokal.com` dan selesaikan verifikasi DNS.
15. Opsional: buat URL-prefix property `https://mulkanmimbaun.dekatlokal.com/`.
16. Submit `https://mulkanmimbaun.dekatlokal.com/sitemap.xml`.
17. Inspect URL homepage.
18. Jalankan Live Test.
19. Request Indexing jika Live Test valid.
20. Setelah data tersedia, bandingkan User-declared canonical dan Google-selected canonical.
21. Pantau Page Indexing dan perbaiki alasan exclusion yang nyata.
22. Pantau Enhancements untuk Product snippets, Merchant listings, FAQ, dan Breadcrumb.
23. Pantau Experience/Core Web Vitals setelah data lapangan tersedia.
24. Pantau Performance berdasarkan query, impressions, clicks, CTR, dan average position.
25. Pantau Links dan pastikan domain utama DekatLokal memberi internal backlink ke subdomain.
26. Gunakan anchor dari direktori Teman Lokal: `Mulkan Mimba'un - Oleh-Oleh Makanan dan Minuman Lokal Makassar`.
27. Evaluasi ulang title/description hanya setelah data query dan CTR cukup; jangan mengubahnya terlalu sering.

## Tindakan manual yang memerlukan akses eksternal

- Vercel/DNS: deploy perubahan dan pastikan custom domain tetap terhubung. Host aktif `web-mulkanmimbaun.vercel.app` sudah redirect permanen ke production; `mulkanmimbaun.vercel.app` saat audit mengembalikan 404 karena deployment/domain tidak ditemukan, sehingga perlu dihubungkan ke project hanya jika host itu memang akan digunakan.
- Search Console: verifikasi Domain Property melalui DNS, submit sitemap, jalankan Live Test, lalu request indexing.
- Google Business Profile: jika profil resmi tersedia, gunakan subdomain production sebagai website dan samakan NAP (Name, Address, Phone) dengan data bisnis terverifikasi.
- DekatLokal: tambahkan internal backlink dari direktori Teman Lokal dengan anchor deskriptif yang direkomendasikan.
- Shopee: konfirmasi bahwa URL produk masih aktif dan idealnya sediakan URL toko resmi yang stabil untuk identitas bisnis.
- Pemilik UMKM: konfirmasi alamat pusat, nomor utama, status sertifikasi terbaru, komposisi, masa simpan, ketersediaan stok, harga final per variasi, SKU/GTIN, kebijakan pengiriman, dan kebijakan pengembalian sebelum memperluas Merchant listings.

## Risiko yang masih terbuka

- Homepage, robots, sitemap, HTTPS, dan redirect HTTP production sudah aktif saat audit. Metadata, aset baru, structured data baru, dan header konfigurasi ini tetap harus diverifikasi ulang setelah deploy.
- Google tidak menjamin hero image, FAQ, Product snippet, atau Merchant listing akan tampil meskipun markup valid.
- Halaman katalog tunggal dengan banyak produk biasanya kurang kuat untuk rich result produk dibanding halaman detail unik per produk.
- Data harga saat ini hanya "mulai dari" sehingga schema menggunakan `AggregateOffer.lowPrice`, bukan harga final atau availability.
- Tidak ada alamat pusat terverifikasi; menambahkannya tanpa konfirmasi akan berisiko membuat data lokal tidak akurat.
- FAQ rich result dibatasi Google untuk jenis situs tertentu; schema tetap berguna untuk pemahaman mesin tetapi tidak menjamin tampilan FAQ di SERP.
