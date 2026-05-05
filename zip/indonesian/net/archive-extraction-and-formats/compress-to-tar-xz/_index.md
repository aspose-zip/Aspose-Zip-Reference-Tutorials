---
date: 2026-02-23
description: Pelajari cara menambahkan file ke tar dan mengompres file ke arsip tarxz
  .NET menggunakan Aspose.Zip. Ikuti panduan langkah demi langkah ini untuk penyimpanan
  dan transmisi yang efisien.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tambahkan file ke tar dan buat arsip tarxz dengan Aspose.Zip
url: /id/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan file ke tar dan membuat arsip tarxz dengan Aspose.Zip

## Perkenalan

Jika Anda perlu **menambahkan file ke tar** dan kemudian **membuat arsip tarxz .net**, Aspose.Zip untuk .NET membuat prosesnya menjadi sederhana dan dapat diandalkan. Baik Anda mengemas log, file konfigurasi, atau aset lainnya untuk penyimpanan atau transmisi, mengompresi ke format TarXz memberikan rasio kompresi tinggi sambil mempertahankan struktur tar yang familiar. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah yang tepat—dilengkapi dengan potongan kode—sehingga Anda dapat mengintegrasikan pembuatan tarxz ke dalam aplikasi .NET Anda dengan percaya diri.

## Jawaban Cepat
- **Apa kelas utamanya?** `TarArchive` dari `Aspose.Zip.Tar`
- **Bagaimana cara mengompresi tarxz?** Gunakan `SaveXzCompressed` setelah menambahkan entri
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Lisensi diperlukan?** Ya, lisensi Aspose.Zip yang valid untuk produksi
- **Waktu penerapan pada umumnya?** ~5‑10 menit

## Apa itu arsip TarXz?

**Arsip TarXz** menggabungkan kontainer Unix tradisional `tar` dengan kompresi XZ. Bagian tar menggabungkan beberapa file menjadi satu aliran, sementara XZ menyediakan kompresi yang kuat dan lossless. Format ini populer untuk mendistribusikan kode sumber, backup, dan kumpulan data besar karena mempertahankan struktur direktori dan menghasilkan ukuran file yang lebih kecil dibandingkan tar atau zip biasa.

## Mengapa membuat arsip tarxz .net dengan Aspose.Zip?

- **Rasio kompresi tinggi** – XZ sering menghasilkan kompresi 30‑50% lebih kecil dibandingkan gzip.
- **Kompatibilitas lintas platform** – File TarXz dapat dibuka di Linux, macOS, dan Windows.
- **API Sederhana** – Aspose.Zip mengoordinasikan detail tingkat rendah, memungkinkan Anda fokus pada logika bisnis.
- **No external tools** – Semua berjalan di dalam proses .NET Anda, cocok untuk cloud atau pipeline CI.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terpasang (unduh dari [dokumentasi Aspose.Zip](https://reference.aspose.com/zip/net/)).
- Sebuah folder yang berisi file‑file yang ingin Anda arsipkan. Pada contoh di bawah, folder ini direferensikan oleh variabel `dataDir`.
- Lisensi Aspose.Zip yang valid (opsional untuk evaluasi, wajib untuk produksi).

## Impor Namespace

Pertama, import namespace yang menyediakan fungsionalitas TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Cara menambahkan file ke tar menggunakan Aspose.Zip

Berikut panduan langkah‑demi‑langkah yang menunjukkan secara tepat cara **menambahkan file ke tar** sebelum mengompresinya.

### Langkah 1: Inisialisasi `TarArchive`

Buat instance `TarArchive` baru yang akan menampung file-file yang ingin Anda kompres.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Tips pro:** Pernyataan `using` memastikan arsip pembuangan benar, melepaskan sumber daya yang tidak dikelola.

### Langkah 2: Tambahkan File ke Arsip

Tambahkan setiap file yang ingin Anda sertakan. Pada contoh ini kami menambahkan dua file teks, tetapi Anda dapat menambahkan sebanyak entri yang diperlukan.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Mengapa ini penting:** Menambahkan entri sebelum kompresi memungkinkan Aspose.Zip membangun kontainer tar terlebih dahulu, kemudian menerapkan kompresi XZ dalam satu langkah.

### Langkah 3: Simpan Arsip dengan Kompresi XZ

Akhirnya, tulis arsip tar ke disk menggunakan kompresi XZ. File yang dihasilkan akan memiliki ekstensi `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Hasil:** Anda kini memiliki file `archive.tar.xz` yang terkompresi penuh dan dapat dipindahkan, disimpan, atau dibuka di platform apa pun yang mendukung TarXz.

## Cara kompres file tarxz dengan Aspose.Zip

Proses yang ditampilkan di atas pada dasarnya **cara mengompres tarxz**: pertama tambahkan file ke wadah tar (`add files to tar`) lalu panggil `SaveXzCompressed`. Pendekatan satu‑panggilan ini menghilangkan kebutuhan akan alat baris perintah eksternal dan menjaga semuanya tetap berada dalam basis kode .NET Anda.

## Masalah & Solusi Umum

| Edisi | Penyebab | Perbaiki |
|-------|-------|-----|
| **Pengecualian “File tidak ditemukan”** | Jalur `dataDir` | Verifikasi jalur direktori diakhiri dengan garis miring terbalik (`\`) atau gunakan `Path.Combine`. |
| **Penggunaan memori besar** | File berukuran sangat besar dikompresi dalam memori | Gunakan `TarArchive` dalam mode streaming (overload `SaveXzCompressed` yang menerima `Stream`). |

| **Lisensi tidak diterapkan** | File lisensi hilang | Muat lisensi saat aplikasi dimulai: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Zip kompatibel dengan semua lingkungan .NET?**
J: Ya, Aspose.Zip bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6+. Lihat [dokumentasi](https://reference.aspose.com/zip/net/) untuk detailnya.

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Zip?**
J: Anda dapat meminta lisensi sementara dari [halaman lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/).

**T: Apakah ada contoh tambahan untuk format arsip lain?**
J: Tentu saja—jelajahi seluruh contoh di [referensi API Aspose.Zip](https://reference.aspose.com/zip/net/).

**T: Di mana saya bisa mendapatkan bantuan atau mendiskusikan masalah?**
J: Bergabunglah dalam percakapan di [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk mendapatkan dukungan komunitas dan jawaban resmi.

**T: Bisakah saya mencoba Aspose.Zip secara gratis sebelum membeli?**
J: Ya, uji coba gratis tersedia di [halaman unduhan Aspose.Zip](https://releases.aspose.com/zip/net).

## Kesimpulan

Dengan mengikuti langkah‑langkah di atas, Anda kini tahu **cara menambahkan file ke tar** dan **mengompres file tarxz**, serta yang lebih penting, **cara membuat arsip tarxz .net** menggunakan Aspose.Zip. Pendekatan ini memberi Anda paket yang kompak dan portabel yang dapat diintegrasikan secara mulus ke dalam alur kerja .NET apa pun—baik Anda membangun utilitas desktop, layanan web, atau pipeline CI/CD otomatis.

---

**Terakhir Diperbarui:** 23-02-2026
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}