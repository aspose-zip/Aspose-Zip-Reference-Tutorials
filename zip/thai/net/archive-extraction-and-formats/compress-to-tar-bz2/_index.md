---
date: 2026-10-31
description: เรียนรู้วิธีสร้าง tar archive และบีบอัดเป็นไฟล์ TarBz2 ใน .NET ด้วย Aspose.Zip
  คู่มือขั้นตอนแสดงการสร้าง tar, การบีบอัด Bzip2 และเคล็ดลับการปฏิบัติที่ดีที่สุด
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: การบีบอัดเป็น TarBz2
og_description: เรียนรู้วิธีสร้าง tar archive และบีบอัดเป็นไฟล์ TarBz2 ด้วย Aspose.Zip
  สำหรับ .NET คู่มือขั้นตอนครอบคลุมการสร้าง tar, การบีบอัด Bzip2 และเคล็ดลับการปฏิบัติที่ดีที่สุด
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: สร้าง tar archive และบีบอัดเป็น TarBz2 ด้วย .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: วิธีสร้าง tar archive และบีบอัดเป็น TarBz2 ด้วย .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ tar archive และบีบอัดเป็น TarBz2 ด้วย .NET

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างไฟล์ tar archive** และจากนั้นบีบอัดเป็นแพ็กเกจ **TarBz2** ที่กะทัดรัดโดยใช้ไลบรารี **Aspose.Zip** สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้สำรองข้อมูล, เตรียมบันเดิลการปรับใช้, หรือจำเป็นต้องใช้รูปแบบการแจกจ่ายที่มีน้ำหนักเบา ขั้นตอนต่อไปนี้จะพาคุณผ่านการเพิ่มไฟล์ลงในคอนเทนเนอร์ tar, ใช้การบีบอัด Bzip2, และเขียนไฟล์ `.tar.bz2` สุดท้าย

## คำตอบสั้น
- **ไลบรารีที่ควรใช้คืออะไร?** Aspose.Zip for .NET  
- **การดำเนินการใช้เวลานานเท่าไหร่?** About 5‑10 minutes  
- **ฉันต้องการไลเซนส์หรือไม่?** A temporary license is required for production; a free trial is available  
- **ฉันสามารถบีบอัดหลายไฟล์ได้หรือไม่?** Yes – add as many entries as you like to the tar archive  
- **เข้ากันได้กับ .NET 6+ หรือไม่?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## TarBz2 archive คืออะไร?
ไฟล์ TarBz2 ผสานคอนเทนเนอร์ **tar** แบบดั้งเดิม (ซึ่งรักษาโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์) กับการบีบอัด **Bzip2** ทำให้ได้แพ็กเกจ `.tar.bz2` ที่บีบอัดสูง รูปแบบนี้เป็นที่นิยมในระบบแบบ Unix เนื่องจากให้สมดุลที่ดีระหว่างอัตราการบีบอัดและความเร็วในการแตกไฟล์

## ทำไมต้องบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip?
Aspose.Zip สามารถสร้าง TarBz2 archive ได้ใน **สองการเรียก API** พร้อมการจัดการสตรีมอย่างมีประสิทธิภาพ รองรับ **รูปแบบ archive และการบีบอัดกว่า 50+** ประมวลผลไฟล์ขนาดถึง **2 GB** โดยไม่ต้องโหลด archive ทั้งหมดเข้าสู่หน่วยความจำ และทำงานบน Windows, Linux และ macOS .NET runtimes ไลบรารียังให้การควบคุมระดับละเอียดต่อชื่อ entry, timestamp และระดับการบีบอัด ทำให้เหมาะสำหรับยูทิลิตี้คอนโซลและบริการเว็บ

## ข้อกำหนดเบื้องต้น
- **Aspose.Zip for .NET** – ดาวน์โหลดแพคเกจล่าสุดจากเว็บไซต์ทางการ: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบันทึกเป็น archive ในตัวอย่างเราอ้างอิงด้วยตัวแปร `dataDir`.

> **เคล็ดลับ:** เก็บไฟล์ต้นฉบับของคุณในโฟลเดอร์เฉพาะเพื่อหลีกเลี่ยงการรวมไฟล์ที่ไม่ต้องการโดยบังเอิญ

## นำเข้า namespace
ก่อนอื่นให้นำเข้า namespace ที่จำเป็นเพื่อให้คุณสามารถเข้าถึงคลาส Tar และ Bzip2 ของ Aspose.Zip

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: ตั้งค่า document directory
กำหนดพาธที่ชี้ไปยังโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบันทึกเป็น archive

