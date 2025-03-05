---
title: Mendekripsi Arsip RAR dengan Aspose.Zip untuk .NET
linktitle: Mendekripsi Arsip RAR
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Buka kunci arsip RAR terenkripsi dengan mudah menggunakan Aspose.Zip untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar dan dekripsi yang efisien.
type: docs
weight: 12
url: /id/net/rar-archive/decrypt-rar-archive/
---

## Perkenalan

Membuka kunci konten arsip RAR yang dilindungi kata sandi bisa menjadi tugas yang menakutkan, namun dengan Aspose.Zip untuk .NET, prosesnya menjadi mudah dan efisien. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah mendekripsi arsip RAR menggunakan perpustakaan Aspose.Zip. Baik Anda seorang pengembang berpengalaman atau penggemar coding, panduan ini akan membantu Anda mengintegrasikan fungsi dekripsi dengan lancar ke dalam aplikasi .NET Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Zip untuk Perpustakaan .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Zip di proyek .NET Anda. Anda dapat mengunduhnya dari[Dokumentasi Aspose.Zip](https://reference.aspose.com/zip/net/).

2. Direktori Dokumen: Siapkan direktori tempat arsip RAR terenkripsi Anda berada. Ganti "Direktori Dokumen Anda" dalam kode contoh dengan jalur sebenarnya ke direktori ini.

## Impor Namespace

Mari kita mulai dengan mengimpor namespace yang diperlukan untuk menggunakan perpustakaan Aspose.Zip secara efektif. Tambahkan baris berikut ke bagian atas file .NET Anda:

```csharp
//ExStart: ImporNamespace
using Aspose.Zip;
using System.IO;
//ExEnd: ImporNamespace
```

## Langkah 1: Buka Arsip RAR Terenkripsi

Mulailah dengan membuka arsip RAR terenkripsi. Pada contoh kode, ganti "encrypted.rar" dengan nama file RAR terenkripsi Anda.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Lanjutkan ke langkah berikutnya di sini...
}
```

## Langkah 2: Tentukan Kata Sandi Dekripsi

Tentukan kata sandi dekripsi untuk arsip RAR. Dalam contoh, kata sandi "p@s$" digunakan. Gantilah dengan kata sandi sebenarnya yang Anda tetapkan untuk file RAR terenkripsi Anda.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DekripsiRarArchive_Step2
    // Lanjutkan ke langkah berikutnya di sini...
}
```

## Langkah 3: Ekstrak Konten ke Direktori

Sekarang, ekstrak isi arsip RAR ke direktori tertentu. Ganti "DecompressRar_out" dengan jalur tempat Anda ingin menyimpan file yang didekripsi.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

Ulangi langkah-langkah ini untuk setiap arsip RAR yang perlu Anda dekripsi, untuk memastikan integrasi Aspose.Zip untuk .NET yang lancar ke dalam proyek Anda.

## Kesimpulan

Selamat! Anda telah berhasil mendekripsi arsip RAR menggunakan Aspose.Zip untuk .NET. Pustaka yang kuat ini menyederhanakan proses kompleks untuk membuka kunci arsip yang dilindungi kata sandi, menjadikannya alat yang sangat berharga bagi pengembang yang bekerja dengan aplikasi .NET.

## Pertanyaan yang Sering Diajukan (FAQ)

### Apakah Aspose.Zip untuk .NET kompatibel dengan semua versi arsip RAR?
Aspose.Zip untuk .NET mendukung berbagai versi arsip RAR, memastikan kompatibilitas dengan berbagai macam file.

### Bisakah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial?
 Ya, Aspose.Zip untuk .NET tersedia untuk penggunaan komersial. Mengunjungi[halaman pembelian](https://purchase.aspose.com/buy) untuk rincian perizinan.

### Apakah lisensi sementara tersedia untuk tujuan pengujian?
 Ya, Anda bisa mendapatkan lisensi sementara untuk pengujian dari[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dukungan tambahan atau diskusi komunitas?
 Mengunjungi[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan dan diskusi komunitas.

### Bagaimana cara mengakses dokumentasi Aspose.Zip untuk .NET?
 Itu[dokumentasi](https://reference.aspose.com/zip/net/) memberikan informasi komprehensif tentang penggunaan Aspose.Zip untuk .NET.
