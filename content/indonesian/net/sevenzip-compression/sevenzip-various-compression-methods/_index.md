---
title: Membuat Tujuh File Zip - Aspose.Zip untuk Tutorial .NET
linktitle: SevenZip dengan Berbagai Metode Kompresi
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Pelajari cara membuat file Seven Zip dengan Aspose.Zip untuk .NET menggunakan metode kompresi yang berbeda. Langkah mudah untuk LZMA2, BZip2, dan Store (tanpa kompresi).
type: docs
weight: 12
url: /id/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## Perkenalan

Dalam bidang pengembangan .NET, mengelola dan mengompresi file adalah tugas yang umum. Aspose.Zip untuk .NET memberikan solusi ampuh untuk bekerja dengan arsip terkompresi, menawarkan berbagai metode kompresi. Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Zip untuk .NET untuk membuat file Seven Zip dengan metode kompresi berbeda.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:

- Pemahaman dasar tentang pemrograman C#.
- Visual Studio diinstal pada mesin Anda.
-  Aspose.Zip untuk perpustakaan .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/zip/net/).

## Impor Namespace

Mulailah dengan mengimpor Namespace yang diperlukan ke dalam proyek C# Anda. Gunakan cuplikan kode berikut untuk memulai:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Kompresi LZMA2

```csharp
//ExStart: SevenZipDenganBerbagaiMetode Kompresi

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipDenganBerbagaiMetode Kompresi
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## Kompresi BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Simpan, Tanpa Kompresi

```csharp
//Simpan, tanpa kompresi
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi keserbagunaan Aspose.Zip untuk .NET dalam membuat file Seven Zip dengan berbagai metode kompresi. Apakah Anda memerlukan rasio kompresi tinggi atau memilih tanpa kompresi sama sekali, Aspose.Zip memberikan fleksibilitas untuk memenuhi kebutuhan Anda.

## FAQ

### Bisakah saya menggunakan Aspose.Zip untuk .NET dengan jenis file apa pun?
Ya, Aspose.Zip untuk .NET mendukung berbagai jenis file, memungkinkan Anda mengompresi dan mendekompresi berbagai format.

### Apakah uji coba gratis tersedia untuk Aspose.Zip untuk .NET?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi Aspose.Zip untuk .NET?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/zip/net/).

### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Zip untuk .NET?
 Lisensi sementara dapat diperoleh[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Zip untuk .NET?
 Anda dapat mencari dukungan di[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).
