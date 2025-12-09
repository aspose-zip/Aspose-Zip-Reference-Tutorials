---
date: 2025-11-29
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

## Pendahuluan

Selamat datang di panduan komprehensif kami tentang **cara menambahkan file ke tar** dan mengompresnya ke format TarBz2 menggunakan Aspose.Zip untuk .NET. Apakah Anda sedang membangun utilitas pencadangan, mengirim paket penyebaran, atau sekadar membutuhkan arsip kompak untuk distribusi, tutorial ini akan memandu Anda melalui setiap langkah dengan penjelasan yang jelas dan tips dunia nyata.

Sebelum kita mulai, pastikan Anda memiliki semua yang diperlukan.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip untuk .NET
- **Berapa lama implementasinya?** Sekitar 5‑10 menit
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; versi percobaan gratis tersedia
- **Bisakah saya mengompres beberapa file?** Ya – tambahkan sebanyak entri yang Anda inginkan ke arsip Tar
- **Apakah kompatibel dengan .NET 6+?** Tentu saja, Aspose.Zip mendukung .NET Framework dan .NET Core/5/6

## Apa itu “menambahkan file ke tar”?
Menambahkan file ke **tar** (Tape Archive) membuat satu kontainer tidak terkompresi yang mempertahankan struktur direktori dan metadata file. Ketika Anda kemudian menerapkan kompresi Bzip2, hasilnya adalah arsip **tar.bz2** (TarBz2) — ideal untuk penyimpanan dan transfer yang efisien.

## Mengapa mengompres file ke TarBz2 dengan Aspose.Zip?
- **Kecepatan & Kesederhanaan** – Panggilan API satu baris menangani pembuatan tar dan kompresi Bzip2.
- **Lintas‑platform** – Berfungsi di Windows, Linux, dan macOS runtime .NET.
- **Kontrol detail** – Pilih file yang akan disertakan, atur nama entri khusus, dan alirkan langsung ke disk.

## Prasyarat

- **Aspose.Zip untuk .NET** – Unduh paket terbaru dari situs resmi: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Direktori Dokumen** – Folder yang berisi file yang ingin Anda arsipkan. Dalam contoh kami merujuknya dengan variabel `dataDir`.

> **Tips pro:** Simpan file sumber Anda dalam folder khusus untuk menghindari penyertaan tidak sengaja file yang tidak diinginkan.

## Impor Namespace

Pertama, impor namespace yang diperlukan sehingga Anda dapat mengakses kelas Tar dan Bzip2 Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Langkah 1: Atur Direktori Dokumen

Tentukan jalur yang mengarah ke folder yang berisi file yang ingin Anda arsipkan.

```csharp
string dataDir = "Your Document Directory";
```

> Ganti `"Your Document Directory"` dengan jalur absolut atau relatif ke folder sumber Anda.

## Langkah 2: Tambahkan file ke tar dan buat arsip TarBz2

Inti proses adalah membuat `TarArchive`, menambahkan entri, lalu membungkusnya dengan `Bzip2Archive`. Kode di bawah ini menunjukkan **cara membuat tarbz2** dengan gaya pola disposable yang bersih.

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
- `bz2.SetSource(archive)` memberi tahu arsip Bzip2 untuk mengompres seluruh aliran tar.  
- `bz2.Save(...)` menulis file **tar.bz2** akhir ke disk.

**Tips:** Untuk **mengompres file ke tarbz2** secara massal, cukup ulangi `archive.CreateEntry` untuk setiap file yang Anda perlukan.

## Masalah Umum & Solusi

| Masalah | Alasan | Perbaikan |
|-------|--------|-----|
| **File tidak ditemukan** error | Jalur `dataDir` salah atau ekstensi file hilang | Verifikasi jalur lengkap dan pastikan file ada. |
| **Arsip kosong** | Tidak ada entri yang ditambahkan sebelum `bz2.Save` | Tambahkan setidaknya satu pemanggilan `CreateEntry`. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis ke folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulis. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Zip kompatibel dengan semua aplikasi .NET?**  
J: Ya. Ia bekerja dengan .NET Framework, .NET Core, .NET 5/6, dan runtime terbaru.

**T: Bisakah saya mengompres beberapa file secara bersamaan?**  
J: Tentu saja. Panggil `CreateEntry` untuk setiap file sebelum menyimpan arsip.

**T: Di mana saya dapat menemukan dokumentasi tambahan?**  
J: Dokumentasi detail tersedia [di sini](https://reference.aspose.com/zip/net/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**  
J: Anda dapat memintanya [di sini](https://purchase.aspose.com/temporary-license/).

**T: Apakah tersedia versi percobaan gratis?**  
J: Ya, unduh versi percobaan [di sini](https://releases.aspose.com/).

## Kesimpulan

Anda kini telah mempelajari cara **menambahkan file ke tar**, membungkusnya dalam aliran Bzip2, dan menghasilkan arsip **TarBz2** menggunakan Aspose.Zip untuk .NET. Teknik ini cepat, dapat diandalkan, dan bekerja di semua platform .NET modern. Jangan ragu untuk bereksperimen dengan set file yang lebih besar, nama entri khusus, atau mengintegrasikan kode ke dalam pipeline pencadangan atau penyebaran Anda sendiri.

Jika Anda menemui tantangan, komunitas Aspose.Zip siap membantu—cukup kunjungi [forum dukungan Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Terakhir Diperbarui:** 2025-11-29  
**Diuji Dengan:** Aspose.Zip untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}