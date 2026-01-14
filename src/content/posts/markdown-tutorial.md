---
title: Panduan Markdown
published: 1970-01-01
pinned: false
description: Sebuah contoh artikel blog Markdown yang ringkas dan jelas.
tags: [Contoh Artikel]
category: Contoh Artikel
licenseName: "Unlicensed"
author: emn178
sourceLink: "https://github.com/emn178/markdown"
draft: false
---

Ini adalah contoh yang menunjukkan cara menulis file Markdown. Dokumen ini merangkum sintaks inti dan ekstensi umum (GFM).

- [Elemen Blok](#block-elements)
    - [Paragraf dan Baris Baru](#paragraphs-and-line-breaks)
    - [Judul (Header)](#headers)
    - [Kutipan (Blockquotes)](#blockquotes)
    - [Daftar (Lists)](#lists)
    - [Blok Kode](#code-blocks)
    - [Garis Pemisah](#horizontal-rules)
    - [Tabel](#table)
- [Elemen Inline](#span-elements)
    - [Tautan (Links)](#links)
    - [Penekanan (Emphasis)](#emphasis)
    - [Kode Inline](#code)
    - [Gambar](#images)
    - [Coretan (Strikethrough)](#strikethrough)
- [Lain-lain](#miscellaneous)
    - [Tautan Otomatis](#automatic-links)
    - [Garis Miring Terbalik (Backslash Escapes)](#backslash-escapes)
- [HTML Inline](#inline-html)

<a id="block-elements"></a>
## Elemen Blok

<a id="paragraphs-and-line-breaks"></a>
### Paragraf dan Baris Baru

#### Paragraf

Tag HTML: `<p>`

Gunakan satu atau lebih baris kosong untuk memisahkan paragraf. (Baris yang hanya berisi **spasi** atau **tab** juga dianggap sebagai baris kosong.)

Kode:
    Ini akan menjadi
    satu baris.

    Ini adalah paragraf kedua.

Pratinjau:
---
Ini akan menjadi
satu baris.

Ini adalah paragraf kedua.
---

#### Baris Baru

Tag HTML: `<br />`

Tambahkan **dua atau lebih spasi** di akhir baris untuk menghasilkan baris baru (line break).

Kode:
    Ini tidak akan menjadi
    satu baris.

Pratinjau:
---
Ini tidak akan menjadi  
satu baris.
---

<a id="headers"></a>
### Judul (Header)

Markdown mendukung dua gaya judul: Setext dan atx.

#### Setext

Tag HTML: `<h1>`, `<h2>`

Gunakan **tanda sama dengan (=)** untuk `<h1>` dan **tanda hubung (-)** untuk `<h2>`. Jumlah tanda tidak ditentukan, berfungsi sebagai "garis bawah".

Kode:
    Ini adalah H1
    =============
    Ini adalah H2
    -------------

Pratinjau:
---
# Ini adalah H1

## Ini adalah H2
---

#### atx

Tag HTML: `<h1>` hingga `<h6>`

Gunakan 1-6 **tanda pagar (#)** di awal baris, sesuai dengan tingkatan `<h1>` hingga `<h6>`.

Kode:
    # Ini adalah H1
    ## Ini adalah H2
    ###### Ini adalah H6

Pratinjau:
---
# Ini adalah H1

## Ini adalah H2

###### Ini adalah H6
---

<a id="blockquotes"></a>
### Kutipan (Blockquotes)

Tag HTML: `<blockquote>`

Markdown menggunakan simbol **>** gaya email untuk kutipan.

Kode:
    > Ini adalah kutipan dengan dua paragraf. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    >
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit.

Pratinjau:
---
> Ini adalah kutipan dengan dua paragraf. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
---



<a id="lists"></a>
### Daftar (Lists)

#### Daftar Tidak Teratur (Unordered)

Tag HTML: `<ul>`

Gunakan **asterisk (*)**, **tanda tambah (+)**, atau **tanda hubung (-)**.

Kode:
    * Merah
    * Hijau
    * Biru

Pratinjau:
---
- Merah
- Hijau
- Biru
---

#### Daftar Teratur (Ordered)

Tag HTML: `<ol>`

Gunakan angka diikuti titik:

Kode:
    1.  Burung
    2.  Kucing
    3.  Ikan

Pratinjau:
---
1.  Burung
2.  Kucing
3.  Ikan
---

<a id="code-blocks"></a>
### Blok Kode

Tag HTML: `<pre>`

Indentasi setiap baris dengan setidaknya **4 spasi** atau **1 tab**.

Kode:
        Ini adalah blok kode.

Pratinjau:
---
    Ini adalah blok kode.
---

#### Fenced Code Blocks (Blok Kode Berpagar)

Gunakan tiga backtick (```).

Kode:
    ```javascript
    function hello() {
      console.log("Halo Neko!");
    }
    ```

Pratinjau:
---
```javascript
function hello() {
  console.log("Halo Neko!");
}

```

---

<a id="table"></a>

### Tabel

Tag HTML: `<table>`

Gunakan **garis vertikal (|)** untuk memisahkan kolom dan **tanda hubung (-)** untuk header. Gunakan **titik dua (:)** untuk perataan.

Kode:
| Kiri | Tengah | Kanan |
|:-----|:------:|------:|
| Lembar 1 | Data A | 100 |
| Lembar 2 | Data B | 200 |

## Pratinjau:

## | Kiri | Tengah | Kanan | | :--- | :----: | ----: | | Lembar 1 | Data A | 100 | | Lembar 2 | Data B | 200 |

<a id="span-elements"></a>

## Elemen Inline

<a id="links"></a>

### Tautan (Links)

Format: `[Teks](URL "Judul Opsional")`

Kode:
Ini adalah [contoh tautan](http://example.com/).

## Pratinjau:

## Ini adalah [contoh tautan](http://example.com/).

<a id="emphasis"></a>

### Penekanan (Emphasis)

Gunakan **satu** simbol untuk miring (*italic*) dan **dua** simbol untuk tebal (**bold**).

Kode:
*miring* dan **tebal**

## Pratinjau:

## *miring* dan **tebal**

<a id="images"></a>

### Gambar

Format: `![Teks Alamat](URL "Judul")`

Kode:

## Pratinjau:

<a id="strikethrough"></a>

### Coretan (Strikethrough)

Gunakan dua tilde (~~).

Kode:
~~Teks yang salah.~~

## Pratinjau:

## ~~Teks yang salah.~~

<a id="miscellaneous"></a>

## Lain-lain

<a id="backslash-escapes"></a>

### Garis Miring Terbalik (Backslash Escapes)

Gunakan `\` untuk menampilkan karakter yang biasanya digunakan sebagai sintaks Markdown.

Kode:
*bukan miring*

## Pratinjau:

## *bukan miring*

<a id="inline-html"></a>

## HTML Inline

Anda dapat menggunakan tag HTML langsung jika diperlukan.

Kode:
<u>Teks bergaris bawah</u>

## Pratinjau:

## <u>Teks bergaris bawah</u>

```
