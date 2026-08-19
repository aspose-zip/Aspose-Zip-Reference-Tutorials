---
date: 2026-07-18
description: Pelajari cara menambahkan folder ke zip dan menambahkan file ke zip menggunakan
  Aspose.Zip untuk .NET. Panduan langkah demi langkah ini menunjukkan cara mengompres
  file dengan FileInfo dalam proyek ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Kompres File menggunakan FileInfo
og_description: Tambahkan folder ke zip menggunakan Aspose.Zip untuk .NET. Pelajari
  cara membuat arsip zip, menambahkan file ke zip, dan mengompres folder secara efisien
  di ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Tambahkan Folder ke Zip – Kompres File dengan Aspose.Zip untuk .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Tambahkan Folder ke Zip Menggunakan Aspose.Zip untuk .NET – Kompres File dengan
  FileInfo
url: /id/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah Folder ke Zip Menggunakan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **add folder to zip** secara programatis, Aspose.Zip untuk .NET menawarkan API yang bersih dan berperforma tinggi yang bekerja di semua aplikasi .NET (termasuk ASP.NET). Dalam tutorial ini kami akan menjelaskan cara mengompres file dengan kelas `FileInfo`, menunjukkan cara **add files to zip**, dan menjelaskan mengapa pendekatan ini ideal untuk proyek .NET modern. Kami juga akan membahas langkah‑langkah tepat untuk **add folder to zip** sehingga Anda dapat menggabungkan seluruh direktori dalam satu operasi. Mari kita mulai!

## Jawaban Cepat
- **Apa cara termudah untuk membuat arsip zip?** Gunakan kelas `Archive` milik Aspose.Zip bersama dengan objek `FileInfo`.  
- **Bisakah saya menambahkan beberapa file sekaligus?** Ya – cukup buat `FileInfo` untuk setiap file dan panggil `CreateEntry`.  
- **Apakah saya memerlukan lisensi khusus untuk ASP.NET?** Lisensi komersial Aspose.Zip diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET mana yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10.  
- **Apakah API thread‑safe?** Ya, selama setiap thread bekerja dengan instance `Archive` masing‑masing.

## Apa Itu Arsip Zip dan Mengapa Membuatnya?
Arsip zip menggabungkan satu atau lebih file ke dalam satu wadah terkompresi. Ini mengurangi ruang penyimpanan, mempercepat transfer jaringan, dan menyederhanakan distribusi. Baik Anda mengirimkan log, mengekspor laporan, atau mengemas aset untuk klien, mengetahui **how to create zip archive** secara programatis adalah keterampilan berharga bagi setiap pengembang .NET.

## Mengapa Menggunakan Aspose.Zip untuk Menambahkan File ke Zip?
Aspose.Zip menyediakan solusi murni‑.NET yang menghilangkan ketergantungan eksternal sekaligus memberi pengembang kontrol detail atas kompresi, pengkodean, dan keamanan. Ini mendukung file besar, perlindungan kata sandi, dan berfungsi secara konsisten di semua versi .NET yang didukung, menjadikannya pilihan andal untuk aplikasi legacy maupun modern.  

- **Zero external dependencies** – implementasi .NET murni.  
- **Full control over compression level and encoding** (ASCII, UTF‑8, dll).  
- **Supports files larger than 4 GB** dan perlindungan kata sandi.  
- **Consistent API across 50+ .NET versions** – dari .NET Framework 2.0 hingga .NET 10.  

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

