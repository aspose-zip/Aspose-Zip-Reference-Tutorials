---
title: Amankan File Anda - Enkripsi AES dengan Aspose.Zip
linktitle: Perlindungan Kata Sandi dengan AES
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Pelajari cara meningkatkan keamanan file Anda menggunakan Aspose.Zip untuk .NET dengan enkripsi AES. Ikuti panduan langkah demi langkah kami untuk perlindungan optimal.
weight: 11
url: /id/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Amankan File Anda - Enkripsi AES dengan Aspose.Zip


## Perkenalan

Mengamankan file sensitif Anda sangat penting di era digital saat ini, dan Aspose.Zip untuk .NET memberikan solusi tangguh untuk melindungi arsip Anda dengan kata sandi menggunakan Advanced Encryption Standard (AES). Dalam tutorial ini, kita akan mempelajari cara menerapkan enkripsi AES dengan tiga panjang kunci – 128-bit, 192-bit, dan 256-bit – memastikan tingkat keamanan tertinggi untuk file terkompresi Anda.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Zip untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Zip yang terintegrasi ke dalam proyek .NET Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/zip/net/).

- Direktori Dokumen: Memiliki direktori tempat file sumber Anda berada.

## Impor Namespace

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Langkah 1: Lindungi Kata Sandi dengan AES-128

```csharp
//ExStart:Perlindungan Kata SandiDenganAES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: Perlindungan Kata SandiDenganAES128
```

Pada langkah ini, kami membuat file zip dan melindunginya dengan enkripsi AES-128. Kata sandi "p@s$" menjamin keamanan arsip Anda.

## Langkah 2: Lindungi Kata Sandi dengan AES-192

```csharp
//ExStart:Perlindungan Kata SandiDenganAES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: Perlindungan Kata SandiDenganAES192
```

Langkah ini menunjukkan cara menerapkan enkripsi AES-192 untuk meningkatkan keamanan. Kata sandi yang sama "p@s$" digunakan untuk konsistensi.

## Langkah 3: Lindungi Kata Sandi dengan AES-256

```csharp
//ExStart:Perlindungan Kata SandiDenganAES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: Perlindungan Kata SandiDenganAES256
```

Pada langkah terakhir ini, kami menerapkan enkripsi tingkat tertinggi, AES-256, yang memberikan lapisan keamanan tambahan untuk file terkompresi Anda.

## Kesimpulan

Dalam tutorial ini, kami telah membahas langkah-langkah penting untuk melindungi arsip Anda dengan kata sandi menggunakan enkripsi AES di Aspose.Zip untuk .NET. Baik Anda memilih enkripsi 128-bit, 192-bit, atau 256-bit, file Anda akan aman dari akses tidak sah.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.Zip untuk .NET dengan bahasa pemrograman lain?
Aspose.Zip terutama dirancang untuk aplikasi .NET, memastikan integrasi yang lancar dan kinerja optimal.

### Apakah metode enkripsi AES aman untuk data sensitif?
Ya, enkripsi AES dikenal luas sebagai metode yang aman dan tangguh untuk melindungi informasi sensitif.

### Bisakah saya mengubah kata sandi untuk arsip yang sudah dienkripsi?
Tidak, kata sandi untuk arsip terenkripsi tidak dapat diubah setelah ditetapkan. Anda harus membuat arsip terenkripsi baru dengan kata sandi berbeda.

### Apakah ada batasan pada jenis file yang dapat dienkripsi menggunakan Aspose.Zip?
Aspose.Zip mendukung enkripsi berbagai jenis file, memastikan fleksibilitas dalam mengamankan berbagai jenis data.

### Apa yang terjadi jika saya lupa kata sandi untuk arsip terenkripsi?
Sayangnya, tidak ada cara untuk memulihkan kata sandi arsip terenkripsi. Sangat penting untuk menyimpan kata sandi di lokasi yang aman.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
