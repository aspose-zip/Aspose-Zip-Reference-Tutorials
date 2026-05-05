---
date: 2026-05-05
description: Pelajari cara mengompres file dengan kata sandi dan mengenkripsi arsip
  ZIP menggunakan Aspose.Zip untuk .NET, mencakup perlindungan kata sandi 7z dan kata
  sandi ZIP per file dalam C#.
keywords:
- compress files with password
- how to encrypt zip
- aes 256 zip encryption
- encrypt zip entries
- per file zip password
linktitle: Entri dengan Kata Sandi Berbeda
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cara mengompres file dengan kata sandi dan mengenkripsi entri ZIP dengan kata
  sandi berbeda menggunakan Aspose.Zip untuk .NET
url: /id/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengompres file dengan kata sandi dan mengenkripsi entri ZIP dengan kata sandi berbeda menggunakan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **mengompres file dengan kata sandi** dan memberikan setiap entri kata sandi masing‑masing, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk membuat arsip 7‑zip di mana setiap file dilindungi dengan kata sandi unik, menggunakan perpustakaan Aspose.Zip untuk .NET. Pada akhir tutorial Anda akan memahami mengapa enkripsi per‑entri penting, cara menyiapkannya, dan cara memverifikasi hasilnya dalam proyek Anda sendiri.

## Jawaban Cepat
- **Apa arti “encrypt zip”?** Itu berarti menerapkan perlindungan berbasis kata sandi (AES atau ZipCrypto) pada isi arsip ZIP/7z.  
- **Apakah setiap entri dapat memiliki kata sandi berbeda?** Ya—Aspose.Zip memungkinkan Anda menetapkan kata sandi yang berbeda per file.  
- **Versi .NET apa yang didukung?** Semua .NET Framework modern, .NET Core, dan .NET 5/6.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Format kompresi apa yang digunakan dalam contoh?** Contoh membuat arsip 7z dengan enkripsi AES‑256.

## Apa itu “cara mengenkripsi zip” dengan Aspose.Zip?
Mengenkripsi file ZIP (atau 7z) berarti mengamankan entri‑entri sehingga tidak dapat dibuka tanpa kata sandi yang benar. Aspose.Zip untuk .NET mendukung baik ZipCrypto klasik maupun enkripsi AES yang lebih kuat, dan memungkinkan Anda menentukan pengaturan enkripsi per entri, memberikan kontrol keamanan yang sangat detail.

## Mengapa mengompres file dengan kata sandi?
- **Segmentasi keamanan:** Jika satu kata sandi bocor, file lain tetap terlindungi.  
- **Kepatuhan regulasi:** Beberapa industri mewajibkan kredensial terpisah untuk kategori data yang berbeda.  
- **Distribusi khusus pengguna:** Satu arsip dapat dikirim ke banyak pengguna, masing‑masing hanya dapat membuka file yang mereka berhak lihat.

