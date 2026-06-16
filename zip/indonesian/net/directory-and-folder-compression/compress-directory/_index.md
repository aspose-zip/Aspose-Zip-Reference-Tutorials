---
date: 2026-05-30
description: Pelajari cara mengompres folder dengan Aspose.Zip untuk .NET, membuat
  arsip zip .NET secara efisien, dan mengurangi ruang penyimpanan dalam aplikasi .NET
  Anda.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Cara Mengompres Folder
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres Folder Menggunakan Aspose.Zip untuk .NET
url: /id/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengompres Folder Menggunakan Aspose.Zip untuk .NET

Dalam tutorial ini Anda akan menemukan **cara mengompres folder** dengan cepat dan andal menggunakan Aspose.Zip untuk .NET. Baik Anda sedang membangun utilitas desktop, layanan berbasis cloud, atau skrip pencadangan otomatis, mengompres folder menjadi arsip ZIP dapat secara dramatis mengurangi kebutuhan penyimpanan dan mempercepat transfer jaringan. Kami akan membahas setiap langkah, menjelaskan mengapa setiap baris penting, dan menyoroti jebakan umum sehingga Anda dapat menerapkan teknik ini dengan percaya diri.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Zip?** Menyediakan API .NET sederhana untuk membuat dan mengekstrak arsip ZIP tanpa ketergantungan eksternal.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk kompresi folder dasar.  
- **Versi .NET mana yang didukung?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, dan .NET 5‑10.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya mengompres beberapa folder sekaligus?** Tentu—gunakan metode `CreateEntries` pada koleksi `DirectoryInfo` apa pun untuk **mengompres beberapa folder** dalam satu kali proses.  

`CreateEntries` menambahkan semua file dari sebuah direktori ke arsip.

## Apa itu “cara mengompres folder”?

Mengompres folder berarti mengambil setiap file dan sub‑folder di dalam sebuah direktori tertentu dan mengemasnya ke dalam satu arsip ZIP. Ini mengurangi ukuran keseluruhan, mempertahankan hierarki asli, dan memudahkan transfer atau penyimpanan data. ZIP yang dihasilkan dapat dibuka di platform apa pun tanpa perangkat lunak khusus, dan tetap mempertahankan struktur folder sehingga saat diekstrak tata letak asli dipulihkan persis seperti semula.

## Mengapa menggunakan Aspose.Zip untuk tugas ini?

Aspose.Zip memungkinkan Anda **membuat file arsip zip** langsung dari kode .NET dengan API konsisten di semua runtime yang didukung. Muat kelas `Archive`, tambahkan entri, atur `CompressionLevel`, opsional beri kata sandi, dan panggil `Save`. Perpustakaan ini memproses folder yang berisi ribuan file dalam kurang dari satu detik pada perangkat keras tipikal, dan mendukung lebih dari 50 format kompresi serta algoritma enkripsi.

## Prasyarat

