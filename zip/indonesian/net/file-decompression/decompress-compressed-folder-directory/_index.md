---
date: 2026-06-04
description: Pelajari cara mengekstrak zip ke folder menggunakan Aspose.Zip untuk
  .NET, termasuk arsip yang dilindungi kata sandi dan ekstraksi zip terenkripsi.
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: ekstrak zip ke folder
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengekstrak zip ke folder dengan Aspose.Zip untuk .NET
url: /id/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengekstrak zip ke folder dengan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **mengekstrak zip ke folder** dengan cepat dan dapat diandalkan dalam aplikasi .NET, Aspose.Zip untuk .NET memberikan API yang bersih dan lintas‑platform yang menangani arsip biasa maupun terenkripsi. Dalam tutorial ini kami akan membahas semua yang Anda butuhkan—dari menyiapkan pustaka hingga mengekstrak file ZIP yang dilindungi kata sandi—sehingga Anda dapat fokus pada logika bisnis Anda alih‑alih penanganan arsip tingkat rendah.

## Jawaban Cepat
- **Apa tujuan utama Aspose.Zip?** Untuk membuat, membaca, dan **mengekstrak zip ke folder** dalam aplikasi .NET.  
- **Bagaimana cara mengekstrak zip dengan kata sandi?** Berikan kata sandi melalui `ArchiveLoadOptions.DecryptionPassword`.  
- **Apakah saya dapat mengekstrak arsip terenkripsi tanpa kata sandi?** Tidak—Aspose.Zip memerlukan kata sandi yang benar untuk membuka arsip terenkripsi.  
- **Versi .NET mana yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10.  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi Aspose.Zip yang valid diperlukan untuk penggunaan komersial.

## Apa itu **mengekstrak zip ke folder**?

Mengekstrak file ZIP berarti membaca data terkompresi dan menulis file asli ke direktori target di disk. Aspose.Zip mengabstraksi detail tingkat rendah, memungkinkan Anda memanggil satu metode untuk melakukan seluruh operasi sekaligus mendukung **lebih dari 30 format arsip** dan menangani file hingga **2 GB** tanpa memuat seluruh arsip ke memori.

## Mengapa menggunakan Aspose.Zip untuk tugas **cara mengekstrak zip**?

Aspose.Zip menyediakan API yang sederhana yang memungkinkan Anda mengekstrak file hanya dengan beberapa baris kode, mendukung arsip yang dilindungi kata sandi dan terenkripsi AES, serta berjalan di Windows, Linux, dan macOS. Ia memproses **arsip ZIP 500‑halaman dalam kurang dari 2 detik** pada server tipikal, menghilangkan kebutuhan akan utilitas zip native dan mengurangi kompleksitas penyebaran.

## Prasyarat

- Aspose.Zip for .NET Library: Unduh dan instal pustaka dari [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/).
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).
- (Opsional) File ZIP yang dilindungi kata sandi jika Anda ingin mencoba **mengekstrak zip dengan kata sandi**.

## Impor Namespace

Pada proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Sekarang mari kita uraikan proses ekstraksi langkah demi langkah.

## Cara **mengekstrak zip ke folder** – Panduan Langkah‑demi‑Langkah

Muat arsip ZIP Anda, secara opsional berikan kata sandi dekripsi, dan panggil `ExtractToDirectory` – itulah alur kerja ekstraksi lengkap dalam tiga langkah singkat. API secara otomatis membuat folder tujuan jika belum ada, dan men‑stream entri ke disk untuk menjaga penggunaan memori tetap rendah, bahkan untuk arsip multi‑gigabyte.

### Langkah 1: Buka file ZIP (atau arsip terenkripsi)

Kelas `FileStream` menyediakan aliran baca‑saja ke file ZIP fisik di disk. Menggunakan aliran memungkinkan Aspose.Zip bekerja dengan file yang berada di jaringan bersama atau sumber daya tersemat tanpa harus menyalinnya ke lokasi sementara terlebih dahulu.

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### Langkah 2: Buat instance `Archive` (berikan kata sandi bila diperlukan)

Kelas `Archive` adalah objek inti yang mewakili arsip ZIP dalam memori. `ArchiveLoadOptions` mendefinisikan pengaturan yang digunakan saat memuat arsip, seperti kata sandi dekripsi. Mengirimkan objek `ArchiveLoadOptions` dengan properti `DecryptionPassword` mengaktifkan dekripsi entri yang terenkripsi AES.

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### Langkah 3: Ekstrak konten ke folder tujuan

`ExtractToDirectory` mengiterasi setiap entri dalam arsip dan menuliskannya ke jalur target, mempertahankan hierarki folder asli. Metode ini secara otomatis membuat direktori yang hilang dan juga dapat memfilter entri jika Anda hanya membutuhkan sebagian.

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **Tips pro:** Jika Anda hanya perlu mengekstrak sebagian file, gunakan overload yang menerima delegasi filter alih‑alih mengekstrak semuanya.

## Masalah Umum & Pemecahan Masalah

- **Kata sandi salah** – Aspose.Zip melemparkan pengecualian otentikasi. Periksa kembali string kata sandi atau ambil secara aman dari sumber konfigurasi.  
- **Jalur tujuan tidak ditemukan** – Pastikan jalur direktori tujuan valid; `ExtractToDirectory` akan membuat folder yang hilang, tetapi jalur induk harus dapat diakses.  
- **Arsip besar** – Untuk file ZIP yang sangat besar, pertimbangkan mengekstrak entri demi entri menggunakan API streaming untuk menjaga penggunaan memori tetap rendah.  

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Zip mendukung format kompresi lain seperti GZIP?**  
A: Ya, Aspose.Zip untuk .NET mendukung ZIP, GZIP, dan beberapa format umum lainnya.

**Q: Bisakah saya menggunakan Aspose.Zip dalam proyek komersial maupun non‑komersial?**  
A: Tentu saja. Lisensi yang valid diperlukan untuk produksi, tetapi Anda dapat menggunakan versi percobaan gratis untuk evaluasi.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk pengujian?**  
A: Anda dapat memperoleh lisensi sementara dari [here](https://purchase.aspose.com/temporary-license/) untuk keperluan pengujian.

**Q: Di mana saya dapat mengunduh versi percobaan gratis Aspose.Zip?**  
A: Kunjungi halaman percobaan Aspose.Zip [here](https://releases.aspose.com/) untuk mengunduh versi terbaru.

**Q: Di mana saya dapat meminta bantuan jika mengalami masalah?**  
A: Forum komunitas Aspose.Zip adalah tempat yang bagus untuk mendapatkan bantuan: [support forum](https://forum.aspose.com/c/zip/37).

---

**Terakhir Diperbarui:** 2026-06-04  
**Diuji Dengan:** Aspose.Zip for .NET (latest release)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Mengekstrak Zip dengan Kata Sandi Menggunakan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [Cara Mengekstrak WIM ke Folder Menggunakan Aspose.Zip untuk .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [Cara Mendekompresi File dengan Aspose.Zip untuk .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}