---
title: Kompres File menggunakan FileInfo di Aspose.Zip untuk .NET
linktitle: Kompres File menggunakan FileInfo
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Pelajari cara mengompresi file menggunakan fileinfo dengan Aspose.Zip untuk .NET. Ikuti panduan langkah demi langkah kami untuk pengelolaan file yang efisien.
type: docs
weight: 11
url: /id/net/file-compression/compress-files-fileinfo/
---
## Perkenalan

Selamat datang di panduan komprehensif kami tentang mengompresi file menggunakan Aspose.Zip untuk .NET! Jika Anda ingin mengoptimalkan penyimpanan atau transmisi file Anda, Aspose.Zip adalah solusi tepat Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses mengompresi file menggunakan kelas FileInfo, memberikan panduan langkah demi langkah yang mendetail. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Zip untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Zip. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/zip/net/).

2. Direktori Dokumen: Siapkan direktori di sistem Anda untuk menyimpan file yang ingin Anda kompres.

## Impor Namespace

Dalam proyek .NET Anda, sertakan namespace yang diperlukan:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Hal pertama yang pertama, tentukan direktori tempat dokumen Anda disimpan. Anda dapat menggunakan kode berikut:

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Kompres File menggunakan FileInfo

 Sekarang, mari masuk ke inti prosesnya. Kami akan menggunakan`FileInfo` kelas bersama dengan Aspose.Zip untuk mengompresi file. Ikuti langkah ini:

### Langkah 2.1: Buka File Zip

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Langkah 2.2: Buat Objek FileInfo

 Membuat`FileInfo` objek untuk file yang ingin Anda kompres:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### Langkah 2.3: Buat Arsip dan Tambahkan Entri

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Langkah 2.4: Simpan File Zip

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Selamat! Anda telah berhasil mengompresi file menggunakan kelas FileInfo di Aspose.Zip untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara mengompresi file secara efisien menggunakan Aspose.Zip untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat meningkatkan kemampuan manajemen file dan mengoptimalkan penggunaan ruang. Bereksperimenlah dengan berbagai jenis dan ukuran file untuk merasakan potensi penuh Aspose.Zip.

## FAQ

### Q1: Apakah Aspose.Zip kompatibel dengan semua jenis file?

A1: Aspose.Zip mendukung berbagai jenis file, memastikan fleksibilitas dalam kompresi.

### Q2: Bisakah saya menggunakan Aspose.Zip untuk proyek komersial?

 A2: Tentu saja! Kunjungi kami[halaman pembelian](https://purchase.aspose.com/buy) untuk mengeksplorasi opsi lisensi.

### Q3: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Zip?

 A3: Bergabunglah dengan komunitas kami di[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan dan diskusi.

### Q4: Apakah tersedia uji coba gratis?

 A4: Ya, Anda bisa mengambilnya[uji coba gratis di sini](https://releases.aspose.com/).

### Q5: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?

 A5: Kunjungi[Link ini](https://purchase.aspose.com/temporary-license/) untuk informasi tentang cara memperoleh izin sementara.