---
date: 2025-12-21
description: Pelajari cara membuat file zip yang dilindungi kata sandi di .NET, mengenkripsi
  folder, dan mengubah kata sandi zip menggunakan Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat zip yang dilindungi kata sandi untuk direktori .NET – Tutorial Aspose.Zip
url: /id/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat zip terlindungi kata sandi untuk direktori .NET – Tutorial Aspose.Zip

Dalam panduan ini Anda akan **membuat zip terlindungi kata sandi** untuk seluruh direktori menggunakan pustaka Aspose.Zip untuk .NET. Apakah Anda perlu **mengenkripsi folder**, mengamankan file cadangan, atau sekadar membatasi akses ke data sensitif, tutorial langkah‑demi‑langkah ini menunjukkan secara tepat cara melakukannya dengan kode C# yang bersih.

## Jawaban Cepat
- **Perpustakaan apa yang direkomendasikan?** Aspose.Zip untuk .NET  
- **Bisakah saya mengenkripsi seluruh folder?** Ya – cukup arahkan API ke folder yang ingin Anda zip.  
- **Apakah mengubah kata sandi zip didukung?** Tentu saja, gunakan `TraditionalEncryptionSettings`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Zip yang valid diperlukan untuk penggunaan komersial.  
- **Berfungsi dengan .NET Core/5/6?** Ya, API sepenuhnya kompatibel dengan runtime .NET modern.  

## Apa itu “membuat zip terlindungi kata sandi”?
Membuat zip terlindungi kata sandi berarti mengompres file atau direktori ke dalam arsip ZIP sambil menerapkan enkripsi sehingga arsip hanya dapat dibuka dengan kata sandi yang benar. Ini melindungi isi dari akses tidak sah.

## Mengapa menggunakan Aspose.Zip untuk melindungi direktori dengan kata sandi di .NET?
Aspose.Zip menawarkan API yang sederhana dan berperforma tinggi yang mendukung **c# zip password protection**, enkripsi tradisional ZipCrypto, dan enkripsi AES. Ia menangani direktori besar secara efisien dan terintegrasi mulus dengan proyek .NET apa pun.

## Prasyarat
- Pengetahuan dasar pemrograman C#.  
- Visual Studio (edisi terbaru apa pun).  
- Pustaka Aspose.Zip untuk .NET – unduh **[di sini](https://releases.aspose.com/zip/net/)**.  
- Folder di disk yang ingin Anda lindungi dengan kata sandi.

## Impor Namespace
Tambahkan namespace yang diperlukan ke file C# Anda sehingga compiler mengetahui di mana menemukan kelas Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Langkah 1: Tetapkan Jalur ke Direktori Sumber Daya
Tentukan jalur yang mengarah ke direktori yang ingin Anda zip dan lindungi.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Lindungi Direktori dengan Kata Sandi
Gunakan `TraditionalEncryptionSettings` untuk menentukan kata sandi dan membuat arsip terenkripsi. Ini adalah inti dari **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Langkah 3: Penjelasan Kode
- **Membuat file output:** `File.Open(..., FileMode.Create)` membuka (atau membuat) file ZIP yang akan menyimpan data terenkripsi.  
- **Memilih folder sumber:** `new DirectoryInfo(".\\CanterburyCorpus")` memberi tahu Aspose.Zip direktori mana yang akan dikompres.  
- **Menerapkan kata sandi:** `new TraditionalEncryptionSettings("p@s$")` menetapkan kata sandi yang akan melindungi arsip.  
- **Menambahkan entri & menyimpan:** `archive.CreateEntries(corpus)` menambahkan setiap file dalam folder, dan `archive.Save(zipFile)` menulis ZIP terenkripsi ke disk.

## Bagaimana cara mengubah kata sandi zip nanti?
Jika Anda perlu **mengubah kata sandi zip**, cukup buat ulang arsip dengan instance `TraditionalEncryptionSettings` baru yang berisi kata sandi baru, lalu simpan kembali.

## Masalah Umum & Tips
- **Folder besar:** Aspose.Zip melakukan streaming data, sehingga penggunaan memori tetap rendah bahkan untuk direktori yang sangat besar.  
- **Kompleksitas kata sandi:** Gunakan kata sandi yang kuat (campuran huruf, angka, simbol) untuk meningkatkan keamanan.  
- **Kesalahan lisensi:** Pastikan Anda telah menerapkan file lisensi yang valid; jika tidak, pustaka akan berjalan dalam mode evaluasi dengan keterbatasan.

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Zip untuk .NET cocok untuk direktori besar?
Ya, Aspose.Zip untuk .NET dirancang untuk menangani direktori besar secara efisien, memberikan kinerja optimal.

### Bisakah saya mengubah kata sandi untuk direktori yang sudah dilindungi?
Ya, Anda dapat mengubah kata sandi dengan menyesuaikan `TraditionalEncryptionSettings` dalam kode sesuai kebutuhan.

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Zip untuk .NET?
Ya, lisensi yang valid diperlukan untuk menggunakan Aspose.Zip untuk .NET di lingkungan produksi. Anda dapat memperoleh lisensi **[di sini](https://purchase.aspose.com/buy)**.

### Apakah tersedia percobaan gratis untuk Aspose.Zip untuk .NET?
Ya, Anda dapat mengakses percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Zip untuk .NET?
Anda dapat mengunjungi **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** untuk dukungan atau pertanyaan apa pun.

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** Aspose.Zip for .NET (latest release)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}