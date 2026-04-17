---
description: Pelajari cara mengekstrak RAR ke folder dan mendekripsi file RAR yang
  dienkripsi menggunakan Aspose.Zip untuk .NET. Ikuti panduan langkah demi langkah
  untuk membaca file RAR terenkripsi dan menentukan kata sandi RAR.
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ekstrak RAR ke Folder dengan Aspose.Zip untuk .NET
url: /id/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak RAR ke Folder dengan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **extract RAR to folder** dan bekerja dengan arsip yang dilindungi password, Aspose.Zip untuk .NET membuat pekerjaan ini menjadi mudah. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah tepat untuk membaca file RAR terenkripsi, menentukan password RAR, dan mengekstrak isi arsip ke direktori target. Baik Anda membangun utilitas desktop maupun layanan sisi‑server, Anda akan melihat cara mengintegrasikan logika dekripsi dengan cepat dan dapat diandalkan.

## Jawaban Cepat
- **Apa arti “extract RAR to folder”?** Artinya membuka arsip RAR dan menuliskan setiap entri ke direktori yang ditentukan di disk.  
- **Library mana yang menangani dekripsi?** Aspose.Zip untuk .NET menyediakan dukungan bawaan untuk arsip RAR terenkripsi.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara tersedia untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk skenario ekstraksi dasar.

## Apa itu “extract RAR to folder”?
Mengekstrak arsip RAR ke folder berarti mendekompresi setiap file yang disimpan di dalam arsip dan menempatkannya di direktori pilihan Anda. Ketika arsip tersebut dienkripsi, Anda juga harus menyediakan password yang benar sebelum proses ekstraksi dapat dilakukan.

## Mengapa menggunakan Aspose.Zip untuk mengekstrak RAR terenkripsi?
Aspose.Zip menyederhanakan kompleksitas format RAR, menangani arsip standar maupun terenkripsi tanpa ketergantungan eksternal. Ia menawarkan API berorientasi objek yang bersih, kinerja tinggi, dan penanganan error yang baik—sempurna untuk pengembang .NET yang menginginkan solusi andal untuk **how to decrypt RAR**.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.Zip untuk .NET Library:** Pastikan Anda telah menginstal library Aspose.Zip dalam proyek .NET Anda. Anda dapat mengunduhnya dari [Aspose.Zip documentation](https://reference.aspose.com/zip/net/).
2. **Direktori Dokumen:** Siapkan direktori tempat arsip RAR terenkripsi Anda berada. Ganti "Your Document Directory" dalam contoh kode dengan jalur aktual ke direktori tersebut.

## Impor Namespace

Mari mulai dengan mengimpor namespace yang diperlukan untuk menggunakan library Aspose.Zip secara efektif. Tambahkan baris berikut di bagian atas file .NET Anda:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Langkah 1 – Buka Arsip RAR Terenkripsi

Pertama, buka stream hanya‑baca untuk file RAR terenkripsi. Ini mempersiapkan file untuk dekripsi dan ekstraksi.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Langkah 2 – Tentukan Password RAR (cara mendekripsi RAR)

Sekarang buat instance `RarArchive` dan beri tahu Aspose.Zip password yang melindungi arsip. Ganti `"p@s$"` dengan password sebenarnya yang Anda gunakan saat membuat RAR terenkripsi.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Langkah 3 – Ekstrak Konten ke Folder (ekstrak RAR terenkripsi)

Akhirnya, ekstrak setiap entri ke folder pilihan Anda. Ini menyelesaikan operasi **extract RAR to folder**.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

Ulangi langkah‑langkah ini untuk setiap arsip RAR yang perlu Anda dekripsi, memastikan integrasi Aspose.Zip untuk .NET ke dalam proyek Anda berjalan mulus.

## Kesalahan Umum & Tips

- **Password salah** – Jika password tidak cocok, Aspose.Zip akan melempar `WrongPasswordException`. Periksa kembali string yang Anda berikan ke `DecryptionPassword`.
- **Arsip besar** – Untuk file RAR yang sangat besar, pertimbangkan mengekstrak ke folder sementara terlebih dahulu, lalu pindahkan file ke lokasi akhir untuk menghindari kehabisan ruang disk.
- **Keamanan jalur** – Selalu validasi `dataDir` dan jalur output untuk mencegah kerentanan traversal direktori.

## Kesimpulan

Selamat! Anda telah berhasil **extracted a RAR to folder** dan mempelajari cara **read encrypted RAR file** menggunakan Aspose.Zip untuk .NET. Library yang kuat ini menyederhanakan proses rumit membuka arsip yang dilindungi password, menjadikannya alat yang tak ternilai bagi pengembang yang bekerja dengan aplikasi .NET.

## Pertanyaan yang Sering Diajukan (FAQ)

### Apakah Aspose.Zip untuk .NET kompatibel dengan semua versi arsip RAR?
Aspose.Zip untuk .NET mendukung berbagai versi arsip RAR, memastikan kompatibilitas dengan beragam file.

### Dapatkah saya menggunakan Aspose.Zip untuk .NET dalam proyek komersial?
Ya, Aspose.Zip untuk .NET tersedia untuk penggunaan komersial. Kunjungi [purchase page](https://purchase.aspose.com/buy) untuk detail lisensi.

### Apakah lisensi sementara tersedia untuk tujuan pengujian?
Ya, Anda dapat memperoleh lisensi sementara untuk pengujian dari [here](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dukungan tambahan atau diskusi komunitas?
Kunjungi [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) untuk dukungan dan diskusi komunitas.

### Bagaimana cara mengakses dokumentasi untuk Aspose.Zip untuk .NET?
[Documentation](https://reference.aspose.com/zip/net/) menyediakan informasi lengkap tentang penggunaan Aspose.Zip untuk .NET.

**Additional Q&A**

**Q:** Bagaimana cara mengekstrak hanya file tertentu dari RAR terenkripsi?  
**A:** Gunakan `RarArchiveEntry` untuk menemukan entri yang diinginkan dan panggil `ExtractToFile` dengan password dekripsi yang sudah ditetapkan pada arsip.

**Q:** Bagaimana jika saya perlu mengubah nama folder output secara dinamis?  
**A:** Bangun jalur output menggunakan `Path.Combine` dan variabel runtime apa pun sebelum memanggil `ExtractToDirectory`.

**Q:** Apakah Aspose.Zip mendukung arsip RAR multi‑volume?  
**A:** Ya, library dapat membuka dan mengekstrak set RAR multi‑volume selama semua bagian dapat diakses.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Zip untuk .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}