- **Aspose.Zip untuk .NET** – unduh di [sini](https://releases.aspose.com/zip/net/) atau [sini](https://releases.aspose.com/zip/net).  
- **Lingkungan Pengembangan** – Visual Studio, Rider, atau IDE apa pun yang mendukung C#.  
- **Direktori Dokumen** – ganti `"Your Document Directory"` dalam kode dengan jalur ke folder yang ingin Anda kompres.  
- **Dokumentasi Referensi** – lihat dokumen resmi [di sini](https://reference.aspose.com/zip/net/).

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan. Ini memberi Anda akses ke kelas kompresi inti.

```csharp
using Aspose.Zip;
using System.IO;
```

## Cara Mengompres Folder dengan Aspose.Zip

Berikut contoh sederhana yang menunjukkan **cara mengompres folder**. Pola yang sama dapat diperluas untuk **mengompres beberapa file .net** atau membuat struktur arsip khusus.

### Langkah 1: Inisialisasi Direktori Dokumen Anda

Setel variabel `dataDir` ke jalur direktori yang ingin Anda kompres.

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Buat File ZIP Output

Buka dua objek `FileStream` untuk file ZIP output. Ini menunjukkan cara menghasilkan lebih dari satu arsip dari sumber yang sama—berguna untuk pencadangan berversi.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Langkah 3: Kompres Direktori

Kelas `Archive` mewakili arsip ZIP dan menyediakan metode untuk menambahkan entri serta menyimpan file. Gunakan untuk menambahkan setiap entri dari folder target. Contoh ini menggunakan folder contoh bernama **CanterburyCorpus**, tetapi Anda dapat menunjuk ke direktori apa pun.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Tip pro:** Jika Anda perlu **membuat arsip zip .net** dengan tingkat kompresi tertentu, setel `archive.CompressionLevel` sebelum memanggil `Save`.

## Masalah Umum dan Solusinya

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| File ZIP kosong | `dataDir` mengarah ke folder yang salah atau tidak ada slash akhir | Verifikasi jalur dan pastikan folder berisi file |
| `UnauthorizedAccessException` | Aplikasi tidak memiliki izin sistem file | Jalankan Visual Studio sebagai administrator atau berikan hak baca/tulis |
| Penggunaan memori tinggi untuk direktori besar | Memuat semua entri ke memori sekaligus | Gunakan `Archive.CreateEntryFromFile` dalam loop untuk streaming file secara individual |

## Pertanyaan yang Sering Diajukan (Tambahan)

**Q: Bisakah saya menambahkan kata sandi ke arsip ZIP?**  
A: Ya. Setel `archive.Password = "yourPassword";` sebelum memanggil `Save`.

**Q: Bagaimana cara menyertakan hanya tipe file tertentu?**  
A: Filter koleksi `DirectoryInfo` dengan `GetFiles("*.txt")` atau serupa sebelum memanggil `CreateEntries`.

**Q: Apakah ada cara memperbarui ZIP yang sudah ada tanpa membuatnya kembali?**  
A: Aspose.Zip mendukung pembaruan inkremental melalui `Archive.UpdateEntry`.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial maupun pribadi?

A1: Ya, Aspose.Zip untuk .NET dilisensikan untuk penggunaan komersial dan pribadi.

### Q2: Apakah tersedia trial gratis?

A2: Ya, Anda dapat menjelajahi trial gratis [di sini](https://releases.aspose.com/zip/net).

### Q3: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip untuk .NET?

A3: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas atau pertimbangkan membeli [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk bantuan khusus.

### Q4: Apakah ada contoh dan tutorial lain yang tersedia?

A4: Ya, [dokumentasi](https://reference.aspose.com/zip/net/) berisi contoh dan tutorial lengkap.

### Q5: Bisakah saya membeli Aspose.Zip untuk .NET?

A5: Tentu, Anda dapat melakukan pembelian [di sini](https://purchase.aspose.com/buy).

## Kesimpulan

Anda kini memiliki pola lengkap yang siap produksi untuk **cara mengompres folder** menggunakan Aspose.Zip untuk .NET. Dengan memanfaatkan kelas `Archive` dari perpustakaan ini, Anda dapat **membuat arsip zip** files, mengatur `CompressionLevel` khusus, menambahkan perlindungan kata sandi, dan bahkan **mengompres beberapa folder** dalam satu proses—menjadikannya sempurna untuk mengotomatisasi tugas pencadangan folder. Bereksperimenlah dengan API untuk menambahkan enkripsi, memecah arsip, atau streaming langsung ke penyimpanan cloud, dan Anda akan memiliki solusi kuat untuk kebutuhan kompresi berbasis .NET apa pun.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [zip multiple files c# – Kompresi Mudah dengan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip untuk .NET - Lindungi Arsip Zip dengan Kata Sandi & Simpan Banyak File Tanpa Kompresi](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Cara Mengompres Folder – Kompres Direktori dengan Aspose.Zip](/zip/net/directory-and-folder-compression/decompress-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}