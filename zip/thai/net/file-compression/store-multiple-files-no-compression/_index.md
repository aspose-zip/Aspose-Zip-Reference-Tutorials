---
date: 2026-05-30
description: เรียนรู้วิธีสร้าง zip โดยไม่มี compression ใน .NET ด้วย Aspose.Zip สำหรับ
  .NET คู่มือนี้จะแสดงวิธี zip ไฟล์โดยไม่มี compression, เก็บไฟล์โดย uncompressed,
  และจัดการ archives อย่างมีประสิทธิภาพ
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: การเก็บหลายไฟล์โดยไม่มี Compression
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้าง zip โดยไม่มี compression ใน .NET ด้วย Aspose.Zip
url: /th/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง zip โดยไม่มีการบีบอัดใน .NET ด้วย Aspose.Zip

ในการพัฒนา .NET สมัยใหม่, **การสร้าง zip โดยไม่มีการบีบอัด** สามารถเพิ่มความเร็วในการบีบอัดไฟล์ได้อย่างมากและทำให้ขนาดไฟล์คาดเดาได้ เมื่อคุณต้องการ **บีบอัดไฟล์เป็น zip โดยไม่มีการบีบอัด** — ตัวอย่างเช่น เพื่อตรงตามกฎระเบียบ, เร่งกระบวนการต่อเนื่อง, หรือรับประกันว่าลำดับไบต์เดิมยังคงเหมือนเดิม — Aspose.Zip สำหรับ .NET ให้ API ที่สะอาดและตรงไปตรงมา ในบทเรียนนี้เราจะอธิบายขั้นตอนที่แน่นอนในการสร้างไฟล์ ZIP ที่ไม่มีการบีบอัด, เพิ่มไฟล์, และผสานโซลูชันเข้ากับแอปพลิเคชันของคุณ.

## คำตอบด่วน
- **อะไรคือ “uncompressed zip” ?** เป็นไฟล์ ZIP ที่แต่ละรายการถูกเก็บโดยใช้วิธี “store” ซึ่งทำให้ไบต์ของไฟล์ต้นฉบับไม่ถูกเปลี่ยนแปลง.  
- **ทำไมต้องหลีกเลี่ยงการบีบอัด?** เพื่อเร่งความเร็วในการบีบอัด, รักษาขนาดไฟล์ต้นฉบับสำหรับการประมวลผลต่อเนื่อง, หรือปฏิบัติตามข้อกำหนดที่ห้ามการเปลี่ยนแปลงข้อมูล.  
- **คลาส Aspose.Zip ใดที่จัดการเรื่องนี้?** `ArchiveEntrySettings` ร่วมกับ `StoreCompressionSettings`.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รุ่น .NET ที่รองรับ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10.  

## zip ที่ไม่มีการบีบอัดคืออะไร?
**Zip without compression** คือไฟล์ ZIP ที่แต่ละรายการไฟล์ใช้วิธี *store* หมายความว่าข้อมูลจะถูกคัดลอกอย่างตรงไปตรงมาไปยังไฟล์ ZIP โดยไม่มีการใช้อัลกอริทึมบีบอัดใด ๆ ผลลัพธ์คือไฟล์ ZIP ที่ขนาดโดยประมาณเป็นผลรวมของไฟล์ต้นฉบับบวกกับไบต์เพิ่มเล็กน้อยของโครงสร้าง ZIP.

## ทำไมต้องใช้ Aspose.Zip สำหรับไฟล์ zip ที่ไม่มีการบีบอัด?
Aspose.Zip ถูกปรับให้เหมาะสำหรับการบีบอัดประสิทธิภาพสูง, ช่วยให้คุณเก็บไฟล์ได้ทันทีโดยไม่มีภาระของอัลกอริทึมบีบอัด มันรับประกันความเข้ากันได้เต็มรูปแบบของ ZIP, ให้คุณผสมรายการที่เก็บและที่บีบอัดได้, และมี API ที่ง่ายซึ่งแยกโครงสร้าง ZIP ระดับต่ำ ทำให้การนำไปใช้เร็วและเชื่อถือได้.

