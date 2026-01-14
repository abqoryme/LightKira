---
title: Penjelasan Detail Sistem Tata Letak Neko
published: 1970-01-03
description: Pelajari lebih dalam tentang sistem tata letak Neko, termasuk tata letak sidebar (kiri/ganda) dan tata letak daftar artikel (list/grid), serta mode grid tiga kolom yang baru.
image: ./images/firefly1.webp
tags: [Neko, Tata Letak, Blog, Panduan Penggunaan]
category: Panduan Blog
draft: false
---

## 📖 Ringkasan

Neko menyediakan sistem tata letak yang fleksibel, memungkinkan Anda menyesuaikan presentasi visual blog berdasarkan kebutuhan konten dan preferensi pribadi. Sistem tata letak ini terutama terdiri dari dua dimensi: **Tata Letak Sidebar** dan **Tata Letak Daftar Artikel**, yang bekerja sama untuk menentukan struktur keseluruhan halaman.

Artikel ini akan menjelaskan berbagai mode tata letak Neko, karakteristiknya, skenario penggunaan, serta efek dari berbagai kombinasi tata letak.

---

## I. Sistem Tata Letak Sidebar

Sidebar adalah komponen penting dari halaman blog, digunakan untuk menampilkan navigasi, kategori, tag, statistik, dan konten tambahan lainnya. Neko mendukung dua mode tata letak sidebar.

### 1.1 Mode Sidebar Kiri (position: "left")

#### Karakteristik

- Sidebar terpaku di sisi kiri halaman.
- Area konten utama berada di sisi kanan.
- Sesuai dengan kebiasaan membaca dari kiri ke kanan.
- Cocok untuk menampilkan informasi penting seperti navigasi dan kategori.

#### Struktur Tata Letak

![Tata Letak Sidebar Kiri](./images/left-list.webp)



#### Skenario Penggunaan

- Gaya blog tradisional.
- Blog yang menekankan pada navigasi dan kategori.
- Blog pribadi yang perlu menonjolkan profil pengguna.
- Skenario di mana konten adalah fokus utama dan informasi tambahan adalah pelengkap.

:::tip
Setelah mengaktifkan sidebar tunggal di sisi kiri, navigasi daftar isi artikel (TOC) yang biasanya ada di sidebar kanan pada halaman detail artikel akan menjadi tidak aktif.

Sebagai gantinya, navigasi daftar isi akan menggunakan mode melayang (floating) yang perlu diklik secara manual untuk muncul.

Namun, Anda dapat mengatur apakah sidebar kanan tetap muncul di halaman detail artikel melalui konfigurasi `showRightSidebarOnPostPage`.

Jika `position` diatur ke `left` dan opsi ini diaktifkan, halaman detail artikel akan menampilkan sidebar ganda (kiri & kanan), sementara halaman beranda dan lainnya tetap menggunakan sidebar tunggal kiri.

Skenario ini cocok bagi Anda yang hanya ingin menggunakan sidebar kiri secara umum, tetapi ingin tetap menggunakan komponen seperti daftar isi di sidebar kanan pada halaman artikel.
:::

#### Contoh Konfigurasi

```typescript
// src/config/sidebarConfig.ts
export const sidebarLayoutConfig: SidebarLayoutConfig = {
  enable: true,
  position: "left", // Sidebar kiri
  showRightSidebarOnPostPage: true, // Apakah menampilkan sidebar kanan di halaman artikel
};

```

---

### 1.2 Mode Sidebar Ganda (position: "both")

#### Karakteristik

* Sidebar ada di sisi kiri dan kanan secara bersamaan.
* Area konten utama berada di tengah.
* Memaksimalkan penggunaan ruang layar.
* Dapat menampilkan lebih banyak informasi tambahan.
* Cocok untuk monitor layar lebar (widescreen).

#### Struktur Tata Letak

#### Skenario Penggunaan

* Penjelajahan di perangkat desktop layar lebar.
* Blog dengan kepadatan informasi yang tinggi.
* Perlu menampilkan banyak konten pendukung.
* Blog teknis yang bersifat profesional.

#### Contoh Konfigurasi

```typescript
// src/config/sidebarConfig.ts
export const sidebarLayoutConfig: SidebarLayoutConfig = {
  enable: true,
  position: "both", // Sidebar ganda

```

---

## II. Sistem Tata Letak Daftar Artikel

