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

# Tambahkan file ke tar dan kompres ke TarZ dengan Aspose.Zip untuk .NET

## Perkenalan

Jika Anda perlu **menambahkan file ke tar** dan kemudian mengompres arsip ke format TarZ, Aspose.Zip untuk .NET membuat seluruh proses menjadi mudah. Dalam tutorial ini kami akan membahas setiap langkah—dari menyiapkan proyek Anda hingga membuat arsip tar, menambahkan file, dan terakhir menyimpan file .tar.z yang terkompresi. Pada akhir tutorial Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam aplikasi .NET apa pun.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pembuatan tar?** Aspose.Zip untuk .NET
- **Berapa banyak baris kode?** Sekitar 15 baris (tidak termasuk komentar)
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+
- **sepertinya saya mengompres folder, bukan hanya file?** Ya – Anda dapat menambahkan seluruh direktori dengan loop.

## Apa itu **tambahkan file ke tar**?
Menambahkan file ke arsip tar menggabungkannya ke dalam satu wadah yang tidak terkompresi yang mempertahankan struktur direktori dan file metadata. Tar adalah format Unix klasik dan menjadi dasar bagi banyak alur kerja kompresi, termasuk format TarZ yang digunakan dalam panduan ini.

## Mengapa menambahkan file ke tar sebelum mengompresi ke TarZ?
- **Portabilitas** – Arsip tar dapat bekerja di berbagai platform tanpa harus khawatir tentang penanganan file individual.
- **Kecepatan** – Membuat wadah tar cepat; kompresi Z‑selanjutnya fokus pada pengurangan ukuran saja.
- **Kompatibilitas** – Banyak alat lama yang mengharapkan `.tar` sebelum menerapkan kompresi gaya gzip, yang tepatnya diberikan oleh `.tar.z`.

### Mengapa ini penting bagi pengembang .NET
Menggunakan wadah tar memungkinkan kode .NET Anda tetap sederhana dan deterministik. Anda dapat menghasilkan arsip di memori, mengalirkannya langsung ke respons, atau menyimpannya di disk tanpa harus membuang file zip sementara. Pola ini sangat berguna untuk pipeline build, agregasi log, atau ketika Anda perlu mengirimkan sekelompok file konfigurasi ke layanan berbasis Linux.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- **Aspose.Zip untuk .NET** terinstal. Unduh dari situs resmi[di sini](https://releases.aspose.com/zip/net/).
- Sebuah folder di mesin Anda yang berisi file yang ingin Anda arsipkan. Ganti path placeholder dengan direktori aktual Anda.

## Impor Namespace

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Tips pro:** Gunakan `Path.Combine` jika Anda perlu membangun path secara dinamis; ini menghindari hilangnya path pada OS yang berbeda.

## Panduan Langkah-demi-Langkah

### Langkah 1: Tentukan Direktori Dokumen Anda

```csharp
string dataDir = "Your Document Directory";
```

> **Mengapa langkah ini penting:** `dataDir` berfungsi sebagai lokasi dasar untuk setiap file yang akan Anda tambahkan. menyimpannya dalam satu variabel membuat kode mudah disimpan dan dapat digunakan kembali pada banyak arsip.

### Langkah 2: Buat Arsip Tar dan tambahkan file

#### 2.1: Membuat instance arsip Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` menjamin bahwa objek `TarArchive` dibuang dengan benar, melepaskan semua file handle atau buffer memori.

#### 2.2: Tambahkan file ke arsip

Di dalam blok `using`, tambahkan setiap file yang ingin Anda sertakan:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Anda dapat mengulang `CreateEntry` sebanyak file yang diperlukan, atau melakukan loop melalui sebuah direktori untuk menambahkannya secara terprogram. Misalnya, loop `foreach (var file in Directory.GetFiles(dataDir))` memungkinkan Anda menangani jumlah file yang tidak terbatas sambil mempertahankan jalur relatif mereka.

#### 2.3: Simpan file TarZ terkompresi

Setelah menambahkan semua entri, kompres arsip tar ke format `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

File `archive.tar.z` yang dihasilkan akan berada di folder yang sama dengan yang Anda temukan di `dataDir`. Sekarang Anda dapat mengirimkan paket terkompresi tunggal ini ke sistem mana pun yang mendukung TarZ.

## Masalah Umum dan Solusinya

| Edisi | Alasan | Perbaiki |
|-------|--------|-----|
| **File tidak ditemukan** | Path salah atau ekstensi file hilang | Pastikan `dataDir` diakhiri dengan pemisah path dan nama file sudah benar. |
| **Akses ditolak** | Izin tidak cukup pada folder target | Jalankan aplikasi dengan hak yang sesuai atau pilih direktori yang dapat ditulisi. |
| **File terkompresi lebih besar dari yang diharapkan** | File asli sudah terkompresi (misalnya gambar, video) | TarZ paling efektif pada file teks atau log; berkeinginan untuk membiarkan file yang sudah terkompresi apa adanya. |

### Kesalahan umum yang harus diwaspadai
- **Slash akhir hilang** – Jika `dataDir` tidak diakhiri dengan `\` atau `/`, penggabungan string akan menghasilkan jalur yang tidak valid.
- **Direktori besar** – Menambahkan ribuan file dapat mengonsumsi memori; berkepentingan untuk men‑stream entri atau menggunakan kelebihan `TarArchive` yang menulis langsung ke file stream.
- **Masalah pengkodean** – Nama file non‑ASCII mungkin memerlukan penanganan pengkodean secara eksplisit; Aspose.Zip mematuhi UTF‑8 secara default, tetapi pastikan pada target platform.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengompres seluruh folder dengan Aspose.Zip untuk .NET?**
J: Tentu saja. Gunakan loop `Directory.GetFiles` dan panggil `CreateEntry` untuk setiap file, sambil mempertahankan jalur relatif.

**Q: Apakah ada versi percobaan untuk Aspose.Zip untuk .NET?**
A: Ya, Anda dapat menjelajahi kemampuan Aspose.Zip untuk .NET dengan mengunduh percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Zip untuk .NET?**
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/zip/net/), memberikan wawasan detail tentang fitur dan penggunaan perpustakaan.

**Q: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Zip untuk .NET?**
A: Kunjungi [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) untuk meminta bantuan, berbagi pengalaman, dan terhubung dengan komunitas.

**Q: Bisakah saya mendapatkan lisensi sementara untuk Aspose.Zip untuk .NET?**
A: Ya, jika Anda membutuhkan lisensi sementara, Anda dapat memperolehnya [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Anda kini telah mempelajari cara **menambahkan file ke tar** dan mengompres hasilnya menjadi arsip TarZ menggunakan Aspose.Zip untuk .NET. Pendekatan ini memberi Anda paket yang bersih dan portabel yang dapat dengan mudah dipindahkan, disimpan, atau diproses lebih lanjut. Silakan sesuaikan potongan kode ini untuk memproses direktori batch, mengintegrasikannya ke dalam pipeline build, atau menggabungkannya dengan komponen Aspose lainnya untuk alur kerja dokumen yang lebih kaya.

---

**Terakhir Diperbarui:** 15-02-2026
**Diuji Dengan:** Aspose.Zip untuk .NET 24.11
**Penulis:** Beranggapan 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}