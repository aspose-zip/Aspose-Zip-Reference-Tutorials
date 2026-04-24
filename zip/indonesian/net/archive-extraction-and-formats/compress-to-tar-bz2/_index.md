---
date: 2026-04-24
description: Pelajari cara mengompres tar dan membuat arsip TarBz2 di .NET dengan
  Aspose.Zip. Panduan langkah demi langkah ini menunjukkan cara menambahkan file ke
  tar dan menghasilkan file tarbz2 secara efisien.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Mengompres ke TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengompres tar dan membuat TarBz2 dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres tar dan membuat TarBz2 dengan Aspose.Zip untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan mempelajari **cara mengompres tar** arsip dan mengubahnya menjadi file **TarBz2** yang kompak menggunakan pustaka **Aspose.Zip** untuk .NET. Baik Anda sedang membuat utilitas cadangan, menerbitkan paket penyebaran, atau sekadar membutuhkan bundel ringan untuk distribusi, langkah-langkah di bawah ini akan memandu Anda menambahkan file ke tar, menerapkan kompresi Bzip2, dan menghasilkan arsip siap‑dibagikan.

Sebelum kita mulai, pastikan Anda memiliki prasyarat yang tercantum di bagian selanjutnya panduan ini sehingga Anda dapat mengikuti tanpa kendala.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip untuk .NET  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit  
- **Apakah saya memerlukan lisensi?** Lisensi sementara diperlukan untuk produksi; versi percobaan gratis tersedia  
- **Bisakah saya mengompres beberapa file?** Ya – tambahkan sebanyak mungkin entri yang Anda inginkan ke arsip tar  
- **Apakah kompatibel dengan .NET 6+?** Tentu, Aspose.Zip mendukung .NET Framework dan .NET Core/5/6  

## Apa itu arsip TarBz2?

File **TarBz2** menggabungkan kontainer **tar** tradisional (yang mempertahankan struktur direktori dan metadata file) dengan kompresi **Bzip2**, menghasilkan paket `.tar.bz2` yang sangat terkompresi. Format ini populer pada sistem mirip Unix karena menawarkan keseimbangan yang baik antara rasio kompresi dan kecepatan dekompresi.

## Mengapa mengompres file ke TarBz2 dengan Aspose.Zip?

- **Kecepatan & Kesederhanaan** – Panggilan API satu baris menangani pembuatan tar dan kompresi Bzip2.  
- **Lintas‑platform** – Berfungsi pada runtime .NET Windows, Linux, dan macOS.  
- **Kontrol detail** – Pilih file mana yang akan disertakan, atur nama entri khusus, dan alirkan langsung ke disk.  
- **Dukungan .NET yang kuat** – Sempurna untuk skenario **tar archive .net**, dari aplikasi konsol hingga layanan web.  

## Prasyarat

- **Aspose.Zip untuk .NET** – Unduh paket terbaru dari situs resmi: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Direktori Dokumen** – Folder yang berisi file yang ingin Anda arsipkan. Dalam contoh kami merujuknya dengan variabel `dataDir`.

> **Tips profesional:** Simpan file sumber Anda dalam folder khusus untuk menghindari penyertaan tidak sengaja file yang tidak diinginkan.

## Impor Namespace

Pertama, impor namespace yang diperlukan sehingga Anda dapat mengakses kelas Tar dan Bzip2 milik Aspose.Zip.

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

Inti proses adalah membuat `TarArchive`, menambahkan entri, lalu membungkusnya dengan `Bzip2Archive`. Kode di bawah ini menunjukkan **cara membuat tar** dan mengompresnya menjadi **TarBz2** dengan gaya pola disposable yang bersih.

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

## Masalah Umum & Solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** error | Jalur `dataDir` salah atau ekstensi file hilang | Verifikasi jalur lengkap dan pastikan file tersebut ada. |
| **Arsip kosong** | Tidak ada entri yang ditambahkan sebelum `bz2.Save` | Tambahkan setidaknya satu pemanggilan `CreateEntry`. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis ke folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Zip kompatibel dengan semua aplikasi .NET?**  
A: Ya. Ini bekerja dengan .NET Framework, .NET Core, .NET 5/6, dan runtime yang lebih baru.

**Q: Apakah saya dapat mengompres beberapa file secara bersamaan?**  
A: Tentu saja. Panggil `CreateEntry` untuk setiap file sebelum menyimpan arsip.

**Q: Di mana saya dapat menemukan dokumentasi tambahan?**  
A: Dokumen detail tersedia [di sini](https://reference.aspose.com/zip/net/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**  
A: Anda dapat memintanya [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Apakah ada percobaan gratis yang tersedia?**  
A: Ya, unduh versi percobaan [di sini](https://releases.aspose.com/).

## Kesimpulan

Anda kini telah mempelajari **cara mengompres tar**, menambahkan file ke dalamnya, dan membungkus hasilnya dalam aliran Bzip2 untuk menghasilkan arsip **TarBz2** menggunakan Aspose.Zip untuk .NET. Pendekatan ini cepat, dapat diandalkan, dan bekerja di semua platform .NET modern. Silakan bereksperimen dengan set file yang lebih besar, nama entri khusus, atau mengintegrasikan kode ke dalam pipeline cadangan atau penyebaran Anda sendiri.

Jika Anda mengalami tantangan, komunitas Aspose.Zip siap membantu—cukup kunjungi [forum dukungan Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Terakhir Diperbarui:** 2026-04-24  
**Diuji Dengan:** Aspose.Zip untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}