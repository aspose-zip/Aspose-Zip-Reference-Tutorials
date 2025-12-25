---
date: 2025-12-25
description: Pelajari cara membuat file 7z dengan Aspose.Zip untuk .NET, mencakup
  tujuh metode kompresi zip seperti LZMA2, BZip2, dan Store. Sempurna untuk skenario
  mengompres folder ke 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Membuat File 7z – Tutorial Aspose.Zip untuk .NET
url: /id/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat File 7z – Tutorial Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **cara membuat 7z** secara programatis dalam aplikasi .NET, Anda berada di tempat yang tepat. Aspose.Zip untuk .NET memudahkan pembuatan arsip Seven Zip dengan salah satu algoritma kompresi yang didukung, baik Anda ingin **compress folder to 7z** untuk distribusi atau sekadar membutuhkan solusi **seven zip archive .net** yang andal. Dalam panduan ini kami akan membahas tiga metode kompresi populer—LZMA2, BZip2, dan Store (tanpa kompresi)—dan menunjukkan cara menghasilkan file 7z hanya dengan beberapa baris kode C#.

## Jawaban Cepat
- **Pustaka apa yang harus saya gunakan?** Aspose.Zip untuk .NET menyediakan rangkaian fitur Seven Zip paling lengkap.  
- **Metode kompresi mana yang memberikan rasio terbaik?** LZMA2 biasanya memberikan kompresi tertinggi untuk data campuran.  
- **Bisakah saya membuat 7z tanpa kompresi?** Ya—gunakan metode Store (tanpa kompresi).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis tersedia; lisensi diperlukan untuk penggunaan produksi.  
- **Apakah ini kompatibel dengan .NET 6/7?** Tentu—Aspose.Zip mendukung .NET Framework, .NET Core, dan .NET 5+.

## Apa Saja Metode Kompresi Seven Zip?

Seven Zip mendukung beberapa algoritma, masing‑masing dioptimalkan untuk skenario berbeda:

* **LZMA2** – rasio kompresi tinggi, ideal untuk file berukuran besar dan tipe campuran.  
* **BZip2** – kompresi solid tetapi lebih lambat dibanding LZMA2; berguna ketika kompatibilitas dengan alat lama diperlukan.  
* **Store** – tanpa kompresi; sempurna ketika Anda hanya membutuhkan arsip tanpa pengurangan ukuran (misalnya, untuk mempertahankan cap waktu file asli).

Memahami **seven zip compression methods** ini membantu Anda memilih pengaturan yang tepat untuk proyek Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Pengetahuan dasar tentang C# dan Visual Studio.  
- Pustaka Aspose.Zip untuk .NET terpasang. Unduh dari halaman resmi **[here](https://releases.aspose.com/zip/net/)**.  
- Sebuah folder (`dataDir`) yang berisi file‑file yang ingin Anda arsipkan.

## Impor Namespace

Pertama, tambahkan namespace yang diperlukan ke file C# Anda:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Kelas‑kelas ini memberi Anda akses ke pengaturan kompresi dan penanganan arsip.

## Kompresi LZMA2 – Cara Membuat 7z dengan Rasio Maksimum

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

> **Tip pro:** LZMA2 bekerja paling baik ketika file sumber berukuran lebih besar dari 1 MB. Untuk banyak file kecil, BZip2 mungkin lebih cepat.

## Kompresi BZip2 – Pilihan Seimbang

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 menawarkan kompresi solid sambil mempertahankan kecepatan yang wajar, menjadikannya pilihan cadangan yang baik ketika LZMA2 tidak didukung oleh lingkungan target.

## Store (Tanpa Kompresi) – Ketika Ukuran Tidak Penting

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Gunakan metode Store jika Anda hanya perlu menggabungkan file tanpa mengubah ukuran mereka—sempurna untuk mempertahankan cap waktu asli atau ketika arsip akan diekstrak secara langsung.

## Kasus Penggunaan Umum

| Skenario | Metode yang Direkomendasikan |
|----------|------------------------------|
| Distribusikan installer besar | LZMA2 |
| Bagikan log dengan alat legacy | BZip2 |
| Paket file untuk ekstraksi cepat | Store (tanpa kompresi) |
| Perlu **compress folder to 7z** secara langsung di layanan web | LZMA2 (untuk rasio terbaik) |

## Pemecahan Masalah & Tips

- **File tidak muncul di arsip?** Pastikan `dataDir` mengarah ke direktori yang benar dan proses memiliki izin baca.  
- **Arsip gagal dibuka pada versi 7‑Zip yang lebih lama?** Gunakan BZip2 atau Store, karena LZMA2 mungkin memerlukan perpustakaan dekompresi yang lebih baru.  
- **Bottleneck kinerja?** Untuk kumpulan data yang sangat besar, pertimbangkan streaming arsip alih‑alih memuat semua entri ke memori.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Zip untuk .NET dengan tipe file apa pun?**  
J: Ya, Aspose.Zip mendukung berbagai format file, memungkinkan Anda mengompres dan mendekompres hampir semua tipe file.

**T: Apakah tersedia versi percobaan gratis untuk Aspose.Zip untuk .NET?**  
J: Ya, Anda dapat memperoleh versi percobaan **[here](https://releases.aspose.com/)**.

**T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Zip untuk .NET?**  
J: Referensi API lengkap tersedia **[here](https://reference.aspose.com/zip/net/)**.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip untuk .NET?**  
J: Lisensi sementara dapat diperoleh **[here](https://purchase.aspose.com/temporary-license/)**.

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
J: Anda dapat mencari dukungan di **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Terakhir Diperbarui:** 2025-12-25  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.12  
**Penulis:** Aspose  

---