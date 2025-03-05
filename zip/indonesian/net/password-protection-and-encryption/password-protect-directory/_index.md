---
title: Direktori Perlindungan Kata Sandi di .NET dengan Tutorial Aspose.Zip
linktitle: Direktori Perlindungan Kata Sandi
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Pelajari cara melindungi direktori dengan kata sandi di .NET menggunakan Aspose.Zip. Amankan file Anda dengan mudah dengan tutorial langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/password-protection-and-encryption/password-protect-directory/
---

## Perkenalan

Dalam dunia pengembangan .NET, pengelolaan dan pengamanan direktori merupakan aspek penting dalam penanganan file. Aspose.Zip untuk .NET memberikan solusi tangguh untuk direktori perlindungan kata sandi, memastikan kerahasiaan dan integritas data sensitif Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses perlindungan kata sandi direktori langkah demi langkah, menggunakan Aspose.Zip untuk .NET.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar bahasa pemrograman C#.
- Visual Studio diinstal pada mesin Anda.
-  Aspose.Zip untuk perpustakaan .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/zip/net/).
- Direktori yang berisi file yang ingin Anda lindungi dengan kata sandi.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Namespace ini sangat penting untuk memanfaatkan fungsionalitas yang disediakan oleh Aspose.Zip untuk .NET.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Langkah 1: Tetapkan Jalur ke Direktori Sumber Daya

Pertama, tentukan jalur ke direktori yang berisi file yang ingin Anda lindungi dengan kata sandi.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Lindungi Direktori dengan Kata Sandi

 Sekarang, mari kita pelajari kode yang melakukan perlindungan kata sandi pada direktori. Kami menggunakan`TraditionalEncryptionSettings` kelas untuk mengatur kata sandi dan menerapkannya ke direktori yang ditentukan.

```csharp
//ExStart: Kata SandiProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: Direktori Perlindungan Kata Sandi
    }
}
```

## Langkah 3: Penjelasan Kode

Mari kita uraikan kodenya untuk memahami setiap langkah:

-  Mengatur File Keluaran:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` membuat file ZIP baru untuk keluaran terenkripsi.

-  Mendefinisikan Direktori:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` menentukan direktori yang akan dilindungi kata sandi.

-  Membuat dan Menyimpan Entri:`archive.CreateEntries(corpus)` membuat entri untuk file di direktori yang ditentukan, dan`archive.Save(zipFile)`menyimpan arsip yang dilindungi kata sandi.

## Kesimpulan

Dalam tutorial ini, kita mempelajari proses melindungi direktori dengan kata sandi menggunakan Aspose.Zip untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan keamanan file sensitif Anda dengan cara yang ramah pengguna dan efisien.

---

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Zip untuk .NET cocok untuk direktori besar?
Ya, Aspose.Zip untuk .NET dirancang untuk menangani direktori besar secara efisien, memberikan kinerja optimal.

### Bisakah saya mengubah kata sandi untuk direktori yang sudah dilindungi?
 Ya, Anda dapat mengubah kata sandi dengan menyesuaikan`TraditionalEncryptionSettings` dalam kode yang sesuai.

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Zip untuk .NET?
 Ya, lisensi yang valid diperlukan untuk menggunakan Aspose.Zip untuk .NET di lingkungan produksi. Anda bisa mendapatkan lisensi[Di Sini](https://purchase.aspose.com/buy).

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Zip untuk .NET?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Zip untuk .NET?
 Anda dapat mengunjungi[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan atau pertanyaan apa pun.