Daftar artikel adalah inti dari halaman beranda dan arsip blog. Neko menyediakan dua cara penyajian dan mendukung berbagai konfigurasi grid.

### 2.1 Mode Daftar / List (defaultMode: "list")

#### Karakteristik

* Tersusun vertikal dalam satu kolom.
* Menampilkan gambar sampul artikel.
* Menampilkan lebih banyak ringkasan artikel.
* Cocok untuk pengalaman membaca yang mendalam.

#### Struktur Tata Letak List

#### Kelebihan

* ✅ Dampak visual yang kuat, gambar sampul menarik perhatian.
* ✅ Dapat menampilkan lebih banyak informasi artikel (ringkasan, tag, dll).
* ✅ Cocok untuk blog dengan konten gambar yang kaya.
* ✅ Ramah perangkat seluler, satu kolom lebih mudah dibaca.
* ✅ Kompatibel dengan semua konfigurasi sidebar (tunggal maupun ganda).

#### Contoh Konfigurasi

```typescript
// src/config/siteConfig.ts
export const siteConfig: SiteConfig = {
  postListLayout: {
    defaultMode: "list", // Mode daftar
    allowSwitch: true,   // Mengizinkan pengguna berpindah mode
  },
};

```

---

### 2.2 Mode Grid (defaultMode: "grid")

#### Karakteristik

* Tersusun horizontal dalam beberapa kolom (mendukung 2 atau 3 kolom).
* Tata letak ringkas, kepadatan informasi tinggi.
* Cocok untuk penjelajahan cepat.

#### 2.2.1 Grid Dua Kolom (Columns: 2)

Ini adalah konfigurasi default untuk mode grid, cocok untuk sebagian besar skenario.

#### 2.2.2 Grid Tiga Kolom (Columns: 3) ✨ Baru

Pada perangkat layar lebar, Anda dapat mengaktifkan mode grid tiga kolom untuk meningkatkan kepadatan informasi lebih lanjut.

**⚠️ Perhatian**: Mode grid tiga kolom hanya berfungsi pada **Mode Sidebar Kiri** (atau tanpa sidebar). Jika Anda mengaktifkan sidebar ganda, sistem akan otomatis kembali ke grid dua kolom untuk memastikan kartu artikel memiliki lebar tampilan yang cukup.

#### Contoh Konfigurasi

```typescript
// src/config/siteConfig.ts
export const siteConfig: SiteConfig = {
  postListLayout: {
    defaultMode: "grid",
    allowSwitch: true,
    grid: {
      masonry: true,  // Mengaktifkan efek masonry (air terjun)
      columns: 3,      // Diatur ke mode 3 kolom (hanya berlaku pada sidebar tunggal)
    },
  },
};

```

---

### 2.3 Tata Letak Masonry (Air Terjun)

Mode grid Neko dilengkapi dengan dukungan tata letak masonry cerdas, yang memecahkan masalah ruang kosong akibat perbedaan tinggi kartu pada artikel yang mencampur teks dan gambar.

[Image showing a masonry or waterfall layout where items of different heights are packed tightly together]

* **Tipografi Cerdas**: Menggunakan distribusi pola-Z (bergantian kiri-kanan), menjaga urutan kronologis artikel dengan ketat.
* **Menghilangkan Ruang Kosong**: Menghitung posisi setiap kartu secara presisi melalui pemosisian absolut, sehingga kartu menempel rapat pada kartu di baris atasnya.
* **Konfigurasi Fleksibel**: Anda dapat mengaktifkan atau menonaktifkan fitur ini melalui opsi `postListLayout.grid.masonry` di `siteConfig.ts`.

---

## III. Panduan Kombinasi Tata Letak

Neko memungkinkan Anda mengombinasikan sidebar dan tata letak daftar artikel secara bebas. Berikut adalah penjelasan efek dari berbagai kombinasi tersebut.

### 3.1 Sidebar Kiri + Mode Grid

Ini adalah kombinasi yang paling fleksibel. Anda dapat memilih grid 2 kolom atau 3 kolom.

* **Mode 2 Kolom**: Tata letak grid klasik, lebar kartu pas, nyaman dibaca.
* **Mode 3 Kolom**: Cocok untuk layar lebar (≥1024px), menampilkan lebih banyak konten dalam satu layar, memberikan efek visual yang luar biasa.

### 3.2 Sidebar Ganda + Mode Grid

Pada versi lama, kombinasi ini dinonaktifkan. Namun pada versi terbaru Neko, kami telah melepaskan batasan ini, memungkinkan sidebar ganda hidup berdampingan dengan mode grid.

