---
date: 2026-06-29
description: เรียนรู้วิธีบีบอัดโฟลเดอร์เป็น 7z ด้วย Aspose.Zip for .NET, ครอบคลุมวิธีการบีบอัด
  Seven Zip เช่น LZMA2, BZip2, และ Store. เหมาะสำหรับการสร้างไฟล์ 7z แบบโปรแกรม
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip กับวิธีการบีบอัดหลายรูปแบบ
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดโฟลเดอร์เป็น 7z – Aspose.Zip for .NET Tutorial
url: /th/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดโฟลเดอร์เป็น 7z – Aspose.Zip for .NET Tutorial

## บทนำ

หากคุณต้องการ **compress folder to 7z** archives อย่างโปรแกรมในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว Aspose.Zip for .NET ทำให้การสร้าง Seven Zip archives ด้วยอัลกอริทึมการบีบอัดที่รองรับเป็นเรื่องง่าย ไม่ว่าคุณจะต้องการบรรจุไดเรกทอรีทั้งหมดเพื่อแจกจ่ายหรือเพียงต้องการโซลูชัน **seven zip archive .net** ที่เชื่อถือได้ ในคู่มือนี้เราจะอธิบายวิธีการบีบอัดสามวิธีที่นิยม—LZMA2, BZip2, และ Store (ไม่มีการบีบอัด)—และแสดงให้คุณเห็นว่าการสร้างไฟล์ 7z ทำได้อย่างไรด้วยไม่กี่บรรทัดของโค้ด C#

## คำตอบสั้น
- **What library should I use?** Aspose.Zip for .NET provides the most complete set of Seven Zip features.  
- **Which compression method gives the best ratio?** LZMA2 usually delivers the highest compression for mixed data.  
- **Can I create a 7z without any compression?** Yes—use the Store (no compression) method.  
- **Do I need a license for development?** A free trial is available; a license is required for production use.  
- **Is this compatible with .NET 6/7?** Absolutely—Aspose.Zip supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.

## วิธีการบีบอัด Seven Zip มีอะไรบ้าง?

