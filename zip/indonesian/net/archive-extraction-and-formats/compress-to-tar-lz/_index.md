---
date: 2026-02-23
description: Pelajari cara mengompres beberapa file menjadi tar menggunakan Aspose.Zip
  untuk .NET dan membuat arsip tar.lz secara efisien.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengompres beberapa file tar dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres beberapa file tar dengan Aspose.Zip untuk .NET

Dalam pengembangan .NET modern, mengemas file secara efisien dapat secara dramatis meningkatkan ukuran penyebaran dan waktu transfer jaringan. **Compress multiple files tar** adalah kebutuhan yang sering muncul ketika Anda memerlukan arsip TAR yang ringan dan terkompresi LZ untuk cadangan, distribusi, atau unggahan ke cloud. Pada tutorial ini kami akan memandu Anda melalui contoh **tar.lz compression** langkah‑demi‑langkah menggunakan pustaka Aspose.Zip, sehingga Anda dapat dengan cepat membuat **arsip tar.lz** dalam aplikasi Anda sendiri.

## Quick Answers
- **Library apa yang harus saya gunakan?** Aspose.Zip untuk .NET.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk contoh dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengompres beberapa file sekaligus?** Ya – cukup tambahkan lebih banyak entri sebelum menyimpan.

## How to compress multiple files tar
Bagian ini secara langsung menjawab kata kunci utama dan menunjukkan langkah‑langkah tepat untuk **compress multiple files tar** menggunakan Aspose.Zip. Pendekatan ini bekerja untuk jumlah file berapa pun, dan Anda dapat dengan mudah menyesuaikannya dengan struktur folder Anda sendiri.

## What is tar.lz compression?
`tar.lz` adalah arsip TAR yang telah dikompresi menggunakan algoritma LZMA (sering disebut hanya **LZ**). Ia menggabungkan kesederhanaan pengelompokan file TAR dengan rasio kompresi tinggi LZ, menjadikannya ideal untuk file cadangan, distribusi paket, atau skenario apa pun di mana bandwidth penting.

## Why use Aspose.Zip for .NET?
Aspose.Zip menyederhanakan detail tingkat rendah pembuatan arsip, memberikan Anda API berorientasi objek yang bersih. Anda mendapatkan:

* **Zero external dependencies** – implementasi murni .NET.  
* **Cross‑platform support** – berfungsi di Windows, Linux, dan macOS.  
* **Built‑in LZ compression** – tidak perlu menginstal alat native tambahan.  
* **Strong error handling** – pengecualian bersifat deskriptif, memudahkan proses debugging.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** – unduh dari [here](https://releases.aspose.com/zip/net/).  
- Sebuah folder yang berisi file‑file yang ingin Anda arsipkan. Jalur ke folder ini akan disimpan dalam variabel `dataDir` (akan Anda atur pada Langkah 3).

## Import Namespaces
Tambahkan namespace yang diperlukan agar compiler mengetahui di mana menemukan kelas‑kelas yang akan kita gunakan.

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to create tar.lz archive – Step‑by‑Step Guide

### Step 1: Compress a single file
Contoh pertama menunjukkan skenario paling dasar – menambahkan satu file ke arsip TAR dan kemudian menyimpannya sebagai file **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explanation**

- `new TarArchive()` membuat kontainer TAR kosong.  
- `CreateEntry` menambahkan file `alice29.txt` dari `dataDir` Anda.  
- `SaveLzipped` menulis arsip ke disk dan menerapkan kompresi LZ, menghasilkan `archive.tar.lz`.

### Step 2: Compress multiple files in one archive
Seringkali Anda perlu menggabungkan beberapa file sekaligus. Cukup panggil `CreateEntry` untuk setiap file sebelum menyimpan. Ini memperlihatkan **add files to tar lz** dan secara efektif **compress multiple files tar**.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explanation**

- Kode mengikuti pola yang sama seperti Langkah 1, tetapi menambahkan entri kedua (`lcet10.txt`).  
- Anda dapat mengulangi `CreateEntry` sebanyak yang diperlukan; pustaka akan menangani struktur TAR internal secara otomatis.

### Step 3: Specify your document directory
Ganti placeholder dengan jalur sebenarnya tempat file sumber Anda berada. Jalur ini digunakan oleh contoh‑contoh di atas.

```csharp
string dataDir = "Your Document Directory";
```

**Explanation**

- Atur `dataDir` ke jalur folder yang lengkap, misalnya `@"C:\MyFiles\"`.  
- Menyimpan direktori dalam variabel membuat kode dapat digunakan kembali dan lebih mudah dipelihara.

## Common pitfalls & troubleshooting
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `FileNotFoundException` saat menjalankan contoh | `dataDir` mengarah ke folder yang tidak ada atau nama file salah ketik | Verifikasi jalur dan nama file; gunakan `Path.Combine` untuk keamanan. |
| File output berukuran **0 KB** | `archive.SaveLzipped` dipanggil sebelum ada entri yang ditambahkan | Pastikan setidaknya satu pemanggilan `CreateEntry` terjadi sebelum `SaveLzipped`. |
| Kompresi terasa lambat | File besar dengan ukuran buffer default | Pertimbangkan memproses file dalam potongan atau menggunakan I/O asinkron jika kinerja kritis. |

## Conclusion
Anda kini tahu **cara mengompres tar.lz** menggunakan Aspose.Zip untuk .NET, baik untuk satu dokumen maupun kumpulan file. Contoh **tar.lz compression** ini memperlihatkan cara bersih dan siap produksi untuk **membuat arsip tar lz** yang dapat dengan mudah dipindahkan atau disimpan.

## Frequently Asked Questions

**Q:** Bisakah saya mengompres file berukuran apa pun dengan Aspose.Zip untuk .NET?  
**A:** Ya, pustaka menangani baik file kecil maupun sangat besar; pastikan Anda memiliki memori dan ruang disk yang cukup untuk struktur TAR sementara.

**Q:** Apakah kode ini kompatibel dengan rilis terbaru Aspose.Zip?  
**A:** Contoh ini menargetkan versi saat ini; selalu perbarui paket NuGet untuk mendapatkan perbaikan bug dan fitur baru.

**Q:** Apakah ada pertimbangan lisensi?  
**A:** Lisensi komersial diperlukan untuk penggunaan produksi. Lihat detail lisensi di [Aspose website](https://purchase.aspose.com/buy).

**Q:** Bisakah saya menggunakan ini dalam proyek komersial?  
**A:** Tentu – setelah Anda memiliki lisensi yang valid, Anda dapat menyematkan pustaka ini dalam aplikasi komersial apa pun.

**Q:** Di mana saya dapat mendapatkan bantuan jika mengalami masalah?  
**A:** Kunjungi [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas dan bantuan resmi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---