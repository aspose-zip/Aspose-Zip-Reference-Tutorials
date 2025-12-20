---
date: 2025-12-20
description: Pelajari cara membuat arsip zip yang dilindungi kata sandi di .NET menggunakan
  Aspose.Zip. Panduan langkah demi langkah ini menunjukkan cara mengompres file dengan
  kata sandi, mengatur kata sandi entri zip, dan menggunakan enkripsi AES.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat File ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip
url: /id/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat File ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip

## Pendahuluan

Jika Anda perlu **membuat arsip zip yang dilindungi kata sandi** dalam aplikasi .NET, Aspose.Zip mempermudahnya. Dengan menetapkan kata sandi unik untuk setiap entri, Anda dapat menjaga dokumen sensitif tetap aman sekaligus menikmati kemudahan kompresi ZIP. Dalam tutorial ini Anda akan belajar cara mengompres file dengan kata sandi individual, memilih metode enkripsi yang berbeda, dan mengatur kata sandi entri zip — semuanya dengan kode yang jelas dan siap produksi.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip untuk .NET.
- **Bisakah saya menetapkan kata sandi berbeda per file?** Ya, setiap entri dapat memiliki kata sandi masing‑masing.
- **Algoritma enkripsi apa yang didukung?** ZipCrypto tradisional, AES‑128, dan AES‑256.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.
- **Apakah ini kompatibel dengan .NET 6+?** Tentu – API menargetkan .NET Standard 2.0 dan yang lebih baru.

## Apa itu “membuat zip yang dilindungi kata sandi”?
Membuat zip yang dilindungi kata sandi berarti menambahkan enkripsi pada satu atau lebih entri di dalam arsip ZIP sehingga isinya tidak dapat dibuka tanpa kata sandi yang benar. Ini ideal untuk mengirim file rahasia, menyimpan cadangan, atau mematuhi kebijakan perlindungan data.

## Mengapa menggunakan Aspose.Zip untuk arsip yang dilindungi kata sandi?
- **Kontrol detail** – tetapkan kata sandi yang berbeda per file.
- **Berbagai pilihan enkripsi** – dari ZipCrypto lama hingga AES‑128/256 yang kuat.
- **Tanpa ketergantungan eksternal** – perpustakaan .NET murni, mudah diintegrasikan.
- **Dokumentasi lengkap** – mencakup **tutorial aspose zip** untuk skenario yang lebih mendalam.

## Prasyarat

Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Zip untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Zip di proyek .NET Anda. Anda dapat menemukan dokumentasi yang diperlukan [di sini](https://reference.aspose.com/zip/net/).
- Unduh: Jika belum, unduh perpustakaan Aspose.Zip untuk .NET dari [tautan ini](https://releases.aspose.com/zip/net/).
- Direktori Dokumen: Siapkan direktori yang berisi file yang ingin Anda kompres.

## Impor Namespace

Dalam proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Langkah 1: Atur Jalur Direktori Sumber Daya

Tentukan jalur ke direktori sumber daya tempat file sumber Anda berada.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Kompres File dengan Kata Sandi Individual

Sekarang, mari kita kompres file dengan kata sandi individual. Kami akan menggunakan tiga file contoh (`alice29.txt`, `asyoulik.txt`, dan `fields.c`) dengan kata sandi yang berbeda untuk masing‑masing. Ini menunjukkan cara **mengompres file dengan kata sandi** serta cara **mengatur kata sandi entri zip** menggunakan skema enkripsi yang berbeda, termasuk **arsip zip dengan aes**.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Cara kerja ini
- **TraditionalEncryptionSettings** menggunakan algoritma ZipCrypto lama (kompatibel dengan sebagian besar utilitas ZIP).
- **AesEcryptionSettings** memungkinkan Anda memilih AES‑128 atau AES‑256 untuk keamanan yang lebih kuat.
- Setiap pemanggilan `CreateEntry` menerima objek `ArchiveEntrySettings` di mana kami menentukan metode kompresi dan pengaturan enkripsi, secara efektif **melindungi entri arsip zip dengan kata sandi**.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| “Kata sandi tidak valid” saat membuka ZIP | Tidak cocok antara kata sandi yang digunakan dalam kode dan yang dimasukkan di ekstraktor | Verifikasi string tepat yang diberikan ke `TraditionalEncryptionSettings` atau `AesEcryptionSettings`. |
| Alat ekstraksi lama tidak dapat membuka entri terenkripsi AES | Tidak semua utilitas ZIP mendukung enkripsi AES | Gunakan metode ZipCrypto tradisional untuk kompatibilitas maksimal, atau sarankan pengguna menggunakan alat modern (misalnya, 7‑Zip). |
| File besar menyebabkan `OutOfMemoryException` | Memuat file besar ke memori sebelum kompresi | Alirkan file secara langsung menggunakan `FileStream` tanpa memuat seluruh file ke dalam objek `FileInfo`. |

## Pertanyaan yang Sering Diajukan (FAQ)

### Bisakah saya menggunakan metode enkripsi berbeda untuk setiap file?
Ya, Aspose.Zip untuk .NET memungkinkan Anda menggunakan metode enkripsi yang berbeda untuk setiap file saat kompresi.

### Apakah ada versi percobaan yang tersedia?
Ya, Anda dapat mengakses percobaan gratis Aspose.Zip untuk .NET [di sini](https://releases.aspose.com/).

### Bagaimana saya dapat mendapatkan dukungan jika saya mengalami masalah?
Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan dari komunitas dan dukungan Aspose.

### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Zip untuk .NET?
Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/).

### Bisakah saya membeli lisensi sementara untuk tujuan pengujian?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

## FAQ Cepat Tambahan

**T: Apakah perpustakaan ini mendukung .NET Core dan .NET 5/6?**  
J: Ya, Aspose.Zip menargetkan .NET Standard, sehingga kompatibel dengan .NET Framework, .NET Core, dan .NET 5/6.

**T: Bisakah saya menambahkan komentar ke setiap entri ZIP?**  
J: Meskipun Aspose.Zip berfokus pada kompresi dan enkripsi, Anda dapat menyimpan metadata dalam file manifest terpisah di dalam arsip.

**T: Apakah memungkinkan mengenkripsi seluruh arsip dengan satu kata sandi?**  
J: Anda dapat menetapkan kata sandi pada setiap entri secara individual (seperti yang ditunjukkan) atau menerapkan kata sandi yang sama pada semua entri untuk pendekatan “arsip zip dengan aes” yang lebih sederhana.

## Kesimpulan

Anda kini telah menguasai cara **membuat file zip yang dilindungi kata sandi** di .NET menggunakan Aspose.Zip. Dengan menetapkan kata sandi individual dan memilih metode enkripsi yang tepat, Anda dapat menjaga data tetap aman tanpa mengorbankan kemudahan kompresi ZIP. Jelajahi fitur Aspose.Zip lainnya seperti streaming file besar, menambahkan metadata khusus, dan integrasi dengan penyimpanan cloud untuk skenario yang lebih kuat.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Zip for .NET 23.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}