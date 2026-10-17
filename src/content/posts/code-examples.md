---
title: Contoh Blok Kode
published: 1970-01-03
pinned: false
description: Tampilan blok kode yang menggunakan kode ekspresif di Markdown.
tags: [Markdown]
category: examples
image: ./images/firefly3.avif
slug: code-examples
series: "Contoh Fungsi 2"
seriesOrder: 5
---

Di sini, kita akan membahas cara menggunakan [Expressive Code](https://expressive-code.com/) untuk menampilkan blok kode. Contoh yang disajikan didasarkan pada dokumentasi resmi. Anda dapat merujuknya untuk informasi lebih lanjut.

## Kode Ekspresif

### Penyorotan Sintaks

[Penyorotan Sintaks](https://expressive-code.com/key-features/syntax-highlighting/)

#### Penyorotan Sintaks Umum

```js
console.log('Kode ini memiliki penyorotan sintaks!')
```

#### Merender Urutan Escape ANSI


```ansi
[1;4mWarna ANSI standar:[0m
- Warna redup:     [2;30m Hitam [2;31m Merah [2;32m Hijau [2;33m Kuning [2;34m Biru [2;35m Magenta [2;36m Sian [2;37m Putih [0m
- Warna teks:      [30m Hitam [31m Merah [32m Hijau [33m Kuning [34m Biru [35m Magenta [36m Sian [37m Putih [0m
- Warna latar:     [40m Hitam [41m Merah [42m Hijau [43m Kuning [44m Biru [45m Magenta [46m Sian [47m Putih [0m
- Warna terbalik:  [7;30m Hitam [7;31m Merah [7;32m Hijau [7;33m Kuning [7;34m Biru [7;35m Magenta [7;36m Sian [7;37m Putih [0m

[1;4mWarna 8-bit (contoh warna 160–171):[0m
- Warna redup:     [2;38;5;160m 160 [2;38;5;161m 161 [2;38;5;162m 162 [2;38;5;163m 163 [2;38;5;164m 164 [2;38;5;165m 165 [2;38;5;166m 166 [2;38;5;167m 167 [2;38;5;168m 168 [2;38;5;169m 169 [2;38;5;170m 170 [2;38;5;171m 171 [0m
- Warna teks:      [38;5;160m 160 [38;5;161m 161 [38;5;162m 162 [38;5;163m 163 [38;5;164m 164 [38;5;165m 165 [38;5;166m 166 [38;5;167m 167 [38;5;168m 168 [38;5;169m 169 [38;5;170m 170 [38;5;171m 171 [0m
- Warna latar:     [48;5;160m 160 [48;5;161m 161 [48;5;162m 162 [48;5;163m 163 [48;5;164m 164 [48;5;165m 165 [48;5;166m 166 [48;5;167m 167 [48;5;168m 168 [48;5;169m 169 [48;5;170m 170 [48;5;171m 171 [0m
- Warna terbalik:  [7;38;5;160m 160 [7;38;5;161m 161 [7;38;5;162m 162 [7;38;5;163m 163 [7;38;5;164m 164 [7;38;5;165m 165 [7;38;5;166m 166 [7;38;5;167m 167 [7;38;5;168m 168 [7;38;5;169m 169 [7;38;5;170m 170 [7;38;5;171m 171 [0m

[1;4mWarna 24-bit (RGB penuh):[0m
- Warna redup:     [2;38;2;34;139;34m Hijau Hutan - RGB(34,139,34) [2;38;2;102;51;153m Ungu Rebecca - RGB(102,51,153) [0m
- Warna teks:      [38;2;34;139;34m Hijau Hutan - RGB(34,139,34) [38;2;102;51;153m Ungu Rebecca - RGB(102,51,153) [0m
- Warna latar:     [48;2;34;139;34m Hijau Hutan - RGB(34,139,34) [48;2;102;51;153m Ungu Rebecca - RGB(102,51,153) [0m
- Warna terbalik:  [7;38;2;34;139;34m Hijau Hutan - RGB(34,139,34) [7;38;2;102;51;153m Ungu Rebecca - RGB(102,51,153) [0m

[1;4mGaya huruf:[0m
- Biasa
- [1mTebal[0m
- [2mRedup[0m
- [3mMiring[0m
- [4mGaris bawah[0m
- [7mWarna terbalik[0m
- [9mDicoret[0m
```

### Kerangka Kerja Editor dan Terminal

[Kerangka Kerja Editor dan Terminal](https://expressive-code.com/key-features/frames/)

#### Kerangka Kerja Editor Kode

```js title="my-test-file.js"
console.log('Contoh atribut judul')
```

---

```html
<!-- src/content/index.html -->
<div>Contoh komentar nama berkas</div>
```

#### Kerangka Kerja Terminal

```bash
echo "Kerangka kerja terminal ini tidak memiliki judul"
```

---

```powershell title="Contoh Terminal PowerShell"
Write-Output "Ini ada judulnya!"
```

#### Mengganti jenis bingkai

```sh frame="none"
echo "Lihat, tidak ada bingkai!"
```

---

```ps frame="code" title="PowerShell Profile.ps1"
# Jika tidak diganti, ini akan menjadi bingkai terminal
function Watch-Tail { Get-Content -Tail 20 -Wait $args }
New-Alias tail Watch-Tail
```

### Penandaan Teks dan Baris

[Penandaan Teks dan Baris](https://expressive-code.com/key-features/text-markers/)

#### Menandai Seluruh Baris dan Rentang Baris

```js {1, 4, 7-8}
// Baris ke-1 - Penentuan posisi berdasarkan nomor baris
// Baris ke-2
// Baris ke-3
// Baris ke-4 - Penentuan posisi berdasarkan nomor baris
// Baris ke-5
// Baris ke-6
// Baris ke-7 - Penentuan posisi berdasarkan rentang "7-8"
// Baris ke-8 - Penentuan posisi berdasarkan rentang "7-8"
```

#### Memilih jenis penanda baris (mark, ins, del)

```js title="line-markers.js" del={2} ins={3-4} {6}
function demo() {
  console.log('Baris ini ditandai sebagai telah dihapus')
  // Baris ini dan baris berikutnya ditandai sebagai telah disisipkan
  console.log('Ini adalah baris sisipan kedua')

  return 'Baris ini menggunakan jenis penanda default netral'
}
```

#### Menambahkan label ke penanda baris

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

#### Menambahkan label panjang pada baris terpisah

```jsx {"1. Cantumkan properti value di sini:":5-6} del={"2. Hapus status disabled dan active:":8-10} ins={"3. Tambahkan ini untuk menampilkan elemen anak di dalam tombol:":12-15}
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

#### Menggunakan sintaks mirip diff

```diff
+Baris ini akan ditandai sebagai baris yang ditambahkan
-Baris ini akan ditandai sebagai baris yang dihapus
Ini adalah baris biasa
```

---

```diff
--- a/README.md
+++ b/README.md
@@ -1,3 +1,4 @@
+ini adalah berkas diff yang sebenarnya
-semua isi akan tetap tidak diubah
 spasi kosong juga tidak akan dihapus
```

#### Menggabungkan penyorotan sintaks dan sintaks mirip diff

```diff lang="js"
  function thisIsJavaScript() {
    // Seluruh blok ini akan disorot sebagai JavaScript,
    // dan kita masih bisa menambahkan tag diff ke dalamnya!
-   console.log('Kode lama yang akan dihapus')
+   console.log('Kode baru yang keren!')
  }
```

#### Menandai teks tertentu dalam baris

```js "teks yang diberikan"
function demo() {
  // Menandai teks apa pun yang diberikan di dalam baris
  return 'Mendukung beberapa kecocokan untuk teks yang diberikan';
}
```

#### Ekspresi reguler

```ts /ye[sp]/
console.log('Kata yes dan yep akan ditandai.')
```

#### Meng-escape tanda garis miring

```sh /\/ho.*\//
echo "Test" > /home/test.txt
```

#### Memilih jenis penanda inline (mark, ins, del)

```js "return true;" ins="inserted" del="deleted"
function demo() {
  console.log('Ini adalah jenis penanda penyisipan dan penghapusan');
  // Pernyataan return menggunakan jenis penanda default
  return true;
}
```

### Pemisahan Baris Otomatis

[Pemisahan Baris Otomatis](https://expressive-code.com/key-features/word-wrap/)

#### Mengonfigurasi pemisahan baris otomatis untuk setiap blok

```js wrap
// Contoh pengaktifan pemotongan baris
function getLongString() {
  return 'Ini adalah string yang sangat panjang; kecuali wadahnya sangat lebar, kemungkinan besar string ini tidak akan muat di ruang yang tersedia'
}
```

---

```js wrap=false
// Contoh dengan wrap=false
function getLongString() {
  return 'Ini adalah string yang sangat panjang; kecuali wadahnya sangat lebar, kemungkinan besar tidak akan muat di ruang yang tersedia'
}
```

#### Konfigurasi indentasi saat pemotongan baris

```js wrap preserveIndent
// Contoh preserveIndent (diaktifkan secara default)
function getLongString() {
  return 'Ini adalah string yang sangat panjang; kecuali wadahnya sangat lebar, kemungkinan besar string ini tidak akan muat di ruang yang tersedia'
}
```

---

```js wrap preserveIndent=false
// Contoh preserveIndent=false
function getLongString() {
  return 'Ini adalah string yang sangat panjang; kecuali wadahnya sangat lebar, kemungkinan besar string ini tidak akan muat di ruang yang tersedia'
}
```

## Bagian yang Dapat Dilipat

[Bagian yang Dapat Dilipat](https://expressive-code.com/plugins/collapsible-sections/)

```js collapse={1-5, 12-14, 21-24}
// Semua kode pengaturan boilerplate ini akan dilipat
import { someBoilerplateEngine } from '@example/some-boilerplate'
import { evenMoreBoilerplate } from '@example/even-more-boilerplate'

const engine = someBoilerplateEngine(evenMoreBoilerplate())

// Bagian kode ini secara default tetap terlihat
engine.doSomething(1, 2, 3, calcFn)

function calcFn() {
  // Anda dapat memiliki beberapa bagian yang dapat dilipat
  const a = 1
  const b = 2
  const c = a + b

  // Bagian ini akan tetap terlihat
  console.log(`Hasil perhitungan: ${a} + ${b} = ${c}`)
  return c
}

// Semua kode hingga akhir blok akan dilipat kembali
engine.closeConnection()
engine.freeMemory()
engine.shutdown({ reason: 'Contoh kode templat berakhir' })
```

## Nomor Baris

[Nomor baris](https://expressive-code.com/plugins/line-numbers/)

### Menampilkan nomor baris untuk setiap blok

```js showLineNumbers
// Blok kode ini akan menampilkan nomor baris
console.log('Salam dari baris ke-2!')
console.log('Saya ada di baris ke-3')
```

---

```js showLineNumbers=false
// Blok ini menonaktifkan nomor baris
console.log('Halo?')
console.log('Maaf, tahukah kamu di baris keberapa aku berada?')
```

### Mengubah nomor baris awal

```js showLineNumbers startLineNumber=5
console.log('Salam dari baris ke-5!')
console.log('Aku ada di baris ke-6')
```

## Blok Kode Tab

Disediakan oleh [rehype-code-group](https://github.com/ITZSHOAIB/rehype-code-group), sintaksnya sama dengan [VitePress code group](https://vitepress.dev/guide/markdown#code-groups): gunakan `::: code-group labels=[...]` untuk menggabungkan beberapa blok kode menjadi satu grup tab.

> [!CATATAN]
> Label dalam `labels=[...]` sesuai urutan dengan blok kode dalam grup tersebut, dipisahkan dengan koma; spasi antara `:::` dan `code-group` tidak boleh dihilangkan.

### Penggunaan Dasar

````markdown
::: kelompok-kode label=[code.js, code.py, code.html]

```js
export function greet(name) {
  return `Hello, ${name}!`;
}
```

```py
def greet(name):
    return f"Hello, {name}!"
```

```html
<p>Hello, world!</p>
```

:::
````

Efek rendering:

::: code-group labels=[code.js, code.py, code.html]

```js
export function greet(name) {
  return `Hello, ${name}!`;
}
```

```py
def greet(name):
    return f"Hello, {name}!"
```

```html
<p>Hello, world!</p>
```

:::

### Penggunaan Emoji dalam Label

Label mendukung [kode pendek emoji](https://github.com/omnidan/node-emoji#readme), yang akan secara otomatis diubah menjadi emoji saat proses kompilasi:

````markdown
::: code-group labels=[:package: npm, :package: pnpm, :yarn: yarn]
````

::: code-group labels=[:package: npm, :package: pnpm, :yarn: yarn]

```bash
npm create astro@latest
```

```bash
pnpm create astro@latest
```

```bash
yarn create astro
```

:::

### Kombinasi dengan Fitur Blok Kode Lainnya

Di dalam grup ini, blok kode Expressive Code tetap berfungsi seperti biasa; fitur-fitur seperti judul, nomor baris, penanda baris, penyembunyian, dan bingkai terminal dapat digunakan seperti biasa.

::: code-group labels=[file konfigurasi, terminal, penyembunyian]

```js title="astro.config.mjs" showLineNumbers {2} ins={3}
export default {
  theme: "firefly",
  codeGroup: true,
};
```

```bash title="Deploy"
pnpm build && pnpm preview
```

```js collapse={1-3}
// Tiga baris ini terlipat secara default
import { a } from "a";
import { b } from "b";

console.log(a, b);
```

:::

### Lebih dari sekadar blok kode

Tab dapat berisi konten apa pun, seperti teks, daftar, atau gambar:

::: code-group labels=[Penjelasan, Daftar]

Ini adalah isi paragraf biasa.

- Item daftar pertama
- Item daftar kedua

:::

> [!TIP]
> Tab dibuat pada tahap pembangunan, dan secara default item pertama akan terbuka; mendukung navigasi dengan klik mouse dan tombol keyboard <kbd>←</kbd> / <kbd>→</kbd> / <kbd>Home</kbd> / <kbd>End</kbd>.

### Penggunaan dalam kotak pemberitahuan (komponen MDX)

Kotak petunjuk bergaya Docusaurus seperti `::: code-group` dan `::: tip` semuanya menggunakan sintaks kontainer `:::`, sedangkan micromark-directive menetapkan bahwa jumlah tanda titik dua pada kontainer induk dan anak harus berbeda. Oleh karena itu, `::: code-group` **tidak dapat disematkan di dalam kotak petunjuk seperti `::: tip`** (seluruh blok akan menjadi tidak berfungsi).

Dalam situasi ini, gunakan komponen MDX [`TabGroup`](@/components/common/TabGroup.svelte): Komponen MDX tidak diproses melalui direktif `:::`, sehingga dapat digunakan dengan normal baik di dalam maupun di luar kotak petunjuk, serta memudahkan pengembangan komponen UI tambahan di masa mendatang. Ubah ekstensi artikel menjadi `.mdx`, lalu impor dari titik masuk terpusat [`@/components/firefly-mdx`](@/components/firefly-mdx.ts) (Anda dapat mengimpor beberapa komponen sekaligus):

````mdx
import { TabGroup } from "@/components/firefly-mdx";

:::tip

<TabGroup labels={["test.js", "test.py"]} client:load>
  ```js
  console.log(1)
  ```

  ```py
  print("hello world")
  ```
</TabGroup>

:::
````

:::tip
- Array `labels` mendeklarasikan label untuk setiap blok kode, dengan urutan yang sesuai satu per satu
- Komponen menggunakan `client:load` untuk mengaktifkan peralihan label
:::
