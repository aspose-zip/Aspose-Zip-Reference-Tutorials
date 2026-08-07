---
date: 2026-08-07
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน tar และสร้างไฟล์ TarBz2 ใน .NET ด้วย Aspose.Zip
  คู่มือขั้นตอนต่อขั้นตอนแสดงการสร้าง tar, การบีบอัด Bzip2 และเคล็ดลับการปฏิบัติที่ดีที่สุด
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: การบีบอัดเป็น TarBz2
og_description: เพิ่มไฟล์ลงใน tar และสร้างไฟล์ TarBz2 ใน .NET ด้วย Aspose.Zip คู่มือนี้ครอบคลุมการสร้าง
  tar, การบีบอัด Bzip2 และเคล็ดลับการแก้ไขปัญหา
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: เพิ่มไฟล์ลงใน tar และสร้างไฟล์ TarBz2 ด้วย Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: เพิ่มไฟล์ลงใน tar และสร้างไฟล์ TarBz2 ด้วย Aspose.Zip
url: /th/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และสร้างไฟล์ TarBz2 ด้วย Aspose.Zip

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเพิ่มไฟล์ลงใน tar** archive และแปลงให้เป็นไฟล์ **TarBz2** ขนาดกะทัดรัดโดยใช้ไลบรารี **Aspose.Zip** สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้สำรองข้อมูล, เผยแพร่แพ็กเกจการปรับใช้, หรือจำเป็นต้องมีบันเดิลขนาดเล็กสำหรับการแจกจ่าย ขั้นตอนต่อไปนี้จะพาคุณผ่านการเพิ่มไฟล์ลงในคอนเทนเนอร์ tar, ใช้การบีบอัด Bzip2, และสร้าง archive ที่พร้อมแชร์

## คำตอบสั้น ๆ
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip สำหรับ .NET  
- **ใช้เวลานานแค่ไหนในการทำตาม?** ประมาณ 5‑10 นาที  
- **ต้องการไลเซนส์หรือไม่?** ต้องมีไลเซนส์ชั่วคราวสำหรับการใช้งานจริง; มีรุ่นทดลองฟรีให้ใช้  
- **สามารถบีบอัดหลายไฟล์ได้หรือไม่?** ได้ – เพิ่มรายการเท่าใดก็ได้ลงใน archive tar  
- **รองรับ .NET 6+ หรือไม่?** แน่นอน, Aspose.Zip รองรับ .NET Framework และ .NET Core/5/6  

## TarBz2 archive คืออะไร?

ไฟล์ TarBz2 ผสานคอนเทนเนอร์ **tar** แบบดั้งเดิม (ซึ่งรักษาโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์) กับการบีบอัด **Bzip2**, ทำให้ได้แพ็กเกจ `.tar.bz2` ที่บีบอัดสูง รูปแบบนี้เป็นที่นิยมในระบบยูนิกซ์‑ลักษณะ เนื่องจากให้สมดุลที่ดีระหว่างอัตราการบีบอัดและความเร็วในการแตกไฟล์

## ทำไมต้องบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip?

Aspose.Zip สามารถสร้าง archive TarBz2 ได้ด้วย **สองคำสั่ง API** พร้อมจัดการสตรีมอย่างมีประสิทธิภาพ รองรับ **รูปแบบ archive และการบีบอัดกว่า 50+ แบบ**, ประมวลผลไฟล์ขนาดถึง **2 GB** โดยไม่ต้องโหลด archive ทั้งหมดเข้าสู่หน่วยความจำ, และทำงานบน Windows, Linux และ macOS .NET runtimes ไลบรารียังให้การควบคุมละเอียดต่อชื่อ entry, timestamp และระดับการบีบอัด ทำให้เหมาะสำหรับยูทิลิตี้คอนโซลและเว็บเซอร์วิส

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดแพ็กเกจล่าสุดจากเว็บไซต์ทางการ: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **โฟลเดอร์เอกสาร** – โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการทำ archive. ในตัวอย่างเราจะอ้างอิงด้วยตัวแปร `dataDir`.

> **เคล็ดลับ:** เก็บไฟล์ต้นฉบับไว้ในโฟลเดอร์เฉพาะเพื่อหลีกเลี่ยงการรวมไฟล์ที่ไม่ต้องการโดยบังเอิญ

## นำเข้า namespace

ก่อนอื่นให้นำเข้า namespace ที่จำเป็นเพื่อให้เข้าถึงคลาส Tar และ Bzip2 ของ Aspose.Zip

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

