---
date: 2025-11-29
description: Pelajari cara menambahkan file ke tar dan mengompresnya menjadi TarZ
  menggunakan Aspose.Zip untuk .NET – panduan langkah demi langkah untuk penanganan
  file .NET yang efisien.
language: id
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tambahkan file ke tar dan kompres menjadi TarZ dengan Aspose.Zip untuk .NET
url: /net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan file ke tar dan mengompres ke TarZ dengan Aspose.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **menambahkan file ke tar** dan kemudian mengompres arsip ke format TarZ, Aspose.Zip untuk .NET membuat seluruh proses menjadi mudah. Dalam tutorial ini kami akan membahas setiap langkah—mulai dari menyiapkan proyek Anda hingga membuat arsip tar, menambahkan file, dan akhirnya menyimpan file .tar.z yang terkompresi. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke dalam aplikasi .NET mana pun.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pembuatan tar?** Aspose.Zip untuk .NET  
- **Berapa banyak baris kode?** Sekitar 15 baris (tidak termasuk komentar)  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Bisakah saya mengompres folder, bukan hanya file?** Ya – Anda dapat menambahkan seluruh direktori dengan loop.

## Apa itu **add files to tar**?
Menambahkan file ke arsip tar menggabungkan mereka ke dalam satu wadah yang tidak terkompresi yang mempertahankan struktur direktori dan metadata file. Tar adalah format Unix klasik dan menjadi dasar bagi banyak alur kerja kompresi, termasuk format TarZ yang digunakan dalam panduan ini.

## Mengapa menambahkan file ke tar sebelum mengompres ke TarZ?
- **Portabilitas** – Arsip tar dapat bekerja di berbagai platform tanpa harus khawatir tentang penanganan file individual.  
- **Kecepatan** – Membuat kontainer tar cepat; kompresi Z‑selanjutnya fokus pada pengurangan ukuran.  
- **Kompatibilitas** – Banyak alat lama mengharapkan `.tar` sebelum menerapkan kompresi gaya gzip, yang tepatnya diberikan oleh `.tar.z`.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terpasang. Unduh dari situs resmi [di sini](https://releases.aspose.com/zip/net/).  
- Sebuah folder di mesin Anda yang berisi file‑file yang ingin Anda arsipkan. Ganti jalur placeholder dengan direktori aktual Anda.

## Impor Namespace

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan Direktori Dokumen Anda

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gunakan `Path.Combine` jika Anda perlu membangun jalur secara dinamis; ini menghindari hilangnya pemisah jalur pada OS yang berbeda.

### Langkah 2: Buat Arsip Tar dan tambahkan file

#### 2.1: Buat instance arsip Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Tambahkan file ke arsip  

Di dalam blok `using`, tambahkan setiap file yang ingin Anda sertakan:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Anda dapat mengulangi `CreateEntry` sebanyak file yang diperlukan, atau melakukan loop melalui sebuah direktori untuk menambahkannya secara programatis.

#### 2.3: Simpan file TarZ yang terkompresi  

Setelah menambahkan semua entri, kompres arsip tar ke format `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

File `archive.tar.z` yang dihasilkan akan berada di folder yang sama dengan yang Anda tentukan di `dataDir`.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** | Path salah atau ekstensi file hilang | Pastikan `dataDir` diakhiri dengan pemisah path dan nama file sudah benar. |
| **Akses ditolak** | Izin tidak cukup pada folder target | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |
| **File terkompresi lebih besar dari yang diharapkan** | File asli sudah terkompresi (misalnya gambar, video) | TarZ paling efektif pada file teks atau log; pertimbangkan untuk membiarkan file yang sudah terkompresi tetap sebagaimana adanya. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengompres seluruh folder dengan Aspose.Zip untuk .NET?**  
A: Tentu saja. Gunakan loop `Directory.GetFiles` dan panggil `CreateEntry` untuk setiap file, sambil mempertahankan jalur relatif.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Zip untuk .NET?**  
A: Ya, Anda dapat menjelajahi kemampuan Aspose.Zip untuk .NET dengan mengunduh versi percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/), memberikan wawasan detail tentang fitur dan penggunaan perpustakaan.

**Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas.

**Q: Bisakah saya memperoleh lisensi sementara untuk Aspose.Zip untuk .NET?**  
A: Ya, jika Anda memerlukan lisensi sementara, Anda dapat memperolehnya [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda kini telah mempelajari cara **menambahkan file ke tar** dan mengompres hasilnya ke arsip TarZ menggunakan Aspose.Zip untuk .NET. Pendekatan ini memberikan paket yang bersih dan portabel yang dapat dengan mudah dipindahkan, disimpan, atau diproses lebih lanjut. Silakan sesuaikan potongan kode ini untuk memproses batch direktori, mengintegrasikannya ke dalam pipeline build, atau menggabungkannya dengan komponen Aspose lainnya untuk alur kerja dokumen yang lebih kaya.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2025-11-29  
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11  
**Penulis:** Aspose  

---