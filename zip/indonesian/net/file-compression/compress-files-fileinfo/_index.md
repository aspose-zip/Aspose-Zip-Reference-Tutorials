---
date: 2026-02-28
description: Pelajari cara menambahkan folder ke zip dan menambahkan file ke zip menggunakan
  Aspose.Zip untuk .NET. Panduan langkah demi langkah ini menunjukkan cara mengompresi
  file dengan FileInfo dalam proyek ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Menambahkan Folder ke Zip Menggunakan Aspose.Zip untuk .NET – Mengompres
  File dengan FileInfo
url: /id/net/file-compression/compress-files-fileinfo/
weight: 11
---

 other markdown links: none else.

Check tables: we translated header row and cells.

Check list items: all translated.

Check headings: all translated except unchanged section.

Check code block placeholders: unchanged.

Check shortcodes: unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Folder ke Zip Menggunakan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **membuat arsip zip** secara programatis, Aspose.Zip untuk .NET memberikan API yang bersih dan berperforma tinggi yang bekerja di aplikasi .NET apa pun (termasuk ASP.NET). Dalam tutorial ini kami akan menjelaskan cara mengompres file dengan kelas `FileInfo`, menunjukkan cara **menambahkan file ke zip**, dan menjelaskan mengapa pendekatan ini ideal untuk proyek .NET modern. Kami juga akan membahas cara **menambahkan folder ke zip** sehingga Anda dapat menggabungkan seluruh direktori dalam satu langkah. Mari kita mulai!

## Jawaban Cepat
- **Apa cara termudah untuk membuat arsip zip?** Gunakan kelas `Archive` Aspose.Zip bersama dengan objek `FileInfo`.  
- **Bisakah saya menambahkan beberapa file sekaligus?** Ya – cukup buat `FileInfo` untuk setiap file dan panggil `CreateEntry`.  
- **Apakah saya memerlukan lisensi khusus untuk ASP.NET?** Lisensi komersial Aspose.Zip diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Apakah API ini thread‑safe?** Ya, selama setiap thread bekerja dengan instance `Archive` masing‑masing.

## Apa Itu Arsip Zip dan Mengapa Membuatnya?

Arsip zip menggabungkan satu atau lebih file ke dalam satu wadah terkompresi. Ini mengurangi ruang penyimpanan, mempercepat transfer jaringan, dan menyederhanakan distribusi. Baik Anda mengirim log, mengekspor laporan, atau mengemas aset untuk klien, mengetahui **cara membuat arsip zip** secara programatis adalah keterampilan berharga bagi setiap pengembang .NET.

## Mengapa Menggunakan Aspose.Zip untuk Menambahkan File ke Zip?

- **Tanpa dependensi eksternal** – implementasi murni .NET.  
- **Kontrol penuh atas tingkat kompresi dan encoding** (ASCII, UTF‑8, dll.).  
- **Mendukung file besar** (> 4 GB) dan perlindungan kata sandi.  
- **API konsisten di seluruh .NET Framework, .NET Core, dan .NET 5+**.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

