---
date: 2026-06-29
description: Pelajari cara mengompres folder ke 7z dengan Aspose.Zip untuk .NET, mencakup
  metode kompresi seven zip seperti LZMA2, BZip2, dan Store. Sempurna untuk membuat
  arsip 7z secara programatis.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip dengan Berbagai Metode Kompresi
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres Folder ke 7z – Tutorial Aspose.Zip untuk .NET
url: /id/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengompres Folder ke 7z – Tutorial Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **compress folder to 7z** arsip secara programatis dalam aplikasi .NET, Anda berada di tempat yang tepat. Aspose.Zip untuk .NET mempermudah menghasilkan arsip Seven Zip dengan salah satu algoritma kompresi yang didukung, baik Anda ingin menggabungkan seluruh direktori untuk distribusi atau hanya membutuhkan solusi **seven zip archive .net** yang andal. Dalam panduan ini kami akan membahas tiga metode kompresi populer—LZMA2, BZip2, dan Store (tanpa kompresi)—dan menunjukkan secara tepat cara menghasilkan file 7z hanya dengan beberapa baris kode C#.

## Jawaban Cepat

- **Library apa yang harus saya gunakan?** Aspose.Zip for .NET menyediakan set fitur Seven Zip paling lengkap.  
- **Metode kompresi mana yang memberikan rasio terbaik?** LZMA2 biasanya memberikan kompresi tertinggi untuk data campuran.  
- **Bisakah saya membuat 7z tanpa kompresi?** Ya—gunakan metode Store (tanpa kompresi).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis tersedia; lisensi diperlukan untuk penggunaan produksi.  
- **Apakah ini kompatibel dengan .NET 6/7?** Tentu—Aspose.Zip mendukung .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10.

## Apa Metode Kompresi Seven Zip?

Seven Zip mendukung beberapa algoritma, masing‑masing dioptimalkan untuk skenario yang berbeda. **LZMA2** menawarkan rasio kompresi tertinggi (sering 30‑40 % lebih kecil dibanding BZip2), **BZip2** memberikan kompresi solid dengan dukungan alat warisan yang lebih luas, dan **Store** hanya mengarsipkan file tanpa memperkecilnya, mempertahankan cap waktu asli dengan sempurna.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang C# dan Visual Studio.  
- Perpustakaan Aspose.Zip untuk .NET terpasang. Unduh dari halaman resmi **[here](https://releases.aspose.com/zip/net/)**.  
- Sebuah folder (`dataDir`) yang berisi file yang ingin Anda arsipkan.

## Impor Namespace

Pertama, tambahkan namespace yang diperlukan ke file C# Anda:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Kelas-kelas ini memberi Anda akses ke pengaturan kompresi dan penanganan arsip.

## Kompresi LZMA2 – Cara Membuat 7z dengan Rasio Maksimum

Kelas `Archive` mewakili arsip 7z yang dapat berisi banyak file.  
Algoritma LZMA2 memberikan rasio kompresi tertinggi di antara metode yang didukung. Ia bekerja dengan membagi input menjadi blok‑blok dan menerapkan kompresi kamus yang canggih. Dalam Aspose.Zip Anda mengatur `CompressionMethod` menjadi `CompressionMethod.Lzma2` pada objek `Archive` sebelum menambahkan file.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2 bekerja paling baik ketika file sumber lebih besar dari 1 MB. Untuk banyak file kecil, BZip2 mungkin lebih cepat.

## Kompresi BZip2 – Pilihan Seimbang

Kelas `Archive` mewakili arsip 7z yang dapat berisi banyak file.  
BZip2 menawarkan kompresi solid dengan kompatibilitas yang baik untuk alat‑alat lama. Ia menggunakan transformasi Burrows‑Wheeler dan pengkodean Huffman untuk mengurangi ukuran. Dalam Aspose.Zip Anda memilih `CompressionMethod.BZip2` saat mengonfigurasi instance `Archive`, yang menyeimbangkan kecepatan dan rasio kompresi untuk kebanyakan file teks dan biner.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 menawarkan kompresi solid sambil mempertahankan kecepatan yang wajar, menjadikannya alternatif yang baik ketika LZMA2 tidak didukung oleh lingkungan target.

## Store (Tanpa Kompresi) – Ketika Ukuran Tidak Penting

Kelas `Archive` mewakili arsip 7z yang dapat berisi banyak file.  
Metode Store membuat arsip tanpa mengompresi data. Ia hanya menyalin file asli ke dalam kontainer 7z, mempertahankan cap waktu dan struktur direktori. Untuk menggunakannya di Aspose.Zip, atur `CompressionMethod.Store` pada `Archive` sebelum menambahkan file yang ingin Anda bundel.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Gunakan metode Store jika Anda hanya perlu menggabungkan file bersama tanpa mengubah ukuran mereka—sempurna untuk mempertahankan cap waktu asli atau ketika arsip akan dibuka tanpa kompresi secara langsung.

## Bagaimana cara menambahkan file ke 7z?

Tambahkan file ke arsip 7z dengan membuat instance `Archive`, mengatur `CompressionMethod` yang diinginkan, dan memanggil `AddAllFiles(dataDir)`. Metode ini memindai folder yang ditentukan secara rekursif, mempertahankan hierarki direktori di dalam arsip. Pendekatan ini memungkinkan Anda **compress folder to 7z** dengan satu baris kode setelah konfigurasi awal.

## Kasus Penggunaan Umum

| Skenario | Metode yang Direkomendasikan |
|----------|------------------------------|
| Mendistribusikan installer besar | LZMA2 |
| Berbagi log dengan alat warisan | BZip2 |
| Mengemas file untuk ekstraksi cepat | Store (no compression) |
| Perlu **compress folder to 7z** secara langsung dalam layanan web | LZMA2 (for best ratio) |

## Pemecahan Masalah & Tips

- **File yang hilang dalam arsip?** Pastikan `dataDir` mengarah ke direktori yang benar dan proses memiliki izin baca.  
- **Arsip gagal dibuka pada versi 7‑Zip yang lebih lama?** Gunakan BZip2 atau Store, karena LZMA2 mungkin memerlukan perpustakaan dekompresi yang lebih baru.  
- **Bottleneck kinerja?** Untuk kumpulan data yang sangat besar, pertimbangkan streaming arsip alih-alih memuat semua entri ke dalam memori.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Zip untuk .NET dengan jenis file apa pun?**  
A: Ya, Aspose.Zip mendukung berbagai format file, memungkinkan Anda mengompres dan mendekompres hampir semua jenis file.

**Q: Apakah tersedia percobaan gratis untuk Aspose.Zip untuk .NET?**  
A: Ya, Anda dapat memperoleh percobaan gratis **[here](https://releases.aspose.com/)**.

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Zip untuk .NET?**  
A: Referensi API lengkap tersedia **[here](https://reference.aspose.com/zip/net/)**.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip untuk .NET?**  
A: Lisensi sementara dapat diperoleh **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Anda dapat mencari dukungan di **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Terakhir Diperbarui:** 2026-06-29  
**Diuji Dengan:** Aspose.Zip for .NET 24.12  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [kompres file c# – Buat arsip 7z dengan Aspose.Zip untuk .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Cara Mengompres Folder Menggunakan Aspose.Zip untuk .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Cara Mengompres LZMA di Aspose.Zip untuk .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}