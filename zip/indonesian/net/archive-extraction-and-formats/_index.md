---
date: 2026-01-28
description: Pelajari cara mengekstrak arsip dengan kata sandi, mengompres file ke
  TarBz2, dan membuat arsip TarGz menggunakan Aspose.Zip untuk .NET. Tingkatkan efisiensi
  penyimpanan dan keamanan.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ekstrak Arsip dengan Kata Sandi dan Kompres ke TarBz2 (.NET)
url: /id/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak Arsip dengan Kata Sandi dan Kompres ke TarBz2 (.NET)

Dalam panduan ini Anda akan menemukan **cara mengekstrak arsip dengan kata sandi** dan juga menguasai **kompres file ke TarBz2** menggunakan Aspose.Zip untuk .NET. Baik Anda membangun layanan cadangan, klien penyimpanan awan, atau pipeline pemrosesan data, teknik ini memungkinkan Anda mengurangi jejak penyimpanan, mempercepat transfer, dan menjaga data sensitif tetap terlindungi.

## Jawaban Cepat
- **Apa itu TarBz2?** Arsip terkompresi yang menggabungkan pengemasan TAR dengan kompresi BZIP2 untuk rasio kompresi tinggi.  
- **Mengapa memilih Aspose.Zip untuk .NET?** Ini menyediakan API tunggal yang fluida untuk banyak format arsip tanpa ketergantungan native.  
- **Bisakah saya membuat arsip TarGz?** Ya – Aspose.Zip mendukung TarGz, TarLz, TarXz, TarZ, dan lainnya.  
- **Bagaimana cara mengekstrak arsip yang dilindungi kata sandi?** Atur properti `Password` pada setiap `ArchiveEntry` sebelum ekstraksi.  
- **Apakah saya perlu lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan untuk produksi; percobaan gratis tersedia untuk evaluasi.

## Cara mengekstrak arsip dengan kata sandi menggunakan Aspose.Zip untuk .NET
Mengekstrak arsip yang **dilindungi kata sandi zip archive** cukup sederhana. Anda membuka arsip, menemukan entri yang dibutuhkan, menetapkan kata sandinya, lalu memanggil `Extract`. Pendekatan ini bekerja untuk TarBz2, TarGz, dan format lain yang didukung.

## Apa arti sebenarnya “kompres file ke TarBz2”?
Mengompres file ke TarBz2 berarti pertama-tama menggabungkan beberapa file dan direktori ke dalam satu kontainer **TAR** tunggal, kemudian menerapkan kompresi **BZIP2**. Hasilnya adalah file `.tar.bz2` yang mudah dipindahkan dan sangat terkompresi.

