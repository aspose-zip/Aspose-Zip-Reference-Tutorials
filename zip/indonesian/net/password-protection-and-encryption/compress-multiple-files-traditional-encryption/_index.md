---
date: 2025-12-20
description: Pelajari cara melindungi arsip zip dengan kata sandi menggunakan Aspose.Zip
  untuk .NET dengan enkripsi tradisional. Panduan ini menunjukkan cara mengenkripsi
  file zip dan menambahkan file ke zip secara efisien.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Melindungi Arsip Zip dengan Kata Sandi menggunakan Aspose.Zip .NET
url: /id/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Melindungi Arsip Zip dengan Kata Sandi menggunakan Aspose.Zip .NET

## Pendahuluan

Selamat datang di tutorial langkah‑demi‑langkah ini tentang **cara melindungi arsip zip dengan kata sandi** menggunakan enkripsi tradisional dengan Aspose.Zip untuk .NET. Aspose.Zip adalah pustaka kuat yang memungkinkan pengembang membuat, membaca, dan memanipulasi arsip zip dengan mudah. Dalam panduan ini, kami akan memandu Anda melalui proses mengompres beberapa file, menambahkannya ke dalam zip, dan mengamankan arsip dengan kata sandi—semua sambil menjaga kode tetap bersih dan dapat dipelihara.

## Jawaban Cepat
- **Apa arti “password protect zip archive”?** Itu berarti mengenkripsi file zip sehingga isinya hanya dapat dibuka setelah memasukkan kata sandi yang benar.  
- **Library mana yang menangani ini di .NET?** Aspose.Zip untuk .NET menyediakan dukungan bawaan untuk enkripsi tradisional.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan produksi; tersedia versi percobaan gratis.  
- **Apakah saya dapat menjalankannya di Linux?** Tentu—Aspose.Zip bersifat lintas‑platform dan bekerja di Windows, Linux, serta macOS.  
- **Berapa banyak file yang dapat saya tambahkan?** Anda dapat menambahkan sejumlah file apa pun; contoh menunjukkan tiga file, tetapi pendekatannya dapat diskalakan.

## Apa itu “password protect zip archive”?

Arsip zip yang dilindungi kata sandi menggunakan enkripsi (dalam hal ini, enkripsi PKZIP tradisional) untuk mengacak data file di dalam arsip. Ketika pengguna mencoba mengekstrak arsip, kata sandi yang benar harus diberikan untuk mendekripsi isinya.

## Mengapa menggunakan Aspose.Zip untuk tugas ini?

- **API sederhana** – Satu baris kode untuk mengaktifkan enkripsi.  
- **Tanpa dependensi eksternal** – Murni .NET, tanpa DLL native.  
- **Lintas‑platform** – Berfungsi dengan .NET Framework, .NET Core, dan .NET 5/6+.  
- **Dioptimalkan untuk kinerja** – Menangani file besar secara efisien.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

- **Aspose.Zip untuk .NET** – Unduh dari situs resmi [di sini](https://releases.aspose.com/zip/net/).  
- **Folder berisi file** – Ganti `"Your Document Directory"` dalam contoh kode dengan jalur sebenarnya yang berisi file yang ingin Anda zip.

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan agar Anda dapat bekerja dengan kelas Aspose.Zip:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Cara mengenkripsi zip dengan enkripsi tradisional

### Langkah 1: Siapkan File Zip (Password Protect Zip Archive)

Buat file zip dan konfigurasikan pengaturan enkripsi tradisional. Kata sandi `"p@s$"` hanya contoh—ganti dengan kata sandi yang kuat untuk proyek nyata.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Tambahkan file ke arsip zip

Sekarang, tambahkan setiap file yang ingin Anda sertakan. Metode `CreateEntry` menerima nama file di dalam zip dan sebuah stream (`source1`, `source2`, `source3`) yang menunjuk ke data file sebenarnya.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Simpan File Zip (kompres file dengan kata sandi)

Akhirnya, simpan arsip ke disk. Langkah ini menulis file zip terenkripsi ke lokasi yang Anda tentukan sebelumnya.

```csharp
archive.Save(zipFile);
```

> **Tip pro:** Selalu tutup stream (`using` statements) untuk melepaskan handle file dengan cepat, terutama saat bekerja dengan file besar.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Kesalahan kata sandi tidak tepat** | Kata sandi tidak cocok atau typo di `TraditionalEncryptionSettings` | Verifikasi string kata sandi dan pastikan kata sandi yang sama digunakan saat mengekstrak. |
| **File tidak ditambahkan** | Stream sumber (`sourceX`) bernilai null atau telah dibuang | Buka stream sumber dengan `File.OpenRead` sebelum mengirimkannya ke `CreateEntry`. |
| **Penurunan kinerja pada file besar** | Menggunakan level kompresi default dengan banyak entri besar | Pertimbangkan mengatur `CompressionLevel` di `ArchiveEntrySettings` untuk pemrosesan yang lebih cepat. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan ini di lingkungan Windows dan Linux?**  
J: Ya, Aspose.Zip untuk .NET sepenuhnya lintas‑platform dan berfungsi di Windows, Linux, serta macOS.

**T: Apakah tersedia versi percobaan gratis?**  
J: Tentu—Anda dapat menjelajahi versi percobaan gratis Aspose.Zip untuk .NET [di sini](https://releases.aspose.com/).

**T: Di mana saya dapat mendapatkan dukungan jika mengalami masalah?**  
J: Kunjungi [forum resmi Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan komunitas dan dukungan resmi.

**T: Apakah lisensi sementara menjadi opsi untuk evaluasi?**  
J: Ya, Anda dapat memperoleh lisensi sementara dari [di sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana dokumentasi API lengkap?**  
J: Materi referensi detail tersedia [di sini](https://reference.aspose.com/zip/net/).

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Zip 24.11 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}