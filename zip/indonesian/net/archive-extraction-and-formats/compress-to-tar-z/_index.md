---
date: 2026-05-30
description: Pelajari cara menambahkan file ke tar dan mengompresnya ke TarZ menggunakan
  Aspose.Zip untuk .NET – panduan langkah demi langkah untuk penanganan file .NET
  yang efisien.
keywords:
- add files to tar
- add directory to tar
- compress folders to tar
- compress files .net
linktitle: Mengompres ke TarZ
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to add files to tar and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: Add files to tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/) ,
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tambahkan file ke tar dan kompres ke TarZ dengan Aspose.Zip untuk .NET
url: /id/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan file ke tar dan kompres ke TarZ dengan Aspise.Zip untuk .NET

## Pendahuluan

Jika Anda perlu **add files to tar** dan kemudian mengompres arsip ke format TarZ, Aspose.Zip untuk .NET membuat seluruh proses menjadi mudah. Dalam tutorial ini kami akan membahas setiap langkah—dari menyiapkan proyek Anda hingga membuat arsip tar, menambahkan file, dan akhirnya menyimpan file .tar.z yang terkompresi. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat disisipkan ke aplikasi .NET apa pun, baik Anda menangani beberapa file konfigurasi maupun seluruh pohon direktori.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pembuatan tar?** Aspose.Zip for .NET  
- **Berapa banyak baris kode?** About 15 lines (excluding comments)  
- **Apakah saya memerlukan lisensi untuk pengujian?** A free trial is available; a license is required for production.  
- **Versi .NET yang didukung?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **Bisakah saya mengompres folder, bukan hanya file?** Yes – you can add entire directories with a loop.

## Apa itu **add files to tar**?
Operasi **add files to tar** menggabungkan file yang dipilih ke dalam satu kontainer tar yang tidak terkompresi sambil mempertahankan hierarki direktori dan metadata.  
Memuat file ke dalam arsip tar adalah langkah pertama sebelum kompresi tambahan seperti TarZ, karena format tar menyediakan paket yang deterministik dan lintas‑platform yang dapat diproses secara efisien oleh algoritma kompresi.

## Mengapa menambahkan file ke tar sebelum mengompres ke TarZ?
Membuat kontainer tar terlebih dahulu memisahkan logika pengemasan dari langkah kompresi, yang menghasilkan tiga manfaat terukur. Dengan memisahkan tahap ini Anda mendapatkan arsip yang dapat diprediksi dan dapat diulang yang dapat dikompres secara independen, memudahkan pengukuran rasio kompresi dan penggunaan kembali tar yang sama untuk algoritma kompresi yang berbeda.  
1. **Portability** – File `.tar` dapat dibongkar pada sistem mirip Unix mana pun tanpa perpustakaan tambahan.  
2. **Speed** – Pembuatan tar pada dasarnya adalah operasi penyalinan aliran; kompresi Z berikutnya kemudian fokus hanya pada pengurangan ukuran, biasanya memotong 30‑70 % data asli.  
3. **Compatibility** – Banyak alat warisan (misalnya, `tar`, `gzip`) mengharapkan file `.tar` sebelum menerapkan kompresi gaya gzip, tepat seperti yang diwakili oleh ekstensi `.tar.z`.

