---
date: 2026-06-24
description: เรียนรู้วิธีบีบอัด LZMA ใน Aspose.Zip สำหรับ .NET เพื่อเพิ่มประสิทธิภาพการจัดเก็บและการถ่ายโอนข้อมูล
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: บีบอัดเป็น Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัด LZMA ใน Aspose.Zip สำหรับ .NET
url: /th/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัด LZMA ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีบีบอัด LZMA** ด้วย Aspose.Zip สำหรับ .NET ซึ่งเป็นทักษะสำคัญสำหรับการเพิ่มประสิทธิภาพการใช้พื้นที่จัดเก็บและการเพิ่มประสิทธิภาพการถ่ายโอนข้อมูล LZMA (อัลกอริธึม Lempel‑Ziv‑Markov chain) สามารถทำให้ไฟล์บีบอัดเล็กลงได้ถึง 70 % เมื่อเทียบกับ ZIP แบบดั้งเดิม พร้อมรักษาความเร็วในการแตกไฟล์ ทำให้เหมาะกับสถานการณ์ที่แบนด์วิธจำกัด

## คำตอบด่วน
- **ต้องใช้ไลบรารีอะไร?** Aspose.Zip for .NET  
- **คู่มือฉบับนี้ครอบคลุมอัลกอริธึมใด?** LZMA compression  
- **ต้องการไลเซนส์หรือไม่?** A temporary license is sufficient for testing; a full license is required for production.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** Typically under 10 minutes for a basic file.

## LZMA compression คืออะไร?

LZMA เป็นอัลกอริธึมการบีบอัดแบบ lossless ที่ให้สัดส่วนการบีบอัดสูงโดยใช้การบีบอัดแบบพจนานุกรมและ range encoding สามารถลดขนาดไฟล์ข้อความได้ 30‑70 % ในขณะที่ยังคงความเร็วในการแตกไฟล์เทียบเท่ากับ ZIP สำหรับชุดข้อมูลขนาดใหญ่ LZMA ช่วยลดค่าใช้จ่ายในการจัดเก็บและเร่งการถ่ายโอนเครือข่ายโดยไม่เสียความสมบูรณ์ของข้อมูล

## ทำไมต้องใช้ Aspose.Zip สำหรับ LZMA?