```csharp
string dataDir = "Your Document Directory";
```

> แทนที่ `"Your Document Directory"` ด้วยพาธแบบ absolute หรือ relative ไปยังโฟลเดอร์ต้นฉบับของคุณ

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน tar และสร้าง TarBz2 archive
คลาส `TarArchive` แทนคอนเทนเนอร์ tar ในหน่วยความจำ, ส่วน `Bzip2Archive` จะบีบอัดสตรีมโดยใช้อัลกอริทึม Bzip2.  
เมธอด `CreateEntry` เพิ่มไฟล์ entry ใหม่ลงใน tar archive.

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

- `CreateEntry` **adds files to tar** – คุณสามารถเรียกเมธอดนี้สำหรับทุกไฟล์ที่ต้องการใน archive.  
- `bz2.SetSource(archive)` บอกให้ Bzip2 archive บีบอัดสตรีม tar ทั้งหมด.  
- `bz2.Save(...)` เขียนไฟล์ **TarBz2** สุดท้ายลงดิสก์.

**เคล็ดลับ:** เพื่อ **add files to tar** เป็นกลุ่ม, เพียงทำซ้ำ `archive.CreateEntry` สำหรับแต่ละไฟล์ก่อนเรียก `bz2.Save`.

## วิธีเพิ่มไฟล์ลงใน tar?
โหลดไดเรกทอรีต้นฉบับ, สร้างอินสแตนซ์ `TarArchive`, เพิ่มไฟล์แต่ละไฟล์ด้วย `CreateEntry`, จากนั้นห่อสตรีม tar ด้วย `Bzip2Archive` และเรียก `Save`. รูปแบบสองขั้นตอนนี้เพิ่มไฟล์จำนวนใดก็ได้และสร้างไฟล์ `.tar.bz2` ในขั้นตอนเดียวอย่างต่อเนื่อง, ไม่ต้องใช้ไฟล์ชั่วคราวหรือเครื่องมือภายนอก.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **File not found** error | พาธ `dataDir` ผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบพาธเต็มและให้แน่ใจว่าไฟล์มีอยู่. |
| **Empty archive** | ไม่มี entry ถูกเพิ่มก่อน `bz2.Save` | เพิ่มอย่างน้อยหนึ่งการเรียก `CreateEntry`. |
| **Permission denied** | แอปพลิเคชันไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | เรียกใช้แอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่สามารถเขียนได้. |

## คำถามที่พบบ่อย
**Q: Aspose.Zip รองรับกับแอปพลิเคชัน .NET ทั้งหมดหรือไม่?**  
A: ใช่. มันทำงานกับ .NET Framework, .NET Core, .NET 5/6 และ runtime รุ่นใหม่

**Q: ฉันสามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?**  
A: แน่นอน. เรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก archive.

**Q: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารโดยละเอียดมีใน **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถ **request a temporary license** ที่นี่: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: มีรุ่นทดลองใช้งานฟรีหรือไม่?**  
A: มี, **download a trial version from Aspose releases**: [download a trial version](https://releases.aspose.com/).

คุณยังสามารถ [download a      trial version](https://releases.aspose.com/).

## สรุป
ตอนนี้คุณรู้แล้ว **วิธีสร้าง tar archive**, บีบอัดสตรีม tar ด้วย Bzip2, และสร้าง **TarBz2** archive โดยใช้ Aspose.Zip สำหรับ .NET วิธีนี้เร็ว, ใช้หน่วยความจำน้อยและทำงานได้บนแพลตฟอร์ม .NET สมัยใหม่ทั้งหมด อย่าลังเลที่จะทดลองกับชุดไฟล์ขนาดใหญ่, ชื่อ entry ที่กำหนดเอง, หรือรวมโค้ดนี้เข้าไปในกระบวนการสำรองข้อมูลหรือการปรับใช้ของคุณ

หากคุณพบปัญหาใด ๆ ชุมชน Aspose.Zip พร้อมช่วยเหลือ—เพียงไปที่ **Aspose.Zip support forum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

**อัปเดตล่าสุด:** 2026-10-31  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

## บทแนะนำที่เกี่ยวข้อง
- [สร้าง tar archive และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [เพิ่มไฟล์ลงใน tar และสร้าง tarxz archive ด้วย Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}