### Mengapa ini penting bagi pengembang .NET
Menggunakan kontainer tar memungkinkan Anda menjaga kode .NET tetap sederhana dan deterministik. Anda dapat menghasilkan arsip di memori, mengalirkannya langsung ke respons, atau menyimpannya ke disk tanpa harus berurusan dengan file zip sementara. Pola ini sangat berguna untuk pipeline build, agregasi log, atau ketika Anda perlu mengirimkan sekumpulan file konfigurasi ke layanan berbasis Linux.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- **Aspose.Zip for .NET** terpasang. Unduh dari situs resmi [here](https://releases.aspose.com/zip/net/).  
- Sebuah folder di mesin Anda yang berisi file yang ingin Anda arsipkan. Ganti jalur placeholder dengan direktori Anda yang sebenarnya.

## Impor Namespace

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tip:** Gunakan `Path.Combine` jika Anda perlu membangun jalur secara dinamis; ini menghindari hilangnya pemisah jalur pada OS yang berbeda.

## Cara menambahkan file ke tar menggunakan Aspose.Zip untuk .NET?

Muat direktori sumber, buat instance `TarArchive`, tambahkan setiap file (atau seluruh sub‑direktori), dan akhirnya panggil `Save` dengan flag kompresi TarZ. Alur end‑to‑end ini hanya memerlukan beberapa baris kode dan berfungsi pada semua runtime .NET yang didukung.

### Definisi anchor
Kelas `TarArchive` adalah objek inti Aspose.Zip yang mewakili kontainer tar yang dapat Anda isi dengan entri.

### Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan Direktori Dokumen Anda

```csharp
string dataDir = "Your Document Directory";
```

> **Mengapa langkah ini penting:** `dataDir` berfungsi sebagai lokasi dasar untuk setiap file yang akan Anda tambahkan. Menyimpannya dalam satu variabel membuat kode mudah dipelihara dan digunakan kembali pada beberapa arsip.

### Langkah 2: Buat Arsip Tar dan tambahkan file

#### 2.1: Buat instance arsip Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` memastikan bahwa objek `TarArchive` dibuang dengan benar, melepaskan semua handle file atau buffer memori.

#### 2.2: Tambahkan file ke arsip  

`CreateEntry` menambahkan file ke arsip tar, menentukan nama dan aliran kontennya.  

Di dalam blok `using`, tambahkan setiap file yang ingin Anda sertakan:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Anda dapat mengulangi `CreateEntry` untuk sebanyak file yang diperlukan, atau melakukan loop melalui direktori untuk menambahkannya secara programatis. Misalnya, loop `foreach (var file in Directory.GetFiles(dataDir))` akan memungkinkan Anda menangani sejumlah file secara arbitrer sambil mempertahankan jalur relatif mereka.

#### 2.3: Simpan file TarZ yang terkompresi  

`Save` menulis arsip ke disk dan menerapkan format kompresi yang dipilih.  

Setelah menambahkan semua entri, kompres arsip tar ke format `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

File `archive.tar.z` yang dihasilkan akan berada di folder yang sama yang Anda tentukan di `dataDir`. Anda kini dapat mengirim paket terkompresi tunggal ini ke sistem mana pun yang memahami TarZ.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** | Jalur salah atau ekstensi file hilang | Verifikasi `dataDir` diakhiri dengan pemisah jalur dan nama file sudah benar. |
| **Akses ditolak** | Izin tidak cukup pada folder target | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |
| **File terkompresi lebih besar dari yang diharapkan** | File asli sudah terkompresi (mis., gambar, video) | TarZ paling cocok untuk file teks atau log; pertimbangkan untuk membiarkan file yang sudah terkompresi tetap sebagaimana adanya. |

### Jebakan umum yang harus diwaspadai
- **Missing trailing slash** – Jika `dataDir` tidak diakhiri dengan `\` atau `/`, penggabungan string akan menghasilkan jalur yang tidak valid.  
- **Large directories** – Menambahkan ribuan file dapat mengonsumsi memori; pertimbangkan untuk men-stream entri atau menggunakan overload `TarArchive` yang menulis langsung ke aliran file.  
- **Encoding issues** – Nama file non‑ASCII mungkin memerlukan penanganan encoding eksplisit; Aspose.Zip menghormati UTF‑8 secara default, tetapi verifikasi di platform target.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengompres seluruh folder dengan Aspose.Zip untuk .NET?**  
A: Tentu saja. Gunakan loop `Directory.GetFiles` dan panggil `CreateEntry` untuk setiap file, sambil mempertahankan jalur relatif.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Zip untuk .NET?**  
A: Ya, Anda dapat menjelajahi kemampuan Aspose.Zip untuk .NET dengan mengunduh percobaan gratis [here](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**  
A: Dokumentasi tersedia [here](https://reference.aspose.com/zip/net/), memberikan wawasan terperinci tentang fitur dan penggunaan perpustakaan.

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Zip untuk .NET?**  
A: Kunjungi [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas.

**Q: Bisakah saya memperoleh lisensi sementara untuk Aspose.Zip untuk .NET?**  
A: Ya, jika Anda memerlukan lisensi sementara, Anda dapat memperoleh satu [here](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda kini telah mempelajari cara **add files to tar** dan mengompres hasilnya ke arsip TarZ menggunakan Aspose.Zip untuk .NET. Pendekatan ini memberi Anda paket yang bersih dan portabel yang dapat dengan mudah dipindahkan, disimpan, atau diproses lebih lanjut. Jangan ragu untuk menyesuaikan potongan kode ini untuk memproses direktori secara batch, mengintegrasikannya ke pipeline build, atau menggabungkannya dengan komponen Aspose lainnya untuk alur kerja dokumen yang lebih kaya.

---

**Terakhir Diperbarui:** 2026-05-30  
**Diuji Dengan:** Aspose.Zip for .NET 24.11  
**Penulis:** Aspose  


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
