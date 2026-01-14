---
title: Fitur Ekstensi Markdown
published: 1970-01-01
updated: 2026-01-14
description: "Pelajari fitur Markdown di dalam Neko"
image: ""
tags: [Demonstrasi, Contoh, Markdown, Neko]
category: "Contoh Artikel"
draft: false
---

## Kartu Repositori GitHub

Anda dapat menambahkan kartu dinamis yang terhubung ke repositori GitHub. Saat halaman dimuat, informasi repositori akan diambil langsung dari GitHub API.

::github{repo="CuteLeaf/Firefly"}

Gunakan kode `::github{repo="CuteLeaf/Firefly"}` untuk membuat kartu repositori GitHub.

```markdown
::github{repo="CuteLeaf/Firefly"}

```

## Konfigurasi Kotak Peringatan (Admonitions)

Neko menggunakan plugin [rehype-callouts](https://github.com/lin-stephanie/rehype-callouts), yang mendukung tiga gaya tema kotak peringatan: `GitHub`, `Obsidian`, dan `VitePress`. Anda dapat mengonfigurasinya di dalam `src/config/siteConfig.ts`:

```typescript
// src/config/siteConfig.ts
export const siteConfig: SiteConfig = {
  // ...
  rehypeCallouts: {
    // Opsi: "github" | "obsidian" | "vitepress"
    theme: "github",
  },
  // ...
};

```

Catatan: **Perubahan konfigurasi memerlukan restart server pengembangan (dev server) agar dapat diterapkan.**

Berikut adalah daftar tipe yang didukung oleh masing-masing tema. Setiap gaya tema memiliki desain dan sintaks yang berbeda, Anda dapat memilih sesuai preferensi.

### 1. Gaya Tema GitHub

Ini adalah 5 tipe dasar yang didukung secara resmi oleh GitHub.

**Sintaks Dasar**

```markdown
> [!NOTE] NOTE
> Menonjolkan informasi yang harus dipertimbangkan pengguna.

> [!TIP] TIP
> Informasi opsional untuk membantu pengguna lebih berhasil.

> [!IMPORTANT] IMPORTANT
> Informasi krusial yang diperlukan agar pengguna berhasil.

> [!WARNING] WARNING
> Konten kritis yang memerlukan perhatian segera.

> [!CAUTION] CAUTION
> Konsekuensi negatif potensial dari suatu tindakan.

> [!NOTE] Judul Kustom
> Ini adalah contoh dengan judul kustom.

```

---

### 2. Gaya Tema Obsidian

Gaya [Obsidian](https://obsidian.md/) mendukung sangat banyak tipe dan alias.

<details>
<summary>Klik untuk membuka daftar sintaks Obsidian</summary>

```markdown
> [!NOTE] NOTE
> Blok catatan umum.

> [!ABSTRACT] ABSTRACT
> Abstrak dari artikel.

> [!SUMMARY] SUMMARY
> Ringkasan artikel (sama dengan Abstract).

> [!TLDR] TLDR
> Terlalu panjang, jangan dibaca (sama dengan Abstract).

> [!INFO] INFO
> Memberikan informasi tambahan.

> [!TODO] TODO
> Hal-hal yang perlu diselesaikan.

> [!TIP] TIP
> Kiat atau petunjuk praktis.

> [!HINT] HINT
> Petunjuk (sama dengan Tip).

> [!IMPORTANT] IMPORTANT
> Informasi penting (Gaya Obsidian biasanya menggunakan ikon serupa).

> [!SUCCESS] SUCCESS
> Operasi berhasil.

> [!CHECK] CHECK
> Pemeriksaan lulus (sama dengan Success).

> [!DONE] DONE
> Selesai (sama dengan Success).

> [!QUESTION] QUESTION
> Mengajukan pertanyaan.

> [!HELP] HELP
> Mencari bantuan (sama dengan Question).

> [!FAQ] FAQ
> Pertanyaan yang sering diajukan (sama dengan Question).

> [!WARNING] WARNING
> Informasi peringatan.

> [!CAUTION] CAUTION
> Hal yang perlu diperhatikan (sama dengan Warning).

> [!ATTENTION] ATTENTION
> Menarik perhatian (sama dengan Warning).

> [!FAILURE] FAILURE
> Operasi gagal.

> [!FAIL] FAIL
> Gagal (sama dengan Failure).

> [!MISSING] MISSING
> Konten hilang (sama dengan Failure).

> [!DANGER] DANGER
> Peringatan operasi berbahaya.

> [!ERROR] ERROR
> Informasi kesalahan (sama dengan Danger).

> [!BUG] BUG
> Melaporkan kutu (bug) perangkat lunak.

> [!EXAMPLE] EXAMPLE
> Menampilkan sebuah contoh.

> [!QUOTE] QUOTE
> Mengutip sebuah kalimat.

> [!CITE] CITE
> Sitasi (sama dengan Quote).

> [!NOTE] Judul Kustom
> Ini adalah contoh dengan judul kustom.

```

</details>

---

### 3. Gaya Tema VitePress

Gaya [VitePress](https://vitepress.dev/) menawarkan tampilan default yang modern dan datar (flat). Saat ini hanya mencakup **5 tipe** dasar yang konsisten dengan GitHub.

<details>
<summary>Klik untuk membuka daftar sintaks VitePress</summary>

```markdown
> [!NOTE] NOTE
> Setara dengan Note di GitHub.

> [!TIP] TIP
> Setara dengan Tip di GitHub.

> [!IMPORTANT] IMPORTANT
> Setara dengan Important di GitHub.

> [!WARNING] WARNING
> Setara dengan Warning di GitHub.

> [!CAUTION] CAUTION
> Setara dengan Caution di GitHub.

> [!TIP] Judul Kustom
> Gaya VitePress juga mendukung judul kustom.

```

</details>

---

### 4. Sintaks Gaya Docusaurus

Hanya mendukung sintaksnya saja, gaya tampilan tetap mengikuti salah satu dari tiga tema di atas.

<details>
<summary>Klik untuk membuka daftar sintaks Docusaurus</summary>

Mendukung tipe kotak peringatan berikut: `note` `tip` `important` `warning` `caution`

```markdown
:::note
Menonjolkan informasi yang harus dipertimbangkan pengguna, bahkan saat memindai cepat.
:::

:::tip
Informasi opsional untuk membantu pengguna lebih berhasil.
:::

:::important
Informasi krusial yang diperlukan agar pengguna berhasil.
:::

:::warning
Konten kritis yang memerlukan perhatian segera karena risiko potensial.
:::

:::caution
Konsekuensi negatif potensial dari suatu tindakan.
:::

:::tip[Judul Kustom]
Informasi opsional untuk membantu pengguna lebih berhasil.
:::

```

</details>

---

## Spoiler

Anda dapat menambahkan fitur spoiler pada teks. Teks di dalamnya juga mendukung sintaks **Markdown**.

Konten :spoiler[telah disembunyikan **haha**]!

```markdown
Konten :spoiler[telah disembunyikan **haha**]!

```
