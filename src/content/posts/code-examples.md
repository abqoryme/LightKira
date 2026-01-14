---
title: Contoh Blok Kode Neko
published: 1970-01-03
pinned: false
description: Tampilan blok kode menggunakan Expressive Code di Markdown dalam Neko.
tags: [Markdown, Neko]
category: Contoh Artikel
draft: false
image: ./images/firefly3.webp
---

Di sini, kita akan mengeksplorasi cara menggunakan [Expressive Code](https://expressive-code.com/) untuk menampilkan blok kode. Contoh yang disediakan didasarkan pada dokumentasi resmi, Anda dapat merujuk ke sana untuk detail lebih lanjut.

## Expressive Code

### Syntax Highlighting

[Syntax Highlighting](https://expressive-code.com/key-features/syntax-highlighting/)

#### Syntax Highlighting Reguler

```js
console.log('Kode ini memiliki syntax highlighting!')

```

#### Render ANSI Escape Sequences

```ansi
ANSI colors:
- Regular: [31mRed[0m [32mGreen[0m [33mYellow[0m [34mBlue[0m [35mMagenta[0m [36mCyan[0m
- Bold:    [1;31mRed[0m [1;32mGreen[0m [1;33mYellow[0m [1;34mBlue[0m [1;35mMagenta[0m [1;36mCyan[0m
- Dimmed:  [2;31mRed[0m [2;32mGreen[0m [2;33mYellow[0m [2;34mBlue[0m [2;35mMagenta[0m [2;36mCyan[0m

256 colors (showing colors 160-177):
[38;5;160m160 [38;5;161m161 [38;5;162m162 [38;5;163m163 [38;5;164m164 [38;5;165m165[0m
[38;5;166m166 [38;5;167m167 [38;5;168m168 [38;5;169m169 [38;5;170m170 [38;5;171m171[0m
[38;5;172m172 [38;5;173m173 [38;5;174m174 [38;5;175m175 [38;5;176m176 [38;5;177m177[0m

Full RGB colors:
[38;2;34;139;34mForestGreen - RGB(34, 139, 34)[0m

Text formatting: [1mBold[0m [2mDimmed[0m [3mItalic[0m [4mUnderline[0m

```

### Editor dan Terminal Frames

[Editor dan Terminal Frames](https://expressive-code.com/key-features/frames/)

#### Frame Editor Kode

```js title="my-test-file.js"
console.log('Contoh atribut judul')

```

---

```html
<div>Contoh komentar nama file</div>

```

#### Frame Terminal

```bash
echo "Frame terminal ini tidak memiliki judul"

```

---

```powershell title="Contoh Terminal PowerShell"
Write-Output "Yang ini punya judul!"

```

#### Mengganti Tipe Frame (Override)

```sh frame="none"
echo "Lihat, tanpa frame!"

```

---

```ps frame="code" title="PowerShell Profile.ps1"
# Jika tidak di-override, ini akan menjadi frame terminal
function Watch-Tail { Get-Content -Tail 20 -Wait $args }
New-Alias tail Watch-Tail

```

### Penanda Teks dan Baris

[Penanda Teks dan Baris](https://expressive-code.com/key-features/text-markers/)

#### Menandai Seluruh Baris dan Rentang Baris

```js {1, 4, 7-8}
// Baris 1 - Ditandai lewat nomor baris
// Baris 2
// Baris 3
// Baris 4 - Ditandai lewat nomor baris
// Baris 5
// Baris 6
// Baris 7 - Ditandai lewat rentang "7-8"
// Baris 8 - Ditandai lewat rentang "7-8"

```

#### Memilih Tipe Penanda Baris (mark, ins, del)

```js title="line-markers.js" del={2} ins={3-4} {6}
function demo() {
  console.log('Baris ini ditandai sebagai dihapus')
  // Baris ini dan baris berikutnya ditandai sebagai disisipkan
  console.log('Ini adalah baris sisipan kedua')

  return 'Baris ini menggunakan tipe penanda default netral'
}

```

#### Menambahkan Label pada Penanda Baris

```jsx {"1":5} del={"2":7-8} ins={"3":10-12}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}
  value={value}
  className={buttonClassName}
  disabled={disabled}
  active={active}
>
  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>

```

#### Menambahkan Label Panjang pada Baris Terpisah

```jsx {"1. Berikan prop value di sini:":5-6} del={"2. Hapus state disabled dan active:":8-10} ins={"3. Tambahkan ini untuk me-render children di dalam button:":12-15}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}

  value={value}
  className={buttonClassName}

  disabled={disabled}
  active={active}
>

  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>

```

#### Menggunakan Sintaks Mirip Diff

```diff
+Baris ini akan ditandai sebagai disisipkan
-Baris ini akan ditandai sebagai dihapus
Ini adalah baris reguler

```

---

```diff
--- a/README.md
+++ b/README.md
@@ -1,3 +1,4 @@
+ini adalah file diff yang sebenarnya
-semua konten akan tetap tidak dimodifikasi
 tidak ada spasi putih yang akan dihapus juga

```

#### Menggabungkan Syntax Highlighting dan Sintaks Mirip Diff

```diff lang="js"
  function iniAdalahJavaScript() {
    // Seluruh blok akan di-highlight sebagai JavaScript,
    // dan kita masih bisa menambahkan penanda diff di dalamnya!
-   console.log('Kode lama yang akan dihapus')
+   console.log('Kode baru yang berkilau!')
  }

```

#### Menandai Teks Tertentu dalam Baris

```js "teks tertentu"
function demo() {
  // Menandai teks tertentu di dalam baris
  return 'Mendukung beberapa kecocokan untuk teks tertentu';
}

```

#### Regular Expressions (Regex)

```ts /ye[sp]/
console.log('Kata yes dan yep akan ditandai.')

```

#### Meng-escape Garis Miring (Slash)

```sh //ho.*//
echo "Test" > /home/test.txt

```

#### Memilih Tipe Penanda Inline (mark, ins, del)

```js "return true;" ins="inserted" del="deleted"
function demo() {
  console.log('Ini adalah tipe penanda disisipkan (inserted) dan dihapus (deleted)');
  // statement return menggunakan tipe penanda default
  return true;
}

```

### Auto Wrap (Pembungkusan Kata)

[Auto Wrap](https://expressive-code.com/key-features/word-wrap/)

#### Mengonfigurasi Auto Wrap per Blok

```js wrap
// Contoh mengaktifkan pembungkusan kata (wrap)
function getLongString() {
  return 'Ini adalah string yang sangat panjang yang kemungkinan besar tidak akan muat di ruang yang tersedia kecuali kontainernya sangat lebar'
}

```

---

```js wrap=false
// Contoh wrap=false
function getLongString() {
  return 'Ini adalah string yang sangat panjang yang kemungkinan besar tidak akan muat di ruang yang tersedia kecuali kontainernya sangat lebar'
}

```

#### Mengonfigurasi Indentasi pada Wrap

```js wrap preserveIndent
// Contoh preserveIndent (diaktifkan secara default)
function getLongString() {
  return 'Ini adalah string yang sangat panjang yang kemungkinan besar tidak akan muat di ruang yang tersedia kecuali kontainernya sangat lebar'
}

```

---

```js wrap preserveIndent=false
// Contoh preserveIndent=false
function getLongString() {
  return 'Ini adalah string yang sangat panjang yang kemungkinan besar tidak akan muat di ruang yang tersedia kecuali kontainernya sangat lebar'
}

```

## Bagian yang Dapat Dilipat (Collapsible Sections)

[Collapsible Sections](https://expressive-code.com/plugins/collapsible-sections/)

```js collapse={1-5, 12-14, 21-24}
// Semua kode pengaturan boilerplate ini akan dilipat
import { someBoilerplateEngine } from '@example/some-boilerplate'
import { evenMoreBoilerplate } from '@example/even-more-boilerplate'

const engine = someBoilerplateEngine(evenMoreBoilerplate())

// Bagian kode ini terlihat secara default
engine.doSomething(1, 2, 3, calcFn)

function calcFn() {
  // Anda dapat memiliki beberapa bagian yang dilipat
  const a = 1
  const b = 2
  const c = a + b

  // Ini akan tetap terlihat
  console.log(`Hasil perhitungan: ${a} + ${b} = ${c}`)
  return c
}

// Semua kode hingga akhir blok akan dilipat kembali
engine.closeConnection()
engine.freeMemory()
engine.shutdown({ reason: 'Akhir dari contoh kode boilerplate' })

```

## Nomor Baris

[Nomor Baris](https://expressive-code.com/plugins/line-numbers/)

### Menampilkan Nomor Baris per Blok

```js showLineNumbers
// Blok kode ini akan menampilkan nomor baris
console.log('Salam dari baris ke-2!')
console.log('Saya ada di baris ke-3')

```

---

```js showLineNumbers=false
// Blok ini menonaktifkan nomor baris
console.log('Halo?')
console.log('Maaf, apakah Anda tahu saya di baris mana?')

```

### Mengubah Nomor Baris Awal

```js showLineNumbers startLineNumber=5
console.log('Salam dari baris ke-5!')
console.log('Saya ada di baris ke-6')

```
