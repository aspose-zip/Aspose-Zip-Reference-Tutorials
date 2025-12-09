---
date: 2025-12-01
description: Pelajari cara mengompres file tar.lz di .NET dengan Aspose.Zip dan membuat
  arsip tar.lz dengan mudah.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengompres tar.lz dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres tar.lz dengan Aspose.Zip untuk .NET

Dalam pengembangan .NET modern, mengemas file secara efisien dapat secara dramatis meningkatkan ukuran penyebaran dan waktu transfer jaringan. **Cara mengompres tar.lz** adalah kebutuhan umum ketika Anda memerlukan arsip TAR yang ringan dan terkompresi LZ. Dalam tutorial ini kami akan memandu Anda melalui contoh **kompresi tar.lz** yang jelas, langkah demi langkah menggunakan pustaka Aspose.Zip, sehingga Anda dapat dengan cepat membuat arsip tar.lz dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip untuk .NET.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk contoh dasar.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya mengompres beberapa file sekaligus?** Ya – cukup tambahkan lebih banyak entri sebelum menyimpan.

## Apa itu kompresi tar.lz?
`tar.lz` adalah arsip TAR yang telah dikompresi menggunakan algoritma LZMA (sering disebut hanya **LZ**). Ini menggabungkan kesederhanaan pengelompokan file TAR dengan rasio kompresi tinggi LZ, menjadikannya ideal untuk file cadangan, distribusi paket, atau skenario apa pun di mana bandwidth penting.

## Mengapa menggunakan Aspose.Zip untuk .NET?
Aspose.Zip menyembunyikan detail tingkat rendah pembuatan arsip, memberikan API berorientasi objek yang bersih. Anda mendapatkan:

* **Tanpa ketergantungan eksternal** – implementasi .NET murni.  
* **Dukungan lintas‑platform** – berfungsi di Windows, Linux, dan macOS.  
* **Kompresi LZ bawaan** – tidak perlu menginstal alat native tambahan.  
* **Penanganan error yang kuat** – pengecualian bersifat deskriptif, memudahkan debugging.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- **Pustaka Aspose.Zip untuk .NET** – unduh dari [sini](https://releases.aspose.com/zip/net/).  
- Sebuah folder yang berisi file yang ingin Anda arsipkan. Path ke folder ini akan disimpan dalam variabel `dataDir` (Anda akan mengaturnya pada Langkah 3).

## Impor Namespace
Tambahkan namespace yang diperlukan agar kompiler mengetahui di mana menemukan kelas yang akan kami gunakan.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Cara membuat arsip tar.lz – Panduan Langkah‑demi‑Langkah

### Langkah 1: Kompres satu file
Contoh pertama menunjukkan skenario paling dasar – menambahkan satu file ke arsip TAR dan kemudian menyimpannya sebagai file **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Penjelasan**

- `new TarArchive()` membuat kontainer TAR kosong.  
- `CreateEntry` menambahkan file `alice29.txt` dari `dataDir` Anda.  
- `SaveLzipped` menulis arsip ke disk dan menerapkan kompresi LZ, menghasilkan `archive.tar.lz`.

### Langkah 2: Kompres beberapa file dalam satu arsip
Seringkali Anda perlu menggabungkan beberapa file bersama. Cukup panggil `CreateEntry` untuk setiap file sebelum menyimpan.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Penjelasan**

- Kode mengikuti pola yang sama seperti Langkah 1, tetapi menambahkan entri kedua (`lcet10.txt`).  
- Anda dapat mengulangi `CreateEntry` sebanyak yang diperlukan; pustaka menangani struktur TAR internal secara otomatis.

### Langkah 3: Tentukan direktori dokumen Anda
Ganti placeholder dengan path sebenarnya tempat file sumber Anda berada. Path ini digunakan oleh contoh-contoh di atas.

```csharp
string dataDir = "Your Document Directory";
```

**Penjelasan**

- Atur `dataDir` ke path folder yang lengkap, misalnya `@"C:\MyFiles\"`.  
- Menyimpan direktori dalam variabel membuat kode dapat digunakan kembali dan lebih mudah dipelihara.

## Kesulitan umum & pemecahan masalah
| Gejala | Penyebab kemungkinan | Solusi |
|---------|--------------|-----|
| `FileNotFoundException` saat menjalankan contoh | `dataDir` mengarah ke folder yang tidak ada atau nama file salah ketik | Verifikasi path dan nama file; gunakan `Path.Combine` untuk keamanan. |
| File output berukuran **0 KB** | `archive.SaveLzipped` dipanggil sebelum ada entri yang ditambahkan | Pastikan setidaknya satu pemanggilan `CreateEntry` sebelum `SaveLzipped`. |
| Kompresi terasa lambat | File besar dengan ukuran buffer default | Pertimbangkan memproses file dalam potongan atau menggunakan I/O asynchronous jika kinerja sangat penting. |

## Kesimpulan
Anda kini tahu **cara mengompres file tar.lz** menggunakan Aspose.Zip untuk .NET, baik Anda menangani satu dokumen maupun kumpulan file. **Contoh kompresi tar.lz** ini menunjukkan cara yang bersih dan siap produksi untuk membuat arsip ringan yang dapat dengan mudah dipindahkan atau disimpan.

## Pertanyaan yang Sering Diajukan

**Q:** Bisakah saya mengompres file dengan ukuran berapa pun menggunakan Aspose.Zip untuk .NET?  
**A:** Ya, pustaka menangani file kecil maupun sangat besar; pastikan Anda memiliki memori dan ruang disk yang cukup untuk struktur TAR sementara.

**Q:** Apakah kode ini kompatibel dengan rilis Aspose.Zip terbaru?  
**A:** Contoh ini menargetkan versi saat ini; selalu perbarui paket NuGet untuk perbaikan bug dan fitur baru.

**Q:** Apakah ada pertimbangan lisensi?  
**A:** Lisensi komersial diperlukan untuk penggunaan produksi. Lihat detail lisensi di [situs Aspose](https://purchase.aspose.com/buy).

**Q:** Bisakah saya menggunakan ini dalam proyek komersial?  
**A:** Tentu – setelah Anda memiliki lisensi yang valid, Anda dapat menyematkan pustaka ini dalam aplikasi komersial apa pun.

**Q:** Di mana saya dapat mendapatkan bantuan jika mengalami masalah?  
**A:** Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas dan bantuan resmi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-12-01  
**Diuji Dengan:** Aspose.Zip untuk .NET (rilis terbaru)  
**Penulis:** Aspose