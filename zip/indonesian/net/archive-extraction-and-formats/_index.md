---
date: 2026-02-20
description: Pelajari cara mengompres file tarbz2, cara membuat arsip targz, serta
  mengekstrak arsip .NET dengan ekstraksi zip yang dilindungi kata sandi menggunakan
  Aspose.Zip untuk .NET. Tingkatkan efisiensi penyimpanan dan keamanan.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres File TarBz2 dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengompres File TarBz2 dengan Aspose.Zip untuk .NET

## Pendahuluan

Dalam panduan ini, Anda akan belajar **cara mengompres file tarbz2** dengan Aspose.Zip untuk .NET sambil juga menemukan cara membuat arsip TarGz dan melakukan ekstraksi arsip .net dari file zip yang dilindungi kata sandi. Penanganan file yang efisien adalah fondasi pengembangan .NET modern, dan menguasai format ini memungkinkan Anda mengurangi biaya penyimpanan, mempercepat transfer data, dan menjaga informasi sensitif tetap aman. Baik Anda membangun layanan cadangan, klien penyimpanan cloud, atau pipeline pemrosesan data, teknik yang dibahas di sini akan membuat tugas manajemen file Anda lebih lancar dan dapat diandalkan.

## Jawaban Cepat
- **Apa itu TarBz2?** Arsip terkompresi yang menggabungkan paket TAR dengan kompresi BZIP2 untuk rasio kompresi tinggi.  
- **Mengapa memilih Aspose.Zip untuk .NET?** Menawarkan API tunggal yang fluently untuk membuat dan mengekstrak banyak format arsip tanpa ketergantungan eksternal.  
- **Bisakah saya membuat arsip TarGz?** Ya – Aspose.Zip mendukung TarGz, TarLz, TarXz, TarZ, dan lainnya.  
- **Bagaimana cara mengekstrak arsip zip yang dilindungi kata sandi?** Gunakan properti `Password` pada objek `ArchiveEntry` saat mengekstrak.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan untuk produksi; percobaan gratis tersedia untuk evaluasi.

## Cara Mengompres File TarBz2

Mengompres file menjadi TarBz2 berarti pertama-tama menggabungkan beberapa file dan direktori ke dalam satu kontainer **TAR** tunggal, kemudian menerapkan kompresi **BZIP2**. Hasilnya adalah satu file `.tar.bz2` yang mudah dipindahkan dan sangat terkompresi.

## Mengapa Menggunakan Aspose.Zip untuk .NET dalam Menangani Format Ini?

