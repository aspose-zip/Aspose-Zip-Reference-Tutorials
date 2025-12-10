---
date: 2025-12-05
description: Pelajari cara membuat arsip zip dan menambahkan file ke zip menggunakan
  Aspose.Zip untuk .NET. Panduan langkah demi langkah ini menunjukkan cara mengompresi
  file dengan FileInfo dalam proyek ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Membuat Arsip Zip Menggunakan Aspose.Zip untuk .NET – Mengompres File
  dengan FileInfo
url: /id/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Arsip Zip Menggunakan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **membuat arsip zip** secara programatis, Aspose.Zip untuk .NET menyediakan API yang bersih, berperforma tinggi, dan dapat bekerja di aplikasi .NET apa pun (termasuk ASP.NET). Pada tutorial ini kami akan menunjukkan cara mengompresi file dengan kelas `FileInfo`, memperlihatkan **cara menambahkan file ke zip**, serta menjelaskan mengapa pendekatan ini ideal untuk proyek .NET modern. Mari kita mulai!

## Jawaban Cepat
- **Apa cara termudah untuk membuat arsip zip?** Gunakan kelas `Archive` milik Aspose.Zip bersama objek `FileInfo`.  
- **Bisakah saya menambahkan beberapa file sekaligus?** Ya – cukup buat `FileInfo` untuk setiap file dan panggil `CreateEntry`.  
- **Apakah saya memerlukan lisensi khusus untuk ASP.NET?** Lisensi komersial Aspose.Zip diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Apakah API ini thread‑safe?** Ya, selama setiap thread menggunakan instance `Archive` masing‑masing.

## Apa Itu Arsip Zip dan Mengapa Membuatnya?
Arsip zip menggabungkan satu atau lebih file ke dalam satu wadah terkompresi. Ini mengurangi ruang penyimpanan, mempercepat transfer jaringan, dan menyederhanakan distribusi. Baik Anda mengirim log, mengekspor laporan, atau mengemas aset untuk klien, mengetahui **cara membuat arsip zip** secara programatis adalah keterampilan berharga bagi setiap pengembang .NET.

## Mengapa Menggunakan Aspose.Zip untuk Menambahkan File ke Zip?
- **Tanpa dependensi eksternal** – implementasi murni .NET.  
- **Kontrol penuh atas tingkat kompresi dan encoding** (ASCII, UTF‑8, dll.).  
- **Mendukung file besar** (> 4 GB) dan proteksi password.  
- **API konsisten di seluruh .NET Framework, .NET Core, dan .NET 5+**.

## Prasyarat

Sebelum masuk ke kode, pastikan Anda memiliki:

1. **Aspose.Zip untuk .NET** terpasang. Unduh paket terbaru dari [halaman unduhan Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Sebuah folder di mesin Anda yang berisi file‑file yang ingin dikompresi (misalnya `alice29.txt` dan `fields.c`).  

## Impor Namespace

Di setiap file C# tempat Anda bekerja dengan arsip zip, tambahkan pernyataan `using` berikut:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Namespace ini memberi Anda akses ke kelas `Archive`, opsi penyimpanan, dan utilitas I/O standar.

## Panduan Langkah‑demi‑Langkah

### Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, tentukan folder yang berisi file sumber. Ganti placeholder dengan jalur absolut atau relatif pada sistem Anda:

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

Instansiasi objek `Archive`, lalu panggil `CreateEntry` untuk setiap `FileInfo`. Argumen pertama adalah nama file di dalam zip, argumen kedua adalah `FileInfo` sumber:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Langkah 5: Simpan Arsip Zip dengan Encoding yang Diinginkan

Akhirnya, persistenkan arsip ke `FileStream` yang telah Anda buka sebelumnya. Di sini kami menggunakan encoding ASCII untuk nama entri, namun Anda dapat beralih ke UTF‑8 bila nama file mengandung karakter non‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Ketika blok `using` selesai, stream secara otomatis ditutup dan file zip siap digunakan.

## Masalah Umum & Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **File zip kosong** | `FileInfo` mengarah ke jalur yang tidak ada | Verifikasi `dataDir` dan nama file; gunakan `File.Exists` untuk memeriksa sebelum membuat entri. |
| **Encoding nama file salah** | Menggunakan encoding default dengan nama non‑ASCII | Atur `Encoding = Encoding.UTF8` pada `ArchiveSaveOptions`. |
| **OutOfMemoryException pada file besar** | Memuat seluruh file ke memori | `FileInfo` melakukan streaming; pastikan Anda tidak membaca file ke byte array di tempat lain. |
| **Permission denied** | Aplikasi tidak memiliki hak menulis pada folder output | Jalankan aplikasi dengan hak yang tepat atau pilih direktori yang dapat ditulisi. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menambahkan proteksi password pada arsip zip?**  
J: Ya. Setelah membuat `Archive`, setel `archive.Password = "yourPassword"` sebelum memanggil `Save`.

**T: Apakah memungkinkan memperbarui file zip yang sudah ada?**  
J: Aspose.Zip mendukung membuka arsip yang ada dengan `Archive.Open` lalu menambahkan entri baru.

**T: Bagaimana cara mengompresi file dalam controller ASP.NET MVC?**  
J: Kode yang sama dapat digunakan; pastikan stream output dikirim kembali sebagai `FileResult` ke klien.

**T: Apakah Aspose.Zip mendukung algoritma enkripsi?**  
J: Ia mendukung ZipCrypto standar dan enkripsi AES‑256.

**T: Bagaimana jika saya perlu mengompresi folder secara rekursif?**  
J: Loop melalui `Directory.GetFiles` (dan sub‑folder) serta buat `FileInfo` untuk setiap file, lalu tambahkan ke arsip.

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

Anda kini mengetahui **cara membuat arsip zip** menggunakan Aspose.Zip untuk .NET, **cara menambahkan file ke zip**, serta mengapa metode ini ideal untuk ASP.NET dan aplikasi .NET lainnya. Bereksperimenlah dengan tingkat kompresi, encoding, dan opsi enkripsi yang berbeda untuk menyesuaikan arsip sesuai kebutuhan Anda. Selamat mengompresi!

---

**Terakhir Diperbarui:** 2025-12-05  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.12 (terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}