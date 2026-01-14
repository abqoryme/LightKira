---
title: Diagram Mermaid di Markdown
published: 1970-01-01
pinned: false
description: Sebuah contoh sederhana artikel blog Markdown yang menyertakan diagram Mermaid.
tags: [Markdown, Blog, Mermaid, Neko]
category: Contoh Artikel
draft: false
---
# Panduan Lengkap Diagram Mermaid di Markdown

Artikel ini mendemonstrasikan cara membuat berbagai diagram kompleks menggunakan Mermaid di dalam dokumen Markdown, termasuk diagram alir (flowchart), diagram urutan (sequence diagram), bagan Gantt, diagram kelas, dan diagram status.

## Contoh Diagram Alir (Flowchart)

Diagram alir sangat cocok untuk merepresentasikan alur proses atau langkah-langkah algoritma.

```mermaid
graph TD
    A[Mulai] --> B{Pemeriksaan Kondisi}
    B -->|Ya| C[Langkah Proses 1]
    B -->|Tidak| D[Langkah Proses 2]
    C --> E[Sub-proses]
    D --> E
    subgraph E [Detail Sub-proses]
        E1[Sub-langkah 1] --> E2[Sub-langkah 2]
        E2 --> E3[Sub-langkah 3]
    end
    E --> F{Keputusan Lain}
    F -->|Opsi 1| G[Hasil 1]
    F -->|Opsi 2| H[Hasil 2]
    F -->|Opsi 3| I[Hasil 3]
    G --> J[Selesai]
    H --> J
    I --> J

```

## Contoh Diagram Urutan (Sequence Diagram)

Diagram urutan menunjukkan interaksi antar objek seiring berjalannya waktu.

```mermaid
sequenceDiagram
    participant User as Pengguna
    participant WebApp as Aplikasi Web
    participant Server as Server
    participant Database as Database

    User->>WebApp: Mengirim permintaan login
    WebApp->>Server: Mengirim permintaan autentikasi
    Server->>Database: Memeriksa kredensial pengguna
    Database-->>Server: Mengembalikan data pengguna
    Server-->>WebApp: Mengembalikan hasil autentikasi
    
    alt Autentikasi Berhasil
        WebApp->>User: Menampilkan halaman selamat datang
        WebApp->>Server: Meminta data pengguna
        Server->>Database: Mengambil preferensi pengguna
        Database-->>Server: Mengembalikan pengaturan preferensi
        Server-->>WebApp: Mengembalikan data pengguna
        WebApp->>User: Memuat antarmuka personalisasi
    else Autentikasi Gagal
        WebApp->>User: Menampilkan pesan kesalahan
        WebApp->>User: Meminta input ulang
    end

```

## Contoh Bagan Gantt (Gantt Chart)

Bagan Gantt sangat ideal untuk menampilkan kemajuan proyek dan lini masa (timeline).

```mermaid
gantt
    title Lini Masa Proyek Pengembangan Situs Web
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d
    
    section Tahap Desain
    Analisis Kebutuhan      :a1, 2023-10-01, 7d
    Desain UI               :a2, after a1, 10d
    Pembuatan Prototipe     :a3, after a2, 5d
    
    section Tahap Pengembangan
    Pengembangan Frontend   :b1, 2023-10-20, 15d
    Pengembangan Backend    :b2, after a2, 18d
    Desain Database         :b3, after a1, 12d
    
    section Tahap Pengujian
    Pengujian Unit          :c1, after b1, 8d
    Pengujian Integrasi     :c2, after b2, 10d
    Uji Penerimaan Pengguna :c3, after c2, 7d
    
    section Penerapan
    Penerapan Lingkungan Produksi :d1, after c3, 3d
    Rilis                         :milestone, after d1, 0d

```

## Contoh Diagram Kelas (Class Diagram)

Diagram kelas menunjukkan struktur statis sistem, termasuk kelas, atribut, metode, dan hubungannya.

```mermaid
classDiagram
    class User {
        +String username
        +String password
        +String email
        +Boolean active
        +login()
        +logout()
        +updateProfile()
    }
    
    class Article {
        +String title
        +String content
        +Date publishDate
        +Boolean published
        +publish()
        +edit()
        +delete()
    }
    
    class Comment {
        +String content
        +Date commentDate
        +addComment()
        +deleteComment()
    }
    
    class Category {
        +String name
        +String description
        +addArticle()
        +removeArticle()
    }
    
    User "1" -- "*" Article : Menulis
    User "1" -- "*" Comment : Memposting
    Article "1" -- "*" Comment : Memiliki
    Article "1" -- "*" Category : Termasuk dalam

```

## Contoh Diagram Status (State Diagram)

Diagram status menunjukkan urutan status yang dilalui objek selama siklus hidupnya.

```mermaid
stateDiagram-v2
    [*] --> Draf
    
    Draf --> DalamTinjauan : Ajukan
    DalamTinjauan --> Draf : Tolak
    DalamTinjauan --> Disetujui : Setujui
    Disetujui --> Dipublikasikan : Publikasikan
    Dipublikasikan --> Diarsipkan : Arsipkan
    Dipublikasikan --> Draf : Tarik Kembali
    
    state Dipublikasikan {
        [*] --> Aktif
        Aktif --> Tersembunyi : Sembunyikan Sementara
        Tersembunyi --> Aktif : Pulihkan
        Aktif --> [*]
        Tersembunyi --> [*]
    }
    
    Diarsipkan --> [*]

```

## Contoh Diagram Lingkaran (Pie Chart)

Diagram lingkaran sangat cocok untuk menampilkan data proporsi dan persentase.

```mermaid
pie title Analisis Sumber Lalu Lintas Situs Web
    "Mesin Pencari" : 45.6
    "Akses Langsung" : 30.1
    "Media Sosial" : 15.3
    "Tautan Referensi" : 6.4
    "Sumber Lainnya" : 2.6

```

## Kesimpulan

Mermaid adalah alat yang ampuh untuk membuat berbagai jenis diagram di dalam dokumen Markdown. Artikel ini telah mendemonstrasikan penggunaan diagram alir, diagram urutan, bagan Gantt, diagram kelas, diagram status, dan diagram lingkaran. Diagram-diagram ini dapat membantu Anda mengekspresikan konsep, proses, dan struktur data yang kompleks dengan lebih jelas.

Untuk menggunakan Mermaid, cukup tentukan bahasa `mermaid` di dalam blok kode dan deskripsikan diagram menggunakan sintaks teks yang ringkas. Mermaid akan secara otomatis mengubah deskripsi tersebut menjadi diagram visual yang indah.

Cobalah gunakan diagram Mermaid di artikel blog teknis atau dokumentasi proyek Anda berikutnya - mereka akan membuat konten Anda lebih profesional dan lebih mudah dipahami!

```
