---
title: Amankan Kompresi File di .NET dengan Aspose.Zip
linktitle: Kompres File dengan Kata Sandi Individual
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Pelajari cara meningkatkan keamanan file di aplikasi .NET! Ikuti panduan langkah demi langkah kami tentang mengompresi file dengan kata sandi individual menggunakan Aspose.Zip untuk .NET.
type: docs
weight: 16
url: /id/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## Perkenalan

Dalam dunia pengembangan .NET, mengelola dan mengompresi file secara efisien adalah tugas yang penting. Aspose.Zip untuk .NET memberikan solusi ampuh untuk kompresi file, menawarkan berbagai fitur untuk menyempurnakan aplikasi Anda. Salah satu fitur penting adalah kemampuan untuk mengompresi file dengan kata sandi individual, memberikan lapisan keamanan tambahan. Dalam tutorial ini, kami akan memandu Anda melalui proses mengompresi file dengan kata sandi individual menggunakan Aspose.Zip untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Zip untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Zip di proyek .NET Anda. Anda dapat menemukan dokumentasi yang diperlukan[Di Sini](https://reference.aspose.com/zip/net/).

-  Unduh: Jika Anda belum melakukannya, unduh perpustakaan Aspose.Zip untuk .NET dari[Link ini](https://releases.aspose.com/zip/net/).

- Direktori Dokumen: Siapkan direktori berisi file yang ingin Anda kompres.

## Impor Namespace

Di proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Langkah 1: Tetapkan Jalur Direktori Sumber Daya

Tentukan jalur ke direktori sumber daya tempat file Anda berada.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Kompres File dengan Kata Sandi Individual

Sekarang, mari kita kompres file dengan kata sandi individual. Kami akan menggunakan tiga file sampel (`alice29.txt`, `asyoulik.txt` , Dan`fields.c`) dengan kata sandi berbeda untuk masing-masingnya.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Kompres setiap file dengan kata sandi individual
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Simpan file terkompresi
        archive.Save(zipFile);
    }
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mengompres file dengan kata sandi individual menggunakan Aspose.Zip untuk .NET. Fitur ini menambahkan lapisan keamanan ekstra pada file terkompresi Anda, sehingga memastikan kerahasiaan.

## Pertanyaan yang Sering Diajukan (FAQ)

### Bisakah saya menggunakan metode enkripsi berbeda untuk setiap file?
Ya, Aspose.Zip untuk .NET memungkinkan Anda menggunakan metode enkripsi berbeda untuk setiap file selama kompresi.

### Apakah ada versi uji coba yang tersedia?
 Ya, Anda dapat mengakses uji coba gratis Aspose.Zip untuk .NET[Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?
 Mengunjungi[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) atas bantuan dari masyarakat dan dukungan Aspose.

### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Zip untuk .NET?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/zip/net/).

### Bisakah saya membeli lisensi sementara untuk tujuan pengujian?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