Seven Zip รองรับอัลกอริทึมหลายแบบ ซึ่งแต่ละแบบถูกปรับให้เหมาะกับสถานการณ์ต่าง ๆ **LZMA2** ให้สัดส่วนการบีบอัดสูงสุด (มักเล็กกว่า BZip2 ถึง 30‑40 %) **BZip2** ให้การบีบอัดที่มั่นคงพร้อมการสนับสนุนเครื่องมือรุ่นเก่าที่กว้างขวาง, และ **Store** เพียงแค่เก็บไฟล์โดยไม่บีบอัด, รักษาเวลาแก้ไขต้นฉบับอย่างสมบูรณ์

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานของ C# และ Visual Studio.  
- ไลบรารี Aspose.Zip for .NET ติดตั้งแล้ว ดาวน์โหลดได้จากหน้าอย่างเป็นทางการ **[here](https://releases.aspose.com/zip/net/)**.  
- โฟลเดอร์ (`dataDir`) ที่มีไฟล์ที่คุณต้องการบีบอัด.

## นำเข้า Namespaces

ขั้นแรก, เพิ่ม namespaces ที่จำเป็นลงในไฟล์ C# ของคุณ:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

คลาสเหล่านี้ให้คุณเข้าถึงการตั้งค่าการบีบอัดและการจัดการ archive.

## การบีบอัด LZMA2 – วิธีสร้าง 7z ด้วยอัตราส่วนสูงสุด

`Archive` class แสดงถึง archive 7z ที่สามารถบรรจุไฟล์หลายไฟล์ได้.  
อัลกอริทึม LZMA2 ให้สัดส่วนการบีบอัดสูงสุดในบรรดาวิธีที่รองรับ. มันทำงานโดยแบ่งอินพุตเป็นบล็อกและใช้การบีบอัดแบบพจนานุกรมที่ซับซ้อน. ใน Aspose.Zip คุณตั้งค่า `CompressionMethod` เป็น `CompressionMethod.Lzma2` บนวัตถุ `Archive` ก่อนเพิ่มไฟล์.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2 ทำงานได้ดีที่สุดเมื่อไฟล์ต้นทางมีขนาดใหญ่กว่า 1 MB. สำหรับไฟล์ขนาดเล็กจำนวนมาก, BZip2 อาจเร็วกว่า.

## การบีบอัด BZip2 – ตัวเลือกที่สมดุล

`Archive` class แสดงถึง archive 7z ที่สามารถบรรจุไฟล์หลายไฟล์ได้.  
BZip2 ให้การบีบอัดที่มั่นคงพร้อมความเข้ากันได้ดีกับเครื่องมือรุ่นเก่า. มันใช้การแปลง Burrows‑Wheeler และการเข้ารหัส Huffman เพื่อลดขนาด. ใน Aspose.Zip คุณเลือก `CompressionMethod.BZip2` เมื่อตั้งค่าอินสแตนซ์ `Archive`, ซึ่งทำให้สมดุลระหว่างความเร็วและสัดส่วนการบีบอัดสำหรับไฟล์ข้อความและไบนารีส่วนใหญ่.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 ให้การบีบอัดที่มั่นคงพร้อมความเร็วที่สมเหตุสมผล, ทำให้เป็นตัวเลือกสำรองที่ดีเมื่อ LZMA2 ไม่ได้รับการสนับสนุนจากสภาพแวดล้อมเป้าหมาย.

## Store (ไม่มีการบีบอัด) – เมื่อขนาดไม่สำคัญ

`Archive` class แสดงถึง archive 7z ที่สามารถบรรจุไฟล์หลายไฟล์ได้.  
วิธี Store สร้าง archive โดยไม่บีบอัดข้อมูล. มันเพียงคัดลอกไฟล์ต้นฉบับเข้าไปในคอนเทนเนอร์ 7z, รักษา timestamp และโครงสร้างไดเรกทอรี. เพื่อใช้ใน Aspose.Zip ให้ตั้งค่า `CompressionMethod.Store` บน `Archive` ก่อนเพิ่มไฟล์ที่ต้องการบรรจุ.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

ใช้วิธี Store หากคุณต้องการบรรจุไฟล์ร่วมกันโดยไม่เปลี่ยนขนาดของมัน—เหมาะสำหรับการรักษา timestamp ดั้งเดิมหรือเมื่อ archive จะถูกแตกออกแบบทันที.

## ฉันจะเพิ่มไฟล์ลงใน 7z อย่างไร?

เพิ่มไฟล์ลงใน archive 7z โดยสร้างอินสแตนซ์ `Archive`, ตั้งค่า `CompressionMethod` ที่ต้องการ, แล้วเรียก `AddAllFiles(dataDir)`. วิธีนี้สแกนโฟลเดอร์ที่ระบุแบบเรียกซ้ำ, รักษาโครงสร้างไดเรกทอรีภายใน archive. วิธีนี้ทำให้คุณ **compress folder to 7z** ด้วยบรรทัดโค้ดเดียวหลังจากตั้งค่าเริ่มต้น.

## กรณีการใช้งานทั่วไป

| สถานการณ์ | วิธีที่แนะนำ |
|----------|--------------------|
| แจกจ่ายตัวติดตั้งขนาดใหญ่ | LZMA2 |
| แชร์บันทึกด้วยเครื่องมือรุ่นเก่า | BZip2 |
| บรรจุไฟล์เพื่อการสกัดที่รวดเร็ว | Store (no compression) |
| ต้องการ **compress folder to 7z** แบบเรียลไทม์ในเว็บเซอร์วิส | LZMA2 (for best ratio) |

## การแก้ไขปัญหาและเคล็ดลับ

- **Missing files in the archive?** ตรวจสอบว่า `dataDir` ชี้ไปยังไดเรกทอรีที่ถูกต้องและกระบวนการมีสิทธิ์อ่าน.  
- **Archive fails to open on older 7‑Zip versions?** ใช้ BZip2 หรือ Store แทน, เนื่องจาก LZMA2 อาจต้องการไลบรารีการแตกที่ใหม่กว่า.  
- **Performance bottleneck?** สำหรับชุดข้อมูลขนาดใหญ่, พิจารณา stream archive แทนการโหลดทุกรายการเข้าสู่หน่วยความจำ.

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Zip for .NET with any type of file?**  
A: ใช่, Aspose.Zip รองรับรูปแบบไฟล์หลากหลาย, ทำให้คุณสามารถบีบอัดและแตกไฟล์ได้เกือบทุกประเภท.

**Q: Is a free trial available for Aspose.Zip for .NET?**  
A: ใช่, คุณสามารถรับการทดลองใช้ฟรี **[here](https://releases.aspose.com/)**.

**Q: Where can I find documentation for Aspose.Zip for .NET?**  
A: เอกสารอ้างอิง API เต็มรูปแบบมีให้ **[here](https://reference.aspose.com/zip/net/)**.

**Q: How can I get temporary licenses for Aspose.Zip for .NET?**  
A: สามารถขอรับลิขสิทธิ์ชั่วคราวได้ **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I get support for Aspose.Zip for .NET?**  
A: คุณสามารถขอรับการสนับสนุนได้ที่ **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

**อัปเดตล่าสุด:** 2026-06-29  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.12  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [บีบอัดไฟล์ c# – สร้าง 7z archive ด้วย Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [วิธีการบีบอัดโฟลเดอร์ด้วย Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [วิธีบีบอัด LZMA ใน Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}