---
date: 2026-06-09
description: Pelajari cara menambahkan kata sandi ke zip dan membuat arsip zip LZMA
  menggunakan Aspose.Zip untuk .NET. Tutorial ini mencakup Bzip2, LZMA (ukuran kamus),
  PPMd, Enhanced Deflate, kompresi Store, dan kompresi file ASP.NET untuk file berukuran
  besar.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Mengoptimalkan Pengaturan Kompresi
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Menambahkan kata sandi ke zip dan membuat arsip LZMA dengan Aspose.Zip untuk
  .NET
url: /id/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah kata sandi ke zip dan buat arsip LZMA dengan Aspose.Zip untuk .NET

In aplikasi .NET modern, **menambahkan kata sandi ke zip** saat membuat arsip zip LZMA dengan rasio tinggi dapat melindungi data sensitif dan tetap memberikan kompresi terbaik. Baik Anda membangun layanan kompresi file ASP.NET, utilitas desktop yang menangani file multi‑gigabyte, atau alur kerja berbasis cloud, tutorial ini memandu Anda melalui langkah‑langkah tepat untuk mengamankan dan mengompres file Anda dengan Aspose.Zip untuk .NET.

## Jawaban Cepat
- **Apa manfaat utama kompresi LZMA?** Rasio kompresi tertinggi dengan kecepatan yang wajar untuk kebanyakan jenis file.  
- **Metode mana yang menyimpan file tanpa kompresi?** Store compression (juga disebut “store compression zip”).  
- **Bisakah saya menggunakan pengaturan ini dalam aplikasi ASP.NET?** Ya—cukup referensikan Aspose.Zip dalam proyek Anda dan panggil API yang sama.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan untuk produksi; versi percobaan gratis tersedia.  
- **Versi .NET apa yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10.

## Apa itu “menambahkan kata sandi ke zip” dalam Aspose.Zip?
**Menambahkan kata sandi zip mengenkripsi setiap entri di dalam arsip ZIP sehingga hanya pengguna yang mengetahui kata sandi yang dapat mengekstrak file.** Aspose.Zip mendukung enkripsi ZipCrypto tradisional dan enkripsi AES (128, 192, atau 256‑bit). Pengaturan enkripsi diberikan sebagai argumen kedua ke `ArchiveEntrySettings` saat membuat `Archive`; tidak ada metode `SetPassword` terpisah.

## Mengapa menggunakan Aspose.Zip untuk kompresi file .NET?
Aspose.Zip menyediakan satu API konsisten yang mencakup banyak algoritma sambil memberikan kinerja tinggi dan penggunaan memori rendah. Ini memungkinkan pengembang memilih metode kompresi terbaik untuk setiap skenario dan menerapkan enkripsi dalam satu langkah, menyederhanakan kode dan mengurangi beban pemeliharaan.

- **API Terpadu** – Satu antarmuka konsisten untuk Bzip2, LZMA, PPMd, Enhanced Deflate, dan Store.  
- **Dioptimalkan untuk Kinerja** – Implementasi native yang dioptimalkan memproses **hingga file 10 GB** tanpa memuat seluruh file ke memori.  
- **Ramahan ASP.NET** – Bekerja mulus dalam proyek web, layanan latar belakang, dan Azure Functions.  
- **Kontrol Detail** – Sesuaikan ukuran kamus, level kompresi, dan enkripsi dengan satu pemanggilan konstruktor.  
- **Mendukung lebih dari 10 algoritma kompresi** – mencakup kasus penggunaan paling umum dalam pipeline data perusahaan.

