---
date: 2026-11-18
description: เรียนรู้วิธีสร้างไฟล์ tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET
  – คู่มือขั้นตอนที่ละเอียดสำหรับการจัดการไฟล์ .NET อย่างมีประสิทธิภาพ
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: การบีบอัดเป็น TarZ
og_description: เรียนรู้วิธีสร้างไฟล์ tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET
  คู่มือนี้จะพาคุณผ่านขั้นตอนการเพิ่มไฟล์ ไดเรกทอรี และการบีบอัดอย่างมีประสิทธิภาพ
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: วิธีสร้างไฟล์ tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: วิธีสร้างไฟล์ tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET

## บทนำ

หากคุณต้องการ **add files to tar** แล้วบีบอัดไฟล์เก็บไว้เป็นรูปแบบ TarZ, Aspose.Zip for .NET ทำให้กระบวนการทั้งหมดเป็นเรื่องง่าย ในบทแนะนำนี้เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าโครงการของคุณ การสร้างไฟล์ tar การเพิ่มไฟล์ และสุดท้ายการบันทึกไฟล์ .tar.z ที่บีบอัดแล้ว เมื่อเสร็จคุณจะมีโค้ดสั้นที่สามารถนำไปใช้ในแอปพลิเคชัน .NET ใดก็ได้ ไม่ว่าจะเป็นการจัดการไฟล์กำหนดค่าจำนวนไม่กี่ไฟล์หรือโครงสร้างไดเรกทอรีทั้งหมด

## คำตอบสั้น
- **ไลบรารีที่จัดการการสร้าง tar คืออะไร?** Aspose.Zip for .NET  
- **จำนวนบรรทัดของโค้ดคือเท่าไหร่?** About 15 lines (excluding comments)  
- **ฉันต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** A free trial is available; a license is required for production.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **ฉันสามารถบีบอัดโฟลเดอร์ได้หรือไม่ ไม่ใช่แค่ไฟล์?** Yes – you can add entire directories with a loop.

## **add files to tar** คืออะไร
**Add files to tar** คือกระบวนการรวมไฟล์ที่เลือกไว้เป็นคอนเทนเนอร์ tar เดียวที่ไม่ได้บีบอัดโดยคงลำดับโครงสร้างไดเรกทอรีและเมตาดาต้า รูปแบบ tar สร้างแพ็กเกจที่กำหนดได้และไม่ขึ้นกับแพลตฟอร์ม ซึ่งอัลกอริทึมการบีบอัดต่อไปสามารถทำงานได้อย่างมีประสิทธิภาพ ทำให้เหมาะสำหรับการแจกจ่ายข้ามแพลตฟอร์ม

## วิธีสร้างไฟล์ tar ด้วย Aspose.Zip for .NET?
`TarArchive` class แสดงถึงคอนเทนเนอร์ tar ที่สามารถเก็บหลายรายการไฟล์ได้ โหลดไดเรกทอรีต้นทาง สร้างอินสแตนซ์ของ `TarArchive` เพิ่มไฟล์แต่ละไฟล์ (หรือไดเรกทอรีย่อยทั้งหมด) แล้วเรียก `Save` พร้อมกับแฟล็กการบีบอัด TarZ กระบวนการนี้ตรงไปตรงมา ต้องใช้เพียงไม่กี่บรรทัดของโค้ด และทำงานอย่างสม่ำเสมอบน .NET runtime ที่รองรับทั้งหมด รวมถึง .NET Framework และ .NET Core

`TarArchive` class เป็นอ็อบเจ็กต์หลักของ Aspose.Zip ที่แสดงถึงคอนเทนเนอร์ tar ที่คุณสามารถเติมรายการได้ การใช้มันทำให้คุณสามารถสร้างไฟล์ tar ได้ทั้งหมดในหน่วยความจำ ส่งสตรีมโดยตรงไปยังการตอบสนอง หรือเขียนลงดิสก์โดยไม่ต้องใช้ไฟล์ zip ชั่วคราว

## ทำไมต้องเพิ่มไฟล์ลงใน tar ก่อนบีบอัดเป็น TarZ?
การสร้างคอนเทนเนอร์ tar ก่อนจะทำให้การบรรจุแยกจากการบีบอัด ซึ่งให้ประโยชน์ที่วัดได้สามประการ โดยการแยกขั้นตอนเหล่านี้คุณจะได้ไฟล์เก็บที่คาดการณ์ได้และทำซ้ำได้ ซึ่งสามารถบีบอัดแยกจากกัน ทำให้การวัดอัตราการบีบอัดง่ายขึ้นและสามารถใช้ tar เดียวกันกับอัลกอริทึมการบีบอัดต่างๆ ได้

