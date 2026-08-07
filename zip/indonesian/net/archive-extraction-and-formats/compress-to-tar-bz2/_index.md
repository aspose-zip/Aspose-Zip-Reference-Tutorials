---
date: 2026-08-07
description: Pelajari cara menambahkan file ke tar dan menghasilkan arsip TarBz2 di
  .NET menggunakan Aspose.Zip. Panduan langkah demi langkah menunjukkan pembuatan
  tar, kompresi Bzip2, dan tips praktik terbaik.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Mengompresi ke TarBz2
og_description: Tambahkan file ke tar dan hasilkan arsip TarBz2 di .NET menggunakan
  Aspose.Zip. Panduan ini mencakup pembuatan tar, kompresi Bzip2, dan tips pemecahan
  masalah.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Tambahkan file ke tar dan buat arsip TarBz2 dengan Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Tambahkan file ke tar dan buat arsip TarBz2 dengan Aspose.Zip
url: /id/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan file ke tar dan buat arsip TarBz2 dengan Aspose.Zip

Dalam tutorial ini Anda akan menemukan **cara menambahkan file ke tar** arsip dan mengubahnya menjadi file **TarBz2** yang kompak menggunakan pustaka **Aspose.Zip** untuk .NET. Baik Anda sedang membangun utilitas cadangan, menerbitkan paket penyebaran, atau membutuhkan bundel ringan untuk distribusi, langkah‑langkah di bawah ini akan memandu Anda menambahkan file ke kontainer tar, menerapkan kompresi Bzip2, dan menghasilkan arsip yang siap‑dibagikan.

## Jawaban Cepat
- **Library apa yang harus saya gunakan?** Aspose.Zip untuk .NET  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit  
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; versi percobaan gratis tersedia  
- **Bisakah saya mengompres beberapa file?** Ya – tambahkan sebanyak entri yang Anda inginkan ke arsip tar  
- **Apakah kompatibel dengan .NET 6+?** Tentu saja, Aspose.Zip mendukung .NET Framework dan .NET Core/5/6  

## Apa itu arsip TarBz2?

File TarBz2 menggabungkan kontainer **tar** tradisional (yang mempertahankan struktur direktori dan metadata file) dengan kompresi **Bzip2**, menghasilkan paket `.tar.bz2` yang sangat terkompresi. Format ini populer pada sistem mirip Unix karena menawarkan keseimbangan yang baik antara rasio kompresi dan kecepatan dekompresi.

## Mengapa mengompres file ke TarBz2 dengan Aspose.Zip?

Aspose.Zip dapat menghasilkan arsip TarBz2 dalam **dua panggilan API** sambil menangani aliran secara efisien. Ia mendukung **lebih dari 50 format arsip dan kompresi**, memproses file hingga **2 GB** tanpa memuat seluruh arsip ke memori, dan berjalan pada runtime .NET Windows, Linux, dan macOS. Pustaka ini juga memberi Anda kontrol detail atas nama entri, cap waktu, dan tingkat kompresi, menjadikannya ideal untuk utilitas konsol maupun layanan web.

## Prasyarat

- **Aspose.Zip untuk .NET** – unduh paket terbaru dari situs resmi: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Direktori dokumen** – folder yang berisi file yang ingin Anda arsipkan. Dalam contoh kami merujuknya dengan variabel `dataDir`.

> **Tip Pro:** Simpan file sumber Anda dalam folder khusus untuk menghindari penyertaan tidak sengaja file yang tidak diinginkan.

## Impor namespace

Pertama, impor namespace yang diperlukan agar Anda dapat mengakses kelas Tar dan Bzip2 milik Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Langkah 1: atur direktori dokumen

Tentukan jalur yang mengarah ke folder yang berisi file yang ingin Anda arsipkan.

```csharp
string dataDir = "Your Document Directory";
```

> Ganti `"Your Document Directory"` dengan jalur absolut atau relatif ke folder sumber Anda.

## Langkah 2: tambahkan file ke tar dan buat arsip TarBz2

`TarArchive` mewakili kontainer tar dalam memori yang dapat menampung banyak entri file.  
`Bzip2Archive` mengompres aliran menggunakan algoritma Bzip2.  
Metode `CreateEntry` menambahkan file ke arsip tar sebagai entri baru.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **menambahkan file ke tar** – Anda dapat memanggil metode ini untuk setiap file yang diperlukan dalam arsip.  
- `bz2.SetSource(archive)` memberi tahu arsip Bzip2 untuk mengompres seluruh aliran tar.  
- `bz2.Save(...)` menulis file **TarBz2** akhir ke disk.

**Tip:** Untuk **menambahkan file ke tar** secara massal, cukup ulangi `archive.CreateEntry` untuk setiap file sebelum memanggil `bz2.Save`.

## Cara menambahkan file ke tar?

Muat direktori sumber, buat instance `TarArchive`, tambahkan setiap file dengan `CreateEntry`, lalu bungkus aliran tar dalam `Bzip2Archive` dan panggil `Save`. Pola dua langkah ini menambahkan sejumlah file apa pun dan menghasilkan file `.tar.bz2` dalam alur tunggal yang lancar, menghilangkan kebutuhan akan file sementara atau alat eksternal.

## Masalah umum & solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** error | Jalur `dataDir` salah atau ekstensi file hilang | Verifikasi jalur lengkap dan pastikan file tersebut ada. |
| **Arsip kosong** | Tidak ada entri yang ditambahkan sebelum `bz2.Save` | Tambahkan setidaknya satu pemanggilan `CreateEntry`. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis ke folder output | Jalankan aplikasi dengan hak yang tepat atau pilih direktori yang dapat ditulisi. |

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Zip kompatibel dengan semua aplikasi .NET?**  
A: Ya. Ia bekerja dengan .NET Framework, .NET Core, .NET 5/6, dan runtime yang lebih baru.

**Q: Bisakah saya mengompres beberapa file secara bersamaan?**  
A: Tentu saja. Panggil `CreateEntry` untuk setiap file sebelum menyimpan arsip.

**Q: Di mana saya dapat menemukan dokumentasi tambahan?**  
A: Dokumentasi terperinci tersedia di **referensi API Aspose.Zip .NET**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**  
A: Anda dapat **meminta lisensi sementara** di sini: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Apakah tersedia versi percobaan gratis?**  
A: Ya, **unduh versi percobaan dari rilis Aspose**: [download a trial version](https://releases.aspose.com/).

## Kesimpulan

Anda sekarang tahu **cara menambahkan file ke tar**, mengompres aliran tar dengan Bzip2, dan menghasilkan arsip **TarBz2** menggunakan Aspose.Zip untuk .NET. Pendekatan ini cepat, efisien memori, dan bekerja di semua platform .NET modern. Silakan bereksperimen dengan set file yang lebih besar, nama entri khusus, atau mengintegrasikan kode ke dalam pipeline cadangan atau penyebaran Anda sendiri.

Jika Anda mengalami tantangan apa pun, komunitas Aspose.Zip siap membantu—kunjungi **forum dukungan Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Terakhir Diperbarui:** 2026-08-07  
**Diuji Dengan:** Aspose.Zip untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Tambahkan file ke tar dan buat arsip tarxz dengan Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Tambahkan file ke tar dan kompres ke TarZ dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}