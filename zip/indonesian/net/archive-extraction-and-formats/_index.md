---
date: 2026-06-19
description: Pelajari cara mengompres tar files, membuat targz archives, dan mengekstrak
  password‑protected zip files menggunakan Aspose.Zip untuk .NET – meningkatkan efisiensi
  penyimpanan dan keamanan.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Ekstraksi Arsip dan Format
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres tar files dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengompres File Tar dengan Aspose.Zip untuk .NET

## Pendahuluan

Dalam panduan ini Anda akan menemukan **cara mengompres tar** file menggunakan Aspose.Zip untuk .NET, belajar membuat arsip TarGz, dan melihat cara mengekstrak arsip zip yang dilindungi kata sandi. Penanganan arsip yang efisien adalah keterampilan inti bagi pengembang .NET modern—baik Anda membangun layanan pencadangan, klien penyimpanan cloud, atau pipeline pemrosesan data, menguasai format ini mengurangi biaya penyimpanan, mempercepat transfer, dan menjaga data sensitif tetap aman.

## Jawaban Cepat
- **Apa itu TarBz2?** Arsip terkompresi yang menggabungkan paket TAR dengan kompresi BZIP2 untuk rasio kompresi tinggi.  
- **Mengapa memilih Aspose.Zip untuk .NET?** Menawarkan API tunggal yang fluently untuk membuat dan mengekstrak banyak format arsip tanpa dependensi eksternal.  
- **Bisakah saya membuat arsip TarGz?** Ya – Aspose.Zip mendukung TarGz, TarLz, TarXz, TarZ, dan lainnya.  
- **Bagaimana cara mengekstrak arsip zip yang dilindungi kata sandi?** Gunakan properti `Password` pada objek `ArchiveEntry` saat mengekstrak.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan untuk produksi; percobaan gratis tersedia untuk evaluasi.

## Apa itu Kompresi Tar?
Tar (Tape Archive) adalah format kontainer yang menggabungkan banyak file dan direktori menjadi satu aliran tanpa kompresi. Ketika Anda menerapkan algoritma kompresi seperti BZIP2, GZip, LZMA, atau XZ, hasilnya adalah **arsip berbasis tar** seperti `.tar.bz2`, `.tar.gz`, `.tar.lz`, dll. Format ini didukung secara luas di Linux, macOS, dan Windows, menjadikannya ideal untuk pertukaran data lintas‑platform.

## Mengapa Menggunakan Aspose.Zip untuk .NET dalam Menangani Format Ini?
Aspose.Zip menyediakan **API terpadu yang bebas dependensi** yang mendukung lebih dari 50 format arsip dan kompresi, termasuk TarBz2, TarGz, TarLz, TarXz, dan TarZ. Ia berjalan di Windows, Linux, dan macOS, dan arsitektur berbasis aliran menjaga penggunaan memori di bawah 10 MB bahkan untuk arsip berukuran ratusan megabyte. Perlindungan kata sandi sudah terintegrasi, memungkinkan enkripsi per‑entri tanpa perpustakaan tambahan.

## Prasyarat
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, atau .NET 5–10.  
- Paket NuGet Aspose.Zip untuk .NET terpasang (`Install-Package Aspose.Zip`).  
- Pemahaman dasar tentang I/O file C# dan sistem proyek .NET.

## Panduan Langkah‑per‑Langkah

### Cara Mengompres File Tar – Jawaban Langsung
`Archive` mewakili file arsip dan menyediakan metode untuk menambahkan entri serta menyimpannya.  
Buat instance `Archive`, tambahkan file yang ingin Anda bundel, setel `CompressionType.BZip2`, dan panggil `Save` dengan `ArchiveFormat.TarBz2`. Perpustakaan menulis kontainer TAR dan mengompresnya dalam satu pass streaming, sehingga Anda tidak pernah memuat seluruh arsip ke memori.

### Langkah 1: Pilih format arsip yang Anda butuhkan
Tentukan format berbasis tar mana yang paling cocok dengan kompromi kecepatan‑kompresi Anda:

- **TarBz2** – Rasio kompresi tertinggi (≈30 % lebih kecil daripada TarGz) tetapi lebih lambat.  
- **TarGz** – Keseimbangan yang baik antara kecepatan dan ukuran; ideal untuk kebanyakan skenario penyimpanan cloud.  
- **TarLz / TarXz** – Kompresi sangat tinggi dengan kecepatan sedang, berguna untuk penyimpanan arsip.  
- **TarZ** – Format warisan untuk kompatibilitas dengan alat Unix lama.

### Langkah 2: Buat instance `Archive` baru
`Archive` adalah objek tingkat atas yang mewakili satu file arsip dalam memori.  

Kelas `Archive` mengelola alur kerja pengepakan dan kompresi, menyediakan metode untuk menambahkan entri dan menulis file akhir.

### Langkah 3: Tambahkan file dan folder
Anda dapat menambahkan seluruh pohon direktori dengan `AddAll` atau menambahkan file individual dengan `AddFile`. Mempertahankan hierarki folder asli semudah memberikan jalur direktori dasar.

### Langkah 4: Atur jenis kompresi yang diinginkan
`CompressionType` mengenumerasikan algoritma yang didukung.  

`CompressionType` menentukan algoritma (BZip2, GZip, LZMA, XZ, dll.) yang akan diterapkan pada aliran TAR selama penyimpanan.