Aspose.Zip รองรับ **5 อัลกอริธึมการบีบอัด** (ZIP, Deflate, BZIP2, LZMA, และ ZSTD) และสามารถจัดการไฟล์บีบอัดขนาดถึง **4 GB** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไลบรารีสามารถประมวลผลเอกสารหลายร้อยหน้าในเวลา **น้อยกว่า 2 วินาที** บนเซิร์ฟเวอร์ทั่วไป ให้ทั้งประสิทธิภาพและความสามารถในการขยายตัว

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Zip for .NET: ตรวจสอบให้แน่ใจว่าได้ติดตั้งไลบรารี Aspose.Zip แล้ว คุณสามารถค้นหาเอกสารได้ [ที่นี่](https://reference.aspose.com/zip/net/).
- Document Directory: เลือกหรือสร้างโฟลเดอร์ที่มีไฟล์ที่ต้องการบีบอัด

## นำเข้า Namespaces

เพิ่ม Namespaces ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณเพื่อให้เข้าถึงฟังก์ชัน LZMA ของ Aspose.Zip ได้:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## วิธีตั้งค่าโฟลเดอร์ต้นทางสำหรับการบีบอัด?

ระบุโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบีบอัด การกำหนดโฟลเดอร์ต้นทางอย่างชัดเจนช่วยให้แน่ใจว่าเฉพาะไฟล์ที่ต้องการเท่านั้นจะถูกประมวลผล ลดความเสี่ยงของการรวมข้อมูลที่ไม่ต้องการ และทำให้การจัดการเส้นทางง่ายขึ้นเมื่อทำงานกับงานบีบอัดหลายงานในโครงการเดียว

```csharp
string dataDir = "Your Document Directory";
```

## วิธีบีบอัดไฟล์ด้วย LZMA?

`LzmaArchive` คือคลาสของ Aspose.Zip สำหรับสร้างและจัดการไฟล์บีบอัด LZMA

สร้างอินสแตนซ์ของ `LzmaArchive` ชี้ไปที่ไฟล์ต้นทาง แล้วเรียก `Save` เพื่อสร้างไฟล์ `.lzma` รูปแบบสองบรรทัดนี้ทำงานบีบอัดทั้งหมดโดยจัดการสตรีมภายในและผลิตไฟล์ที่กะทัดรัดพร้อมใช้สำหรับการแจกจ่ายหรือจัดเก็บ

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## วิธีตรวจสอบว่าการบีบอัดสำเร็จหรือไม่?

`Console.WriteLine` จะเขียนข้อความหนึ่งบรรทัดไปยังคอนโซลมาตรฐาน

หลังจากบันทึกไฟล์บีบอัดแล้ว ให้ใช้ `Console.WriteLine` แสดงข้อความยืนยันสั้น ๆ การตอบสนองทันทีนี้ช่วยให้นักพัฒนาตรวจสอบว่าขั้นตอนบีบอัดเสร็จสมบูรณ์โดยไม่มีข้อผิดพลาด ทำให้การดีบักในกระบวนการอัตโนมัติง่ายขึ้น และให้ข้อมูลสถานะที่ชัดเจนเมื่อรวมฟังก์ชันนี้เข้าสู่แอปพลิเคชันหรือสคริปต์ขนาดใหญ่

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## ปัญหาทั่วไปและวิธีแก้ไข

- **File not found** – ตรวจสอบให้แน่ใจว่า string ของพาธใช้ backslash คู่ (`\\`) หรือใช้ verbatim string (`@"C:\Path"`).  
- **Insufficient memory** – Aspose.Zip ทำการสตรีมข้อมูล แต่ไฟล์ขนาดใหญ่มากอาจต้องเพิ่มขีดจำกัดหน่วยความจำของกระบวนการ.  
- **License not applied** – ตรวจสอบว่าคุณได้เรียก `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` ก่อนทำงานใด ๆ ของ Aspose.Zip.

## คำถามที่พบบ่อย

**Q: สามารถบีบอัดหลายไฟล์ลงในไฟล์ LZMA เดียวได้หรือไม่?**  
A: ใช่. Call `archive.AddFile()` for each file before invoking `archive.Save()`.

**Q: มีวิธีตั้งค่าระดับการบีบอัดสำหรับ LZMA หรือไม่?**  
A: คลาส `LzmaArchive` ใช้ระดับการบีบอัดเริ่มต้นซึ่งให้ความสมดุลที่ดีระหว่างความเร็วและขนาด การตั้งค่าขั้นสูงสามารถทำได้ผ่าน `LzmaEncoder` หากต้องการควบคุมอย่างละเอียด.

**Q: ไฟล์ .lzma ที่สร้างขึ้นจะทำงานบนแพลตฟอร์มที่ไม่ใช่ Windows หรือไม่?**  
A: แน่นอน. รูปแบบ LZMA เป็นแพลตฟอร์มอิสระ ดังนั้นไฟล์บีบอัดสามารถแตกได้บนระบบปฏิบัติการใด ๆ ที่มีเครื่องมือรองรับ LZMA.

**Q: วิธีแตกไฟล์ LZMA ด้วย Aspose.Zip คืออะไร?**  
A: ใช้คอนสตรัคเตอร์ `LzmaArchive` พร้อมพาธของไฟล์บีบอัด แล้วเรียก `ExtractToDirectory()` เพื่อแตกเนื้อหาออกมา.

**Q: Aspose.Zip รองรับการบีบอัดแบบสตรีมเพื่อหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำหรือไม่?**  
A: ใช่. คุณสามารถทำงานกับสตรีมโดยส่งออบเจกต์ `Stream` ไปยังเมธอด `SetSource()` และ `Save()`.

---

**อัปเดตล่าสุด:** 2026-06-24  
**ทดสอบกับ:** Aspose.Zip for .NET (latest version at time of writing)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีบีบอัดไฟล์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-compression/compress-file/)
- [วิธีเปิด GZip Archive และเทคนิคการบีบอัดอื่น ๆ ด้วย Aspose.Zip สำหรับ .NET](/zip/net/other-compression-techniques/)
- [compress files c# – สร้างไฟล์ 7z ด้วย Aspose.Zip สำหรับ .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}