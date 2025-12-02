---
date: 2025-12-01
description: Pelajari cara mengompres direktori menjadi zip dan mengekstrak zip ke
  direktori menggunakan Aspose.Zip untuk .NET – panduan lengkap tentang kompresi zip
  .NET dan pembuatan arsip zip .NET.
language: id
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Kompres Direktori ke Zip & Ekstrak – Aspose.Zip untuk .NET
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kompres Direktori ke Zip & Ekstrak – Aspose.Zip untuk .NET

Jika Anda perlu **compress directory to zip** dan kemudian mengekstrak arsip tersebut dalam aplikasi .NET, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas seluruh alur kerja—dimulai dengan membuat arsip zip, lalu menunjukkan cara unzip yang bersih, langkah demi langkah menggunakan Aspose.Zip untuk .NET. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali untuk kompresi zip pada proyek .NET dan pemahaman yang kuat tentang cara unzip gaya .NET.

## Jawaban Cepat
- **What does “compress directory to zip” mean?** Artinya mengubah isi folder menjadi satu file .zip.  
- **How do I extract zip to directory?** Gunakan metode `Archive.ExtractToDirectory` seperti yang ditunjukkan dalam panduan.  
- **Which .NET versions are supported?** Semua versi .NET Framework, .NET Core, dan .NET 5/6+ modern.  
- **Is a license required for production?** Ya, lisensi komersial Aspose.Zip diperlukan untuk penggunaan non‑trial.  
- **Can I automate this in CI/CD pipelines?** Tentu—cukup tambahkan kode yang sama ke skrip build Anda.

## Apa itu “compress directory to zip”?
Mengkompres sebuah direktori ke zip menggabungkan setiap file dan sub‑folder menjadi satu arsip terkompresi. Ini mengurangi ukuran penyimpanan, mempermudah transfer, dan merupakan cara standar untuk mengemas sumber daya untuk deployment.

## Mengapa menggunakan Aspose.Zip untuk .NET?
Aspose.Zip menawarkan API **pure‑managed** yang berfungsi tanpa ketergantungan native, mendukung file besar, dan menyediakan kemampuan kompresi zip .NET dengan kinerja tinggi. Ia juga menangani kasus khusus seperti arsip yang dilindungi kata sandi dan nama file Unicode secara langsung.

## Prasyarat
- **Aspose.Zip for .NET** library installed (download it [here](https://releases.aspose.com/zip/net/)).  
- Sebuah folder di disk yang ingin Anda arsipkan – atur jalurnya di variabel `dataDir`.  
- Lingkungan pengembangan .NET (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).

## Impor Namespace
Pertama, masukkan namespace yang diperlukan ke dalam ruang lingkup:

```csharp
using Aspose.Zip;
using System.IO;
```

## Langkah 1: Kompres Direktori ke Zip
Kami akan membuat file zip dari direktori yang akan Anda dekompres nanti. Helper `CompressDirectory.Run()` melakukan pekerjaan berat.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Contoh `CompressDirectory` mengemas setiap file di `dataDir` ke dalam `CompressDirectory_out.zip`. Silakan ganti nama file output sesuai konvensi penamaan Anda.

## Langkah 2: Dekompres Folder (Cara unzip .NET)

### Langkah 2.1: Buka File Zip
Buka arsip yang dihasilkan dengan `FileStream`. Ini menyiapkan file untuk dibaca.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### Langkah 2.2: Buat Instance Archive
Instansiasi objek `Archive`, yang mewakili kontainer zip.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### Langkah 2.3: Ekstrak ke Direktori
Akhirnya, ekstrak konten ke folder baru. Ini adalah langkah **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Selamat! Anda telah berhasil **compressed a directory to zip** dan kemudian **extracted the zip to a directory** menggunakan Aspose.Zip untuk .NET. Pendekatan ini menjamin integritas data sambil menjaga kode tetap ringkas dan mudah dibaca.

## Masalah Umum & Solusi
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| `UnauthorizedAccessException` saat mengekstrak | Folder target bersifat read‑only atau sedang digunakan | Pastikan jalur tujuan dapat ditulisi dan tidak terkunci |
| Folder output kosong setelah ekstraksi | Jalur zip sumber salah | Periksa kembali `dataDir + "CompressDirectory_out.zip"` mengarah ke file yang benar |
| File besar menyebabkan OutOfMemoryException | Menggunakan ukuran buffer default pada arsip yang sangat besar | Gunakan `ArchiveOptions` untuk meningkatkan ukuran buffer atau alirkan file dalam potongan |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Zip untuk .NET dengan jenis file apa pun?**  
A: Ya, Aspose.Zip mendukung semua jenis file—teks, biner, gambar, PDF, apa saja.

**Q: Apakah Aspose.Zip cocok untuk aplikasi berskala besar?**  
A: Tentu. Ia dirancang untuk skenario kompresi zip .NET dengan kinerja tinggi, menangani arsip multi‑gigabyte dengan overhead memori yang rendah.

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**  
A: Jelajahi dokumen detail [di sini](https://reference.aspose.com/zip/net/).

**Q: Bisakah saya mencoba Aspose.Zip sebelum membeli?**  
A: Ya, percobaan gratis tersedia di [halaman unduhan Aspose.Zip](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan komunitas dan dukungan resmi.

---

**Terakhir Diperbarui:** 2025-12-01  
**Diuji Dengan:** Aspose.Zip 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}