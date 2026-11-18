---
date: 2026-11-18
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน tar และบีบอัดไฟล์เป็น archive tarxz บน .NET
  ด้วย Aspose.Zip. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนเพื่อการจัดเก็บและการส่งข้อมูลที่มีประสิทธิภาพ
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: การบีบอัดเป็น TarXz
og_description: เพิ่มไฟล์ลงใน tar และสร้าง archive tarxz ด้วย Aspose.Zip. เรียนรู้วิธีบีบอัดไฟล์เป็น
  TarXz บน .NET อย่างรวดเร็ว ด้วยประสิทธิภาพการบีบอัดสูงและความเข้ากันได้ข้ามแพลตฟอร์ม
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: เพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarxz ด้วย Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: เพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarxz ด้วย Aspose.Zip
url: /th/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarxz ด้วย Aspose.Zip

## บทนำ

หากคุณต้องการ **add files to tar** แล้ว **create a tarxz archive .net** Aspose.Zip สำหรับ .NET ทำให้กระบวนการนี้ง่ายและเชื่อถือได้ ไม่ว่าคุณจะบรรจุ log, ไฟล์การกำหนดค่า หรือทรัพยากรอื่น ๆ เพื่อการจัดเก็บหรือการส่งต่อ การบีบอัดเป็นรูปแบบ TarXz ให้สัดส่วนการบีบอัดสูงในขณะที่คงโครงสร้าง tar ที่คุ้นเคยไว้ ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนอย่างละเอียดพร้อมตัวอย่างโค้ด เพื่อให้คุณสามารถผสานการสร้าง tarxz เข้าไปในแอปพลิเคชัน .NET ของคุณได้อย่างมั่นใจ เมื่อเสร็จสิ้นคุณจะเข้าใจว่าทำไม “add files to tar” ถึงเป็นขั้นตอนแรกสู่แพ็กเกจที่กะทัดรัดและข้ามแพลตฟอร์ม

## คำตอบสั้น
- **คลาสหลักคืออะไร?** `TarArchive` from `Aspose.Zip.Tar`
- **ฉันจะบีบอัดเป็น tarxz อย่างไร?** Call `SaveXzCompressed` after adding entries
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **ต้องใช้ไลเซนส์หรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์ Aspose.Zip ที่ถูกต้องสำหรับการใช้งานในสภาพแวดล้อมการผลิต
- **เวลาในการทำงานประมาณเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการสร้าง archive เบื้องต้น

## TarXz archive คืออะไร?

TarXz archive ผสานคอนเทนเนอร์ `tar` แบบดั้งเดิมของ Unix กับการบีบอัด XZ ส่วน tar จะรวมหลายไฟล์เป็นสตรีมเดียว ในขณะที่ XZ ให้การบีบอัดที่แข็งแรงและไม่มีการสูญเสียรูปแบบนี้เป็นที่นิยมสำหรับการแจกจ่ายซอร์สโค้ด, การสำรองข้อมูล, และชุดข้อมูลขนาดใหญ่ เนื่องจากรักษาโครงสร้างไดเรกทอรีและทำให้ขนาดไฟล์เล็กลงกว่าการใช้ tar หรือ zip ธรรมดา

## ทำไมต้องสร้าง tarxz archive .net ด้วย Aspose.Zip?