### Langkah 5: Simpan arsip
`ArchiveFormat` adalah sekumpulan enum (misalnya `TarBz2`, `TarGz`) yang memberi tahu penulis kontainer dan kompresi mana yang akan digunakan.  

Memanggil `Save` menulis arsip ke disk menggunakan format yang dipilih.

### Langkah 6: Mengekstrak arsip dengan kata sandi
`ArchiveEntry` mewakili satu file atau entri direktori di dalam arsip.  

Untuk mengekstrak zip yang dilindungi kata sandi, buka arsip, temukan setiap `ArchiveEntry`, tetapkan properti `Password`‑nya, dan panggil `Extract`. Model kata sandi per‑entri ini memungkinkan Anda melindungi file individual di dalam satu zip.

### Langkah 7: Verifikasi hasil
Setelah ekstraksi, bandingkan ukuran file dan checksum SHA‑256 untuk memastikan bahwa proses putar‑balik arsip mempertahankan integritas data.

## Kasus Penggunaan Umum
- **Utilitas pencadangan** – Simpan cadangan harian sebagai `.tar.bz2` untuk mengurangi biaya penyimpanan hingga 30 %.  
- **Pertukaran data lintas‑platform** – Format berbasis Tar dipahami secara native oleh alat Linux, macOS, dan Windows.  
- **Distribusi aman** – Tetapkan kata sandi pada entri sensitif, memenuhi persyaratan kepatuhan tanpa alat enkripsi tambahan.

## Pemecahan Masalah & Tips
- **Arsip besar** – Pilih API streaming (`Archive.CreateEntryFromFile`) untuk menjaga penggunaan memori tetap rendah.  
- **Kecocokan kata sandi** – Kata sandi yang ditetapkan pada setiap `ArchiveEntry` harus cocok persis; jika tidak, `InvalidPasswordException` akan dilempar.  
- **Tingkat kompresi** – BZIP2 tidak menyediakan tingkat kustom; jika Anda memerlukan kontrol lebih halus, beralih ke LZMA (`CompressionType.LZMA`) atau XZ (`CompressionType.XZ`).  

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara membuat arsip TarGz?**  
A: Setel `CompressionType.GZip` dan gunakan `ArchiveFormat.TarGz` saat memanggil `Save`. Ini menghasilkan file `.tar.gz` dalam satu langkah.

**Q: Bisakah saya mengekstrak arsip yang dilindungi kata sandi tanpa mengetahui kata sandinya?**  
A: Tidak. Setiap entri harus diberikan kata sandi yang benar; ekstraksi gagal dengan `InvalidPasswordException` jika tidak.

**Q: Apakah Aspose.Zip mendukung mengekstrak arsip dengan kata sandi berbeda per entri?**  
A: Ya. Tetapkan kata sandi pada setiap `ArchiveEntry` secara individual sebelum memanggil `Extract`.

**Q: Format mana yang memberikan kompresi terbaik?**  
A: TarBz2 biasanya menghasilkan ukuran terkecil, diikuti oleh TarLz dan TarXz. TarGz menawarkan alternatif yang lebih cepat namun tetap efektif.

**Q: Apakah ada batas jumlah file yang dapat saya tambahkan ke arsip TAR?**  
A: Praktis tidak ada, tetapi arsip yang sangat besar (>10 GB) mungkin lebih mudah ditangani jika dibagi menjadi beberapa bagian.

## Tutorial Ekstraksi Arsip dan Format

### [Mengompres File ke TarBz2 dengan Aspose.Zip untuk .NET](./compress-to-tar-bz2/)
Pelajari cara mengompres file ke format TarBz2 di .NET menggunakan Aspose.Zip. Ikuti panduan langkah‑per‑langkah kami untuk kompresi file yang efisien.  
### [Mengompres ke TarGz dengan Aspose.Zip untuk .NET](./compress-to-tar-gz/)
Jelajahi kompresi file yang efisien di .NET dengan Aspose.Zip. Kompres ke TarGz dengan mudah.  
### [Mengompres ke TarLz dengan Aspose.Zip untuk .NET](./compress-to-tar-lz/)
Kompres file di .NET dengan Aspose.Zip secara mudah. Pelajari cara membuat arsip TarLz langkah‑per‑langkah.  
### [Mengompres ke TarXz dengan Aspose.Zip untuk .NET](./compress-to-tar-xz/)
Pelajari cara mengompres file ke format TarXz di .NET menggunakan Aspose.Zip. Ikuti panduan kami untuk penyimpanan dan transmisi yang efisien.  
### [Mengompres ke TarZ dengan Aspose.Zip untuk .NET](./compress-to-tar-z/)
Jelajahi kompresi langkah‑per‑langkah ke TarZ menggunakan Aspose.Zip untuk .NET. Penanganan file yang efisien untuk proyek .NET Anda.  
### [Mengekstrak Entri Arsip dengan Kata Sandi Berbeda di Aspose.Zip untuk .NET](./extract-archive-different-passwords/)
Pelajari cara mengekstrak entri arsip dengan kata sandi berbeda di Aspose.Zip untuk .NET. Tingkatkan keamanan dan fleksibilitas dalam aplikasi Anda.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Tutorial Terkait

- [Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cara mengompres tar dan membuat TarBz2 dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Tambahkan file ke tar dan buat arsip tarxz dengan Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}