1. **พกพาได้** – ไฟล์ `.tar` สามารถแตกออกได้บนระบบที่คล้าย Unix ใดก็ได้โดยไม่ต้องใช้ไลบรารีเพิ่มเติม.  
2. **ความเร็ว** – การสร้าง tar เป็นการคัดลอกสตรีมโดยพื้นฐาน; การบีบอัด Z ต่อมาจะมุ่งเน้นที่การลดขนาดเท่านั้น โดยทั่วไปจะลด **30‑70 %** ของข้อมูลต้นฉบับ.  
3. **ความเข้ากันได้** – เครื่องมือเก่าหลายตัว (เช่น `tar`, `gzip`) คาดหวังไฟล์ `.tar` ก่อนที่จะทำการบีบอัดแบบ gzip ซึ่งตรงกับนามสกุล `.tar.z`

### ทำไมเรื่องนี้ถึงสำคัญสำหรับนักพัฒนา .NET
การใช้คอนเทนเนอร์ tar ทำให้โค้ด .NET ของคุณง่ายและกำหนดผลลัพธ์ได้ คุณสามารถสร้างไฟล์เก็บในหน่วยความจำ ส่งสตรีมโดยตรงไปยังการตอบสนอง หรือเก็บไว้บนดิสก์โดยไม่ต้องจัดการไฟล์ zip ชั่วคราว รูปแบบนี้มีประโยชน์อย่างยิ่งสำหรับ pipeline การสร้าง, การรวมบันทึก, หรือเมื่อคุณต้องส่งชุดไฟล์กำหนดค่าไปยังบริการที่ทำงานบน Linux

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกไปในโค้ด โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** ติดตั้งแล้ว ดาวน์โหลดจากเว็บไซต์ทางการ [here](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการเก็บเป็น archive. แทนที่พาธตัวอย่างด้วยไดเรกทอรีจริงของคุณ.

## นำเข้า namespace
เพิ่มคำสั่ง `using` ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณ:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **เคล็ดลับ:** ใช้ `Path.Combine` หากคุณต้องสร้างพาธแบบไดนามิก; มันช่วยหลีกเลี่ยงการขาดเครื่องหมายแยกพาธบนระบบปฏิบัติการต่างๆ.

## วิธีเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip for .NET?
`CreateEntry` method เพิ่มรายการไฟล์ใหม่ลงใน tar archive พร้อมกับชื่อและสตรีมเนื้อหาที่ระบุ โหลดไดเรกทอรีต้นทาง สร้างอินสแตนซ์ `TarArchive` เพิ่มไฟล์แต่ละไฟล์ (หรือไดเรกทอรีย่อยทั้งหมด) แล้วเรียก `Save` พร้อมกับแฟล็กการบีบอัด TarZ กระบวนการนี้สั้นกระชับ ปกติไม่เกิน 20 บรรทัด และทำงานบน .NET runtime ที่รองรับทั้งหมด ให้วิธีที่เชื่อถือได้ในการบรรจุและบีบอัดข้อมูล

`Save` method เขียน archive ลงดิสก์และอาจบีบอัดเพิ่มเติมได้.

### จุดอ้างอิงการกำหนด
`TarArchive` class เป็นอ็อบเจ็กต์หลักของ Aspose.Zip ที่แสดงถึงคอนเทนเนอร์ tar ที่คุณสามารถเติมรายการได้.

### คู่มือขั้นตอนต่อขั้นตอน

#### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
```

> **ทำไมขั้นตอนนี้ถึงสำคัญ:** `dataDir` ทำหน้าที่เป็นตำแหน่งฐานสำหรับไฟล์ทุกไฟล์ที่คุณจะเพิ่ม การเก็บไว้ในตัวแปรเดียวทำให้โค้ดง่ายต่อการบำรุงรักษาและนำกลับใช้ได้ในหลาย archive.

#### ขั้นตอนที่ 2: สร้าง Tar archive และเพิ่มไฟล์
##### 2.1: สร้างอินสแตนซ์ Tar archive
```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> บล็อก `using` รับประกันว่าอ็อบเจ็กต์ `TarArchive` จะถูกทำลายอย่างเหมาะสม ปล่อยตัวจัดการไฟล์หรือบัฟเฟอร์หน่วยความจำ

##### 2.2: เพิ่มไฟล์ลงใน archive  
`CreateEntry` เพิ่มไฟล์ลงใน tar archive โดยระบุชื่อและสตรีมเนื้อหา.  

ภายในบล็อก `using` ให้เพิ่มไฟล์แต่ละไฟล์ที่คุณต้องการรวม:
```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

คุณสามารถทำซ้ำ `CreateEntry` สำหรับไฟล์จำนวนที่ต้องการ หรือวนลูปผ่านไดเรกทอรีเพื่อเพิ่มไฟล์โดยอัตโนมัติ ตัวอย่างเช่น ลูป `foreach (var file in Directory.GetFiles(dataDir))` จะช่วยให้คุณจัดการไฟล์จำนวนไม่จำกัดพร้อมคงรักษาเส้นทางสัมพันธ์ของไฟล์

##### 2.3: บันทึกไฟล์ TarZ ที่บีบอัด  
`Save` เขียน archive ลงดิสก์และใช้รูปแบบการบีบอัดที่เลือก.  

หลังจากเพิ่มรายการทั้งหมดแล้ว ให้บีบอัด tar archive เป็นรูปแบบ `.tar.z`:
```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

ไฟล์ `archive.tar.z` ที่ได้จะอยู่ในโฟลเดอร์เดียวกับที่คุณระบุใน `dataDir`. ตอนนี้คุณสามารถส่งแพ็กเกจบีบอัดเดียวนี้ไปยังระบบใดก็ได้ที่รองรับ TarZ.

## ปัญหาทั่วไปและวิธีแก้
| Issue | Reason | Fix |
|-------|--------|-----|
| **ไม่พบไฟล์** | พาธผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นพาธและชื่อไฟล์ถูกต้อง. |
| **การเข้าถึงถูกปฏิเสธ** | สิทธิ์ไม่เพียงพอบนโฟลเดอร์เป้าหมาย | รันแอปพลิเคชันด้วยสิทธิ์ที่เหมาะสมหรือเลือกไดเรกทอรีที่สามารถเขียนได้. |
| **ไฟล์ที่บีบอัดใหญ่กว่าที่คาด** | ไฟล์ต้นฉบับถูกบีบอัดแล้ว (เช่น รูปภาพ, วิดีโอ) | TarZ ทำงานดีที่สุดกับไฟล์ข้อความหรือไฟล์บันทึก; พิจารณาเก็บไฟล์ที่บีบอัดแล้วไว้โดยไม่ทำการบีบอัดเพิ่มเติม. |

### จุดหลบหลีกทั่วไปที่ควรระวัง
- **Missing trailing slash** – หาก `dataDir` ไม่ลงท้ายด้วย `\` หรือ `/` การต่อสตริงจะทำให้พาธไม่ถูกต้อง.  
- **Large directories** – การเพิ่มไฟล์หลายพันไฟล์อาจใช้หน่วยความจำมาก; พิจารณาการสตรีมรายการหรือใช้ overload ของ `TarArchive` ที่เขียนโดยตรงไปยังสตรีมไฟล์.  
- **Encoding issues** – ชื่อไฟล์ที่ไม่ใช่ ASCII อาจต้องการการจัดการการเข้ารหัสอย่างชัดเจน; Aspose.Zip รองรับ UTF‑8 เป็นค่าเริ่มต้น แต่ควรตรวจสอบบนแพลตฟอร์มเป้าหมาย.

## คำถามที่พบบ่อย
**Q: ฉันสามารถบีบอัดโฟลเดอร์ทั้งหมดด้วย Aspose.Zip for .NET ได้หรือไม่?**  
A: แน่นอน ใช้ลูป `Directory.GetFiles` และเรียก `CreateEntry` สำหรับแต่ละไฟล์ โดยคงรักษาเส้นทางสัมพันธ์.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Zip for .NET หรือไม่?**  
A: มี คุณสามารถสำรวจความสามารถของ Aspose.Zip for .NET ได้โดยดาวน์โหลดเวอร์ชันทดลองฟรี [here](https://releases.aspose.com/).

**Q: ฉันสามารถหาเอกสารประกอบที่ครอบคลุมสำหรับ Aspose.Zip for .NET ได้ที่ไหน?**  
A: เอกสารพร้อมให้บริการ [here](https://reference.aspose.com/zip/net/), ให้ข้อมูลเชิงลึกเกี่ยวกับคุณลักษณะและการใช้งานของไลบรารี.

**Q: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Zip for .NET อย่างไร?**  
A: เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือ แบ่งปันประสบการณ์ และเชื่อมต่อกับชุมชน.

**Q: ฉันสามารถขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip for .NET ได้หรือไม่?**  
A: ได้ หากคุณต้องการไลเซนส์ชั่วคราว คุณสามารถรับได้ [here](https://purchase.aspose.com/temporary-license/).

## สรุป
คุณได้เรียนรู้วิธี **add files to tar** และบีบอัดผลลัพธ์เป็น archive TarZ ด้วย Aspose.Zip for .NET แล้ว วิธีนี้ให้แพ็กเกจที่สะอาดและพกพาได้ง่าย สามารถถ่ายโอน เก็บ หรือประมวลผลต่อได้อย่างสะดวก อย่าลังเลที่จะปรับโค้ดสั้นนี้เพื่อประมวลผลไดเรกทอรีเป็นชุด, ผสานเข้ากับ pipeline การสร้าง, หรือรวมกับคอมโพเนนต์ Aspose อื่นเพื่อเวิร์กโฟลว์เอกสารที่สมบูรณ์ยิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2026-11-18  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.11  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง
- [เพิ่มหลายไฟล์ลงใน tar และสร้าง archive tar.gz ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [การสกัดและรูปแบบ Archive](/zip/net/archive-extraction-and-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}