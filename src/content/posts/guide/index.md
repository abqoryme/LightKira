---
title: Panduan Penggunaan Sederhana Neko
published: 1970-01-02
pinned: true
description: "Cara menggunakan template blog Neko."
image: "./cover.webp"
tags: ["Neko", "Blog", "Markdown", "Panduan Penggunaan"]
category: Panduan Blog
draft: false
---

Template blog ini dibangun berdasarkan [Astro](https://astro.build/). Untuk hal-hal yang tidak disebutkan dalam panduan ini, Anda dapat menemukan jawabannya di [Dokumentasi Astro](https://docs.astro.build/).

## Front-matter Artikel

```yaml
---
title: Artikel Blog Pertama Saya
published: 2023-09-09
description: Ini adalah artikel pertama di blog Astro baru saya.
image: ./cover.jpg
tags: [Frontend, Pengembangan]
category: Pengembangan Frontend
draft: false
---

```

| Properti | Deskripsi |
| --- | --- |
| `title` | Judul artikel. |
| `published` | Tanggal publikasi artikel. |
| `updated` | Tanggal pembaruan artikel. Jika tidak diatur, akan menggunakan tanggal publikasi secara default. |
| `pinned` | Apakah artikel ini akan disematkan (pin) di bagian atas daftar artikel. |
| `description` | Deskripsi singkat artikel. Ditampilkan di halaman beranda. |
| `image` | Jalur gambar sampul artikel.<br>

<br>1. Diawali `http://` atau `https://`: Menggunakan gambar daring<br>

<br>2. Diawali `/`: Gambar di dalam direktori `public`<br>

<br>3. Tanpa awalan: Jalur relatif terhadap file markdown |
| `tags` | Tag artikel. |
| `category` | Kategori artikel. |
| `lang` | Kode bahasa artikel (misalnya `zh-CN`). Hanya diatur jika bahasa artikel berbeda dari bahasa default situs. |
| `licenseName` | Nama lisensi konten artikel. |
| `licenseUrl` | Tautan lisensi konten artikel. |
| `author` | Penulis artikel. |
| `sourceLink` | Tautan sumber atau referensi konten artikel. |
| `draft` | Jika artikel ini masih berupa draf, maka tidak akan ditampilkan. |
| `comment` | Apakah fitur komentar diaktifkan untuk artikel ini. Default adalah `true`. |
| `slug` | Jalur URL artikel kustom. Jika tidak diatur, nama file akan digunakan sebagai URL. |

## Lokasi Penempatan File Artikel

File artikel Anda harus diletakkan di dalam direktori `src/content/posts/`. Anda juga dapat membuat subdirektori untuk mengelola artikel dan aset Anda dengan lebih baik.

```
src/content/posts/
├── post-1.md
└── post-2/
    ├── cover.png
    └── index.md

```

## URL Artikel Kustom (Slug)

### Apa itu Slug?

Slug adalah bagian kustom dari jalur URL artikel. Jika slug tidak diatur, sistem akan menggunakan nama file sebagai URL.

### Contoh Penggunaan Slug

#### Contoh 1: Menggunakan nama file sebagai URL

```yaml
---
title: Artikel Blog Pertama Saya
published: 2023-09-09
---

```

File: `src/content/posts/artikel-blog-pertama-saya.md`

URL: `/posts/artikel-blog-pertama-saya`

#### Contoh 2: Kustom Slug

```yaml
---
title: Artikel Blog Pertama Saya
published: 2023-09-09
slug: halo-dunia
---

```

File: `src/content/posts/artikel-blog-pertama-saya.md`

URL: `/posts/halo-dunia`

#### Contoh 3: Menggunakan Slug untuk nama file bahasa lain

```yaml
---
title: Cara Menggunakan Tema Blog Neko
published: 2023-09-09
slug: cara-menggunakan-tema-blog-neko
---

```

File: `src/content/posts/如何使用Neko博客主题.md`

URL: `/posts/cara-menggunakan-tema-blog-neko`

### Saran Penggunaan Slug

1. **Gunakan bahasa Inggris dan tanda hubung**: `my-awesome-post` alih-alih `my awesome post`
2. **Tetap ringkas**: Hindari slug yang terlalu panjang
3. **Deskriptif**: Biarkan URL mencerminkan isi artikel
4. **Hindari karakter khusus**: Hanya gunakan huruf, angka, dan tanda hubung
5. **Konsistensi**: Gunakan pola penamaan yang serupa di seluruh blog

### Catatan

* Setelah slug diatur dan dipublikasikan, disarankan untuk tidak mengubahnya sembarangan agar tidak memengaruhi SEO dan tautan yang sudah ada.
* Jika beberapa artikel menggunakan slug yang sama, artikel yang lebih baru akan menimpa yang sebelumnya.
* Slug akan secara otomatis dikonversi menjadi huruf kecil.
