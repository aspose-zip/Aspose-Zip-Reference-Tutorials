---
title: Aspose.Zip untuk .NET - Tutorial Penyimpanan File Aman
linktitle: Simpan Banyak File Tanpa Kompresi dengan Kata Sandi
second_title: Aspose.Zip .NET API untuk Kompresi & Pengarsipan File
description: Jelajahi cara menggunakan Aspose.Zip untuk .NET untuk menyimpan banyak file dengan aman tanpa kompresi. Langkah mudah untuk perlindungan kata sandi. Buka kekuatan manajemen file!
type: docs
weight: 13
url: /id/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

Dalam dunia pengembangan .NET, mengelola dan memanipulasi file adalah tugas yang umum. Aspose.Zip untuk .NET adalah perpustakaan canggih yang memberi pengembang kemampuan untuk mengompresi, mendekompresi, dan memanipulasi arsip zip dengan lancar. Dalam tutorial ini, kita akan mempelajari skenario spesifik: menyimpan banyak file tanpa kompresi dan melindunginya dengan kata sandi. Di akhir panduan ini, Anda akan dibekali dengan pengetahuan untuk mengimplementasikan fungsi ini menggunakan Aspose.Zip untuk .NET.

## Prasyarat

Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Zip untuk Perpustakaan .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Zip untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/zip/net/).

-  Direktori Dokumen: Siapkan direktori tempat file sumber Anda berada. Dalam contoh yang diberikan, variabel`dataDir` mewakili direktori dokumen Anda.

## Impor Namespace

Untuk memulai, mari impor namespace yang diperlukan untuk kode kita:

```csharp
// Jalur ke direktori sumber daya.
string dataDir = "Your Document Directory"

// Impor namespace Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Langkah 1: Buka File Zip

```csharp
//ExStart: StoreMutlipleFilesTanpaCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Langkah ini melibatkan pembuatan file zip baru menggunakan`FileStream`. File tersebut akan diberi nama "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## Langkah 2: Buka File Sumber

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Di sini, kita membuka file sumber pertama, "alice29.txt," yang akan disimpan dalam arsip zip.

## Langkah 3: Buat Arsip

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 Pada langkah ini, kita membuat sebuah instance dari`Archive` kelas, menentukan pengaturan kompresi dan enkripsi. Kami menggunakan`StoreCompressionSettings` untuk menyimpan file tanpa kompresi dan`AesEcryptionSettings` untuk menerapkan enkripsi AES dengan kata sandi ("p@s$").

## Langkah 4: Buat Entri Arsip dan Simpan

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Langkah terakhir ini melibatkan pembuatan entri dalam arsip untuk "alice29.txt" dan menyimpan arsip, menyelesaikan proses penyimpanan file tanpa kompresi dan dengan perlindungan kata sandi.

Akhiri tutorial Anda dengan merangkum poin-poin penting dan mendorong pembaca untuk mengeksplorasi kemungkinan lebih lanjut dengan Aspose.Zip untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.Zip untuk .NET untuk menyimpan banyak file tanpa kompresi dan mengamankannya dengan kata sandi. Saat Anda melanjutkan perjalanan Anda dengan pengembangan .NET, manfaatkan kemampuan Aspose.Zip untuk menyederhanakan tugas manajemen file dan meningkatkan keamanan aplikasi Anda.

---

### FAQ

### Bisakah saya menggunakan Aspose.Zip untuk .NET dengan metode enkripsi lainnya?
 Ya, Aspose.Zip mendukung berbagai metode enkripsi. Periksa dokumentasinya[Di Sini](https://reference.aspose.com/zip/net/) untuk detailnya.

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Zip untuk .NET?
 Mengunjungi[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan dan diskusi komunitas.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Zip untuk .NET?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Zip untuk .NET?
 Minta izin sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat membeli Aspose.Zip untuk .NET?
 Anda dapat membeli Aspose.Zip untuk .NET[Di Sini](https://purchase.aspose.com/buy).
