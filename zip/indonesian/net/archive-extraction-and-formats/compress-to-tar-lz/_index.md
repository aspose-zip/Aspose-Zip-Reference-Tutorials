---
date: 2026-07-04
description: Pelajari cara mengompres beberapa file tar menggunakan Aspose.Zip for
  .NET dan membuat arsip tar.lz secara efisien.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Mengompres ke TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengompres beberapa file tar dengan Aspose.Zip for .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres beberapa file tar dengan Aspose.Zip untuk .NET

Dalam pengembangan .NET modern, mengemas file secara efisien dapat secara dramatis meningkatkan ukuran penyebaran dan waktu transfer jaringan. **Compress multiple files tar** adalah kebutuhan yang sering muncul ketika Anda memerlukan arsip TAR berkompresi LZ yang ringan untuk cadangan, distribusi, atau unggahan ke cloud. Pada tutorial ini kami akan memandu Anda melalui contoh **tar.lz compression example** yang jelas, langkah‑demi‑langkah menggunakan perpustakaan Aspose.Zip, sehingga Anda dapat dengan cepat membuat **arsip tar.lz** dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip untuk .NET.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk contoh dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengompres beberapa file sekaligus?** Ya – cukup tambahkan lebih banyak entri sebelum menyimpan.

## Bagaimana cara mengompres beberapa file tar dengan Aspose.Zip untuk .NET?
Muat file sumber Anda, buat instance `TarArchive`, tambahkan setiap file dengan `CreateEntry`, dan selesaikan dengan memanggil `SaveLzipped`. Perpustakaan menangani struktur TAR dan kompresi LZ secara internal, sehingga Anda mendapatkan satu file `*.tar.lz` hanya dalam beberapa baris kode. Pendekatan ini bekerja di Windows, Linux, dan macOS tanpa ketergantungan native.

## Apa itu kompresi tar.lz?
`tar.lz` adalah arsip TAR yang telah dikompresi menggunakan algoritma LZMA (sering disebut hanya **LZ**). Ini menggabungkan kesederhanaan pengelompokan file TAR dengan rasio kompresi tinggi LZ, menjadikannya ideal untuk file cadangan, distribusi paket, atau skenario apa pun di mana bandwidth penting.