**Karakteristik & Batasan**:

* **Paksa Dua Kolom**: Meskipun Anda mengonfigurasi `columns: 3`, dalam mode ini akan dipaksa menjadi 2 kolom.
* **Ruang Ringkas**: Karena ada sidebar di kiri dan kanan, area konten utama di tengah menjadi relatif lebih sempit.
* **Kepadatan Informasi Sangat Tinggi**: Ini adalah tata letak dengan kepadatan informasi tertinggi, cocok untuk situs yang perlu menampilkan banyak informasi navigasi sekaligus daftar artikel.

### 3.3 Saran Pemilihan Tata Letak

| Mode Sidebar | Mode Daftar Artikel | Rekomendasi | Skenario Penggunaan |
| --- | --- | --- | --- |
| Sidebar Kiri | Mode List | ⭐⭐⭐⭐⭐ | Blog fotografi, desain, gaya hidup; menekankan gambar dan imersi |
| Sidebar Kiri | Grid 2 Kolom | ⭐⭐⭐⭐⭐ | Blog teknis, catatan; keseimbangan antara membaca dan efisiensi pencarian |
| Sidebar Kiri | Grid 3 Kolom | ⭐⭐⭐⭐⭐ | Situs dengan volume konten besar, pengalaman layar lebar yang luar biasa |
| Sidebar Ganda | Mode List | ⭐⭐⭐⭐⭐ | Situs yang perlu menampilkan banyak informasi di sidebar |
| Sidebar Ganda | Grid 2 Kolom | ⭐⭐⭐⭐⭐ | Gaya geek, mengejar kepadatan informasi tertinggi |

---

## IV. Perilaku Tata Letak Responsif

Sistem tata letak Neko memiliki desain responsif cerdas yang akan menyesuaikan secara otomatis berdasarkan ukuran layar.

### 4.1 Aturan Penurunan (Downgrade) Cerdas

Untuk memastikan pengalaman membaca terbaik, sistem akan menyesuaikan tata letak secara otomatis saat layar menyempit:

1. **Grid 3 Kolom -> Grid 2 Kolom**: Ketika lebar layar tidak cukup untuk 3 kolom (atau saat mengaktifkan sidebar ganda), otomatis turun menjadi mode daftar tunggal.
2. **Mode Grid -> Mode List**: Ketika lebar layar kurang dari 1200px (tablet dan ponsel), mode grid akan otomatis beralih ke mode daftar satu kolom untuk menjaga keterbacaan konten kartu.
3. **Sidebar Ganda -> Sidebar Kiri**: Ketika lebar layar kurang dari 1200px, sidebar kanan akan otomatis disembunyikan, dan navigasi daftar isi artikel akan beralih menjadi navigasi melayang.

---

## V. Pertanyaan Umum (FAQ)

### Q1: Mengapa saya sudah mengatur grid 3 kolom, tetapi hanya muncul 2 kolom?

**A**: Harap periksa hal berikut:

1. Apakah Anda mengaktifkan sidebar ganda (`position: "both"`)? Dalam mode sidebar ganda, grid dipaksa menjadi 2 kolom.
2. Apakah lebar layar cukup? Mode 3 kolom biasanya memerlukan lebar layar ≥1024px.

### Q2: Mengapa efek grid tidak terlihat di ponsel?

**A**: Untuk menjaga pengalaman membaca, Neko akan memaksa peralihan ke mode list saat lebar layar di bawah 1200px. Layar ponsel terlalu sempit untuk menampilkan grid multikolom.

### Q3: Di mana tombol pengalih tata letak berada?

**A**: Tombol pengalih tata letak berada di sisi kanan bilah navigasi (navbar). Tombol ini hanya muncul pada lebar layar ≥ 1200px, karena pada layar kecil sistem memaksa penggunaan mode list sehingga tidak perlu pengalihan.

---

## VI. Kesimpulan

Sistem tata letak versi baru Neko memberikan Anda kebebasan yang lebih besar. Baik itu mengejar dampak visual **Grid Tiga Kolom**, maupun mengejar kepadatan informasi **Grid Sidebar Ganda**, semuanya dapat Anda wujudkan melalui konfigurasi sederhana.

Kami menyarankan Anda mencoba berbagai kombinasi untuk menemukan bentuk blog yang paling sesuai dengan jenis konten dan preferensi perangkat pembaca target Anda.

---
