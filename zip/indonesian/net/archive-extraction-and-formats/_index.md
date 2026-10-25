---
date: 2026-10-25
description: Pelajari cara mengekstrak kata sandi zip dan mengatur algoritma kompresi
  saat mengompres file tar dengan Aspose.Zip untuk .NET, meningkatkan efisiensi penyimpanan
  dan keamanan.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Ekstraksi Arsip dan Format
og_description: Pelajari cara mengekstrak kata sandi zip dan mengatur algoritma kompresi
  saat mengompres file tar dengan Aspose.Zip untuk .NET, meningkatkan efisiensi penyimpanan
  dan keamanan.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Ekstrak kata sandi zip dan kompres file tar dengan Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Ekstrak kata sandi zip dan kompres file tar dengan Aspose.Zip
url: /id/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak kata sandi zip dan kompres file tar dengan Aspose.Zip

## Pendahuluan

Dalam panduan ini Anda akan menemukan teknik **ekstrak zip password**, mempelajari cara mengatur algoritma kompresi saat membuat arsip berbasis tar, dan melihat cara membangun TarGz, TarBz2, serta format lainnya dengan Aspose.Zip untuk .NET. Baik Anda membangun layanan backup, klien cloud‑storage, atau pipeline pemrosesan data, menguasai operasi ini mengurangi biaya penyimpanan, mempercepat transfer, dan mengamankan file sensitif.

## Jawaban Cepat
- **Apa itu TarBz2?** Arsip terkompresi yang menggabungkan paket TAR dengan kompresi BZIP2 untuk rasio kompresi tinggi.  
- **Mengapa memilih Aspose.Zip untuk .NET?** Mendukung lebih dari 50 format arsip dan kompresi, berjalan di Windows, Linux, dan macOS, serta menjaga penggunaan memori di bawah 10 MB untuk arsip berukuran ratusan megabyte.  
- **Apakah saya dapat membuat arsip TarGz?** Ya – Aspose.Zip menawarkan TarGz, TarLz, TarXz, TarZ, dan lainnya.  
- **Bagaimana cara mengekstrak arsip zip yang dilindungi kata sandi?** Atur properti `Password` pada setiap `ArchiveEntry` sebelum memanggil `Extract`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan untuk produksi; versi percobaan gratis tersedia untuk evaluasi.

## Apa itu kompresi tar?

Kompresi tar menggabungkan kontainer TAR dengan algoritma kompresi seperti BZIP2, GZIP, LZMA, atau XZ. Hasilnya adalah satu file (misalnya `.tar.gz`, `.tar.bz2`) yang dapat dibongkar di Linux, macOS, dan Windows. Ini mempertahankan hierarki direktori asli, memungkinkan ekstraksi akses acak, dan didukung secara luas oleh alat baris perintah serta perpustakaan pemrograman, menjadikannya ideal untuk distribusi lintas‑platform dan penyimpanan arsip.

## Mengapa menggunakan Aspose.Zip untuk .NET dalam menangani format ini?

Aspose.Zip menyediakan API terpadu tanpa ketergantungan yang mendukung **50+** format arsip dan kompresi, termasuk semua tipe berbasis tar utama. Arsitektur streaming‑nya memproses arsip lebih besar dari 10 GB sambil menjaga penggunaan RAM di bawah 10 MB, menjadikannya ideal untuk beban kerja server berkecepatan tinggi.  

**Jawaban langsung:** Anda menggunakan Aspose.Zip karena memungkinkan Anda membuat, mengompres, dan mengekstrak arsip berbasis tar serta file zip yang dilindungi kata sandi dengan satu API fluens, tanpa alat eksternal, sambil menangani arsip multi‑gigabyte dalam mode streaming yang efisien memori.

## Prasyarat
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, atau .NET 5–10.  
- Paket NuGet Aspose.Zip untuk .NET (`Install-Package Aspose.Zip`).  
- Familiaritas dasar dengan I/O file C# dan sistem proyek .NET.

