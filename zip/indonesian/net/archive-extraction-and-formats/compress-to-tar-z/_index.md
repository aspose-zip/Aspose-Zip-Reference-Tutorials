---
date: 2026-11-18
description: Pelajari cara membuat arsip tar dan mengompresnya ke TarZ menggunakan
  Aspose.Zip for .NET – panduan langkah demi langkah untuk penanganan file .NET yang
  efisien.
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: Mengompres ke TarZ
og_description: Pelajari cara membuat arsip tar dan mengompresnya ke TarZ menggunakan
  Aspose.Zip for .NET. Panduan ini memandu Anda menambahkan file, direktori, dan mengompres
  secara efisien.
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: Cara membuat tar dan mengompres ke TarZ dengan Aspose.Zip for .NET
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Cara membuat tar dan mengompres ke TarZ dengan Aspose.Zip for .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan file ke tar dan kompres ke TarZ dengan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **add files to tar** dan kemudian mengompres arsip ke format TarZ, Aspose.Zip untuk .NET membuat seluruh proses menjadi mudah. Dalam tutorial ini kami akan membahas setiap langkah—dari menyiapkan proyek Anda hingga membuat arsip tar, menambahkan file, dan akhirnya menyimpan file .tar.z yang terkompresi. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke dalam aplikasi .NET apa pun, baik Anda menangani beberapa file konfigurasi maupun seluruh pohon direktori.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pembuatan tar?** Aspose.Zip for .NET  
- **Berapa baris kode?** Sekitar 15 baris (tidak termasuk komentar)  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10  
- **Bisakah saya mengompres folder, bukan hanya file?** Ya – Anda dapat menambahkan seluruh direktori dengan loop.

## Apa itu **add files to tar**?
**Add files to tar** adalah proses menggabungkan file terpilih ke dalam satu kontainer tar yang tidak terkompresi sambil mempertahankan hierarki direktori dan metadata. Format tar menghasilkan paket deterministik yang bersifat platform‑agnostik sehingga algoritma kompresi selanjutnya dapat bekerja secara efisien, menjadikannya ideal untuk distribusi lintas‑platform.

## Cara membuat arsip tar dengan Aspose.Zip untuk .NET?

Kelas `TarArchive` mewakili kontainer tar yang dapat menampung banyak entri file. Muat direktori sumber, buat instance `TarArchive`, tambahkan setiap file (atau seluruh sub‑direktori), dan akhirnya panggil `Save` dengan flag kompresi TarZ. Proses ini sederhana, hanya memerlukan beberapa baris kode, dan berfungsi konsisten di semua runtime .NET yang didukung, termasuk .NET Framework dan .NET Core.

Kelas `TarArchive` adalah objek inti Aspose.Zip yang mewakili kontainer tar yang dapat Anda isi dengan entri. Menggunakannya memungkinkan Anda menghasilkan file tar sepenuhnya di memori, mengalirkannya langsung ke respons, atau menuliskannya ke disk tanpa file zip sementara.

## Mengapa menambahkan file ke tar sebelum mengompres ke TarZ?

Membuat kontainer tar terlebih dahulu memisahkan proses pengemasan dari kompresi, yang menghasilkan tiga manfaat terukur. Dengan memisahkan tahap‑tahap ini Anda memperoleh arsip yang dapat diprediksi dan dapat diulang yang dapat dikompres secara terpisah, memudahkan pengukuran rasio kompresi dan penggunaan kembali tar yang sama untuk algoritma kompresi yang berbeda.

1. **Portability** – File `.tar` dapat diekstrak pada sistem mirip Unix mana pun tanpa perpustakaan tambahan.  
2. **Speed** – Pembuatan tar pada dasarnya adalah operasi penyalinan aliran; kompresi Z selanjutnya kemudian fokus pada pengurangan ukuran, biasanya memotong **30‑70 %** data asli.  
3. **Compatibility** – Banyak alat warisan (misalnya `tar`, `gzip`) mengharapkan file `.tar` sebelum menerapkan kompresi gaya gzip, tepat seperti yang diwakili oleh ekstensi `.tar.z`.