- **Unified API** – Satu perpustakaan, banyak format (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Berfungsi di Windows, Linux, dan macOS langsung.  
- **Password support** – Melindungi dan mengekstrak arsip secara aman dengan kata sandi per‑entry.  
- **Performance‑focused** – Pemrosesan berbasis stream meminimalkan jejak memori.

## Prasyarat
- .NET 6.0 atau lebih baru (atau .NET Core 3.1+ / .NET Framework 4.5+).  
- Paket NuGet Aspose.Zip untuk .NET terinstal (`Install-Package Aspose.Zip`).  
- Pemahaman dasar tentang C# dan I/O file.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Pilih format arsip yang Anda butuhkan
Tentukan apakah **TarBz2**, **TarGz**, **TarLz**, **TarXz**, atau **TarZ** paling cocok dengan rasio kompresi dan persyaratan kompatibilitas Anda.  
- **TarBz2** – Kompresi terbaik, pemrosesan lebih lambat.  
- **TarGz** – Keseimbangan yang baik antara kecepatan dan ukuran (mencakup kata kunci sekunder *how to create targz*).  
- **TarZ** – Format warisan, berguna untuk kompatibilitas dengan alat Unix lama.

### Langkah 2: Buat instance `Archive` baru
Instansiasi kelas `Archive` dan arahkan ke jalur file output. Objek ini akan mengelola proses pengemasan dan kompresi.

### Langkah 3: Tambahkan file dan folder
Gunakan metode `AddAll` atau `AddFile` untuk menyertakan file yang ingin Anda kompres. Anda dapat mempertahankan struktur direktori dengan menambahkan folder dasar.

### Langkah 4: Atur tipe kompresi yang diinginkan
Tentukan algoritma kompresi (`CompressionType.BZip2`, `CompressionType.GZip`, dll.) saat menyimpan arsip. Di sinilah Anda benar‑benar **mengompres file menjadi TarBz2** atau format lain.

### Langkah 5: Simpan arsip
Panggil `Save` dengan enum format yang sesuai (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, dll.). Perpustakaan menulis kontainer TAR dan menerapkan kompresi yang dipilih dalam satu langkah.

### Langkah 6: Mengekstrak arsip dengan kata sandi
Jika Anda perlu **mengekstrak entri arsip dengan kata sandi yang berbeda** (kata kunci sekunder *password protected zip extraction*), buka arsip, temukan setiap entri, tetapkan kata sandinya, lalu ekstrak.

### Langkah 7: Verifikasi hasil
Setelah ekstraksi, bandingkan ukuran file dan checksum untuk memastikan arsip dibuat dan dibongkar dengan benar.

## Kasus Penggunaan Umum
- **Backup utilities** – Simpan cadangan harian sebagai `.tar.bz2` untuk meminimalkan biaya penyimpanan.  
- **Cross‑platform data exchange** – Format berbasis Tar dipahami secara universal di Linux, macOS, dan Windows.  
- **Secure distribution** – Lindungi entri individual dengan kata sandi untuk lingkungan yang mengutamakan kepatuhan.

## Pemecahan Masalah & Tips
- **Large archives** – Gunakan API streaming (`Archive.CreateEntryFromFile`) untuk menghindari memuat seluruh file ke memori.  
- **Password mismatches** – Pastikan kata sandi yang ditetapkan pada setiap `ArchiveEntry` cocok dengan yang digunakan saat ekstraksi; jika tidak, Anda akan menemukan `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 tidak mendukung level kompresi khusus; jika Anda memerlukan kontrol lebih halus, pertimbangkan TarLz atau TarXz.

## Pertanyaan yang Sering Diajukan

**Q: How do I create a TarGz archive?**  
A: Set the compression type to `CompressionType.GZip` and the format to `ArchiveFormat.TarGz` when calling `Save`.  

**Q: Can I extract a password‑protected archive without knowing the password?**  
A: No. Each entry must be supplied with the correct password; otherwise extraction will fail.  

**Q: Does Aspose.Zip support extracting archives with different passwords per entry?**  
A: Yes. You can assign a password to each `ArchiveEntry` individually before extraction.  

**Q: Which format gives the best compression?**  
A: TarBz2 typically provides the highest compression ratio, followed by TarLz and TarXz. TarGz offers a good speed‑to‑size balance.  

**Q: Is there a limit to the number of files I can add to a TAR archive?**  
A: Practically no, but extremely large archives may benefit from splitting into multiple parts for easier handling.  

## Tutorial Ekstraksi Arsip dan Format

### [Mengompres File ke TarBz2 dengan Aspose.Zip untuk .NET](./compress-to-tar-bz2/)
Pelajari cara mengompres file ke format TarBz2 di .NET menggunakan Aspose.Zip. Ikuti panduan langkah‑per‑langkah kami untuk kompresi file yang efisien.

### [Mengompres ke TarGz dengan Aspose.Zip untuk .NET](./compress-to-tar-gz/)
Jelajahi kompresi file yang efisien di .NET dengan Aspose.Zip. Kompres ke TarGz dengan mudah.

### [Mengompres ke TarLz dengan Aspose.Zip untuk .NET](./compress-to-tar-lz/)
Kompres file di .NET dengan Aspose.Zip secara mudah. Pelajari cara membuat arsip TarLz langkah demi langkah.

### [Mengompres ke TarXz dengan Aspose.Zip untuk .NET](./compress-to-tar-xz/)
Pelajari cara mengompres file ke format TarXz di .NET menggunakan Aspose.Zip. Ikuti panduan langkah‑per‑langkah kami untuk penyimpanan dan transmisi file yang efisien.

### [Mengompres ke TarZ dengan Aspose.Zip untuk .NET](./compress-to-tar-z/)
Jelajahi kompresi langkah‑per‑langkah ke TarZ menggunakan Aspose.Zip untuk .NET. Penanganan file yang efisien untuk proyek .NET Anda.

### [Mengekstrak Entri Arsip dengan Kata Sandi Berbeda di Aspose.Zip untuk .NET](./extract-archive-different-passwords/)
Pelajari cara mengekstrak entri arsip dengan kata sandi yang berbeda di Aspose.Zip untuk .NET. Tingkatkan keamanan dan fleksibilitas dalam aplikasi Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-02-20  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11  
**Penulis:** Aspose  

---