## Panduan langkah demi langkah

### Cara mengompres file tar – jawaban langsung
Buat instance `Archive`, tambahkan file yang ingin Anda bundel, atur `CompressionType.BZip2` (atau algoritma lain), dan panggil `Save` dengan `ArchiveFormat.TarBz2`. Perpustakaan menulis kontainer TAR dan mengompresnya dalam satu pass streaming, sehingga Anda tidak pernah memuat seluruh arsip ke memori.

### Langkah 1: Pilih format arsip yang Anda butuhkan
Tentukan format berbasis tar yang paling cocok dengan trade‑off kecepatan‑kompresi Anda:

- **TarBz2** – Rasio kompresi tertinggi (≈30 % lebih kecil daripada TarGz) tetapi lebih lambat.  
- **TarGz** – Keseimbangan baik antara kecepatan dan ukuran; ideal untuk kebanyakan skenario cloud‑storage.  
- **TarLz / TarXz** – Kompresi sangat tinggi dengan kecepatan sedang, berguna untuk penyimpanan arsip.  
- **TarZ** – Format legacy untuk kompatibilitas dengan alat Unix lama.

### Langkah 2: Buat instance `Archive` baru
`Archive` mewakili satu file arsip dan menyediakan metode untuk menambahkan entri serta menyimpan arsip.  

Kelas `Archive` mengelola alur kerja pengepakan dan kompresi, mengekspor metode untuk menambah entri dan menulis file akhir.

### Langkah 3: Tambahkan file dan folder
Anda dapat menambahkan seluruh pohon direktori dengan `AddAll` atau menambahkan file individual dengan `AddFile`.  

`AddAll` menambahkan seluruh pohon direktori ke arsip, mempertahankan strukturnya.  
`AddFile` menambahkan satu file ke arsip. Mempertahankan hierarki folder asli semudah memberikan jalur direktori dasar.

### Langkah 4: Atur tipe kompresi yang diinginkan
Enum `CompressionType` menentukan algoritma kompresi yang diterapkan pada aliran TAR.  

`CompressionType` mencakup algoritma yang didukung (BZip2, GZip, LZMA, XZ, dll.) yang akan diterapkan saat penyimpanan.

### Langkah 5: Simpan arsip
Enum `ArchiveFormat` memilih kombinasi kontainer dan kompresi untuk file output.  

Memanggil `Save` menulis arsip ke disk menggunakan format yang dipilih.

### Langkah 6: Mengekstrak arsip dengan kata sandi
`ArchiveEntry` mewakili satu file atau entri direktori di dalam arsip.  

Untuk mengekstrak zip yang dilindungi kata sandi, buka arsip, temukan setiap `ArchiveEntry`, tetapkan properti `Password`‑nya, dan panggil `Extract`. Properti `Password` menetapkan kata sandi dekripsi untuk entri zip. Model kata sandi per‑entri ini memungkinkan Anda melindungi file individual di dalam satu zip.

### Langkah 7: Verifikasi hasil
Setelah ekstraksi, bandingkan ukuran file dan checksum SHA‑256 untuk memastikan bahwa perjalanan arsip mempertahankan integritas data.

## Kasus penggunaan umum
- **Utilitas backup** – Simpan backup harian sebagai `.tar.bz2` untuk mengurangi biaya penyimpanan hingga 30 %.  
- **Pertukaran data lintas‑platform** – Format berbasis tar dipahami secara native oleh alat Linux, macOS, dan Windows.  
- **Distribusi aman** – Tetapkan kata sandi pada entri sensitif, memenuhi persyaratan kepatuhan tanpa alat enkripsi tambahan.