1. **Aspose.Zip for .NET** terpasang. Unduh paket terbaru dari [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Sebuah folder di mesin Anda yang berisi file yang ingin Anda kompres (mis., `alice29.txt` dan `fields.c`).  

## Impor Namespace

Di setiap file C# tempat Anda akan bekerja dengan arsip zip, tambahkan pernyataan `using` berikut:

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

Pertama, tentukan folder yang berisi file sumber. Ganti placeholder dengan jalur absolut atau relatif di sistem Anda:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gunakan `Path.Combine` untuk membangun jalur secara lintas‑platform.

### Langkah 2: Buka File Zip untuk Menulis

Buat `FileStream` yang mengarah ke file zip output. Stream dibuka dalam mode **Create**, yang menimpa file yang ada dengan nama yang sama:

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

> **Why use `FileInfo`?** Ini menghindari memuat seluruh file ke memori, yang sangat membantu untuk file besar.

### Langkah 4: Buat Arsip dan Tambahkan Entri

Kelas `Archive` adalah objek inti Aspose.Zip yang mewakili kontainer zip dalam memori. Buat instance `Archive`, lalu panggil `CreateEntry` untuk setiap `FileInfo`. Argumen pertama adalah nama file di dalam zip, argumen kedua adalah `FileInfo` sumber:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Metode `CreateEntry` menambahkan entri file baru ke arsip, menghubungkan nama entri dengan `FileInfo` sumber sehingga data disalurkan langsung dari disk saat arsip disimpan.

### Langkah 5: Simpan Arsip Zip dengan Pengkodean yang Diinginkan

Terakhir, simpan arsip ke `FileStream` yang Anda buka sebelumnya. Di sini kami menggunakan pengkodean ASCII untuk nama entri, tetapi Anda dapat beralih ke UTF‑8 jika nama file Anda mengandung karakter non‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Saat blok `using` selesai, stream secara otomatis ditutup dan file zip siap digunakan.

## Cara Menambahkan Folder ke Zip Menggunakan Aspose.Zip?

Muat direktori target, enumerasi setiap file, dan tambahkan masing‑masing dengan jalur relatif yang mencakup nama folder. Pendekatan ini memungkinkan Anda **add folder to zip** tanpa harus mencantumkan setiap file secara manual. Dengan mempertahankan hierarki folder dalam nama entri, arsip yang dihasilkan dapat diekstrak dengan struktur direktori asli tetap utuh, yang penting untuk banyak skenario penyebaran.

1. Gunakan `DirectoryInfo` untuk menunjuk ke folder yang ingin Anda kompres.  
2. Panggil `GetFiles("*", SearchOption.AllDirectories)` untuk mengambil semua file secara rekursif.  
3. Untuk setiap file, buat `FileInfo` dan panggil `CreateEntry` dengan jalur seperti `"MyFolder/Report.pdf"`.

Karena API bekerja dengan `FileInfo`, ia menyalurkan setiap file langsung dari disk, menjaga penggunaan memori tetap rendah bahkan untuk folder yang berisi ratusan megabyte.

## Masalah Umum & Solusi

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **File zip kosong** | `FileInfo` menunjuk ke jalur yang tidak ada | Verifikasi `dataDir` dan nama file; gunakan `File.Exists` untuk memeriksa sebelum membuat entri. |
| **Pengkodean nama file tidak tepat** | Menggunakan pengkodean default dengan nama non‑ASCII | Setel `Encoding = Encoding.UTF8` di `ArchiveSaveOptions`. |
| **OutOfMemoryException pada file besar** | Memuat seluruh file ke memori | `FileInfo` menyalurkan file; pastikan Anda tidak membaca file ke dalam array byte di tempat lain. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis untuk folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulis. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menambahkan seluruh folder ke arsip zip dalam satu panggilan?**  
A: Tidak ada metode satu‑panggilan, tetapi enumerasi file dengan `DirectoryInfo` dan menambahkan masing‑masing melalui `CreateEntry` menghasilkan hasil yang sama secara efisien.

**Q: Apakah Aspose.Zip mendukung perlindungan kata sandi?**  
A: Ya, Anda dapat mengatur kata sandi pada objek `Archive` sebelum menyimpan untuk mengenkripsi seluruh arsip.

**Q: Seberapa besar file zip yang dapat ditangani Aspose.Zip?**  
A: Perpustakaan ini memproses file lebih besar dari 4 GB dan dapat membuat arsip melebihi 10 GB tanpa memuat seluruh arsip ke memori.

**Q: Apakah API kompatibel dengan .NET 6 dan .NET 8?**  
A: Tentu saja. Aspose.Zip mendukung .NET 5 hingga .NET 10, mencakup semua rilis LTS saat ini.

**Q: Tingkat kompresi apa yang tersedia?**  
A: Anda dapat memilih `CompressionLevel.NoCompression`, `Fast`, `Normal`, atau `Maximum` untuk menyeimbangkan kecepatan dan ukuran.

## Sumber Daya Lebih Lanjut

- Unduh paket Aspose.Zip terbaru: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Beli lisensi untuk penggunaan produksi: [purchase page](https://purchase.aspose.com/buy)  
- Dapatkan bantuan dari komunitas: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Coba Aspose.Zip secara gratis: [free trial here](https://releases.aspose.com/)  
- Dapatkan lisensi sementara untuk evaluasi: [this link](https://purchase.aspose.com/temporary-license/)

## Kesimpulan

Anda kini tahu **how to add folder to zip** dan **how to create zip archive** menggunakan Aspose.Zip untuk .NET, cara **add files to zip**, serta mengapa metode ini ideal untuk ASP.NET dan aplikasi .NET lainnya. Bereksperimenlah dengan tingkat kompresi, pengkodean, dan opsi enkripsi yang berbeda untuk menyesuaikan arsip dengan kebutuhan Anda. Selamat mengompres!

---

**Terakhir Diperbarui:** 2026-07-18  
**Diuji Dengan:** Aspose.Zip for .NET 24.12 (latest)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mengompres Folder Menggunakan Aspose.Zip untuk .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Kompresi Mudah dengan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-multiple-files/)
- [Buat Arsip Zip .NET – Kompresi File dengan Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}