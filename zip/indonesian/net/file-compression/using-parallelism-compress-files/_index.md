---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip multiple files c# dengan Aspose.Zip Parallel Compression

## Pendahuluan

Jika Anda perlu **zip multiple files c#** dengan cepat dan efisien, memanfaatkan pemrosesan paralel adalah cara yang tepat. Dalam aplikasi .NET modern, membuat arsip zip besar dapat menjadi bottleneck—terutama saat menangani puluhan atau ratusan file. Aspose.Zip untuk .NET menghilangkan masalah tersebut dengan menawarkan **parallel zip compression** bawaan yang menyebarkan pekerjaan ke semua core CPU yang tersedia. Dalam tutorial ini kami akan membahas seluruh proses: mulai dari menyiapkan lingkungan hingga menyimpan arsip zip dengan paralelisme diaktifkan, dan kami juga akan menunjukkan cara **create zip archive c#** yang berjalan lancar di .NET Core.

## Jawaban Cepat
- **Apa itu parallel zip compression?** Ia mengompres beberapa file secara bersamaan, menggunakan banyak thread untuk mengurangi waktu pemrosesan keseluruhan.  
- **Perpustakaan .NET mana yang mendukungnya?** Aspose.Zip untuk .NET menyediakan API sederhana untuk kompresi paralel.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya—lisensi penuh diperlukan; lisensi sementara tersedia untuk pengujian.  
- **Bisakah saya menambahkan file ke zip secara dinamis?** Tentu—gunakan `Archive.CreateEntry` untuk setiap file yang ingin Anda sertakan.  
- **Apakah kompatibel dengan .NET 6/7?** Ya, API berfungsi di semua runtime .NET modern.

## Apa itu zip multiple files c#?
`zip multiple files c#` mengacu pada praktik membuat satu arsip ZIP yang berisi banyak file individual, menggunakan kode C#. Ketika Anda menggabungkannya dengan **parallel zip compression**, perpustakaan memproses setiap file pada thread terpisah, secara dramatis mengurangi waktu yang dibutuhkan untuk menghasilkan arsip akhir.

## Mengapa menggunakan Aspose.Zip untuk kompresi paralel?
Kompresi paralel memungkinkan Anda memanfaatkan setiap core mesin multi‑processor, sering kali memberikan throughput **2‑3× lebih cepat** dibandingkan pendekatan satu‑thread. Ini juga berskala dengan baik: menambah lebih banyak file tidak meningkatkan waktu secara linier, dan API menangani manajemen thread untuk Anda, sehingga Anda dapat fokus pada logika bisnis.  

- **Kecepatan:** Memanfaatkan semua prosesor logis, memotong waktu pembuatan zip hingga 70 % pada beban kerja tipikal.  
- **Skalabilitas:** Menangani batch 500+ file tanpa peningkatan proporsional pada waktu CPU.  
- **Kesederhanaan:** Metode tingkat tinggi menyembunyikan kompleksitas `System.Threading.Tasks`.  
- **Fleksibilitas:** Mendukung .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, dan .NET 5–10, termasuk .NET 6/7 untuk layanan cloud‑native.

## Prasyarat

- Pengetahuan dasar tentang C# dan pengembangan .NET.  
- Aspose.Zip untuk .NET terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/zip/net/)**.  
- Lisensi sementara atau penuh (lisensi sementara sudah cukup untuk tutorial ini).  

## Impor Namespace

Namespace `Aspose.Zip` berisi semua tipe yang Anda perlukan untuk bekerja dengan arsip ZIP.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Pertama, bawa namespace yang diperlukan ke file C# Anda agar kompiler mengetahui di mana menemukan kelas yang akan Anda gunakan.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

Tentukan folder yang berisi file yang ingin Anda kompres. Jalur ini disimpan dalam variabel `dataDir`, yang dapat Anda arahkan ke lokasi mana saja di disk.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Langkah 2: Inisialisasi Proses Kompresi

Buka file ZIP baru untuk penulisan. Pernyataan `using` memastikan aliran file dibuang dengan benar setelah operasi selesai, mencegah kebocoran handle file.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Langkah 3: Baca dan Kompres File Secara Paralel

`Parallel.ForEach` mengeksekusi loop foreach di mana iterasi dapat berjalan secara bersamaan pada banyak thread.  

