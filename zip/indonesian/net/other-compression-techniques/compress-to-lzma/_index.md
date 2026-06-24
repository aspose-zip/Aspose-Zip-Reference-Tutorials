---
date: 2026-06-24
description: Pelajari cara mengompres LZMA di Aspose.Zip untuk .NET, mengoptimalkan
  penyimpanan dan efisiensi transfer data.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Kompres ke Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres LZMA di Aspose.Zip untuk .NET
url: /id/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengompresi LZMA di Aspose.Zip untuk .NET

## Pendahuluan

Dalam tutorial ini, Anda akan belajar **cara mengompresi LZMA** di Aspose.Zip untuk .NET, sebuah keterampilan penting untuk mengoptimalkan ruang penyimpanan dan meningkatkan efisiensi transfer data. LZMA (algoritma Lempel‑Ziv‑Markov chain) menghasilkan arsip hingga 70 % lebih kecil dibandingkan ZIP tradisional sambil mempertahankan dekompresi yang cepat, menjadikannya ideal untuk skenario dengan bandwidth terbatas.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Zip untuk .NET  
- **Algoritma mana yang dibahas dalam panduan ini?** Kompresi LZMA  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk file dasar.

## Apa itu kompresi LZMA?

LZMA adalah algoritma kompresi lossless dengan rasio tinggi yang menggunakan kompresi kamus dan range encoding. Ia dapat memperkecil file teks sebesar 30‑70 % sambil mempertahankan kecepatan dekompresi yang sebanding dengan ZIP. Untuk kumpulan data besar, LZMA mengurangi biaya penyimpanan dan mempercepat transfer jaringan tanpa mengorbankan integritas data.

## Mengapa menggunakan Aspose.Zip untuk LZMA?

Aspose.Zip mendukung **5 algoritma kompresi** (ZIP, Deflate, BZIP2, LZMA, dan ZSTD) dan dapat menangani arsip hingga **4 GB** tanpa memuat seluruh file ke memori. Perpustakaan ini memproses dokumen ratusan halaman dalam waktu kurang dari **2 detik** pada server tipikal, memberikan kinerja dan skalabilitas.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Zip untuk .NET: Pastikan perpustakaan Aspose.Zip terpasang. Anda dapat menemukan dokumentasinya [di sini](https://reference.aspose.com/zip/net/).
- Direktori Dokumen: Pilih atau buat folder yang berisi file yang ingin Anda kompres.

## Impor Namespace

Tambahkan namespace yang diperlukan di bagian atas file C# Anda sehingga Anda dapat mengakses fungsionalitas LZMA Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Bagaimana cara mengatur folder sumber untuk kompresi?

Tentukan folder yang berisi file yang ingin Anda arsipkan. Menyediakan direktori sumber khusus memastikan hanya file yang dimaksud yang diproses, mengurangi risiko memasukkan data yang tidak diinginkan, dan mempermudah manajemen jalur saat bekerja dengan beberapa tugas kompresi dalam proyek yang sama.

```csharp
string dataDir = "Your Document Directory";
```

## Bagaimana cara mengompresi file menggunakan LZMA?

`LzmaArchive` adalah kelas Aspose.Zip untuk membuat dan mengelola arsip LZMA.

Buat instance `LzmaArchive`, arahkan ke file sumber, dan panggil `Save` untuk menghasilkan arsip `.lzma`. Pola dua baris ini melakukan seluruh alur kerja kompresi, menangani manajemen stream secara internal, dan menghasilkan file kompak yang siap untuk distribusi atau penyimpanan.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Bagaimana saya dapat memastikan kompresi berhasil?

`Console.WriteLine` menulis satu baris teks ke konsol output standar.

Setelah arsip disimpan, keluarkan pesan konfirmasi singkat menggunakan `Console.WriteLine`. Umpan balik langsung ini membantu pengembang memastikan langkah kompresi selesai tanpa kesalahan, menyederhanakan proses debugging selama build otomatis, dan memberikan informasi status yang jelas ketika rutin ini diintegrasikan ke dalam aplikasi atau skrip yang lebih besar.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Masalah Umum dan Solusinya

- **File tidak ditemukan** – Verifikasi string jalur menggunakan backslash ganda (`\\`) atau string verbatim (`@"C:\Path"`).  
- **Memori tidak cukup** – Aspose.Zip melakukan streaming data, tetapi file yang sangat besar mungkin memerlukan peningkatan batas memori proses.  
- **Lisensi tidak diterapkan** – Pastikan Anda memanggil `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` sebelum operasi Aspose.Zip apa pun.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengompresi beberapa file menjadi satu arsip LZMA?**  
A: Ya. Panggil `archive.AddFile()` untuk setiap file sebelum memanggil `archive.Save()`.

**Q: Apakah ada cara untuk mengatur tingkat kompresi untuk LZMA?**  
A: Kelas `LzmaArchive` menggunakan tingkat kompresi default, yang memberikan keseimbangan yang baik antara kecepatan dan ukuran. Pengaturan lanjutan tersedia melalui `LzmaEncoder` jika Anda memerlukan kontrol yang lebih halus.

**Q: Apakah file .lzma yang dihasilkan akan berfungsi di platform non‑Windows?**  
A: Tentu saja. Format LZMA bersifat platform‑agnostik, sehingga arsip dapat didekompresi di sistem operasi apa pun dengan alat yang kompatibel dengan LZMA.

**Q: Bagaimana cara mendekompresi arsip LZMA menggunakan Aspose.Zip?**  
A: Gunakan konstruktor `LzmaArchive` dengan jalur arsip, lalu panggil `ExtractToDirectory()` untuk mengekstrak isinya.

**Q: Apakah Aspose.Zip mendukung kompresi streaming untuk menghindari memuat seluruh file ke memori?**  
A: Ya. Anda dapat bekerja dengan stream dengan memberikan objek `Stream` ke metode `SetSource()` dan `Save()`.

---

**Terakhir Diperbarui:** 2026-06-24  
**Diuji Dengan:** Aspose.Zip untuk .NET (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mengompresi File dengan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-file/)
- [Cara Membuka Arsip GZip dan Teknik Kompresi Lain dengan Aspose.Zip untuk .NET](/zip/net/other-compression-techniques/)
- [compress files c# – Buat arsip 7z dengan Aspose.Zip untuk .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}