### Mengapa ini penting bagi pengembang .NET
Menggunakan kontainer tar memungkinkan kode .NET Anda tetap sederhana dan deterministik. Anda dapat menghasilkan arsip di memori, mengalirkannya langsung ke respons, atau menyimpannya di disk tanpa harus berurusan dengan file zip sementara. Pola ini sangat berguna untuk pipeline build, agregasi log, atau ketika Anda perlu mengirimkan sekumpulan file konfigurasi ke layanan berbasis Linux.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- **Aspose.Zip for .NET** terpasang. Unduh dari situs resmi [here](https://releases.aspose.com/zip/net/).  
- Sebuah folder di mesin Anda yang berisi file yang ingin diarsipkan. Ganti path placeholder dengan direktori Anda yang sebenarnya.

## Impor namespace

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tip:** Gunakan `Path.Combine` jika Anda perlu membangun path secara dinamis; ini menghindari hilangnya pemisah path pada OS yang berbeda.

## Cara menambahkan file ke tar menggunakan Aspose.Zip untuk .NET?

Metode `CreateEntry` menambahkan entri file baru ke arsip tar dengan nama dan aliran konten yang ditentukan. Muat direktori sumber, buat instance `TarArchive`, tambahkan setiap file (atau seluruh sub‑direktori), dan akhirnya panggil `Save` dengan flag kompresi TarZ. Alur kerja ini tetap singkat, biasanya di bawah 20 baris, dan berfungsi di semua runtime .NET yang didukung, memberikan cara yang dapat diandalkan untuk mengemas dan mengompres data.

Metode `Save` menuliskan arsip ke disk dan secara opsional menerapkan kompresi.

### Anchor definisi
Kelas `TarArchive` adalah objek inti Aspose.Zip yang mewakili kontainer tar yang dapat Anda isi dengan entri.

### Panduan Langkah‑per‑Langkah

#### Langkah 1: Tentukan direktori dokumen Anda

```csharp
string dataDir = "Your Document Directory";
```

> **Mengapa langkah ini penting:** `dataDir` berfungsi sebagai lokasi dasar untuk setiap file yang akan Anda tambahkan. Menyimpannya dalam satu variabel membuat kode mudah dipelihara dan dapat digunakan kembali di banyak arsip.

#### Langkah 2: Buat arsip Tar dan tambahkan file

##### 2.1: Buat instance arsip Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` menjamin bahwa objek `TarArchive` dibuang dengan benar, melepaskan semua handle file atau buffer memori.

##### 2.2: Tambahkan file ke arsip  

`CreateEntry` menambahkan file ke arsip tar, menentukan nama dan aliran kontennya.  

Di dalam blok `using`, tambahkan setiap file yang ingin Anda sertakan:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Anda dapat mengulang `CreateEntry` sebanyak yang diperlukan, atau melakukan loop melalui sebuah direktori untuk menambahkannya secara programatis. Misalnya, loop `foreach (var file in Directory.GetFiles(dataDir))` memungkinkan Anda menangani jumlah file yang tidak terbatas sambil mempertahankan jalur relatif mereka.

##### 2.3: Simpan file TarZ yang terkompresi  

`Save` menuliskan arsip ke disk dan menerapkan format kompresi yang dipilih.  

Setelah menambahkan semua entri, kompres arsip tar ke format `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

File `archive.tar.z` yang dihasilkan akan berada di folder yang sama dengan yang Anda tentukan di `dataDir`. Sekarang Anda dapat mengirimkan paket terkompresi tunggal ini ke sistem mana pun yang memahami TarZ.

## Masalah umum dan solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** | Path salah atau ekstensi file hilang | Pastikan `dataDir` diakhiri dengan pemisah path dan nama file sudah benar. |
| **Akses ditolak** | Izin tidak cukup pada folder target | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |
| **File terkompresi lebih besar dari yang diharapkan** | File asli sudah terkompresi (misalnya gambar, video) | TarZ paling efektif pada file teks atau log; pertimbangkan untuk membiarkan file yang sudah terkompresi apa adanya. |

### Kesalahan umum yang harus diwaspadai
- **Missing trailing slash** – Jika `dataDir` tidak diakhiri dengan `\` atau `/`, penggabungan string akan menghasilkan path yang tidak valid.  
- **Large directories** – Menambahkan ribuan file dapat mengonsumsi memori; pertimbangkan untuk mengalirkan entri atau menggunakan overload `TarArchive` yang menulis langsung ke aliran file.  
- **Encoding issues** – Nama file non‑ASCII mungkin memerlukan penanganan encoding eksplisit; Aspose.Zip menghormati UTF‑8 secara default, tetapi verifikasi pada platform target.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengompres seluruh folder dengan Aspose.Zip untuk .NET?**  
A: Tentu saja. Gunakan loop `Directory.GetFiles` dan panggil `CreateEntry` untuk setiap file, sambil mempertahankan jalur relatif.

**Q: Apakah ada versi percobaan tersedia untuk Aspose.Zip untuk .NET?**  
A: Ya, Anda dapat menjelajahi kemampuan Aspose.Zip untuk .NET dengan mengunduh versi percobaan gratis [here](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**  
A: Dokumentasi tersedia [here](https://reference.aspose.com/zip/net/), memberikan wawasan detail tentang fitur dan penggunaan perpustakaan.

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Kunjungi [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas.

**Q: Bisakah saya memperoleh lisensi sementara untuk Aspose.Zip untuk .NET?**  
A: Ya, jika Anda memerlukan lisensi sementara, Anda dapat mendapatkannya [here](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda kini telah mempelajari cara **add files to tar** dan mengompres hasilnya menjadi arsip TarZ menggunakan Aspose.Zip untuk .NET. Pendekatan ini memberi Anda paket yang bersih, portabel, dan mudah dipindahkan, disimpan, atau diproses lebih lanjut. Silakan sesuaikan potongan kode untuk memproses batch direktori, mengintegrasikannya ke dalam pipeline build, atau menggabungkannya dengan komponen Aspose lainnya untuk alur kerja dokumen yang lebih kaya.

---

**Terakhir Diperbarui:** 2026-11-18  
**Diuji Dengan:** Aspose.Zip for .NET 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambahkan beberapa file ke tar dan buat arsip tar.gz dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cara mengompres beberapa file tar dengan Aspose.Zip untuk .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Ekstraksi Arsip dan Format](/zip/net/archive-extraction-and-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}