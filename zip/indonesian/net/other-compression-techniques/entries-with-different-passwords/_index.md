---
date: 2025-12-18
description: Pelajari cara mengenkripsi file zip dengan kata sandi yang berbeda menggunakan
  Aspose.Zip untuk .NET. Panduan ini menunjukkan cara mengompres file dengan kata
  sandi dan membuat arsip 7z dalam C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara Mengenkripsi File ZIP dengan Kata Sandi Berbeda di Aspose.Zip untuk .NET
url: /id/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengenkripsi File ZIP dengan Password Berbeda di Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **cara mengenkripsi zip** arsip sambil memberikan setiap entri passwordnya masing‑masing, Anda berada di tempat yang tepat. Pada tutorial ini kami akan membahas langkah‑langkah tepat untuk membuat arsip 7‑zip dimana setiap file dilindungi dengan password unik, menggunakan pustaka Aspose.Zip untuk .NET. Pada akhir tutorial Anda akan memahami mengapa enkripsi per‑entri penting, cara menyiapkannya, dan cara memverifikasi hasilnya dalam proyek Anda sendiri.

## Jawaban Cepat
- **Apa arti “encrypt zip”?** Artinya menerapkan perlindungan berbasis password (AES atau ZipCrypto) pada isi arsip ZIP/7z.  
- **Apakah setiap entri dapat memiliki password berbeda?** Ya—Aspose.Zip memungkinkan Anda menetapkan password yang berbeda untuk tiap file.  
- **Versi .NET apa yang didukung?** Semua .NET Framework modern, .NET Core, dan .NET 5/6.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan produksi; tersedia versi percobaan gratis.  
- **Format kompresi apa yang digunakan dalam contoh?** Contoh membuat arsip 7z dengan enkripsi AES‑256.

## Apa itu “cara mengenkripsi zip” dengan Aspose.Zip?

Mengenkripsi file ZIP (atau 7z) berarti mengamankan entri‑entri sehingga tidak dapat dibuka tanpa password yang benar. Aspose.Zip untuk .NET mendukung baik ZipCrypto klasik maupun enkripsi AES yang lebih kuat, dan memungkinkan Anda menentukan pengaturan enkripsi per entri, memberi kontrol keamanan yang sangat detail.

## Mengapa menggunakan password berbeda untuk setiap entri?

- **Segmentasi keamanan:** Jika satu password bocor, file lainnya tetap terlindungi.  
- **Kepatuhan regulasi:** Beberapa industri mengharuskan kredensial terpisah untuk kategori data yang berbeda.  
- **Akses khusus pengguna:** Anda dapat mendistribusikan satu arsip ke banyak pengguna, masing‑masing hanya dapat membuka file yang mereka berhak lihat.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terpasang – lihat [dokumentasi](https://reference.aspose.com/zip/net/) resmi untuk petunjuk unduh dan instalasi.  
- Sebuah folder di mesin Anda tempat menyimpan file sumber (yang disebut “Document Directory”).  
- Pengetahuan dasar tentang C# dan Visual Studio (atau IDE .NET pilihan Anda).

## Impor Namespace

Kita mulai dengan mengimpor namespace yang berisi kelas‑kelas yang diperlukan.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Langkah 1: Tetapkan Direktori Dokumen Anda

Definisikan jalur yang berisi file‑file yang ingin Anda arsipkan.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Buat Entri dengan Password Berbeda

Berikut inti tutorial. Kami membuka file 7z baru, membuat tiga objek `FileInfo`, dan menambahkan masing‑masing sebagai entri dengan password AES‑nya sendiri.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Cara Kerja Ini

- `SevenZipArchive` adalah wadah untuk arsip 7‑z.  
- `CreateEntry` menerima nama entri, file sumber, flag penimpaan, dan objek `SevenZipEntrySettings`.  
- Di dalam `SevenZipEntrySettings` kami menyediakan dua objek pengaturan: satu untuk kompresi (`SevenZipStoreCompressionSettings`) dan satu untuk enkripsi (`SevenZipAESEncryptionSettings`).  
- Setiap pemanggilan menyediakan **password yang berbeda** (`"test1"`, `"test2"`, `"test3"`), sehingga tercapai perlindungan per‑entri.

## Langkah 3: Verifikasi

Setelah arsip disimpan, Anda dapat menampilkan pesan konfirmasi sederhana.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Jalankan program, lalu coba buka `archive.7z` dengan alat seperti 7‑Zip. Ia akan meminta password untuk setiap entri, mengonfirmasi bahwa password‑nya memang berbeda.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Kesalahan password tidak tepat** | String password mengandung spasi tambahan atau karakter tak terlihat. | Potong string password (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Arsip tidak dapat dibuka di alat lama** | Beberapa alat ZIP lama tidak mendukung enkripsi AES‑256 yang digunakan oleh 7z. | Gunakan extractor modern (7‑Zip 19.00+). |
| **File tidak ditambahkan ke arsip** | Path file sumber salah atau file tidak ada. | Verifikasi `dataDir` dan nama file, atau gunakan `Path.Combine(dataDir, "data1.bin")`. |

## Pertanyaan yang Sering Diajukan

### Q1: Apakah Aspose.Zip untuk .NET kompatibel dengan semua versi .NET?

A1: Ya, Aspose.Zip untuk .NET dirancang untuk terintegrasi mulus dengan semua versi .NET framework.

### Q2: Bisakah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial saya?

A2: Tentu! Aspose.Zip untuk .NET menawarkan lisensi komersial, dan Anda dapat menemukan informasi lebih lanjut tentang cara membeli [di sini](https://purchase.aspose.com/buy).

### Q3: Apakah tersedia versi percobaan gratis?

A3: Ya, Anda dapat menjelajahi fitur Aspose.Zip untuk .NET dengan versi percobaan gratis. Mulai [di sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip untuk .NET?

A4: Untuk pertanyaan atau bantuan, kunjungi [Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5: Bisakah saya menggunakan Aspose.Zip untuk .NET tanpa lisensi permanen?

A5: Ya, Anda dapat memperoleh lisensi sementara untuk kebutuhan jangka pendek Anda. Temukan detail lebih lanjut [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda baru saja mempelajari **cara mengenkripsi zip** arsip dengan password per‑entri menggunakan Aspose.Zip untuk .NET. Teknik ini memberi Anda fleksibilitas untuk melindungi setiap file secara individual, memenuhi persyaratan keamanan yang lebih ketat, dan mempermudah distribusi khusus pengguna. Silakan bereksperimen dengan pengaturan kompresi lain, kumpulan file yang lebih besar, atau integrasikan logika ini ke dalam layanan web yang menghasilkan arsip aman secara dinamis.

---

**Terakhir Diperbarui:** 2025-12-18  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}