## ข้อกำหนดเบื้องต้น
- **Aspose.Zip for .NET** – รวมไว้ในโครงการของคุณ ดู [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับขั้นตอนการติดตั้ง.  
- **.NET Development Environment** – Visual Studio, VS Code หรือ IDE ใด ๆ ที่คุณชอบ.  
- **Document Directory** – โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด (เช่น “Your Document Directory”).

## นำเข้า Namespaces
ก่อนเขียนโค้ดใด ๆ ให้ทำการนำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสของ Aspose ได้จากที่ไหน.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory
กำหนดเส้นทางที่ไฟล์ต้นทางของคุณอยู่ แทนที่ตัวแสดงตำแหน่งด้วยโฟลเดอร์จริงบนระบบของคุณ.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง Zip Archive โดยไม่มีการบีบอัด
หัวใจของบทเรียน – เราจะสร้างอินสแตนซ์ `Archive` ที่กำหนดค่าด้วย `StoreCompressionSettings`. `Archive` แทนคอนเทนเนอร์ ZIP ที่สามารถบรรจุหลายรายการได้. `StoreCompressionSettings` ระบุว่ารายการควรจะถูกเก็บโดยไม่มีการบีบอัด ซึ่งบอกให้ Aspose.Zip *store* (คือ ไม่บีบอัด) แต่ละรายการ.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **เคล็ดลับ:** หากคุณต้องการ **บันทึกไฟล์ลง zip** โดยบีบอัดบางไฟล์และปล่อยไฟล์อื่น ๆ ไม่บีบอัด, สร้างอินสแตนซ์ `ArchiveEntrySettings` แยกสำหรับแต่ละไฟล์และเพิ่มลงใน `Archive` เดียวกัน.

## วิธีสร้าง zip โดยไม่มีการบีบอัดใน .NET?
โหลดไฟล์ต้นทางของคุณ, สร้างอ็อบเจ็กต์ `Archive`, และเพิ่มแต่ละไฟล์โดยใช้ `ArchiveEntrySettings` พร้อมกับ `new StoreCompressionSettings()`. การดำเนินการทั้งหมดต้องใช้เพียงสามบรรทัดของโค้ดและทำงานในเวลาเชิงเส้นสัมพันธ์กับขนาดไฟล์รวม, ให้คุณได้รับประสบการณ์การบีบอัดที่เร็วที่สุด.

### ขั้นตอนการทำงานทีละขั้นตอน
1. **สร้าง archive** – สร้างอินสแตนซ์ `Archive` ด้วยสตรีมหรือเส้นทางไฟล์เป้าหมาย.  
2. **กำหนดค่าการตั้งค่ารายการ** – สำหรับแต่ละไฟล์, สร้างอ็อบเจ็กต์ `ArchiveEntrySettings` และกำหนด `new StoreCompressionSettings()` ให้กับ property `Compression` ของมัน.  
3. **เพิ่มรายการ** – เรียก `archive.Add(entrySettings)` สำหรับทุกไฟล์, แล้วสรุปด้วย `archive.Save()`.

## ปัญหาและวิธีแก้ไขทั่วไป
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **ไฟล์ไม่พบ** | เส้นทาง `dataDir` ไม่ถูกต้องหรือขาดส่วนขยายไฟล์. | ตรวจสอบเส้นทางและยืนยันว่าไฟล์มีอยู่ ใช้ `Path.Combine` เพื่อการต่อสตริงที่ปลอดภัยยิ่งขึ้น. |
| **การเข้าถึงถูกปฏิเสธ** | กระบวนการไม่มีสิทธิ์อ่านไฟล์ต้นทางหรือเขียนไฟล์ ZIP. | รันแอปพลิเคชันด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่มีสิทธิ์เขียน. |
| **ขนาดไฟล์ใน ZIP ไม่คาดคิด** | ไฟล์ ZIP ถูกสร้างด้วยการบีบอัดค่าเริ่มต้น. | ตรวจสอบว่าได้ส่ง `new StoreCompressionSettings()` ไปยัง `ArchiveEntrySettings`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถบีบอัดไฟล์ประเภทเฉพาะในขณะที่เก็บไฟล์อื่น ๆ ไว้โดยไม่บีบอัดได้หรือไม่?**  
A: ใช่, คุณสามารถสร้าง `ArchiveEntrySettings` ที่แตกต่างกันสำหรับแต่ละไฟล์และผสมรายการที่บีบอัดและไม่บีบอัดใน archive เดียวกัน.

**Q: Aspose.Zip สำหรับ .NET รองรับ .NET Core และ .NET 5/6 หรือไม่?**  
A: แน่นอน. ไลบรารีนี้รองรับ .NET Framework, .NET Core, .NET Standard, และเวอร์ชัน .NET ล่าสุด.

**Q: ฉันควรจัดการกับข้อยกเว้นระหว่างกระบวนการบีบอัดอย่างไร?**  
A: ห่อโค้ดการบีบอัดด้วยบล็อก `try‑catch` และบันทึกรายละเอียดของข้อยกเว้น ซึ่งจะทำให้การล้มเหลวเป็นไปอย่างราบรื่นและง่ายต่อการดีบัก.

**Q: Aspose.Zip รองรับการบีบอัดแบบหลายเธรดหรือไม่?**  
A: ใช่, คุณสามารถประมวลผลหลายไฟล์พร้อมกันและเพิ่มลงใน archive, แต่ต้องจำว่าอ็อบเจ็กต์ `Archive` เองไม่ปลอดภัยต่อการทำงานหลายเธรด; ควรซิงโครไนซ์การเข้าถึงเมื่อเพิ่มรายการ.

**Q: ฉันสามารถผสาน Aspose.Zip เข้ากับโครงการที่มีอยู่โดยไม่ต้องเปลี่ยนโค้ดมากหรือไม่?**  
A: แน่นอน. API ถูกออกแบบให้ใช้งานง่ายแบบ drop‑in. ดู [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับคำแนะนำการย้าย.

---

**อัปเดตล่าสุด:** 2026-05-30  
**ทดสอบด้วย:** Aspose.Zip for .NET (เวอร์ชันล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง Zip Archive .NET – การบีบอัดไฟล์ด้วย Aspose.Zip](/zip/net/file-compression/)
- [zip หลายไฟล์ c# – การบีบอัดที่ง่ายดายด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-compression/compress-multiple-files/)
- [สร้าง Zip โดยไม่มีการบีบอัด & แยกไฟล์ – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}