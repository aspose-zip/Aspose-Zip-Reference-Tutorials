---
date: 2026-03-02
description: Pelajari cara membuat arsip zip yang dilindungi kata sandi dan mengompres
  file dengan kata sandi di .NET menggunakan Aspose.Zip. Ikuti panduan langkah demi
  langkah kami.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat Arsip ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip
url: /id/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Arsip ZIP yang Dilindungi Kata Sandi di .NET dengan Aspose.Zip

## Pendahuluan

Ketika Anda perlu membagikan data sensitif, **arsip zip yang dilindungi kata sandi** adalah salah satu cara paling sederhana namun efektif untuk menjaga informasi tetap aman. Pada aplikasi .NET, Aspose.Zip memudahkan **kompres file dengan kata sandi**, memberikan setiap file kunci enkripsi masing‑masing. Pada tutorial ini Anda akan mempelajari cara membuat arsip tersebut, mengapa hal itu penting, dan di mana Anda dapat menerapkannya dalam proyek dunia nyata.

## Jawaban Cepat
- **Pustaka apa yang harus saya gunakan?** Aspose.Zip untuk .NET menyediakan dukungan bawaan untuk kata sandi per‑file dan berbagai metode enkripsi.  
- **Berapa baris kode?** Sekitar 30 baris, termasuk penyiapan dan penyimpanan arsip.  
- **Apakah setiap file dapat memiliki kata sandi yang berbeda?** Ya – Anda dapat menetapkan kata sandi unik untuk setiap entri.  
- **Metode enkripsi apa yang tersedia?** ZipCrypto tradisional, AES‑128, dan AES‑256.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan produksi; versi percobaan tersedia.

## Apa itu arsip zip yang dilindungi kata sandi?
Arsip zip yang dilindungi kata sandi adalah file terkompresi (ZIP) yang memerlukan kata sandi untuk mengekstrak isinya. Kata sandi dapat melindungi seluruh arsip atau entri individual, dan algoritma modern seperti AES‑128/256 memberikan enkripsi yang kuat.

## Mengapa mengompres file dengan kata sandi menggunakan Aspose.Zip?
- **Keamanan granular** – tetapkan kata sandi berbeda per file, ideal untuk skenario multi‑tenant.  
- **Berbagai standar enkripsi** – pilih antara ZipCrypto legacy dan AES yang kuat.  
- **Tanpa alat eksternal** – semua ditangani secara programatis dalam basis kode .NET Anda.  
- **Kinerja** – kompresi cepat dengan Deflate sambil menjaga ukuran arsip tetap kecil.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** – instal pustaka di proyek Anda. Dokumentasi lengkap tersedia [di sini](https://reference.aspose.com/zip/net/).  
- **Unduh paket terbaru** jika belum, dari [tautan ini](https://releases.aspose.com/zip/net/).  
- Sebuah folder yang berisi file‑file yang ingin Anda kompres.

## Impor Namespace

Tambahkan namespace yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Langkah 1: Atur Jalur Direktori Sumber Daya

Arahkan kode ke folder yang berisi file sumber:

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Kompres File dengan Kata Sandi Individual

Sekarang kita akan membuat **arsip zip yang dilindungi kata sandi** di mana setiap file menggunakan kata sandi dan metode enkripsi masing‑masing. Contoh ini menggunakan tiga file contoh (`alice29.txt`, `asyoulik.txt`, dan `fields.c`) dengan kata sandi yang berbeda.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Cara kerjanya
- **CreateEntry** menambahkan file ke dalam arsip.  
- Argumen keempat (`ArchiveEntrySettings`) memungkinkan Anda menentukan baik kompresi (`DeflateCompressionSettings`) maupun enkripsi (`TraditionalEncryptionSettings` atau `AesEcryptionSettings`).  
- Dengan memberikan string kata sandi yang berbeda untuk setiap entri, Anda menghasilkan **arsip zip yang dilindungi kata sandi** di mana setiap file hanya dapat dibuka dengan kunci masing‑masing.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|-------|
| Ekstraksi gagal dengan “Wrong password” | Kata sandi tidak cocok atau metode enkripsi salah | Verifikasi string kata sandi yang tepat dan pastikan Anda menggunakan `EncryptionMethod` yang sama saat mengekstrak. |
| Ukuran arsip lebih besar dari yang diharapkan | Menggunakan AES‑256 pada file teks kecil dapat menambah overhead | Untuk file kecil, AES‑128 mungkin cukup dan menghasilkan arsip yang lebih kecil. |
| Pengecualian runtime pada `archive.Save` | Tidak ada izin menulis pada folder target | Pastikan aplikasi memiliki akses menulis ke `dataDir` atau gunakan jalur output yang berbeda. |

## Pertanyaan yang Sering Diajukan (FAQ)

### Apakah saya dapat menggunakan metode enkripsi yang berbeda untuk setiap file?
Ya, Aspose.Zip untuk .NET memungkinkan Anda mencampur metode enkripsi—ZipCrypto tradisional, AES‑128, dan AES‑256—secara per‑file.

### Apakah ada versi percobaan yang tersedia?
Ya, Anda dapat mengakses versi percobaan gratis Aspose.Zip untuk .NET [di sini](https://releases.aspose.com/).

### Bagaimana saya mendapatkan dukungan jika mengalami masalah?
Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk bantuan dari komunitas dan tim dukungan Aspose.

### Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Zip untuk .NET?
Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/).

### Bisakah saya membeli lisensi sementara untuk tujuan pengujian?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-03-02  
**Diuji Dengan:** Aspose.Zip untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

---