## Prasyarat
- **Pustaka Aspose.Zip untuk .NET** – Unduh dan instal dari [Aspose documentation](https://reference.aspose.com/zip/net/).  
- **File Teks Contoh** – Siapkan file contoh (misalnya `sample.txt`) yang akan Anda kompres.  
- **Lingkungan pengembangan .NET** – Visual Studio 2022 atau IDE kompatibel lainnya.  

## Impor Namespace

Kelas `Archive`, `ArchiveEntrySettings`, dan kelas enkripsi berada di namespace `Aspose.Zip`. Impor mereka di bagian atas file Anda:

- `Archive` mewakili kontainer arsip ZIP.  
- `ArchiveEntrySettings` menyimpan opsi kompresi dan enkripsi untuk setiap entri.  
- Kelas enkripsi (mis., `AesEncryptionSettings`) menentukan cara data dienkripsi.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Sekarang mari jelajahi setiap pengaturan kompresi dan lihat bagaimana cara **menambahkan kata sandi ke zip** bila diperlukan.

## Menggunakan Pengaturan Kompresi Bzip2

### Langkah 1: Inisialisasi Kompresi Bzip2 dengan Enkripsi Tradisional

`Bzip2CompressionSettings` mengkonfigurasi algoritma Bzip2 (ukuran blok, dll.). `TraditionalEncryptionSettings` menerapkan enkripsi ZipCrypto lama pada sebuah entri.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*Proteksi kata sandi diterapkan melalui `TraditionalEncryptionSettings` yang diberikan langsung ke `ArchiveEntrySettings`.*

## Cara menambahkan kata sandi ke zip menggunakan Aspose.Zip untuk .NET

Muat file sumber Anda, buat `Archive` dengan pengaturan entri, dan tambahkan file ke arsip. Enkripsi diterapkan secara otomatis karena telah diberikan saat instance `ArchiveEntrySettings` dibuat.

**Jawaban langsung (40‑70 kata):**  
Buat objek `ArchiveEntrySettings` yang mencakup pengaturan kompresi yang diinginkan serta `TraditionalEncryptionSettings` atau `AesEncryptionSettings`. Kemudian berikan objek ini ke konstruktor `Archive` dan tambahkan file dengan `AddEntry`. Arsip ditulis dengan kata sandi yang sudah tersemat, sehingga tidak diperlukan langkah tambahan setelah pembuatan.

`ArchiveEntrySettings` adalah penampung konfigurasi yang memberi tahu Aspose.Zip bagaimana setiap entri harus dikompresi dan dienkripsi.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Cara membuat arsip zip LZMA menggunakan Aspose.Zip

### Langkah 1: Inisialisasi Kompresi LZMA dengan Enkripsi AES256

`LzmaCompressionSettings` mengontrol parameter khusus LZMA seperti ukuran kamus dan fast bytes. `AesEncryptionSettings` menyediakan enkripsi AES‑256 untuk entri arsip.

**Jawaban langsung (40‑70 kata):**  
Buat instance `LzmaCompressionSettings` dengan `DictionarySize` yang dipilih, buat objek `AesEncryptionSettings` dengan kata sandi Anda dan `EncryptionMethod.AES256`, lalu bangun `ArchiveEntrySettings` dari keduanya. Berikan ini ke konstruktor `Archive` dan tambahkan file Anda; zip yang dihasilkan akan terkompresi LZMA dan dilindungi AES dalam satu operasi.

`LzmaCompressionSettings` adalah kelas yang mengontrol parameter khusus LZMA seperti ukuran kamus dan fast bytes.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Tip:** LZMA menawarkan **ukuran kamus LZMA** yang dapat dikonfigurasi yang memengaruhi rasio kompresi dan penggunaan memori. Anda dapat mengaturnya melalui `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` jika perlu menyesuaikan untuk file yang sangat besar.

## Menggunakan Pengaturan Kompresi PPMd

### Langkah 1: Inisialisasi Kompresi PPMd dengan Enkripsi AES256

`PpmdCompressionSettings` menentukan urutan dan penggunaan memori untuk algoritma PPMd. `AesEncryptionSettings` menyediakan enkripsi AES‑256 untuk entri arsip.

**Jawaban langsung (40‑70 kata):**  
Buat instance `PpmdCompressionSettings`, gabungkan dengan objek `AesEncryptionSettings` yang berisi kata sandi Anda, dan masukkan keduanya ke dalam `ArchiveEntrySettings`. Gunakan objek pengaturan ini saat membangun `Archive`; zip yang dihasilkan akan terkompresi PPMd dan dilindungi kata sandi tanpa panggilan tambahan.

`PpmdCompressionSettings` menentukan urutan dan penggunaan memori untuk algoritma PPMd.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Menggunakan Pengaturan Kompresi Enhanced Deflate

### Langkah 1: Inisialisasi Kompresi Enhanced Deflate dengan Enkripsi AES256

`EnhancedDeflateCompressionSettings` memungkinkan Anda menentukan level kompresi yang menyeimbangkan kecepatan dan ukuran. `AesEncryptionSettings` menyediakan enkripsi AES‑256 untuk entri arsip.

**Jawaban langsung (40‑70 kata):**  
Buat `EnhancedDeflateCompressionSettings` dengan level yang diinginkan (0‑9), gabungkan dengan `AesEncryptionSettings`, dan bungkus keduanya dalam `ArchiveEntrySettings`. Berikan ini ke konstruktor `Archive` dan tambahkan file; arsip akan dibuat dengan kompresi Enhanced Deflate dan proteksi kata sandi AES‑256 dalam satu langkah.

`EnhancedDeflateCompressionSettings` memungkinkan Anda menentukan level kompresi yang menyeimbangkan kecepatan dan ukuran.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Menggunakan Pengaturan Kompresi Store (store compression zip)

### Langkah 1: Inisialisasi Kompresi Store dengan Enkripsi Tradisional

`StoreCompressionSettings` memberi tahu Aspose.Zip untuk melewatkan kompresi sepenuhnya, mempertahankan file sumber byte‑per‑byte. `TraditionalEncryptionSettings` menerapkan enkripsi ZipCrypto lama.

**Jawaban langsung (40‑70 kata):**  
Buat instance `StoreCompressionSettings` (yang tidak melakukan kompresi), gabungkan dengan `TraditionalEncryptionSettings` yang berisi kata sandi Anda, dan bungkus keduanya dalam `ArchiveEntrySettings`. Berikan ini ke konstruktor `Archive`; zip yang dihasilkan akan berisi file asli tanpa kompresi namun dilindungi kata sandi.

`StoreCompressionSettings` memberi tahu Aspose.Zip untuk melewatkan kompresi sepenuhnya, mempertahankan file sumber byte‑per‑byte.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro tip:** Sesuaikan variabel `dataDir` untuk menunjuk ke direktori kerja Anda yang sebenarnya, dan gunakan kembali instance `Archive` yang sama jika Anda perlu menambahkan beberapa file ke satu arsip.

## Masalah Umum & Solusi
- **Kesalahan “File not found”** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`\` atau `/`) dan bahwa `sample.txt` ada.  
- **Konsumsi memori dengan file besar** – Gunakan `ArchiveEntrySettings` untuk mengaktifkan mode streaming, yang menulis data langsung ke aliran output.  
- **Level kompresi tidak kompatibel** – Beberapa algoritma (mis., LZMA) memiliki properti tambahan seperti `DictionarySize`. Konsultasikan dokumentasi API jika Anda memerlukan kontrol yang lebih halus.  
- **Kata sandi tidak diterapkan** – Pastikan objek pengaturan enkripsi diberikan sebagai argumen kedua ke `ArchiveEntrySettings` saat konstruksi, bukan setelah arsip dibuat.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Zip untuk .NET dengan perpustakaan kompresi lain?**  
**A:** Aspose.Zip dirancang untuk bekerja dengan algoritma bawaan-nya. Mengintegrasikan perpustakaan pihak ketiga memungkinkan tetapi memerlukan penanganan khusus di luar API Aspose.

**Q: Bagaimana saya dapat menambahkan perlindungan kata sandi ke zip yang dibuat dengan Aspose.Zip?**  
**A:** Berikan `TraditionalEncryptionSettings` atau `AesEncryptionSettings` sebagai argumen kedua ke `ArchiveEntrySettings` saat membangun `Archive`. Lihat [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) untuk contoh lengkap.

**Q: Apakah ada versi percobaan yang dapat saya uji?**  
**A:** Ya, Anda dapat mengakses versi percobaan [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan bantuan komunitas atau mengajukan pertanyaan?**  
**A:** Untuk dukungan dan diskusi komunitas, kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**Q: Bisakah saya memperoleh lisensi sementara untuk evaluasi?**  
**A:** Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Bagaimana ini membantu dengan kompresi file ASP.NET?**  
**A:** Dengan memanggil API yang sama dari controller atau middleware ASP.NET, Anda dapat mengompres file secara langsung sebelum mengirimkannya ke klien, mengurangi bandwidth dan meningkatkan kinerja yang dirasakan.

**Q: Apa cara terbaik untuk mengompres file besar secara efisien?**  
**A:** Gabungkan mode streaming dengan kompresi LZMA dan `DictionarySize` yang sesuai. Ini menyeimbangkan penggunaan memori dan rasio kompresi untuk dataset yang sangat besar.

---

**Terakhir Diperbarui:** 2026-06-09  
**Diuji Dengan:** Aspose.Zip 24.11 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Aspose.Zip untuk .NET - Lindungi Zip dengan Kata Sandi & Simpan Banyak File Tanpa Kompresi](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Buat zip terlindungi kata sandi untuk direktori .NET – Tutorial Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [zip beberapa file c# – Kompresi Mudah dengan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}