---
date: 2026-02-15
description: Pelajari cara menambahkan file ke tar dan mengompresnya menjadi TarZ
  menggunakan Aspose.Zip untuk .NET – panduan langkah demi langkah untuk penanganan
  file .NET yang efisien.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tambahkan file ke tar dan kompres menjadi TarZ dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambah file ke tar dan kompres ke TarZ dengan Aspose.Zip untuk .NET

## Introduction

Jika Anda perlu **menambahkan file ke tar** dan kemudian mengompres arsip ke format TarZ, Aspose.Zip untuk .NET membuat seluruh proses menjadi mudah. Dalam tutorial ini kami akan membahas setiap langkah—dari menyiapkan proyek Anda hingga membuat arsip tar, menambahkan file, dan akhirnya menyimpan file .tar.z yang terkompresi. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke dalam aplikasi .NET apa pun.

## Quick Answers
- **Perpustakaan apa yang menangani pembuatan tar?** Aspose.Zip untuk .NET  
- **Berapa banyak baris kode?** Sekitar 15 baris (tidak termasuk komentar)  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Bisakah saya mengompres folder, bukan hanya file?** Ya – Anda dapat menambahkan seluruh direktori dengan loop.

## What is **add files to tar**?
Menambahkan file ke arsip tar menggabungkan mereka ke dalam satu wadah yang tidak terkompresi yang mempertahankan struktur direktori dan metadata file. Tar adalah format Unix klasik dan menjadi dasar bagi banyak alur kerja kompresi, termasuk format TarZ yang digunakan dalam panduan ini.

## Why add files to tar before compressing to TarZ?
- **Portabilitas** – Arsip tar dapat bekerja di berbagai platform tanpa harus khawatir tentang penanganan file individual.  
- **Kecepatan** – Membuat wadah tar cepat; kompresi Z‑selanjutnya fokus pada pengurangan ukuran saja.  
- **Kompatibilitas** – Banyak alat lama mengharapkan `.tar` sebelum menerapkan kompresi gaya gzip, yang tepatnya diberikan oleh `.tar.z`.  

### Why this matters for .NET developers
Menggunakan wadah tar memungkinkan kode .NET Anda tetap sederhana dan deterministik. Anda dapat menghasilkan arsip di memori, mengalirkannya langsung ke respons, atau menyimpannya di disk tanpa harus berurusan dengan file zip sementara. Pola ini sangat berguna untuk pipeline build, agregasi log, atau ketika Anda perlu mengirimkan sekumpulan file konfigurasi ke layanan berbasis Linux.

## Prerequisites

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- **Aspose.Zip for .NET** terinstal. Unduh dari situs resmi [here](https://releases.aspose.com/zip/net/).  
- Sebuah folder di mesin Anda yang berisi file yang ingin Anda arsipkan. Ganti path placeholder dengan direktori aktual Anda.

## Import Namespaces

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tip:** Gunakan `Path.Combine` jika Anda perlu membangun path secara dinamis; ini menghindari hilangnya pemisah path pada OS yang berbeda.

## Step‑by‑Step Guide

### Step 1: Define Your Document Directory

```csharp
string dataDir = "Your Document Directory";
```

> **Mengapa langkah ini penting:** `dataDir` berfungsi sebagai lokasi dasar untuk setiap file yang akan Anda tambahkan. Menyimpannya dalam satu variabel membuat kode mudah dipelihara dan dapat digunakan kembali pada banyak arsip.

### Step 2: Create a Tar Archive and add files

#### 2.1: Create the Tar archive instance

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` menjamin bahwa objek `TarArchive` dibuang dengan benar, melepaskan semua handle file atau buffer memori.

#### 2.2: Add files to the archive  

Inside the `using` block, add each file you want to include:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Anda dapat mengulang `CreateEntry` sebanyak file yang diperlukan, atau melakukan loop melalui sebuah direktori untuk menambahkannya secara programatis. Misalnya, loop `foreach (var file in Directory.GetFiles(dataDir))` memungkinkan Anda menangani jumlah file yang tidak terbatas sambil mempertahankan jalur relatif mereka.

#### 2.3: Save the compressed TarZ file  

After adding all entries, compress the tar archive to the `.tar.z` format:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

File `archive.tar.z` yang dihasilkan akan berada di folder yang sama dengan yang Anda tentukan di `dataDir`. Sekarang Anda dapat mengirimkan paket terkompresi tunggal ini ke sistem mana pun yang mendukung TarZ.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File tidak ditemukan** | Path salah atau ekstensi file hilang | Pastikan `dataDir` diakhiri dengan pemisah path dan nama file sudah benar. |
| **Akses ditolak** | Izin tidak cukup pada folder target | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |
| **File terkompresi lebih besar dari yang diharapkan** | File asli sudah terkompresi (misalnya gambar, video) | TarZ paling efektif pada file teks atau log; pertimbangkan untuk membiarkan file yang sudah terkompresi apa adanya. |

### Common pitfalls to watch out for
- **Slash akhir hilang** – Jika `dataDir` tidak diakhiri dengan `\` atau `/`, penggabungan string akan menghasilkan path yang tidak valid.  
- **Direktori besar** – Menambahkan ribuan file dapat mengonsumsi memori; pertimbangkan untuk men‑stream entri atau menggunakan overload `TarArchive` yang menulis langsung ke stream file.  
- **Masalah encoding** – Nama file non‑ASCII mungkin memerlukan penanganan encoding secara eksplisit; Aspose.Zip menghormati UTF‑8 secara default, tetapi pastikan pada platform target.  

## Frequently Asked Questions

**Q: Bisakah saya mengompres seluruh folder dengan Aspose.Zip untuk .NET?**  
A: Tentu saja. Gunakan loop `Directory.GetFiles` dan panggil `CreateEntry` untuk setiap file, sambil mempertahankan jalur relatif.

**Q: Apakah ada versi percobaan untuk Aspose.Zip untuk .NET?**  
A: Ya, Anda dapat menjelajahi kemampuan Aspose.Zip untuk .NET dengan mengunduh percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/), memberikan wawasan detail tentang fitur dan penggunaan perpustakaan.

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas.

**Q: Bisakah saya memperoleh lisensi sementara untuk Aspose.Zip untuk .NET?**  
A: Ya, jika Anda membutuhkan lisensi sementara, Anda dapat memperolehnya [di sini](https://purchase.aspose.com/temporary-license/).

## Conclusion

Anda kini telah mempelajari cara **menambahkan file ke tar** dan mengompres hasilnya menjadi arsip TarZ menggunakan Aspose.Zip untuk .NET. Pendekatan ini memberi Anda paket yang bersih dan portabel yang dapat dengan mudah dipindahkan, disimpan, atau diproses lebih lanjut. Silakan sesuaikan potongan kode ini untuk memproses batch direktori, mengintegrasikannya ke dalam pipeline build, atau menggabungkannya dengan komponen Aspose lainnya untuk alur kerja dokumen yang lebih kaya.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}