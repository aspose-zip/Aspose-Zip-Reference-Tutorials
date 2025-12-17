---
date: 2025-12-17
description: Pelajari cara mengekstrak arsip Xar dan mendekompresi arsip Xar ke folder
  menggunakan Aspose.Zip untuk .NET. Ikuti panduan langkah demi langkah ini.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengekstrak Xar ke Folder Menggunakan Aspose.Zip untuk .NET
url: /id/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekstrak Xar ke Folder Menggunakan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda seorang pengembang .NET yang mencari cara **cara mengekstrak xar** yang andal, Aspose.Zip untuk .NET menyediakan API yang bersih dan berperforma tinggi. Pada tutorial ini kami akan memandu Anda melalui seluruh proses mendekompresi arsip Xar ke sebuah folder, menjelaskan mengapa pendekatan ini menghemat waktu Anda, dan menunjukkan kode tepat yang perlu Anda jalankan.

## Jawaban Cepat
- **Apa yang dilakukan perpustakaan ini?** Membaca dan mengekstrak arsip Xar tanpa alat eksternal.  
- **Versi .NET apa yang didukung?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah saya membutuhkan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit.  
- **Bisakah saya mengekstrak ke folder khusus?** Ya—cukup tentukan jalur target di `ExtractToDirectory`.

## Apa itu “cara mengekstrak xar”?
Mengekstrak arsip Xar berarti membaca paket terkompresi dan menuliskan file‑file internalnya ke sebuah direktori di disk. Ini berguna ketika Anda menerima paket XAR dari installer macOS, utilitas backup, atau alat pihak ketiga lainnya dan perlu memproses isinya dalam aplikasi .NET.

## Mengapa menggunakan Aspose.Zip untuk tugas ini?
- **Tanpa ketergantungan eksternal** – murni .NET, tanpa binari native.  
- **API berbasis stream** – bekerja dengan file, memory stream, atau network stream.  
- **Penanganan error yang kuat** – pengecualian detail membantu Anda memecahkan masalah arsip yang rusak.  
- **Kompatibilitas .NET penuh** – bekerja di runtime Windows, Linux, dan macOS.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.Zip untuk .NET** – terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari [sini](https://releases.aspose.com/zip/net/).
- **Direktori Dokumen** – folder dalam solusi Anda tempat file `.xar` contoh dan output yang diekstrak akan berada.

## Impor Namespace

Di proyek .NET Anda, sertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Langkah 1: Tentukan Direktori Dokumen Anda

```csharp
string dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur absolut atau relatif yang berisi `sample.xar` dan tempat Anda ingin folder output dibuat.

## Langkah 2: Dekompres Arsip Xar

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Potongan kode ini membuka file Xar, membuat instance `XarArchive`, dan mengekstrak **seluruh arsip xar yang didekompres** ke `DecompressXar_out`. Operasi ini sepenuhnya berbasis stream, sehingga bekerja secara efisien bahkan dengan paket berukuran besar.

## Langkah 3: Jalankan Kode

Bangun dan jalankan aplikasi Anda. Setelah eksekusi, Anda akan menemukan folder baru bernama `DecompressXar_out` di dalam direktori dokumen Anda, berisi semua file yang dipaketkan dalam arsip `.xar` asli.

## Masalah Umum & Tips

- **File tidak ditemukan** – Pastikan jalur di `File.OpenRead` mengarah ke `sample.xar` dengan benar. Gunakan `Path.Combine` untuk penanganan jalur yang lebih aman.  
- **Akses ditolak** – Jalankan aplikasi dengan izin sistem file yang cukup, terutama saat menulis ke direktori yang dilindungi.  
- **Arsip rusak** – Aspose.Zip melempar `InvalidDataException`; pastikan file `.xar` sumber tidak korup.

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Zip kompatibel dengan versi .NET terbaru?**  
J: Ya, Aspose.Zip secara rutin diperbarui untuk memastikan kompatibilitas dengan versi .NET terbaru. Lihat [dokumentasi](https://reference.aspose.com/zip/net/) untuk detail spesifik.

**T: Bisakah saya mencoba Aspose.Zip sebelum membeli?**  
J: Tentu! Anda dapat mengunduh versi percobaan gratis dari [sini](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip?**  
J: Untuk pertanyaan atau bantuan, kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**T: Apakah ada lisensi sementara untuk Aspose.Zip?**  
J: Ya, lisensi sementara dapat diperoleh dari [sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat membeli Aspose.Zip untuk .NET?**  
J: Anda dapat membeli Aspose.Zip untuk .NET [di sini](https://purchase.aspose.com/buy).

**T: Bisakah saya mengekstrak hanya file tertentu dari arsip Xar?**  
J: Ya—gunakan `archive.Entries` untuk mengenumerasi item dan panggil `ExtractToFile` pada entri yang dipilih.

**T: Apakah perpustakaan mendukung file Xar yang dilindungi kata sandi?**  
J: Saat ini, arsip Xar tidak mendukung enkripsi; jika Anda menemukan file yang dilindungi, Anda harus mendekripsinya terlebih dahulu sebelum menggunakan Aspose.Zip.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}