## Pemecahan masalah & tips
- **Arsip besar** – Gunakan API streaming (`Archive.CreateEntryFromFile`) untuk menjaga penggunaan memori tetap rendah.  
- **Kecocokan kata sandi** – Kata sandi yang ditetapkan pada setiap `ArchiveEntry` harus persis cocok; jika tidak, `InvalidPasswordException` akan dilempar.  
- **Level kompresi** – BZIP2 tidak menyediakan level khusus; jika Anda memerlukan kontrol lebih halus, beralihlah ke LZMA (`CompressionType.LZMA`) atau XZ (`CompressionType.XZ`).  

## Pertanyaan yang sering diajukan

**T: Bagaimana cara membuat arsip TarGz?**  
J: Atur `CompressionType.GZip` dan gunakan `ArchiveFormat.TarGz` saat memanggil `Save`. Ini menghasilkan file `.tar.gz` dalam satu langkah.

**T: Bisakah saya mengekstrak arsip yang dilindungi kata sandi tanpa mengetahui kata sandinya?**  
J: Tidak. Setiap entri harus diberikan kata sandi yang benar; ekstraksi akan gagal dengan `InvalidPasswordException` jika tidak.

**T: Apakah Aspose.Zip mendukung mengekstrak arsip dengan kata sandi berbeda per entri?**  
J: Ya. Tetapkan kata sandi pada masing‑masing `ArchiveEntry` sebelum memanggil `Extract`.

**T: Format mana yang memberikan kompresi terbaik?**  
J: TarBz2 biasanya menghasilkan ukuran terkecil, diikuti oleh TarLz dan TarXz. TarGz menawarkan alternatif yang lebih cepat namun tetap efektif.

**T: Apakah ada batas jumlah file yang dapat saya tambahkan ke arsip TAR?**  
J: Secara praktis tidak ada, tetapi arsip yang sangat besar (>10 GB) mungkin lebih mudah ditangani jika dibagi menjadi beberapa bagian.

## Tutorial ekstraksi arsip dan format

### [Mengompres File ke TarBz2 dengan Aspose.Zip untuk .NET](./compress-to-tar-bz2/)
Pelajari cara mengompres file ke format TarBz2 di .NET menggunakan Aspose.Zip. Ikuti panduan langkah demi langkah untuk kompresi file yang efisien.  

### [Mengompres ke TarGz dengan Aspose.Zip untuk .NET](./compress-to-tar-gz/)
Jelajahi kompresi file yang efisien di .NET dengan Aspose.Zip. Kompres ke TarGz dengan mudah.  

### [Mengompres ke TarLz dengan Aspose.Zip untuk .NET](./compress-to-tar-lz/)
Kompress file di .NET dengan Aspose.Zip secara mudah. Pelajari cara membuat arsip TarLz langkah demi langkah.  

### [Mengompres ke TarXz dengan Aspose.Zip untuk .NET](./compress-to-tar-xz/)
Pelajari cara mengompres file ke format TarXz di .NET menggunakan Aspose.Zip. Ikuti panduan kami untuk penyimpanan dan transmisi yang efisien.  

### [Mengompres ke TarZ dengan Aspose.Zip untuk .NET](./compress-to-tar-z/)
Jelajahi kompresi langkah demi langkah ke TarZ menggunakan Aspose.Zip untuk .NET. Penanganan file yang efisien untuk proyek .NET Anda.  

### [Mengekstrak entri arsip dengan kata sandi berbeda di Aspose.Zip untuk .NET](./extract-archive-different-passwords/)
Pelajari cara mengekstrak entri arsip dengan kata sandi berbeda di Aspose.Zip untuk .NET. Tingkatkan keamanan dan fleksibilitas dalam aplikasi Anda.

## Tutorial terkait

- [Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cara mengompres tar dan membuat TarBz2 dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Tambahkan file ke tar dan buat arsip tarxz dengan Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Terakhir Diperbarui:** 2026-10-25  
**Diuji Dengan:** Aspose.Zip for .NET 24.11  
**Penulis:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}