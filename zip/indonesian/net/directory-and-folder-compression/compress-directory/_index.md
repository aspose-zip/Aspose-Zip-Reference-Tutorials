---
date: 2025-12-09
description: Pelajari cara mengompres direktori menggunakan Aspose.Zip untuk .NET
  dan membuat arsip zip .NET secara efisien. Optimalkan ruang penyimpanan dalam aplikasi
  .NET Anda.
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengompres Direktori Menggunakan Aspose.Zip untuk .NET
url: /id/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kompresi Direktori Tanpa Usaha dengan Aspose.Zip untuk .NET

Dalam tutorial ini, kami akan menunjukkan **cara mengompres direktori** menggunakan Aspose.Zip untuk .NET, cara yang kuat untuk mengelola kumpulan data besar dan menghemat ruang penyimpanan. Baik Anda membangun utilitas desktop atau layanan berbasis cloud, mengompres folder secara efisien dapat secara dramatis meningkatkan kinerja dan mengurangi biaya. Kami akan membimbing Anda melalui setiap langkah, menjelaskan alasan di balik kode, dan menunjukkan jebakan umum sehingga Anda dapat menerapkan teknik ini dengan percaya diri.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Zip?** Ia menyediakan API .NET sederhana untuk membuat dan mengekstrak arsip ZIP tanpa ketergantungan eksternal.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk kompresi direktori dasar.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya mengompres beberapa folder sekaligus?** Tentu—gunakan metode `CreateEntries` pada koleksi `DirectoryInfo` apa pun.

## Pendahuluan

Aspose.Zip untuk .NET adalah perpustakaan yang kuat yang memungkinkan pengembang .NET bekerja secara mulus dengan file dan direktori terkompresi. Baik Anda menangani kumpulan data besar atau perlu **generate zip file c#**‑style, Aspose.Zip menyediakan serangkaian fitur yang kuat untuk tugas kompresi dan dekompresi.

## Apa itu “cara mengompres direktori”?

Mengompres sebuah direktori berarti mengambil semua file dan sub‑folder dalam sebuah folder tertentu dan mengemasnya ke dalam satu arsip ZIP. Ini mengurangi ukuran keseluruhan, mempermudah transfer, dan mempertahankan hierarki folder asli.

## Mengapa menggunakan Aspose.Zip untuk tugas ini?

- **Kecepatan & Efisiensi:** Algoritma yang dioptimalkan menangani folder besar dengan cepat.  
- **Pure .NET:** Tidak memerlukan binari native atau alat pihak ketiga.  
- **Set Fitur Kaya:** Mendukung perlindungan kata sandi, streaming, dan penambahan entri secara dinamis—sempurna untuk skenario **zip multiple files .net**.  
- **API Konsisten:** Bekerja sama di .NET Framework, .NET Core, dan .NET 5/6.

## Prasyarat

- **Aspose.Zip untuk .NET** – unduh di [sini](https://releases.aspose.com/zip/net/).  
- **Lingkungan Pengembangan** – Visual Studio, Rider, atau IDE apa pun yang mendukung C#.  
- **Direktori Dokumen** – ganti `"Your Document Directory"` dalam kode dengan path ke folder yang ingin Anda kompres.  
- **Dokumentasi Referensi** – lihat dokumen resmi [di sini](https://reference.aspose.com/zip/net/).

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan. Ini memberi Anda akses ke kelas kompresi inti.

```csharp
using Aspose.Zip;
using System.IO;
```

## Cara Mengompres Folder dengan Aspose.Zip

Berikut adalah contoh sederhana yang menunjukkan **cara mengompres folder** isi. Pola yang sama dapat diperluas ke **zip multiple files .net** atau untuk membuat struktur arsip khusus.

### Langkah 1: Inisialisasi Direktori Dokumen Anda

Setel variabel `dataDir` ke path direktori yang ingin Anda kompres.

```csharp
string dataDir = "Your Document Directory";
```

### Langkah 2: Buat File ZIP Output

Buka dua objek `FileStream` untuk file ZIP output. Ini menunjukkan cara Anda dapat menghasilkan lebih dari satu arsip dari sumber yang sama—berguna untuk cadangan berversi.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Langkah 3: Kompres Direktori

Gunakan kelas `Archive` untuk menambahkan setiap entri dari folder target. Contoh ini menggunakan folder contoh bernama **CanterburyCorpus**, tetapi Anda dapat menunjukkannya ke direktori apa pun.

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

> **Tip Pro:** Jika Anda perlu **create zip archive .net** dengan tingkat kompresi tertentu, setel `archive.CompressionLevel` sebelum memanggil `Save`.

## Masalah Umum dan Solusinya

| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| File ZIP kosong | `dataDir` mengarah ke folder yang salah atau kehilangan slash di akhir | Verifikasi path dan pastikan folder berisi file |
| `UnauthorizedAccessException` | Aplikasi tidak memiliki izin sistem file | Jalankan Visual Studio sebagai administrator atau berikan hak baca/tulis |
| Penggunaan memori besar untuk direktori sangat besar | Memuat semua entri ke memori sekaligus | Gunakan `Archive.CreateEntryFromFile` dalam loop untuk men-stream file secara individual |

## Pertanyaan yang Sering Diajukan (Tambahan)

**Q: Bisakah saya menambahkan kata sandi ke arsip ZIP?**  
A: Ya. Setel `archive.Password = "yourPassword";` sebelum memanggil `Save`.

**Q: Bagaimana cara saya menyertakan hanya tipe file tertentu?**  
A: Filter koleksi `DirectoryInfo` dengan `GetFiles("*.txt")` atau serupa sebelum memanggil `CreateEntries`.

**Q: Apakah ada cara memperbarui ZIP yang ada tanpa membuat ulang?**  
A: Aspose.Zip mendukung pembaruan inkremental melalui `Archive.UpdateEntry`.

## FAQ

### Q1: Bisakah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial maupun pribadi?

A1: Ya, Aspose.Zip untuk .NET dilisensikan untuk penggunaan komersial dan pribadi.

### Q2: Apakah tersedia versi percobaan gratis?

A2: Ya, Anda dapat menjelajahi versi percobaan gratis [di sini](https://releases.aspose.com/zip/net).

### Q3: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip untuk .NET?

A3: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk dukungan komunitas atau pertimbangkan membeli [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk bantuan khusus.

### Q4: Apakah ada contoh dan tutorial lain yang tersedia?

A4: Ya, [dokumentasi](https://reference.aspose.com/zip/net/) berisi contoh dan tutorial yang komprehensif.

### Q5: Bisakah saya membeli Aspose.Zip untuk .NET?

A5: Tentu, Anda dapat melakukan pembelian [di sini](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-12-09  
**Diuji Dengan:** Aspose.Zip 24.11 untuk .NET  
**Penulis:** Aspose