การสร้าง TarXz archive ด้วย Aspose.Zip ให้วิธีแก้ไขที่รวดเร็วและทำในขั้นตอนเดียวโดยไม่ต้องใช้เครื่องมือภายนอก ไฟล์จะเล็กลง 30‑50 % เมื่อเทียบกับ gzip และคุณสามารถจัดการกับรูปแบบ archive มากกว่า 20 รูปแบบโดยตรงใน .NET ไลบรารีสามารถประมวลผล archive ขนาดใหญ่โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้เหมาะสำหรับบริการคลาวด์และ pipeline CI อีกทั้งยังรองรับรูปแบบอินพุตและเอาต์พุตมากกว่า 50 รูปแบบ

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** ติดตั้งแล้ว (ดาวน์โหลดจาก [Aspose.Zip documentation](https://reference.aspose.com/zip/net/))  
- โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบีบอัด ในตัวอย่างด้านล่าง โฟลเดอร์นี้อ้างอิงโดยตัวแปร `dataDir`  
- ไลเซนส์ Aspose.Zip ที่ถูกต้อง (ไม่บังคับสำหรับการประเมินผล, จำเป็นสำหรับการใช้งานจริง)

## นำเข้า namespace

คุณเพียงแค่ต้องนำเข้า namespace ที่เปิดเผยฟังก์ชัน TarXz ไม่จำเป็นต้องใช้แพ็กเกจเพิ่มเติมใด ๆ นอกเหนือจากไลบรารีหลักของ Aspose.Zip

## วิธีเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip

`TarArchive` คือคลาสที่แทนคอนเทนเนอร์ tar ใน Aspose.Zip คุณสามารถเพิ่มไฟล์ลงใน tar archive ได้โดยสร้างอินสแตนซ์ของ `TarArchive` แล้วเรียกเมธอด `AddEntry` สำหรับแต่ละไฟล์ที่ต้องการรวม โดยระบุเส้นทางต้นทางและชื่อ entry ที่เป็นตัวเลือก archive จะสร้างคอนเทนเนอร์ tar ในหน่วยความจำพร้อมสำหรับการบีบอัด XZ ต่อไป

```csharp
using System;
using Aspose.Zip.Tar;
```

> **เคล็ดลับ:** คำสั่ง `using` ทำให้แน่ใจว่า archive ถูกทำลายอย่างถูกต้อง ปล่อยทรัพยากรที่ไม่ได้จัดการออก

### ขั้นตอนที่ 1: เริ่มต้น `TarArchive`

สร้างอ็อบเจกต์ `TarArchive` ภายในบล็อก `using` เพื่อให้ทรัพยากรที่ไม่ได้จัดการทั้งหมดถูกปล่อยโดยอัตโนมัติเมื่อการดำเนินการเสร็จสิ้น

```csharp
using (TarArchive archive = new TarArchive())
{
```

### ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน archive

เพิ่มไฟล์แต่ละไฟล์ที่คุณต้องการรวม ในตัวอย่างนี้เราจะเพิ่มไฟล์ข้อความสองไฟล์ แต่คุณสามารถเพิ่ม entry ได้ตามต้องการ เมธอด `AddEntry` รับพาธไฟล์เต็มและชื่อ entry ที่เป็นตัวเลือกซึ่งจะปรากฏภายใน tar

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **ทำไมเรื่องนี้สำคัญ:** การเพิ่ม entry ก่อนการบีบอัดทำให้ Aspose.Zip สร้างคอนเทนเนอร์ tar ก่อน แล้วจึงใช้การบีบอัด XZ ในขั้นตอนเดียว

### ขั้นตอนที่ 3: บันทึก archive ด้วยการบีบอัด XZ

เมธอด `SaveXzCompressed` จะเขียน tar archive ไปยังไฟล์พร้อมกับทำการบีบอัด XZ ในขั้นตอนเดียว ผลลัพธ์คือไฟล์ `.tar.xz` ที่พร้อมสำหรับการแจกจ่าย

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **ผลลัพธ์:** ตอนนี้คุณมีไฟล์ `archive.tar.xz` ที่บีบอัดเต็มรูปแบบ ซึ่งสามารถโอนย้าย, เก็บรักษา หรือแตกไฟล์บนแพลตฟอร์มใดก็ได้ที่รองรับ TarXz

## วิธีบีบอัดไฟล์ tarxz ด้วย Aspose.Zip

การบีบอัดเป็น tarxz ด้วย Aspose.Zip เป็นกระบวนการสองขั้นตอนที่ห่อหุ้มในเมธอดเดียว: ขั้นแรกคุณ **add files to tar**, จากนั้นเรียก `SaveXzCompressed`. วิธีนี้ทำให้ไม่ต้องใช้ยูทิลิตี้บรรทัดคำสั่งภายนอกและทำให้เวิร์กโฟลว์ทั้งหมดอยู่ภายในโค้ดเบส .NET ของคุณ

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **“File not found” exception** | พาธ `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าพาธของไดเรกทอรีลงท้ายด้วยแบ็คสแลช (`\`) หรือใช้ `Path.Combine`. |
| **Large memory usage** | ไฟล์ขนาดใหญ่มากถูกบีบอัดในหน่วยความจำ | ใช้ `TarArchive` ในโหมดสตรีมมิ่ง (overload ของ `SaveXzCompressed` ที่รับ `Stream`). |
| **License not applied** | ไม่มีไฟล์ไลเซนส์ | โหลดไลเซนส์เมื่อเริ่มแอปพลิเคชัน: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับสภาพแวดล้อม .NET ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Zip ทำงานกับ .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10 ดูที่ [documentation](https://reference.aspose.com/zip/net/) สำหรับรายละเอียด

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอไลเซนส์ชั่วคราวจาก [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: มีตัวอย่างเพิ่มเติมสำหรับรูปแบบ archive อื่น ๆ หรือไม่?**  
A: มีแน่นอน—สำรวจชุดตัวอย่างทั้งหมดใน [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: ฉันจะหาแนวทางช่วยเหลือหรือหารือปัญหาได้จากที่ไหน?**  
A: เข้าร่วมการสนทนาที่ [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและคำตอบจากทางการ

**Q: ฉันสามารถทดลองใช้ Aspose.Zip ฟรีก่อนซื้อได้หรือไม่?**  
A: ได้, มีการทดลองใช้งานฟรีที่ [Aspose.Zip download page](https://releases.aspose.com/zip/net)

## สรุป

โดยทำตามขั้นตอนข้างต้น คุณจะรู้ **how to add files to tar** และ **compress tarxz** รวมถึงที่สำคัญที่สุดคือ **create tarxz archive .net** ด้วย Aspose.Zip วิธีนี้ให้แพ็กเกจที่กะทัดรัดและพกพาได้ซึ่งสามารถผสานรวมอย่างราบรื่นในเวิร์กโฟลว์ .NET ใด ๆ ไม่ว่าจะเป็นการสร้างยูทิลิตี้เดสก์ท็อป, เว็บเซอร์วิส, หรือ pipeline CI/CD อัตโนมัติ

---

**อัปเดตล่าสุด:** 2026-11-18  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.11  
**ผู้เขียน:** Aspose  

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง tar archive และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}