## Mengapa menggunakan Aspose.Zip untuk .NET?
Aspose.Zip menyediakan solusi murni‑managed, lintas‑platform yang membuat arsip TAR, ZIP, dan berbasis LZ tanpa alat eksternal, mendukung lebih dari 30 format arsip, dan memberikan hingga 30 % kompresi lebih baik pada file besar, sambil menawarkan pengecualian terperinci untuk penanganan error yang kuat. Ia juga terintegrasi mulus dengan kerangka kerja logging .NET dan menyediakan peristiwa kemajuan yang detail.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- **Perpustakaan Aspose.Zip untuk .NET** – unduh dari [here](https://releases.aspose.com/zip/net/).  
- Folder yang berisi file yang ingin Anda arsipkan. Path ke folder ini akan disimpan dalam variabel `dataDir` (Anda akan mengaturnya pada Langkah 3).

## Impor Namespace
Tambahkan namespace yang diperlukan agar kompilator mengetahui di mana menemukan kelas yang akan kita gunakan.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Cara membuat arsip tar.lz – Panduan Langkah‑per‑Langkah

### Langkah 1: Kompres satu file
Contoh pertama menunjukkan skenario paling dasar – menambahkan satu file ke arsip TAR dan kemudian menyimpannya sebagai file **tar.lz**.

Kelas `TarArchive` mewakili kontainer TAR yang dapat menampung banyak file dalam satu arsip.  

**Penjelasan**

- `new TarArchive()` membuat kontainer TAR kosong.  
- `CreateEntry` menambahkan file `alice29.txt` dari `dataDir` Anda.  
- `SaveLzipped` menulis arsip ke disk dan menerapkan kompresi LZ, menghasilkan `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Langkah 2: Kompres beberapa file dalam satu arsip
Sering kali Anda perlu menggabungkan beberapa file bersama. Cukup panggil `CreateEntry` untuk setiap file sebelum menyimpan. Ini mendemonstrasikan **add files to tar lz** dan secara efektif **compress multiple files tar**.

**Penjelasan**

- Kode mengikuti pola yang sama seperti Langkah 1, tetapi menambahkan entri kedua (`lcet10.txt`).  
- Anda dapat mengulangi `CreateEntry` sebanyak yang diperlukan; perpustakaan menangani struktur TAR internal secara otomatis.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Langkah 3: Tentukan direktori dokumen Anda
Ganti placeholder dengan path sebenarnya tempat file sumber Anda berada. Path ini digunakan oleh contoh-contoh di atas.

**Penjelasan**

- Setel `dataDir` ke path folder yang lengkap, misalnya `@"C:\MyFiles\"`.  
- Menyimpan direktori dalam variabel membuat kode dapat digunakan kembali dan lebih mudah dipelihara.

```csharp
string dataDir = "Your Document Directory";
```

## Kesulitan umum & pemecahan masalah
| Gejala | Penyebab kemungkinan | Solusi |
|---------|----------------------|--------|
| `FileNotFoundException` saat menjalankan contoh | `dataDir` mengarah ke folder yang tidak ada atau nama file salah ketik | Verifikasi path dan nama file; gunakan `Path.Combine` untuk keamanan. |
| File output berukuran **0 KB** | `archive.SaveLzipped` dipanggil sebelum ada entri yang ditambahkan | Pastikan setidaknya satu panggilan `CreateEntry` terjadi sebelum `SaveLzipped`. |
| Kompresi terasa lambat | File besar dengan ukuran buffer default | Pertimbangkan memproses file dalam potongan atau menggunakan I/O asynchronous jika kinerja penting. |

## Kesimpulan
Anda kini tahu **cara mengompres file tar.lz** menggunakan Aspose.Zip untuk .NET, baik saat menangani satu dokumen maupun kumpulan file. **Contoh kompresi tar.lz** ini menunjukkan cara bersih dan siap produksi untuk **membuat arsip tar lz** yang dapat dengan mudah dipindahkan atau disimpan. Anda dapat mengompres file ke tar.lz menggunakan API yang sama dengan memanggil `SaveLzipped` setelah menambahkan semua entri yang diinginkan.

## Pertanyaan yang Sering Diajukan

**Q:** Bisakah saya mengompres file berukuran apa pun menggunakan Aspose.Zip untuk .NET?  
**A:** Ya, perpustakaan menangani baik file kecil maupun sangat besar; cukup pastikan Anda memiliki memori dan ruang disk yang cukup untuk struktur TAR sementara.

**Q:** Apakah kode kompatibel dengan rilis terbaru Aspose.Zip?  
**A:** Contoh ini menargetkan versi saat ini; selalu perbarui paket NuGet agar tetap up‑to‑date untuk perbaikan bug dan fitur baru.

**Q:** Apakah ada pertimbangan lisensi?  
**A:** Lisensi komersial diperlukan untuk penggunaan produksi. Lihat detail lisensi di [Aspose website](https://purchase.aspose.com/buy).

**Q:** Bisakah saya menggunakan ini dalam proyek komersial?  
**A:** Tentu – setelah Anda memiliki lisensi yang valid, Anda dapat menyematkan perpustakaan dalam aplikasi komersial apa pun.

**Q:** Di mana saya dapat mendapatkan bantuan jika mengalami masalah?  
**A:** Kunjungi [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas dan bantuan resmi.

---

**Last Updated:** 2026-07-04  
**Tested With:** Aspose.Zip untuk .NET (rilis terbaru)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cara mengompres tar dan membuat TarBz2 dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Tambahkan file ke tar dan buat arsip tarxz dengan Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}