---
date: 2025-12-05
description: เรียนรู้วิธีสร้างไฟล์เก็บข้อมูล tarxz ด้วย .NET และวิธีบีบอัดไฟล์ tarxz
  โดยใช้ Aspose.Zip สำหรับ .NET ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อการจัดเก็บและการส่งข้อมูลที่มีประสิทธิภาพ
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีสร้างไฟล์ tarxz ใน .NET ด้วย Aspose.Zip
url: /th/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง tarxz archive .net ด้วย Aspose.Zip

## บทนำ

หากคุณต้องการ **สร้าง tarxz archive .net** Aspose.Zip สำหรับ .NET ทำให้กระบวนการเป็นเรื่องง่ายและเชื่อถือได้ ไม่ว่าคุณจะบรรจุไฟล์บันทึก, ไฟล์การกำหนดค่า หรือทรัพยากรอื่นใดสำหรับการจัดเก็บหรือการส่งต่อ การบีบอัดเป็นรูปแบบ TarXz จะให้สัดส่วนการบีบอัดสูงพร้อมคงโครงสร้าง tar ที่คุ้นเคย ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนอย่างละเอียดพร้อมตัวอย่างโค้ด เพื่อให้คุณสามารถผสานการสร้าง tarxz เข้าไปในแอปพลิเคชัน .NET ของคุณได้อย่างมั่นใจ

## คำตอบด่วน
- **คลาสหลักคืออะไร?** `TarArchive` from `Aspose.Zip.Tar`
- **วิธีบีบอัด tarxz?** Use `SaveXzCompressed` after adding entries
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **ต้องการไลเซนส์หรือไม่?** Yes, a valid Aspose.Zip license for production
- **เวลาในการทำงานโดยประมาณ?** ~5‑10 minutes

## TarXz archive คืออะไร?

A **TarXz archive** combines the traditional Unix `tar` container with XZ compression. The tar part bundles multiple files into a single stream, while XZ provides strong, lossless compression. This format is popular for distributing source code, backups, and large data sets because it retains directory structures and achieves smaller file sizes than plain tar or zip.

## ทำไมต้องสร้าง tarxz archive .net ด้วย Aspose.Zip?

- **อัตราการบีบอัดสูง** – XZ มักบีบอัดได้ 30‑50 % เล็กกว่าการบีบอัดด้วย gzip
- **ความเข้ากันได้ข้ามแพลตฟอร์ม** – ไฟล์ TarXz สามารถเปิดได้บน Linux, macOS, และ Windows
- **API ที่เรียบง่าย** – Aspose.Zip abstracts the low‑level details, letting you focus on your business logic
- **ไม่ต้องใช้เครื่องมือภายนอก** – ทุกอย่างทำงานภายในกระบวนการ .NET ของคุณ เหมาะสำหรับคลาวด์หรือ pipeline CI

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** installed (download from the official [Aspose.Zip documentation](https://reference.aspose.com/zip/net/))
- โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบีบอัด ในตัวอย่างด้านล่างโฟลเดอร์นี้อ้างอิงโดยตัวแปร `dataDir`
- ไลเซนส์ Aspose.Zip ที่ถูกต้อง (ไม่บังคับสำหรับการประเมินผล แต่จำเป็นสำหรับการใช้งานจริง)

## นำเข้า Namespaces

First, import the namespaces that expose the TarXz functionality.

```csharp
using System;
using Aspose.Zip.Tar;
```

## คู่มือขั้นตอนการสร้าง tarxz archive .net

### ขั้นตอนที่ 1: เริ่มต้น `TarArchive`

Create a new `TarArchive` instance that will hold the files you want to compress.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **เคล็ดลับ:** คำสั่ง `using` ทำให้แน่ใจว่า archive ถูกทำลายอย่างถูกต้อง ปล่อยทรัพยากรที่ไม่ได้จัดการออก

### ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน Archive

Add each file you wish to include. In this example we add two text files, but you can add as many entries as needed.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **ทำไมเรื่องนี้สำคัญ:** การเพิ่ม entry ก่อนการบีบอัดทำให้ Aspose.Zip สร้าง tar container ก่อน แล้วค่อยใช้การบีบอัด XZ ในขั้นตอนเดียว

### ขั้นตอนที่ 3: บันทึก Archive ด้วยการบีบอัด XZ

Finally, write the tar archive to disk using XZ compression. The resulting file will have a `.tar.xz` extension.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **ผลลัพธ์:** ตอนนี้คุณมีไฟล์ `archive.tar.xz` ที่บีบอัดเต็มรูปแบบแล้ว สามารถถ่ายโอน, เก็บรักษา หรือแตกไฟล์บนแพลตฟอร์มใดก็ได้ที่รองรับ TarXz

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ข้อยกเว้น “File not found”** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าเส้นทางไดเรกทอรีลงท้ายด้วยเครื่องหมายแบ็กสแลช (`\`) หรือใช้ `Path.Combine` |
| **การใช้หน่วยความจำมาก** | ไฟล์ขนาดใหญ่มากถูกบีบอัดในหน่วยความจำ | ใช้ `TarArchive` ในโหมดสตรีม (`SaveXzCompressed` overload ที่รับ `Stream`) |
| **ไลเซนส์ไม่ถูกนำไปใช้** | ไฟล์ไลเซนส์หายไป | โหลดไลเซนส์เมื่อแอปเริ่มต้น: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## คำถามที่พบบ่อย

**ถาม: Aspose.Zip รองรับสภาพแวดล้อม .NET ทั้งหมดหรือไม่?**  
**ตอบ:** ใช่, Aspose.Zip ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+ ดูรายละเอียดเพิ่มเติมใน [documentation](https://reference.aspose.com/zip/net/)

**ถาม: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
**ตอบ:** คุณสามารถขอไลเซนส์ชั่วคราวได้จาก [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)

**ถาม: มีตัวอย่างเพิ่มเติมสำหรับรูปแบบ archive อื่น ๆ หรือไม่?**  
**ตอบ:** แน่นอน—สำรวจชุดตัวอย่างทั้งหมดใน [Aspose.Zip API reference](https://reference.aspose.com/zip/net/)

**ถาม: ฉันจะหาแนวทางช่วยเหลือหรือหารือเกี่ยวกับปัญหาได้จากที่ไหน?**  
**ตอบ:** เข้าร่วมการสนทนาที่ [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและคำตอบจากทีมอย่างเป็นทางการ

**ถาม: ฉันสามารถลองใช้ Aspose.Zip ฟรีก่อนซื้อได้หรือไม่?**  
**ตอบ:** ใช่, มีเวอร์ชันทดลองฟรีที่ [Aspose.Zip download page](https://releases.aspose.com/zip/net)

## สรุป

โดยทำตามขั้นตอนข้างต้น คุณจะรู้ **วิธีบีบอัดไฟล์ tarxz** และที่สำคัญ **วิธีสร้าง tarxz archive .net** ด้วย Aspose.Zip วิธีนี้ให้คุณได้แพ็กเกจที่กะทัดรัดและพกพาได้ง่าย สามารถผสานเข้ากับเวิร์กโฟลว์ .NET ใดก็ได้ ไม่ว่าจะเป็นยูทิลิตี้เดสก์ท็อป, เว็บเซอร์วิส, หรือ pipeline CI/CD อัตโนมัติ

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}