1. **Aspose.Zip untuk .NET** terpasang. Unduh paket terbaru dari [halaman unduhan Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Sebuah folder di mesin Anda yang berisi file yang ingin Anda kompres (misalnya, `alice29.txt` dan `fields.c`).  

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

Pertama, tentukan folder yang berisi file sumber. Ganti placeholder dengan jalur absolut atau relatif pada sistem Anda:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip Pro:** Gunakan `Path.Combine` untuk membangun jalur secara lintas‑platform.

### Langkah 2: Buka File Zip untuk Menulis

Buat `FileStream` yang mengarah ke file zip output. Stream dibuka dalam mode **Create**, yang akan menimpa file yang ada dengan nama yang sama:

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

> **Mengapa menggunakan `FileInfo`?** Ini menghindari pemuatan seluruh file ke memori, yang sangat membantu untuk file berukuran besar.

### Langkah 4: Buat Arsip dan Tambahkan Entri

Instansiasi objek `Archive`, lalu panggil `CreateEntry` untuk setiap `FileInfo`. Argumen pertama adalah nama file di dalam zip, argumen kedua adalah `FileInfo` sumber:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Langkah 5: Simpan Arsip Zip dengan Encoding yang Diinginkan

Akhirnya, simpan arsip ke `FileStream` yang Anda buka sebelumnya. Di sini kami menggunakan encoding ASCII untuk nama entri, tetapi Anda dapat beralih ke UTF‑8 jika nama file Anda mengandung karakter non‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Saat blok `using` selesai, stream secara otomatis ditutup dan file zip siap digunakan.

## Cara Menambahkan Folder ke Zip Menggunakan Aspose.Zip

Jika Anda perlu **menambahkan folder ke zip** alih‑alih file individual, prosesnya sederhana:

1. **Enumerasi folder** dengan `DirectoryInfo.GetFiles` (dan opsional `GetDirectories` untuk rekursi).  
2. **Buat `FileInfo`** untuk setiap file yang ditemukan.  
3. **Panggil `CreateEntry`** dengan jalur relatif yang mencakup nama folder, misalnya, `"MyFolder/Report.pdf"`.

Karena API bekerja dengan `FileInfo`, Anda tidak pernah perlu memuat seluruh file ke memori, sehingga aman untuk direktori besar. Teknik ini juga berfungsi untuk skenario **zip multiple files asp.net** di mana Anda menghasilkan sekumpulan laporan secara dinamis dan perlu menyediakannya sebagai satu arsip.

## Masalah Umum & Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **File zip kosong** | `FileInfo` mengarah ke jalur yang tidak ada | Verifikasi `dataDir` dan nama file; gunakan `File.Exists` untuk memeriksa sebelum membuat entri. |
| **Encoding nama file tidak tepat** | Menggunakan encoding default dengan nama non‑ASCII | Setel `Encoding = Encoding.UTF8` di `ArchiveSaveOptions`. |
| **OutOfMemoryException pada file besar** | Memuat seluruh file ke memori | `FileInfo` melakukan streaming file; pastikan Anda tidak membaca file ke dalam array byte di tempat lain. |
| **Izin ditolak** | Aplikasi tidak memiliki izin menulis untuk folder output | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulis. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menambahkan perlindungan kata sandi ke arsip zip?**  
J: Ya. Setelah membuat `Archive`, setel `archive.Password = "yourPassword"` sebelum memanggil `Save`.

**T: Apakah memungkinkan memperbarui file zip yang sudah ada?**  
J: Aspose.Zip mendukung membuka arsip yang ada dengan `Archive.Open` dan kemudian menambahkan entri baru.

**T: Bagaimana cara mengompres file dalam controller ASP.NET MVC?**  
J: Kode yang sama berfungsi; pastikan aliran output dikembalikan sebagai `FileResult` ke klien.

**T: Apakah Aspose.Zip mendukung algoritma enkripsi?**  
J: Ia mendukung enkripsi standar ZipCrypto dan AES‑256.

**T: Bagaimana jika saya perlu mengompres folder secara rekursif?**  
J: Lakukan loop melalui `Directory.GetFiles` (dan sub‑folder) dan buat `FileInfo` untuk setiap file, lalu tambahkan ke arsip.

## FAQ Tambahan

**T: Bagaimana cara membuat arsip zip .net untuk kumpulan data besar?**  
J: Gunakan objek `FileInfo` untuk streaming data dan setel `CompressionLevel` di `ArchiveSaveOptions` untuk kinerja optimal.

**T: Bisakah saya menggunakan Aspose.Zip dalam API web .NET Core (zip files asp.net core)?**  
J: Tentu – perpustakaan ini sepenuhnya kompatibel dengan .NET Core 3.1 dan yang lebih baru.

**T: Apakah ada cara menambahkan folder ke zip tanpa menulis loop khusus?**  
J: Aspose.Zip tidak memiliki metode “add folder” tunggal, tetapi iterasi dengan `DirectoryInfo` ringan dan memberi Anda kontrol penuh atas nama entri.

**T: Apakah perlindungan kata sandi pada arsip zip memengaruhi kecepatan kompresi?**  
J: Mengaktifkan enkripsi menambah overhead kecil, tetapi dampaknya minimal untuk kebanyakan kasus penggunaan.

**T: Lisensi apa yang diperlukan untuk penyebaran komersial?**  
J: Lisensi Aspose.Zip berbayar diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk pengembangan dan pengujian.

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

Anda kini tahu **cara menambahkan folder ke zip** dan **cara membuat file arsip zip** menggunakan Aspose.Zip untuk .NET, cara **menambahkan file ke zip**, serta mengapa metode ini ideal untuk ASP.NET dan aplikasi .NET lainnya. Bereksperimenlah dengan tingkat kompresi, encoding, dan opsi enkripsi yang berbeda untuk menyesuaikan arsip dengan kebutuhan Anda. Selamat mengompres!

---

**Terakhir Diperbarui:** 2026-02-28  
**Diuji Dengan:** Aspose.Zip for .NET 24.12 (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}