กำหนดพาธที่ชี้ไปยังโฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการทำ archive

```csharp
string dataDir = "Your Document Directory";
```

> แทนที่ `"Your Document Directory"` ด้วยพาธแบบ absolute หรือ relative ของโฟลเดอร์ต้นฉบับของคุณ

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน tar และสร้าง TarBz2 archive

`TarArchive` แทนคอนเทนเนอร์ tar ในหน่วยความจำที่สามารถเก็บหลาย entry ของไฟล์ได้  
`Bzip2Archive` บีบอัดสตรีมโดยใช้อัลกอริทึม Bzip2  
เมธอด `CreateEntry` จะเพิ่มไฟล์ลงใน archive tar เป็น entry ใหม่

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **เพิ่มไฟล์ลงใน tar** – คุณสามารถเรียกเมธอดนี้สำหรับทุกไฟล์ที่ต้องการใน archive  
- `bz2.SetSource(archive)` บอกให้ Bzip2 archive บีบอัดสตรีม tar ทั้งหมด  
- `bz2.Save(...)` เขียนไฟล์ **TarBz2** สุดท้ายลงดิสก์

**เคล็ดลับ:** หากต้อง **เพิ่มไฟล์ลงใน tar** เป็นกลุ่ม, เพียงทำซ้ำ `archive.CreateEntry` สำหรับแต่ละไฟล์ก่อนเรียก `bz2.Save`

## วิธีเพิ่มไฟล์ลงใน tar?

โหลดไดเรกทอรีต้นทาง, สร้างอินสแตนซ์ `TarArchive`, เพิ่มไฟล์แต่ละไฟล์ด้วย `CreateEntry`, จากนั้นห่อสตรีม tar ด้วย `Bzip2Archive` และเรียก `Save`. รูปแบบสองขั้นตอนนี้ช่วยให้เพิ่มไฟล์จำนวนใดก็ได้และสร้างไฟล์ `.tar.bz2` ในขั้นตอนเดียว, ไม่ต้องใช้ไฟล์ชั่วคราวหรือเครื่องมือภายนอก

## ปัญหาทั่วไป & วิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **File not found** error | พาธ `dataDir` ผิดหรือขาดนามสกุลไฟล์ | ตรวจสอบพาธเต็มและยืนยันว่าไฟล์มีอยู่ |
| **Empty archive** | ไม่มี entry ถูกเพิ่มก่อน `bz2.Save` | เพิ่มอย่างน้อยหนึ่งการเรียก `CreateEntry` |
| **Permission denied** | แอปไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่เขียนได้ |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับแอปพลิเคชัน .NET ทุกประเภทหรือไม่?**  
A: ใช่. รองรับ .NET Framework, .NET Core, .NET 5/6 และ runtime รุ่นใหม่ ๆ

**Q: สามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?**  
A: แน่นอน. เรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก archive

**Q: จะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: ดูเอกสารโดยละเอียดใน **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/)

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถ **ขอรับไลเซนส์ชั่วคราว** ได้ที่นี่: [request a temporary license](https://purchase.aspose.com/temporary-license/)

**Q: มีรุ่นทดลองฟรีหรือไม่?**  
A: มี, **ดาวน์โหลดรุ่นทดลองจาก Aspose releases**: [download a trial version](https://releases.aspose.com/)

## สรุป

คุณได้เรียนรู้ **วิธีเพิ่มไฟล์ลงใน tar**, บีบอัดสตรีม tar ด้วย Bzip2, และสร้าง **TarBz2** archive ด้วย Aspose.Zip สำหรับ .NET วิธีนี้เร็ว, ใช้หน่วยความจำน้อย, และทำงานได้บนทุกแพลตฟอร์ม .NET สมัยใหม่ อย่าลังเลทดลองกับชุดไฟล์ขนาดใหญ่, ชื่อ entry ที่กำหนดเอง, หรือผสานโค้ดนี้เข้ากับกระบวนการสำรองข้อมูลหรือการปรับใช้ของคุณ

หากพบอุปสรรคใด ๆ ชุมชน Aspose.Zip พร้อมให้ความช่วยเหลือ—แค่ไปที่ **ฟอรั่มสนับสนุน Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)

---

**Last Updated:** 2026-08-07  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง archive tar และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [เพิ่มไฟล์ลงใน tar และสร้าง archive tarxz ด้วย Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}