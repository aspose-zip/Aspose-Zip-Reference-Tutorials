---
date: 2026-03-08
description: Pelajari cara membuat file zip yang dilindungi kata sandi, melindungi
  folder zip dengan kata sandi, dan mengubah kata sandi zip menggunakan Aspose.Zip
  untuk .NET.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat zip berproteksi kata sandi untuk direktori .NET – Tutorial Aspose.Zip
url: /id/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat zip terlindungi kata sandi untuk direktori .NET – Tutorial Aspose.Zip

Dalam panduan ini Anda akan **membuat arsip zip terlindungi kata sandi** untuk seluruh direktori menggunakan pustaka Aspose.Zip untuk .NET. Baik Anda perlu **mengenkripsi sebuah folder**, mengamankan file cadangan, atau sekadar membatasi akses ke data sensitif, tutorial langkah‑demi‑langkah ini menunjukkan secara tepat cara melakukannya dengan kode C# yang bersih.

## Jawaban Cepat
- **Perpustakaan apa yang direkomendasikan?** Aspose.Zip untuk .NET  
- **Bisakah saya mengenkripsi seluruh folder?** Ya – cukup arahkan API ke folder yang ingin Anda zip.  
- **Apakah mengubah kata sandi zip didukung?** Tentu saja, gunakan `TraditionalEncryptionSettings`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Zip yang valid diperlukan untuk penggunaan komersial.  
- **Berfungsi dengan .NET Core/5/6?** Ya, API sepenuhnya kompatibel dengan runtime .NET modern.  

## Apa itu “membuat zip terlindungi kata sandi”?
Membuat zip terlindungi kata sandi berarti mengompresi file atau direktori ke dalam arsip ZIP sambil menerapkan enkripsi sehingga arsip hanya dapat dibuka dengan kata sandi yang benar. Ini melindungi isi dari akses tidak sah.

## Cara membuat zip terlindungi kata sandi untuk sebuah direktori
Di bawah ini Anda akan menemukan panduan lengkap yang mudah dipahami yang mencakup semua hal mulai dari penyiapan proyek hingga mengubah kata sandi kemudian.

## Mengapa menggunakan Aspose.Zip untuk melindungi direktori dengan kata sandi di .NET?
Aspose.Zip menawarkan API yang sederhana dan berperforma tinggi yang mendukung **c# zip password protection**, enkripsi tradisional ZipCrypto, dan enkripsi AES. Ia menangani direktori besar secara efisien dan terintegrasi mulus dengan proyek .NET apa pun.

## Kasus penggunaan umum
- **Perlindungan cadangan:** Zip folder cadangan harian dan kunci dengan kata sandi yang kuat.  
- **Pertukaran file aman:** Kirim kata sandi folder zip ke klien tanpa mengekspos isi.  
- **Kepatuhan regulasi:** Simpan informasi pribadi yang dapat diidentifikasi (PII) dalam arsip zip terenkripsi untuk memenuhi standar perlindungan data.  

## Prasyarat
- Pengetahuan dasar pemrograman C#.  
- Visual Studio (edisi terbaru apa pun).  
- Pustaka Aspose.Zip untuk .NET – unduh **[di sini](https://releases.aspose.com/zip/net/)**.  
- Sebuah folder di disk yang ingin Anda lindungi dengan kata sandi.

## Impor Namespace
Tambahkan namespace yang diperlukan ke file C# Anda agar kompilator mengetahui di mana menemukan kelas Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Langkah 1: Tetapkan Jalur ke Direktori Sumber
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

## Cara mengubah kata sandi zip nanti?
Jika Anda perlu **mengubah kata sandi zip**, cukup buat ulang arsip dengan instance `TraditionalEncryptionSettings` baru yang berisi kata sandi baru, lalu simpan lagi. Pendekatan ini juga berfungsi ketika Anda ingin **membuat arsip zip terenkripsi** dari folder yang ada dengan kata sandi yang berbeda.

## Tips untuk kata sandi folder zip yang kuat
- Gunakan campuran huruf besar, huruf kecil, angka, dan simbol.  
- Targetkan setidaknya 12 karakter; kata sandi yang lebih panjang secara eksponensial lebih sulit dipecahkan.  
- Hindari kata atau pola umum; pertimbangkan menggunakan frasa sandi.  

## Masalah Umum & Tips
- **Folder besar:** Aspose.Zip melakukan streaming data, sehingga penggunaan memori tetap rendah bahkan untuk direktori yang sangat besar.  
- **Kompleksitas kata sandi:** Gunakan kata sandi yang kuat (campuran huruf, angka, simbol) untuk meningkatkan keamanan.  
- **Kesalahan lisensi:** Pastikan Anda telah menerapkan file lisensi yang valid; jika tidak, pustaka berjalan dalam mode evaluasi dengan batasan.  
- **kata sandi folder zip tidak dikenali:** Verifikasi bahwa Anda menggunakan metode enkripsi yang sama (`TraditionalEncryptionSettings`) saat membuka arsip.  

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Zip untuk .NET cocok untuk direktori besar?
Ya, Aspose.Zip untuk .NET dirancang untuk menangani direktori besar secara efisien, memberikan kinerja optimal.

### Bisakah saya mengubah kata sandi untuk direktori yang sudah dilindungi?
Ya, Anda dapat mengubah kata sandi dengan menyesuaikan `TraditionalEncryptionSettings` dalam kode sesuai kebutuhan.

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Zip untuk .NET?
Ya, lisensi yang valid diperlukan untuk menggunakan Aspose.Zip untuk .NET di lingkungan produksi. Anda dapat memperoleh lisensi **[di sini](https://purchase.aspose.com/buy)**.

### Apakah ada percobaan gratis untuk Aspose.Zip untuk .NET?
Ya, Anda dapat mengakses percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Zip untuk .NET?
Anda dapat mengunjungi **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** untuk dukungan atau pertanyaan apa pun.

## FAQ Cepat (ramah AI)

**Q: Bagaimana cara saya mengenkripsi folder dengan zip menggunakan Aspose.Zip?**  
A: Gunakan `TraditionalEncryptionSettings` saat membuat objek `Archive`, lalu panggil `CreateEntries` pada folder target.

**Q: Bisakah saya menetapkan kata sandi folder zip setelah arsip dibuat?**  
A: Tidak, kata sandi harus ditentukan saat pembuatan; untuk mengubahnya, buat ulang arsip dengan kata sandi baru.

**Q: Apakah Aspose.Zip mendukung enkripsi AES untuk keamanan yang lebih kuat?**  
A: Ya, Anda dapat beralih ke `AesEncryptionSettings` untuk enkripsi AES‑256 alih‑alih ZipCrypto tradisional.

**Q: Apakah perpustakaan ini kompatibel dengan .NET 6 dan .NET 7?**  
A: Tentu saja – rilis saat ini bekerja dengan semua runtime .NET modern.

**Q: Apa yang terjadi jika saya mencoba membuka zip yang dilindungi kata sandi tanpa kata sandi?**  
A: Aspose.Zip akan melempar `PasswordRequiredException`, meminta Anda memasukkan kata sandi yang benar.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}