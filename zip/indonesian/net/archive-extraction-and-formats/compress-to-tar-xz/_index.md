---
date: 2025-12-05
description: Pelajari cara membuat arsip tarxz di .NET dan cara mengompres file tarxz
  menggunakan Aspose.Zip untuk .NET. Ikuti panduan langkah demi langkah ini untuk
  penyimpanan dan transmisi yang efisien.
language: id
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara membuat arsip tarxz .net dengan Aspose.Zip
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat arsip tarxz .net dengan Aspose.Zip

## Pendahuluan

Jika Anda perlu **membuat arsip tarxz .net**, Aspose.Zip untuk .NET membuat prosesnya sederhana dan dapat diandalkan. Baik Anda mengemas log, file konfigurasi, atau aset lainnya untuk penyimpanan atau transmisi, mengompresi ke format TarXz memberi Anda rasio kompresi tinggi sambil mempertahankan struktur tar yang familiar. Dalam tutorial ini kami akan memandu langkah demi langkah—dilengkapi dengan potongan kode—sehingga Anda dapat mengintegrasikan pembuatan tarxz ke dalam aplikasi .NET Anda dengan percaya diri.

## Jawaban Cepat
- **Apa kelas utama?** `TarArchive` dari `Aspose.Zip.Tar`
- **Bagaimana cara mengompresi tarxz?** Gunakan `SaveXzCompressed` setelah menambahkan entri
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Apakah lisensi diperlukan?** Ya, lisensi Aspose.Zip yang valid untuk produksi
- **Waktu implementasi tipikal?** ~5‑10 menit

## Apa itu arsip TarXz?

Sebuah **arsip TarXz** menggabungkan kontainer Unix tradisional `tar` dengan kompresi XZ. Bagian tar menggabungkan beberapa file menjadi satu aliran, sementara XZ menyediakan kompresi kuat dan lossless. Format ini populer untuk mendistribusikan kode sumber, cadangan, dan set data besar karena mempertahankan struktur direktori dan menghasilkan ukuran file lebih kecil dibandingkan tar atau zip biasa.

## Mengapa membuat arsip tarxz .net dengan Aspose.Zip?

- **Rasio kompresi tinggi** – XZ sering menghasilkan ukuran 30‑50 % lebih kecil dibandingkan gzip.
- **Kompatibilitas lintas‑platform** – File TarXz dapat dibuka di Linux, macOS, dan Windows.
- **API sederhana** – Aspose.Zip menyembunyikan detail tingkat rendah, memungkinkan Anda fokus pada logika bisnis.
- **Tanpa alat eksternal** – Semua berjalan di dalam proses .NET Anda, cocok untuk cloud atau pipeline CI.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terpasang (unduh dari [dokumentasi resmi Aspose.Zip](https://reference.aspose.com/zip/net/)).
- Sebuah folder yang berisi file‑file yang ingin Anda arsipkan. Pada contoh di bawah, folder ini direferensikan oleh variabel `dataDir`.
- Lisensi Aspose.Zip yang valid (opsional untuk evaluasi, wajib untuk produksi).

## Impor Namespace

Pertama, impor namespace yang menyediakan fungsionalitas TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Panduan Langkah‑demi‑Langkah untuk membuat arsip tarxz .net

### Langkah 1: Inisialisasi `TarArchive`

Buat instance `TarArchive` baru yang akan menampung file‑file yang ingin Anda kompres.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tip:** Pernyataan `using` memastikan arsip dibuang dengan benar, melepaskan sumber daya tak terkelola apa pun.

### Langkah 2: Tambahkan File ke Arsip

Tambahkan setiap file yang ingin Anda sertakan. Pada contoh ini kami menambahkan dua file teks, tetapi Anda dapat menambahkan sebanyak entri yang diperlukan.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Mengapa ini penting:** Menambahkan entri sebelum kompresi memungkinkan Aspose.Zip membangun kontainer tar terlebih dahulu, lalu menerapkan kompresi XZ dalam satu langkah.

### Langkah 3: Simpan Arsip dengan Kompresi XZ

Akhirnya, tulis arsip tar ke disk menggunakan kompresi XZ. File yang dihasilkan akan memiliki ekstensi `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Hasil:** Anda kini memiliki file `archive.tar.xz` yang terkompresi penuh dan dapat dipindahkan, disimpan, atau dibuka di platform mana pun yang mendukung TarXz.

## Masalah Umum & Solusi

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| **Exception “File not found”** | Path `dataDir` tidak tepat | Pastikan jalur direktori diakhiri dengan backslash (`\`) atau gunakan `Path.Combine`. |
| **Penggunaan memori tinggi** | File berukuran sangat besar dikompresi di memori | Gunakan `TarArchive` dalam mode streaming (`SaveXzCompressed` overload yang menerima `Stream`). |
| **Lisensi tidak diterapkan** | File lisensi hilang | Muat lisensi saat aplikasi dimulai: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Zip kompatibel dengan semua lingkungan .NET?**  
J: Ya, Aspose.Zip bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+. Lihat [dokumentasi](https://reference.aspose.com/zip/net/) untuk detailnya.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**  
J: Anda dapat meminta lisensi sementara melalui [halaman lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/).

**T: Apakah ada contoh tambahan untuk format arsip lain?**  
J: Tentu—jelajahi kumpulan contoh lengkap di [referensi API Aspose.Zip](https://reference.aspose.com/zip/net/).

**T: Di mana saya dapat mendapatkan bantuan atau berdiskusi tentang masalah?**  
J: Bergabunglah dalam percakapan di [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas dan jawaban resmi.

**T: Bisakah saya mencoba Aspose.Zip secara gratis sebelum membeli?**  
J: Ya, percobaan gratis tersedia di [halaman unduhan Aspose.Zip](https://releases.aspose.com/zip/net).

## Kesimpulan

Dengan mengikuti langkah‑langkah di atas, Anda kini tahu **cara mengompresi tarxz** dan, yang lebih penting, **cara membuat arsip tarxz .net** menggunakan Aspose.Zip. Pendekatan ini memberi Anda paket yang kompak dan portabel yang dapat diintegrasikan secara mulus ke dalam alur kerja .NET apa pun—baik Anda membangun utilitas desktop, layanan web, atau pipeline CI/CD otomatis.

---

**Terakhir Diperbarui:** 2025-12-05  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}