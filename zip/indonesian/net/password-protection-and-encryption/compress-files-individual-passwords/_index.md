---
date: 2026-05-15
description: Pelajari cara membuat file zip yang dilindungi kata sandi dan mengompres
  file dengan kata sandi menggunakan Aspose.Zip untuk .NET dalam beberapa langkah
  sederhana.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Kompres File dengan Kata Sandi Individu
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip
url: /id/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip

## Pendahuluan

Dalam tutorial ini Anda akan belajar cara **membuat file zip yang dilindungi kata sandi** dalam aplikasi .NET menggunakan Aspose.Zip. Kompresi yang aman sangat penting ketika Anda perlu mengirim data rahasia atau menyimpan dokumen sensitif tanpa mengeksposnya kepada akses yang tidak sah.

Aspose.Zip adalah perpustakaan .NET yang memungkinkan pembuatan, pembacaan, dan enkripsi arsip ZIP secara programatik. Ia mendukung enkripsi AES‑256 dan memungkinkan Anda menetapkan kata sandi unik untuk setiap entri di dalam arsip.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Zip?** Ia membuat dan memanipulasi arsip ZIP, termasuk perlindungan kata sandi per‑file.  
- **Berapa banyak kata sandi yang dapat saya tetapkan?** Satu kata sandi berbeda per file; entri tidak terbatas.  
- **Algoritma enkripsi apa yang digunakan?** AES‑256, memberikan keamanan 256‑bit.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prasyarat

Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.Zip untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Zip yang terpasang di proyek .NET Anda. Anda dapat menemukan dokumentasi yang diperlukan [di sini](https://reference.aspose.com/zip/net/).

- Unduh: Jika belum, unduh perpustakaan Aspose.Zip untuk .NET dari [tautan ini](https://releases.aspose.com/zip/net/).

- Direktori Dokumen: Siapkan sebuah direktori yang berisi file-file yang ingin Anda kompres.

## Impor Namespace

Di proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan:

`ZipFile` adalah kelas utama Aspose.Zip untuk membuat arsip ZIP dan menetapkan kata sandi individual untuk setiap entri.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Cara membuat file zip yang dilindungi kata sandi di .NET?

Muat folder target, buat objek `ZipFile`, tambahkan setiap file dengan kata sandinya masing‑masing, dan akhirnya panggil `Save` untuk menulis arsip. Seluruh proses ini hanya memerlukan beberapa baris kode dan menjamin setiap entri dienkripsi dengan kata sandi yang Anda tentukan.

### Langkah 1: Atur Jalur Direktori Sumber Daya

Tentukan jalur ke direktori sumber daya tempat file Anda berada.

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Kompres File dengan Kata Sandi Individual

Sekarang, mari kita kompres file dengan kata sandi individual. Kami akan menggunakan tiga file contoh (`alice29.txt`, `asyoulik.txt`, dan `fields.c`) dengan kata sandi yang berbeda untuk masing‑masing.

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

## Mengapa menggunakan perlindungan kata sandi untuk arsip ZIP?

Aspose.Zip mendukung **lebih dari 30 algoritma kompresi** dan dapat mengenkripsi arsip dengan AES‑256, memberikan hingga **keamanan 256‑bit**. Ia dapat memproses arsip berukuran ratusan megabyte tanpa memuat seluruh file ke memori, menjadikannya ideal untuk skenario server‑side berperforma tinggi. Selain itu, perlindungan kata sandi membantu memenuhi kepatuhan regulasi seperti GDPR dan HIPAA dengan memastikan data sensitif tetap terenkripsi baik saat disimpan maupun saat ditransmisikan.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara **membuat file zip yang dilindungi kata sandi** dan **mengompres file dengan kata sandi** menggunakan Aspose.Zip untuk .NET. Fitur ini menambahkan lapisan keamanan ekstra pada file terkompresi Anda, memastikan kerahasiaan dan kepatuhan terhadap kebijakan perlindungan data.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan metode enkripsi yang berbeda untuk setiap file?**  
A: Ya, Aspose.Zip memungkinkan Anda memilih algoritma enkripsi (misalnya AES‑256) untuk setiap entri saat menambahkannya ke arsip.

**Q: Apakah ada versi percobaan yang tersedia?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.Zip untuk .NET [di sini](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan jika saya mengalami masalah?**  
A: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan dari komunitas dan dukungan Aspose.

**Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Zip untuk .NET?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/).

**Q: Bisakah saya membeli lisensi sementara untuk tujuan pengujian?**  
A: Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-05-15  
**Diuji Dengan:** Aspose.Zip 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat ZIP yang Dilindungi Kata Sandi dengan Aspose.Zip untuk .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Lindungi ZIP dengan Kata Sandi menggunakan Enkripsi AES dengan Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Kompres Beberapa File dengan Enkripsi di Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}