## Mengapa menggunakan Aspose.Zip untuk .NET dalam menangani format ini?
- **API Terpadu** – Satu perpustakaan, banyak format (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Tanpa ketergantungan native** – Berfungsi di Windows, Linux, dan macOS secara langsung.  
- **Dukungan kata sandi** – Melindungi dan mengekstrak arsip secara aman dengan kata sandi per‑entri.  
- **Berfokus pada kinerja** – Pemrosesan berbasis aliran meminimalkan penggunaan memori.

## Prasyarat
- .NET 6.0 atau yang lebih baru (atau .NET Core 3.1+ / .NET Framework 4.5+).  
- Paket NuGet Aspose.Zip untuk .NET terpasang (`Install-Package Aspose.Zip`).  
- Pengetahuan dasar tentang C# dan I/O file.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Pilih format arsip yang Anda butuhkan
Tentukan apakah **TarBz2**, **TarGz**, **TarLz**, **TarXz**, atau **TarZ** paling cocok dengan rasio kompresi dan persyaratan kompatibilitas Anda.  
- **TarBz2** – Kompresi terbaik, pemrosesan lebih lambat.  
- **TarGz** – Keseimbangan yang baik antara kecepatan dan ukuran (mencakup kata kunci sekunder *compress files to targz*).  
- **TarZ** – Format warisan untuk alat Unix lama.

### Langkah 2: Buat instance `Archive` baru
Instansiasi kelas `Archive` dan arahkan ke jalur file output. Objek ini akan mengelola proses pengemasan dan kompresi.

### Langkah 3: Tambahkan file dan folder
Gunakan metode `AddAll` atau `AddFile` untuk memasukkan file yang ingin Anda kompres. Pertahankan struktur direktori dengan menambahkan folder dasar.

### Langkah 4: Tetapkan jenis kompresi yang diinginkan
Tentukan algoritma kompresi (`CompressionType.BZip2`, `CompressionType.GZip`, dll.) saat menyimpan arsip. Di sinilah Anda benar‑benar **mengompres file ke tarbz2** atau format lain.

### Langkah 5: Simpan arsip
Panggil `Save` dengan enum format yang sesuai (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, dll.). Perpustakaan menulis kontainer TAR dan menerapkan kompresi yang dipilih dalam satu langkah.

### Langkah 6: Ekstrak arsip dengan kata sandi
Jika Anda perlu **mengekstrak entri arsip dengan kata sandi berbeda** (kata kunci sekunder *how to extract password protected archive*), buka arsip, temukan setiap entri, tetapkan kata sandinya, lalu ekstrak.

### Langkah 7: Verifikasi hasil
Setelah ekstraksi, bandingkan ukuran file dan checksum untuk memastikan arsip dibuat dan dibongkar dengan benar.

## Kasus Penggunaan Umum
- **Utilitas cadangan** – Simpan cadangan harian sebagai `.tar.bz2` untuk meminimalkan biaya penyimpanan.  
- **Pertukaran data lintas‑platform** – Format berbasis Tar dipahami secara universal di Linux, macOS, dan Windows.  
- **Distribusi aman** – Lindungi entri individual dengan kata sandi untuk lingkungan yang mengutamakan kepatuhan.

## Pemecahan Masalah & Tips
- **Arsip besar** – Gunakan API streaming (`Archive.CreateEntryFromFile`) untuk menghindari memuat seluruh file ke memori.  
- **Kecocokan kata sandi** – Pastikan kata sandi yang ditetapkan pada setiap `ArchiveEntry` cocok dengan yang digunakan saat ekstraksi; jika tidak, Anda akan menemukan `InvalidPasswordException`.  
- **Level kompresi tidak didukung** – BZIP2 tidak mendukung level kompresi khusus; jika Anda memerlukan kontrol lebih halus, pertimbangkan TarLz atau TarXz.  
- **Tip kinerja** – Saat membuat **arsip tarbz2**, aktifkan buffering pada aliran dasar untuk meningkatkan kecepatan penulisan.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara membuat arsip TarGz?**  
A: Atur jenis kompresi ke `CompressionType.GZip` dan format ke `ArchiveFormat.TarGz` saat memanggil `Save`.

**T: Bisakah saya mengekstrak arsip yang dilindungi kata sandi tanpa mengetahui kata sandinya?**  
A: Tidak. Setiap entri harus diberikan kata sandi yang benar; jika tidak, ekstraksi akan gagal.

**T: Apakah Aspose.Zip mendukung mengekstrak arsip dengan kata sandi berbeda per entri?**  
A: Ya. Anda dapat menetapkan kata sandi ke setiap `ArchiveEntry` secara individual sebelum ekstraksi.

**T: Format mana yang memberikan kompresi terbaik?**  
A: TarBz2 biasanya memberikan rasio kompresi tertinggi, diikuti oleh TarLz dan TarXz. TarGz menawarkan keseimbangan yang baik antara kecepatan dan ukuran.

**T: Apakah ada batas jumlah file yang dapat saya tambahkan ke arsip TAR?**  
A: Secara praktis tidak, tetapi arsip yang sangat besar mungkin lebih baik dibagi menjadi beberapa bagian untuk memudahkan penanganan.

## Tutorial Ekstraksi Arsip dan Format

### [Mengompres File ke TarBz2 dengan Aspose.Zip untuk .NET](./compress-to-tar-bz2/)
Pelajari cara mengompres file ke format TarBz2 dalam .NET menggunakan Aspose.Zip. Ikuti panduan langkah‑per‑langkah kami untuk kompresi file yang efisien.

### [Mengompres ke TarGz dengan Aspose.Zip untuk .NET](./compress-to-tar-gz/)
Jelajahi kompresi file yang efisien di .NET dengan Aspose.Zip. Kompres ke TarGz dengan mudah.

### [Mengompres ke TarLz dengan Aspose.Zip untuk .NET](./compress-to-tar-lz/)
Kompres file secara mudah di .NET dengan Aspose.Zip. Pelajari cara membuat arsip TarLz langkah‑per‑langkah.

### [Mengompres ke TarXz dengan Aspose.Zip untuk .NET](./compress-to-tar-xz/)
Pelajari cara mengompres file ke format TarXz dalam .NET menggunakan Aspose.Zip. Ikuti panduan langkah‑per‑langkah kami untuk penyimpanan dan transmisi file yang efisien.

### [Mengompres ke TarZ dengan Aspose.Zip untuk .NET](./compress-to-tar-z/)
Jelajahi kompresi langkah‑per‑langkah ke TarZ menggunakan Aspose.Zip untuk .NET. Penanganan file yang efisien untuk proyek .NET Anda.

### [Mengekstrak Entri Arsip dengan Kata Sandi Berbeda di Aspose.Zip untuk .NET](./extract-archive-different-passwords/)
Pelajari cara mengekstrak entri arsip dengan kata sandi berbeda di Aspose.Zip untuk .NET. Tingkatkan keamanan dan fleksibilitas dalam aplikasi Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose