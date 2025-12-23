---
date: 2025-12-23
description: Pelajari cara mengekstrak arsip RAR di .NET menggunakan Aspose.Zip. Panduan
  langkah demi langkah untuk mendekompresi file RAR, mengekstrak RAR ke folder, dan
  membaca file RAR dengan C#.
linktitle: Decompressing a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengekstrak Arsip RAR dengan Aspose.Zip untuk .NET
url: /id/net/rar-archive/decompress-rar-archive/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekstrak Arsip RAR dengan Aspose.Zip untuk .NET

## Pendahuluan

Dalam pengembangan .NET, mengetahui **cara mengekstrak RAR** dengan cepat dapat menghemat waktu Anda dan menyederhanakan penanganan file. Aspose.Zip untuk .NET menawarkan API yang sederhana untuk **dekompresi arsip RAR**, **ekstrak RAR ke folder**, dan bahkan **baca file RAR C#**. Panduan ini akan membawa Anda melalui setiap langkah, mulai dari menyiapkan lingkungan hingga mengekstrak file ke disk.

## Jawaban Cepat
- **Perpustakaan apa yang mendukung ekstraksi RAR di .NET?** Aspose.Zip untuk .NET.  
- **Berapa baris kode yang diperlukan untuk mengekstrak arsip RAR?** Sekitar 10 baris, termasuk pengaturan.  
- **Apakah saya dapat mengekstrak RAR ke folder tertentu?** Ya, gunakan `ExtractToDirectory` untuk menentukan folder output.  
- **Apakah lisensi diperlukan untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Prasyarat

Sebelum memulai tutorial ini, pastikan Anda memiliki hal‑hal berikut:

- Visual Studio: Pastikan Anda memiliki instalasi Visual Studio yang berfungsi, karena kita akan menggunakannya untuk menulis dan menjalankan kode .NET.

- Aspose.Zip untuk .NET: Unduh dan instal perpustakaan Aspose.Zip untuk .NET. Anda dapat menemukannya [di sini](https://releases.aspose.com/zip/net/).

- Direktori Sumber Daya: Buat sebuah direktori di sistem Anda untuk menyimpan sumber daya yang diperlukan untuk tutorial ini. Direktori ini akan disebut "Your Document Directory" dalam contoh kode.

- Arsip RAR: Dapatkan file arsip RAR yang ingin Anda dekompres untuk tutorial ini. Anda dapat menggunakan milik Anda sendiri atau menemukan satu untuk tujuan pengujian.

## Impor Namespace

Sebelum masuk ke kode, pastikan kita telah mengimpor namespace yang tepat:

```csharp
using System.IO;
using Aspose.Zip;
using Aspose.Zip.Rar;
```

## Langkah 1: Atur Direktori Sumber Daya (c# extract rar archive)

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## Langkah 2: Buka Arsip RAR

```csharp
//ExStart: DecompressRarArchive
using (FileStream fs = File.OpenRead(dataDir + "your_archive.rar"))
{
    using (RarArchive archive = new RarArchive(fs))
    {
        // Rest of the code goes here.
    }
}
//ExEnd: DecompressRarArchive 
```

## Langkah 3: Ekstrak ke Direktori (extract rar to folder)

```csharp
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
```

Dalam tiga langkah sederhana ini, Anda telah berhasil **mengekstrak arsip RAR** menggunakan Aspose.Zip untuk .NET! Pastikan untuk menyesuaikan jalur file dan nama sesuai dengan pengaturan Anda.

## Mengapa Ini Penting

Mengekstrak file RAR secara programatis adalah kebutuhan umum ketika menangani impor data batch, pembuatan laporan otomatis, atau migrasi konten. Dengan memanfaatkan Aspose.Zip, Anda menghindari ketergantungan eksternal dan menjaga seluruh alur kerja di dalam solusi .NET Anda.

## Kesimpulan

Selamat! Anda baru saja menambahkan alat berharga ke dalam kotak peralatan pemrograman Anda dengan menguasai **cara mengekstrak RAR** menggunakan Aspose.Zip untuk .NET. Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsionalitas yang ditawarkan oleh Aspose.Zip untuk .NET di [dokumentasi](https://reference.aspose.com/zip/net/).

## FAQ

### Apakah saya dapat menggunakan Aspose.Zip untuk .NET dengan format arsip lain?
Saat ini, Aspose.Zip untuk .NET terutama mendukung format arsip ZIP dan RAR.

### Apakah ada versi percobaan yang tersedia?
Ya, Anda dapat mengunduh versi percobaan gratis [di sini](https://releases.aspose.com/).

### Bagaimana cara saya mendapatkan dukungan komunitas?
Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas.

### Bisakah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial?
Ya, Anda dapat membeli lisensi [di sini](https://purchase.aspose.com/buy).

### Apakah lisensi sementara tersedia?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

## Pertanyaan yang Sering Diajukan

**T:** Bagaimana cara membaca file RAR di C# tanpa mengekstraknya?  
**J:** Anda dapat menenumerasi entri menggunakan `RarArchive` dan membaca aliran secara langsung, tetapi ekstraksi penuh biasanya disarankan untuk sebagian besar skenario.

**T:** Bagaimana jika arsip RAR dilindungi kata sandi?  
**J:** Aspose.Zip saat ini tidak mendukung file RAR yang terenkripsi; Anda harus mendekripsinya terlebih dahulu.

**T:** Bisakah saya mengekstrak beberapa arsip RAR dalam sebuah loop?  
**J:** Ya, bungkus logika ekstraksi dalam loop `foreach` yang mengiterasi daftar file Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-12-23  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11 (terbaru)  
**Penulis:** Aspose