---
title: Mendekompresi File Tunggal dengan Aspose.Zip untuk .NET
linktitle: Mendekompresi Satu File
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Jelajahi dunia dekompresi file yang lancar dengan Aspose.Zip untuk .NET. Tangani file terkompresi dengan mudah di proyek C# Anda.
weight: 12
url: /id/net/file-decompression/decompress-single-file/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mendekompresi File Tunggal dengan Aspose.Zip untuk .NET

## Perkenalan

Dalam bidang pengembangan .NET, Aspose.Zip berdiri sebagai solusi tangguh untuk menangani file terkompresi dengan kemahiran. Tutorial ini akan memandu Anda melalui proses dekompresi satu file menggunakan Aspose.Zip untuk .NET. Bergabunglah saat kami mengungkap kemampuan perpustakaan canggih ini selangkah demi selangkah.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Zip untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Zip untuk Dokumentasi .NET](https://reference.aspose.com/zip/net/).

- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET yang fungsional, termasuk Visual Studio atau IDE lain yang kompatibel.

- Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar pemrograman C#.

Sekarang, mari kita mengotori tangan kita dengan beberapa kode!

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan untuk memulai perjalanan Aspose.Zip Anda:

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## Mendekompresi File Tunggal dengan Aspose.Zip untuk .NET

### Langkah 1: Atur Direktori Dokumen Anda

 Mulailah dengan menentukan direktori tempat dokumen Anda disimpan. Mengganti`"Your Document Directory"` dengan jalur sebenarnya.

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Buat File Terkompresi

Manfaatkan cuplikan kode berikut untuk membuat file terkompresi yang nantinya akan kita dekompresi.

```csharp
CompressSingleFile.Run();
```

### Langkah 3: Dekompresi File

Sekarang, mari selami inti permasalahannya – mendekompresi satu file. Gunakan kode berikut:

```csharp
// ExStart: DekompresiSingleFile
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

Kode ini secara efisien menangani proses dekompresi, memberikan pembaruan kemajuan waktu nyata.

## Kesimpulan

Selamat! Anda telah berhasil menavigasi seluk-beluk mendekompresi satu file menggunakan Aspose.Zip untuk .NET. Manfaatkan kekuatan perpustakaan ini untuk menyederhanakan tugas manipulasi file Anda dengan mudah.

## FAQ

### Q1: Bisakah saya mengompresi banyak file menggunakan Aspose.Zip untuk .NET?

A1: Ya, Aspose.Zip untuk .NET mendukung kompresi banyak file. Lihat dokumentasi untuk petunjuk rinci.

### Q2: Apakah Aspose.Zip kompatibel dengan .NET Core?

A2: Tentu saja! Aspose.Zip terintegrasi secara mulus dengan .NET Framework dan .NET Core.

### Q3: Bagaimana cara menangani file terkompresi yang dilindungi kata sandi?

A3: Aspose.Zip menyediakan metode untuk bekerja dengan arsip yang dilindungi kata sandi. Konsultasikan dokumentasi untuk panduan.

### Q4: Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Zip?

 A4: Tinjau informasi perizinan di[Asumsikan situs web](https://purchase.aspose.com/buy).

### Q5: Di mana saya bisa mencari bantuan jika saya mengalami masalah?

 A5: Kunjungi[Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) untuk dukungan masyarakat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