Buka setiap file sumber yang ingin Anda tambahkan ke arsip. Dalam contoh ini kami bekerja dengan dua teks klasik, tetapi Anda dapat **add files to zip** untuk jumlah dokumen berapa pun. Loop `Parallel.ForEach` secara otomatis mendistribusikan pekerjaan ke thread.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Langkah 4: Buat Entri Arsip

Kelas `Archive` adalah objek tingkat‑atas Aspose.Zip yang mewakili kontainer ZIP yang sedang Anda bangun.  

`CreateEntry` membuat entri baru dalam arsip ZIP untuk file yang ditentukan. Setiap pemanggilan `CreateEntry` menambahkan entri file baru ke arsip.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Langkah 5: Tentukan Kriteria Paralelisme

`ParallelOptions` adalah tipe .NET yang mengontrol bagaimana loop paralel dijalankan.  

Konfigurasikan kompresi agar berjalan paralel dengan mengatur `ParallelOptions`. Flag `ParallelCompressInMemory` memberi tahu Aspose.Zip untuk selalu menggunakan pemrosesan paralel, sementara `MaxDegreeOfParallelism` memungkinkan Anda membatasi jumlah thread bersamaan.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Langkah 6: Simpan Arsip yang Dikompresi

Akhirnya, tulis arsip ke disk dengan opsi yang diinginkan, termasuk encoding, komentar, dan pengaturan paralel yang telah didefinisikan sebelumnya. Metode `Save` menyelesaikan file ZIP.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Jika Anda mengompres file yang sangat besar, pertimbangkan untuk mengatur `ParallelOptions.MaxDegreeOfParallelism` ke nilai yang lebih rendah daripada jumlah prosesor logis. Ini membantu menjaga server Anda tetap responsif di bawah beban.

### Kasus Penggunaan Umum

- **Pelaporan batch:** Menghasilkan bundel zip laporan CSV harian untuk sistem hilir.  
- **Pengarsipan dokumen:** Menyimpan koleksi besar PDF, gambar, atau log dalam satu arsip untuk pencadangan.  
- **API ekspor data:** Mengembalikan file zip yang berisi beberapa file data ke klien dalam satu respons HTTP.  

## Masalah Umum & Tips

- **Tekanan memori pada file besar:** Alih-alih memuat seluruh file ke memori, alirkan file dalam potongan atau gunakan mode `ParallelCompressInMemory` secara selektif.  
- **Keamanan thread:** API Aspose.Zip aman untuk thread dalam mode paralel, tetapi hindari memodifikasi `FileStream` yang sama dari luar perpustakaan saat kompresi sedang berjalan.  
- **Penyesuaian performa:** Bereksperimenlah dengan `ParallelOptions.MaxDegreeOfParallelism` jika Anda perlu membatasi penggunaan CPU pada server bersama.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Zip untuk .NET bersama dengan perpustakaan kompresi lain?**  
A: Ya, Aspose.Zip dapat berdampingan dengan perpustakaan .NET lainnya; cukup pastikan namespace mereka tetap terpisah.

**Q: Apakah lisensi sementara tersedia untuk tujuan pengujian?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk pengujian dari **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q: Di mana saya dapat meminta bantuan jika mengalami masalah?**  
A: Kunjungi **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** untuk dukungan komunitas dan diskusi.

**Q: Di mana saya dapat menemukan contoh kode lebih banyak dan dokumentasi API detail?**  
A: Jelajahi **[dokumentasi Aspose.Zip](https://reference.aspose.com/zip/net/)** untuk contoh komprehensif.

**Q: Bagaimana cara membeli lisensi penuh untuk Aspose.Zip?**  
A: Anda dapat membeli Aspose.Zip untuk .NET **[di sini](https://purchase.aspose.com/buy)**.

---

**Terakhir Diperbarui:** 2026-06-09  
**Diuji Dengan:** Aspose.Zip 24.11 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [zip multiple files c# – Kompresi Tanpa Usaha dengan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-multiple-files/)
- [Cara Membuat Arsip Zip dan Menambahkan File ke Zip Menggunakan Aspose.Zip untuk .NET](/zip/net/file-compression/compress-single-file/)
- [Kompres Banyak File dengan Enkripsi di Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}