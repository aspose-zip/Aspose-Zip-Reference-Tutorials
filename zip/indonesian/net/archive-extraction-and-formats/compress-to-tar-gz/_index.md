---
date: 2026-02-20
description: Pelajari cara membuat arsip tar, menambahkan file ke tar, dan mengompres
  menjadi tar.gz menggunakan Aspose.Zip untuk .NET – cara cepat dan lintas platform
  untuk membuat arsip TarGz.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat arsip tar dan tambahkan file ke tar dengan Aspose.Zip untuk .NET

## Perkenalan

Dalam aplikasi .NET modern, **membuat arsip tar** dan **menambahkan file ke tar** dengan cepat dan dapat diandalkan adalah kebutuhan umum—baik Anda mengemas log, menyiapkan data untuk penyimpanan cloud, atau membangun bundel penyebaran. Aspose.Zip untuk .NET memberikan API yang bersih dan berperforma tinggi untuk **menambahkan file ke tar**, lalu mengompres arsip ke format **tar.gz** yang banyak digunakan. Dalam panduan ini kami akan membahas seluruh proses, mulai dari menyiapkan proyek Anda hingga menghasilkan `archive.tar.gz` siap kirim.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.Zip for .NET
- **Bagaimana cara menambahkan file ke tar?** Gunakan `TarArchive.CreateEntry` untuk setiap file.
- ** tiba-tiba saya mengompres langsung ke tar.gz?** Ya—panggil `SaveGzipped`.
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose yang valid diperlukan untuk penggunaan non-trial.
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “tambahkan file ke tar”?

Menambahkan file ke arsip tar berarti menggabungkan beberapa file menjadi satu wadah yang tidak terkompresi. Format tar mempertahankan struktur direktori dan file metadata, menjadikannya ideal untuk pengarsipan sebelum kompresi opsional (mis., gzip) untuk **membuat arsip tar.gz**.

## Mengapa menggunakan Aspose.Zip untuk mengompresi file ke tar.gz?
- **Tanpa alat eksternal** – semuanya berjalan di dalam kode .NET Anda.
- **Kinerja tinggi** – API berbasis aliran menangani file besar secara efisien.
- **Tar lintas‑platform** – berfungsi di Windows, Linux, dan macOS tanpa perubahan.
- **Set fitur lengkap** – mendukung enkripsi, perlindungan kata sandi, dan entri atribut khusus.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Pengalaman dasar pengembangan .NET.
- Visual Studio (atau IDE pilihan Anda).
- Aspose.Zip for .NET terpasang – lihat dokumentasi resmi [di sini](https://reference.aspose.com/zip/net/).
- Perpustakaan Aspose.Zip diunduh dari [tautan ini](https://releases.aspose.com/zip/net/).

## Impor Namespace

Di proyek .NET Anda, import namespace yang menyediakan kelas‑kelas terkait tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Cara menambahkan file ke tar menggunakan Aspose.Zip untuk .NET

### Langkah 1: Tetapkan Direktori Dokumen Anda

Pertama, arahkan kode ke folder yang berisi file yang ingin Anda arsipkan.

```csharp
string dataDir = "Your Document Directory";
```

> **Tips profesional:** Gunakan `Path.Combine` saat membangun path untuk menghindari masalah pemisah yang spesifik platform.

### Langkah 2: Buat Arsip TarGz

Sekarang kita akan membuat arsip tar, menambahkan entri, dan mengompresnya dalam satu alur fluens.

#### 2.1 Inisialisasi TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Tambahkan File – inti dari “menambahkan file ke tar”

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Setiap pemanggilan `CreateEntry` mengambil **nama entri** (bagaimana file akan muncul di dalam tar) dan **jalur file sumber** di disk. Anda dapat memanggil `CreateEntry` berulang kali untuk **menambahkan beberapa file ke tar** dalam satu arsip.

#### 2.3 Simpan sebagai Tar Terkompresi Gzipped (cara mengompres tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` menulis konten tar ke aliran gzip, memberikan Anda file `archive.tar.gz` yang kompak dan siap didistribusikan.

## Kasus Penggunaan Umum

| Skenario | Mengapa “menambahkan file ke tar” membantu |
|----------|--------------------------------------------|
| **Penggabungan log** | Menggabungkan log harian menjadi satu arsip sebelum mengunggah ke penyimpanan cloud. |
| **Paket penyebaran** | Membuat bundel tar.gz portabel untuk server Linux dari pipeline build Windows. |
| **Data Cadangan** | Mempertahankan hierarki folder dan metadata sambil menjaga ukuran cadangan tetap kecil. |

## Masalah Umum dan Solusinya

- **Kesalahan file tidak ditemukan** – Pastikan `dataDir` diakhiri dengan batas path yang tepat atau gunakan `Path.Combine`.
- **File besar menyebabkan tekanan memori** – Gunakan kelebihan beban berbasis aliran (`CreateEntry` dengan `Stream`) untuk menghindari memuat seluruh file ke memori.
- **Output gzip rusak** – Pastikan arsip ditutup (`using` block) sebelum memanggil `SaveGzipped`.

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Zip untuk .NET kompatibel dengan semua aplikasi .NET?**
J: Ya, saya bekerja dengan proyek .NET Framework, .NET Core, dan .NET 5/6/7.

**T: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Zip untuk .NET?**
J: Kunjungi [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk meminta lisensi percobaan.

**T: Apakah ada batasan ukuran file?**
J: Perpustakaan dioptimalkan untuk file besar; tidak ada batasan ukuran keras selain sistem memori yang tersedia.

**T: Di mana saya bisa mendapatkan dukungan?**
J: Gunakan forum dukungan berbasis komunitas [di sini](https://forum.aspose.com/c/zip/37) untuk bantuan dari insinyur Aspose dan pengembang lainnya.

**T: Bisakah saya mencoba Aspose.Zip untuk .NET secara gratis?**
J: Tentu—unduh percobaan gratis dari [halaman rilis Aspose Zip](https://releases.aspose.com/zip/net).

## Kesimpulan

Anda kini telah mempelajari **cara membuat arsip tar**, menambahkan file ke dalamnya, dan mengompresnya menjadi **tar.gz** menggunakan Aspose.Zip untuk .NET. Pendekatan ini membantu ketergantungan eksternal, memberi Anda kontrol detail atas isi arsip, dan dapat menangani kumpulan data besar. Jangan ragu untuk menjelajahi fitur tambahan Aspose.Zip seperti enkripsi, atribut entri khusus, dan API streaming untuk lebih meningkatkan alur kerja pengarsipan Anda.

---

**Terakhir Diperbarui:** 20-02-2026
**Diuji Dengan:** Aspose.Zip 24.11 untuk .NET
**Penulis:** Beranggapan

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
