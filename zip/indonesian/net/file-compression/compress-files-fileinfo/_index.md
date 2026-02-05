---
date: 2026-02-05
description: Pelajari cara mengompres beberapa file dengan C# dan membuat arsip zip
  .NET menggunakan Aspose.Zip. Panduan langkah demi langkah ini menunjukkan cara mengompres
  file dengan FileInfo dalam proyek ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara meng-zip beberapa file c# menggunakan Aspose.Zip untuk .NET
url: /id/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres beberapa file c# menggunakan Aspise.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **mengompres beberapa file c#** secara programatis, Aspose.Zip untuk .NET menyediakan API yang bersih dan berperforma tinggi yang dapat bekerja di aplikasi .NET apa pun (termasuk ASP.NET). Pada tutorial ini kami akan menunjukkan cara mengompres file dengan kelas `FileInfo`, memperlihatkan cara **menambahkan file ke zip**, dan menjelaskan mengapa pendekatan ini ideal untuk proyek .NET modern. Mari kita mulai!

## Jawaban Cepat
- **Apa cara termudah untuk membuat arsip zip?** Gunakan kelas `Archive` Aspose.Zip bersama objek `FileInfo`.  
- **Bisakah saya menambahkan beberapa file sekaligus?** Ya – cukup buat `FileInfo` untuk setiap file dan panggil `CreateEntry`.  
- **Apakah saya memerlukan lisensi khusus untuk ASP.NET?** Lisensi komersial Aspose.Zip diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Apakah API ini thread‑safe?** Ya, selama setiap thread bekerja dengan instance `Archive` masing‑masing.  
- **Bagaimana cara mengompres file c# tanpa memuatnya ke memori?** Gunakan objek `FileInfo` – mereka men-stream data secara langsung.  

## Cara mengompres beberapa file c#
Arsip zip menggabungkan satu atau lebih file ke dalam satu wadah terkompresi. Ini mengurangi ruang penyimpanan, mempercepat transfer jaringan, dan menyederhanakan distribusi. Baik Anda mengirim log, mengekspor laporan, atau mengemas aset untuk klien, mengetahui **cara mengompres file c#** secara programatis adalah keterampilan berharga bagi setiap pengembang .NET.

## Mengapa Menggunakan Aspose.Zip untuk Menambahkan File ke Zip?
- **Tanpa ketergantungan eksternal** – implementasi murni .NET.  
- **Kontrol penuh atas tingkat kompresi dan pengkodean** (ASCII, UTF‑8, dll.).  
- **Mendukung file besar** (> 4 GB) dan perlindungan password.  
- **API konsisten di seluruh .NET Framework, .NET Core, dan .NET 5+**.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

1. **Aspose.Zip untuk .NET** terpasang. Unduh paket terbaru dari [halaman unduhan Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Sebuah folder di mesin Anda yang berisi file‑file yang ingin Anda kompres (misalnya `alice29.txt` dan `fields.c`).  

## Mengimpor Namespace

Di setiap file C# tempat Anda bekerja dengan arsip zip, tambahkan pernyataan `using` berikut:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Namespace ini memberi Anda akses ke kelas `Archive`, opsi penyimpanan, dan utilitas I/O standar.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, tentukan folder yang menyimpan file sumber. Ganti placeholder dengan jalur absolut atau relatif pada sistem Anda:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip profesional:** Gunakan `Path.Combine` untuk membangun jalur secara lintas‑platform.

### Langkah 2: Buka File Zip untuk Penulisan

Buat `FileStream` yang menunjuk ke file zip output. Stream dibuka dalam mode **Create**, yang akan menimpa file dengan nama yang sama jika sudah ada:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Langkah 3: Siapkan Objek `FileInfo` untuk Setiap File Sumber

`FileInfo` memberi Aspose.Zip akses langsung ke file fisik di disk. Buat satu instance per file yang ingin Anda kompres:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Mengapa menggunakan `FileInfo`?** Karena tidak memuat seluruh file ke memori, sangat membantu untuk file berukuran besar.

### Langkah 4: Buat Arsip dan Tambahkan Entri

Instansiasikan objek `Archive`, lalu panggil `CreateEntry` untuk setiap `FileInfo`. Argumen pertama adalah nama file di dalam zip, argumen kedua adalah `FileInfo` sumber:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Langkah 5: Simpan Arsip Zip dengan Pengkodean yang Diinginkan

Akhirnya, persistenkan arsip ke `FileStream` yang telah Anda buka sebelumnya. Di sini kami menggunakan pengkodean ASCII untuk nama entri, namun Anda dapat beralih ke UTF‑8 jika nama file mengandung karakter non‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Saat blok `using` selesai, stream secara otomatis ditutup dan file zip siap digunakan.

## Masalah Umum & Solusinya

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| **File zip kosong** | `FileInfo` mengarah ke jalur yang tidak ada | Verifikasi `dataDir` dan nama file; gunakan `File.Exists` untuk memeriksa sebelum membuat entri. |
| **Pengkodean nama file tidak tepat** | Menggunakan pengkodean default dengan nama non‑ASCII | Atur `Encoding = Encoding.UTF8` pada `ArchiveSaveOptions`. |
| **OutOfMemoryException pada file besar** | Memuat seluruh file ke memori | `FileInfo` men‑stream file; pastikan Anda tidak membaca file ke array byte di tempat lain. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis ke folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menambahkan perlindungan password ke arsip zip?**  
J: Ya. Setelah membuat `Archive`, setel `archive.Password = "yourPassword"` sebelum memanggil `Save`.

**T: Apakah memungkinkan memperbarui file zip yang sudah ada?**  
J: Aspose.Zip mendukung membuka arsip yang ada dengan `Archive.Open` dan kemudian menambahkan entri baru.

**T: Bagaimana cara mengompres file dalam kontroler ASP.NET MVC?**  
J: Kode yang sama dapat digunakan; pastikan aliran output dikirim kembali sebagai `FileResult` ke klien.

**T: Apakah Aspose.Zip mendukung algoritma enkripsi?**  
J: Ia mendukung enkripsi standar ZipCrypto dan AES‑256.

**T: Bagaimana jika saya perlu mengompres sebuah folder secara rekursif?**  
J: Loop melalui `Directory.GetFiles` (dan sub‑folder) dan buat `FileInfo` untuk setiap file, lalu tambahkan ke arsip.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Kesimpulan

Anda kini mengetahui **cara mengompres beberapa file c#** menggunakan Aspose.Zip untuk .NET, cara **menambahkan file ke zip**, dan mengapa metode ini ideal untuk ASP.NET serta aplikasi .NET lainnya. Bereksperimenlah dengan tingkat kompresi, pengkodean, dan opsi enkripsi yang berbeda untuk menyesuaikan arsip sesuai kebutuhan Anda. Selamat mengompres!

---

**Terakhir Diperbarui:** 2026-02-05  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.12 (terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}