## Mengapa menggunakan enkripsi zip AES 256?
AES‑256 adalah standar industri saat ini untuk enkripsi simetris yang kuat. Dibandingkan dengan ZipCrypto, ia tahan terhadap serangan brute‑force modern dan sepenuhnya kompatibel dengan 7‑Zip serta ekstraktor kontemporer lainnya. Ketika Anda membutuhkan **aes 256 zip encryption**, Aspose.Zip membuat konfigurasi menjadi sederhana.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terpasang – lihat [dokumentasi resmi](https://reference.aspose.com/zip/net/) untuk petunjuk unduh dan instalasi.  
- Sebuah folder di mesin Anda tempat menyimpan file sumber (yang disebut “Document Directory”).  
- Familiaritas dasar dengan C# dan Visual Studio (atau IDE .NET pilihan Anda).

## Impor Namespace

Kami mulai dengan mengimpor namespace yang berisi kelas‑kelas yang diperlukan.

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

## Langkah 1: Atur Direktori Dokumen Anda

Tentukan jalur yang berisi file‑file yang ingin Anda arsipkan.

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Buat Entri dengan Kata Sandi Berbeda

Berikut inti tutorial. Kami membuka file 7z baru, membuat tiga objek `FileInfo`, dan menambahkan masing‑masing sebagai entri dengan kata sandi AES sendiri.

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
- `CreateEntry` menerima nama entri, file sumber, flag untuk menimpa, dan objek `SevenZipEntrySettings`.  
- Di dalam `SevenZipEntrySettings` kami menyediakan dua objek pengaturan: satu untuk kompresi (`SevenZipStoreCompressionSettings`) dan satu untuk enkripsi (`SevenZipAESEncryptionSettings`).  
- Setiap pemanggilan menyediakan **kata sandi yang berbeda** (`"test1"`, `"test2"`, `"test3"`), sehingga tercapai perlindungan per‑entri.

## Langkah 3: Verifikasi

Setelah arsip disimpan, Anda dapat menampilkan pesan konfirmasi sederhana.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Jalankan program, lalu coba buka `archive.7z` dengan alat seperti 7‑Zip. Ia akan meminta kata sandi untuk setiap entri, mengonfirmasi bahwa kata sandi memang berbeda.

## Enkripsi entri zip dengan kata sandi zip per file – praktik terbaik

Saat Anda **mengenkripsi entri zip** menggunakan kata sandi per‑file, perhatikan tips berikut:

1. **Gunakan kata sandi yang kuat dan unik** – hindari kata umum dan penggunaan ulang.  
2. **Simpan kata sandi dengan aman** – pertimbangkan manajer kata sandi atau brankas aman jika Anda perlu mendistribusikannya.  
3. **Uji dengan beberapa alat** – pastikan baik 7‑Zip maupun WinRAR dapat membaca arsip, karena beberapa alat lama mungkin tidak mendukung AES‑256.  
4. **Dokumentasikan pemetaan kata sandi‑file** – CSV sederhana (file, kata sandi) membantu administrator melacak kata sandi mana yang terkait dengan entri mana.

## Perlindungan kata sandi arsip zip – jebakan umum

| Masalah | Alasan | Perbaikan |
|-------|--------|-----|
| **Kesalahan kata sandi tidak tepat** | String kata sandi mengandung spasi berlebih atau karakter tak terlihat. | Potong string kata sandi (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Arsip tidak dapat dibuka di alat lama** | Beberapa alat ZIP warisan tidak mendukung enkripsi AES‑256 yang dipakai oleh 7z. | Gunakan ekstraktor modern (7‑Zip 19.00+). |
| **File tidak ditambahkan ke arsip** | Jalur file sumber salah atau file tidak ada. | Verifikasi `dataDir` dan nama file, atau gunakan `Path.Combine(dataDir, "data1.bin")`. |

## Pertanyaan yang Sering Diajukan

### Q1: Apakah Aspose.Zip untuk .NET kompatibel dengan semua versi .NET?

A1: Ya, Aspose.Zip untuk .NET dirancang untuk terintegrasi mulus dengan semua versi .NET framework.

### Q2: Dapatkah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial saya?

A2: Tentu saja! Aspose.Zip untuk .NET menawarkan lisensi komersial, dan Anda dapat menemukan informasi lebih lanjut tentang cara membeli [di sini](https://purchase.aspose.com/buy).

### Q3: Apakah tersedia versi percobaan gratis?

A3: Ya, Anda dapat menjelajahi fitur Aspose.Zip untuk .NET dengan versi percobaan gratis. Mulai sekarang [di sini](https://releases.aspose.com/).

### Q4: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip untuk .NET?

A4: Untuk pertanyaan atau bantuan, kunjungi [Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5: Dapatkah saya menggunakan Aspose.Zip untuk .NET tanpa lisensi permanen?

A5: Ya, Anda dapat memperoleh lisensi sementara untuk kebutuhan jangka pendek Anda. Temukan detail lebih lanjut [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda baru saja mempelajari **cara mengompres file dengan kata sandi** dan mengenkripsi arsip ZIP dengan kata sandi per‑entri menggunakan Aspose.Zip untuk .NET. Teknik ini memberi Anda fleksibilitas melindungi setiap file secara individual, memenuhi persyaratan keamanan yang lebih ketat, dan mempermudah distribusi khusus pengguna. Jangan ragu bereksperimen dengan pengaturan kompresi lain, kumpulan file yang lebih besar, atau mengintegrasikan logika ini ke layanan web yang menghasilkan arsip aman secara dinamis.

---

**Terakhir Diperbarui:** 2026-05-05  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}