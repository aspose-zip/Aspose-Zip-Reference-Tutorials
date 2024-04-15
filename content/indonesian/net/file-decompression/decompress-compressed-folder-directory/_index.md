---
title: Dekompresi Folder Terkompresi ke Direktori di Aspose.Zip untuk .NET
linktitle: Dekompresi Folder Terkompresi ke Direktori
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Buka potensi Aspose.Zip untuk .NET! Pelajari cara mendekompresi folder dengan mudah menggunakan panduan langkah demi langkah ini. Selami dunia kompresi dan ekstraksi yang mulus.
type: docs
weight: 14
url: /id/net/file-decompression/decompress-compressed-folder-directory/
---
## Perkenalan

Selamat datang di dunia Aspose.Zip untuk .NET, perpustakaan tangguh yang memberdayakan pengembang untuk menangani folder terkompresi dengan mudah. Dalam tutorial ini, kita akan mempelajari proses mendekompresi folder terkompresi ke direktori menggunakan Aspose.Zip untuk .NET. Bersiaplah saat kami membawa Anda melalui setiap langkah secara mendetail, mengungkap seluk-beluk alat canggih ini.

## Prasyarat

Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Zip untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Zip untuk dokumentasi .NET](https://reference.aspose.com/zip/net/).

## Impor Namespace

Dalam proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang komprehensif.

## Langkah 1: Membuka Folder Terkompresi

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

 Mulailah dengan membuka folder terkompresi menggunakan a`FileStream`Sesuaikan jalur file sesuai struktur proyek Anda.

## Langkah 2: Membuat Instans Arsip

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

 Buat contoh sebuah`Archive` objek, melewati`zipFile` streaming dan menyediakan opsi pemuatan opsional, seperti kata sandi dekripsi dalam kasus ini.

## Langkah 3: Mengekstrak ke Direktori

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

 Terakhir, gunakan`ExtractToDirectory` metode untuk mendekompresi dan mengekstrak isi folder terkompresi ke direktori yang ditentukan.

Ulangi langkah-langkah ini untuk folder terkompresi lainnya, pastikan integrasi lancar dengan Aspose.Zip untuk .NET.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mendekompresi folder terkompresi ke direktori menggunakan Aspose.Zip untuk .NET. Pustaka ini terbukti menjadi aset yang sangat berharga bagi pengembang yang menangani data terkompresi dalam proyek mereka.

## FAQ

### Q1: Apakah Aspose.Zip untuk .NET kompatibel dengan berbagai format kompresi?

A1: Ya, Aspose.Zip untuk .NET mendukung format kompresi populer seperti ZIP, GZIP, dan lainnya.

### Q2: Bisakah saya menggunakan Aspose.Zip untuk .NET di proyek komersial dan non-komersial?

A2: Tentu saja, Anda dapat menggunakan Aspose.Zip untuk .NET baik dalam aplikasi komersial maupun non-komersial.

### Q3: Apakah tersedia uji coba gratis untuk Aspose.Zip untuk .NET?

 A3: Ya, Anda dapat menjelajahi fitur-fitur dengan uji coba gratis dengan mengunjungi[Di Sini](https://releases.aspose.com/).

### Q4: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Zip untuk .NET?

 A4: Carilah bantuan dari komunitas Aspose.Zip di[forum dukungan](https://forum.aspose.com/c/zip/37).

### Q5: Apakah saya memerlukan lisensi sementara untuk menguji Aspose.Zip untuk .NET?

 A5: Ya, Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.