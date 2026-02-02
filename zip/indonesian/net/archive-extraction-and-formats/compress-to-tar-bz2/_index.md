---
date: 2026-02-02
description: Pelajari cara menambahkan file ke tar dan mengompres file ke format tarbz2
  di .NET dengan Aspose.Zip. Panduan langkah demi langkah ini menunjukkan cara membuat
  arsip tarbz2 secara efisien.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Menambahkan file ke tar dan mengompres ke TarBz2 menggunakan Aspose.Zip untuk
  .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan file ke tar dan mengompres ke TarBz2 menggunakan Aspose.Zip untuk .NET

## Introduction

Selamat datang di panduan komprehensif kami tentang **add files to tar** dan mengompresnya ke format TarBz2 menggunakan Aspose.Zip untuk .NET. Baik Anda sedang membangun utilitas pencadanganusi, tutorial ini akan memandu Anda melalui setiap langkah dengan penjelasan yang jelas, semua yang diperlukan.

## Quick Answers
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip for .NET  
- **Berapa lama implementasinya?** About 5‑10 minutes  
- **Apakah saya memerlukan lisensi?** A temporary license is required for production; a free trial is available  
- **Bisakah saya mengompres beberapa file?** Yes – add as many entries as you like to the Tar archive  
- **Apakah kompatibel dengan .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## What is “add files to tar”?
Menambahkan file ke **tar** (Tape Archive) membuat satu kontainer tidak terkompresi yang mempertahankan struktur direktori dan metadata file. Ketika Anda kemudian menerapkan kompresi Bzip2, hasilnya adalah arsip **tar.bz2** (TarBz2) — ideal untuk penyimpanan dan transfer yang efisien.

## Why compress files to TarBz2 with Aspose.Zip?
- **Kecepatan & Kesederhanaan** – Panggilan API satu baris menangani pembuatan tar dan kompresi Bzip2.  
- **Lintas‑platform** – Berfungsi di runtime .NET Windows, Linux, dan macOS.  
- **Kontrol detail** – Pilih file mana yang akan dimasukkan, atur nama entri khusus, dan alirkan langsung ke disk.  

## Prerequisites

- **Aspose.Zip for .NET** – Unduh paket terbaru dari situs resmi: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – Sebuah folder yang berisi file yang ingin Anda arsipkan. Dalam contoh kami merujuknya dengan variabel `dataDir`.

> **Pro tip:** Simpan file sumber Anda dalam folder khusus untuk menghindari penyertaan tidak sengaja file yang tidak diinginkan.

## Import Namespaces

Pertama, impor namespace yang diperlukan sehingga Anda dapat mengakses kelas Tar dan Bzip2 dari Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Step 1: Set the Document Directory

Define the path that points to the folder holding the files you want to archive.

```csharp
string dataDir = "Your Document Directory";
```

> Ganti `"Your Document Directory"` dengan path absolut atau relatif ke folder sumber Anda.

## Step 2: Add files to tar and create a TarBz2 archive

The core of the process is creating a `TarArchive`, adding entries, then wrapping it with a `Bzip2Archive`. The code below demonstrates **how to create tarbz2** in a clean, disposable‑pattern style.

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

- `CreateEntry` menambahkan setiap file ke kontainer **tar**.  
- `bz2.SetSource tar.  
- `bz2.Save(...)` menulis file **tar.bz2** akhir ke disk.

**Tip:** Untuk **mengompres file2 archive – step‑by‑step checklist
1. Siapkan folder sumber (`dataDir`).  
2. Inisialisasi `TarArchive` dan tambahkan setiap file dengan `CreateEntry`.  
3. Bungkus arsip tar dengan ` file **tar.b ini memastikan alur kerja **generate tarbz2 archive** yang konsisten.

## Common Issues & Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File tidak ditemukan** error | Jalur `dataDir` salah atau ekstensi file hilang | Verifikasi path lengkap dan pastikan file ada. |
| **Arsip kosong** | Tidak ada entri yang ditambahkan sebelum `bz2.Save` memiliki izin menulis ke folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |

## Frequently Asked Questions

**Q: Apakah Aspose.Zip kompatibel dengan semua aplikasi .NET?**  
A: Ya. Itu bekerja dengan .NET Framework,akah saya mengompres beberapa file secara bersamaan?**  
A: Tentu saja. Panggil `CreateEntry` untuk setiap file sebelum menyimpan arsip.

**Q: Di mana saya dapat menemukan dokumentasi tambahan?**  
A: Dokumentasi detail tersedia [here](https://reference.aspose.com/zip/net/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**  
A: Anda dapat meminta satu lisensi [here](https://purchase.aspose.com/temporary-license/).

**Q: Apakah ada versi percobaan gratis yang tersedia?**  
A: Ya, unduh versi percobaan [here](https://releases.aspose.com/).

## Conclusion

Anda kini telah mempelajari cara **add files to tar**, membungkusnya dalam aliran Bzip2, dan menghasilkan arsip **TarBz2** menggunakan Aspose.Zip untuk .NET. Teknik ini cepat, andperimen dengan set file yang lebih besar, nama entri khusus, atau apa pun, komunitas Aspose.Zip siap membantu—cukup kunjungi [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-02-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}