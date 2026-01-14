---
title: Contoh Rumus Matematika KaTeX
published: 1970-01-02
description: Menampilkan dukungan tema Neko terhadap rumus matematika KaTeX, termasuk rumus inline, blok, dan simbol matematika kompleks.
tags: [KaTeX, Math, Contoh]
category: Contoh Artikel
draft: false
image: api
---

Artikel ini menampilkan dukungan rendering rumus matematika KaTeX pada tema [Neko](https://github.com/CuteLeaf/Firefly).

## Rumus Inline (Dalam Baris)

Rumus inline menggunakan sepasang simbol `$` untuk membungkus teks.

Contoh: Rumus Euler $e^{i\pi} + 1 = 0$ adalah salah satu rumus terindah dalam matematika.

Persamaan massa-energi $E = mc^2$ juga sudah sangat dikenal luas.

## Rumus Blok (Block)

Rumus blok menggunakan dua simbol `$$` untuk membungkus teks, dan akan ditampilkan di tengah baris (centered).

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

## Contoh Kompleks

### Matriks (Matrices)

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
\begin{pmatrix}
\alpha & \beta \\
\gamma & \delta
\end{pmatrix} =
\begin{pmatrix}
a\alpha + b\gamma & a\beta + b\delta \\
c\alpha + d\gamma & c\beta + d\delta
\end{pmatrix}
$$

### Limit dan Penjumlahan (Limits and Sums)

$$
\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}
$$

$$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$$

### Persamaan Maxwell (Maxwell's Equations)

$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
$$

### Persamaan Kimia (Chemical Equations)

$$
\ce{CH4 + 2O2 -> CO2 + 2H2O}
$$

## Simbol Lainnya

| Simbol | Kode | Hasil Render |
| :--- | :--- | :--- |
| Alpha | `\alpha` | $\alpha$ |
| Beta | `\beta` | $\beta$ |
| Gamma | `\Gamma` | $\Gamma$ |
| Pi | `\pi` | $\pi$ |
| Infinity | `\infty` | $\infty$ |
| Panah Kanan | `\rightarrow` | $\rightarrow$ |
| Parsial | `\partial` | $\partial$ |

Untuk sintaks KaTeX lebih lanjut, silakan merujuk pada [KaTeX Supported Functions](https://katex.org/docs/supported.html).