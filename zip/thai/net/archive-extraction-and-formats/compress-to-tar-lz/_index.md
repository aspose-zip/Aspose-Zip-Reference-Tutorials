---
date: 2026-07-04
description: เรียนรู้วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip for .NET และสร้างไฟล์
  tar.lz อย่างมีประสิทธิภาพ
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: การบีบอัดเป็น TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip for .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดหลายไฟล์ tar ด้วย Aspose.Zip สำหรับ .NET

ในการพัฒนา .NET สมัยใหม่ การจัดแพ็กไฟล์อย่างมีประสิทธิภาพสามารถปรับปรุงขนาดการปรับใช้และเวลาในการถ่ายโอนเครือข่ายได้อย่างมาก **Compress multiple files tar** เป็นความต้องการที่พบบ่อยเมื่อคุณต้องการ archive TAR ที่บีบอัดด้วย LZ ที่มีน้ำหนักเบา สำหรับการสำรองข้อมูล การแจกจ่าย หรือการอัปโหลดไปยังคลาวด์ ในบทแนะนำนี้เราจะเดินผ่าน **tar.lz compression example** อย่างชัดเจน ทีละขั้นตอนโดยใช้ไลบรารี Aspose.Zip เพื่อให้คุณสามารถสร้าง **tar.lz archive** ในแอปพลิเคชันของคุณได้อย่างรวดเร็ว

## คำตอบสั้น
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับตัวอย่างพื้นฐาน.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันสามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?** ได้ – เพียงเพิ่มรายการเพิ่มเติมก่อนบันทึก.

## ฉันจะบีบอัดหลายไฟล์ tar ด้วย Aspose.Zip สำหรับ .NET อย่างไร?
โหลดไฟล์ต้นฉบับของคุณ, สร้างอินสแตนซ์ `TarArchive`, เพิ่มไฟล์แต่ละไฟล์ด้วย `CreateEntry`, และจบด้วยการเรียก `SaveLzipped`. ไลบรารีจัดการโครงสร้าง TAR และการบีบอัด LZ ภายใน, ดังนั้นคุณจะได้ไฟล์ `*.tar.lz` เพียงไฟล์เดียวในไม่กี่บรรทัดของโค้ด วิธีนี้ทำงานได้บน Windows, Linux, และ macOS โดยไม่มีการพึ่งพา native ใด ๆ

## tar.lz compression คืออะไร?
`tar.lz` คือ archive TAR ที่ถูกบีบอัดด้วยอัลกอริทึม LZMA (ซึ่งมักเรียกสั้น ๆ ว่า **LZ**). มันผสานความเรียบง่ายของการจัดกลุ่มไฟล์ของ TAR กับอัตราการบีบอัดสูงของ LZ ทำให้เหมาะสำหรับไฟล์สำรอง, การแจกจ่ายแพ็กเกจ, หรือสถานการณ์ใด ๆ ที่แบนด์วิธเป็นสิ่งสำคัญ

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?
Aspose.Zip ให้โซลูชัน pure‑managed, ข้ามแพลตฟอร์ม ที่สร้าง archive TAR, ZIP, และ LZ‑based โดยไม่ต้องใช้เครื่องมือภายนอก, รองรับกว่า 30 รูปแบบ archive, และให้การบีบอัดที่ดีกว่า 30 % สำหรับไฟล์ขนาดใหญ่, พร้อมข้อยกเว้นที่ละเอียดสำหรับการจัดการข้อผิดพลาดอย่างแข็งแรง นอกจากนี้ยังรวมเข้ากับเฟรมเวิร์ก logging ของ .NET อย่างราบรื่นและให้เหตุการณ์ความคืบหน้าที่ละเอียด

## ข้อกำหนดเบื้องต้น
- **Aspose.Zip for .NET** library – download it from [here](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบีบอัด. เส้นทางไปยังโฟลเดอร์นี้จะถูกเก็บไว้ในตัวแปร `dataDir` (คุณจะตั้งค่าในขั้นตอน 3)

## นำเข้า Namespaces
เพิ่ม namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหา class ที่เราจะใช้ได้จากที่ไหน

```csharp
using System;
using Aspose.Zip.Tar;
```

## วิธีสร้าง tar.lz archive – คำแนะนำขั้นตอนต่อขั้นตอน

### ขั้นตอน 1: บีบอัดไฟล์เดียว
ตัวอย่างแรกแสดงสถานการณ์พื้นฐานที่สุด – การเพิ่มไฟล์หนึ่งไฟล์ลงใน archive TAR แล้วบันทึกเป็นไฟล์ **tar.lz**  

คลาส `TarArchive` แสดงถึงคอนเทนเนอร์ TAR ที่สามารถเก็บหลายไฟล์ใน archive เดียว  

**คำอธิบาย**

- `new TarArchive()` สร้างคอนเทนเนอร์ TAR ว่างเปล่า.  
- `CreateEntry` เพิ่มไฟล์ `alice29.txt` จาก `dataDir` ของคุณ.  
- `SaveLzipped` เขียน archive ไปยังดิสก์และทำการบีบอัด LZ, ผลลัพธ์เป็น `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### ขั้นตอน 2: บีบอัดหลายไฟล์ใน archive เดียว
บ่อยครั้งคุณจะต้องรวมไฟล์หลายไฟล์เข้าด้วยกัน เพียงเรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก นี่แสดง **add files to tar lz** และโดยอ้อม **compress multiple files tar**  

**คำอธิบาย**

- โค้ดทำตามรูปแบบเดียวกับขั้นตอน 1, แต่เพิ่มรายการที่สอง (`lcet10.txt`).  
- คุณสามารถเรียก `CreateEntry` ซ้ำได้ตามต้องการ; ไลบรารีจะจัดการโครงสร้าง TAR ภายในโดยอัตโนมัติ.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### ขั้นตอน 3: ระบุไดเรกทอรีเอกสารของคุณ
แทนที่ placeholder ด้วยเส้นทางจริงที่ไฟล์ต้นฉบับของคุณอยู่ เส้นทางนี้จะถูกใช้โดยตัวอย่างข้างต้น  

**คำอธิบาย**

- ตั้งค่า `dataDir` ให้เป็นเส้นทางโฟลเดอร์เต็มรูปแบบ, เช่น `@"C:\MyFiles\"`.  
- การเก็บไดเรกทอรีในตัวแปรทำให้โค้ดนำกลับใช้ใหม่ได้และบำรุงรักษาง่ายขึ้น.

```csharp
string dataDir = "Your Document Directory";
```

## ปัญหาที่พบบ่อย & การแก้ไขข้อผิดพลาด
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `FileNotFoundException` เมื่อรันตัวอย่าง | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่หรือชื่อไฟล์สะกดผิด | ตรวจสอบเส้นทางและชื่อไฟล์; ใช้ `Path.Combine` เพื่อความปลอดภัย. |
| ไฟล์ผลลัพธ์เป็น **0 KB** | `archive.SaveLzipped` ถูกเรียกก่อนที่มีการเพิ่มรายการใด ๆ | ตรวจสอบให้มีการเรียก `CreateEntry` อย่างน้อยหนึ่งครั้งก่อน `SaveLzipped`. |
| การบีบอัดดูช้า | ไฟล์ขนาดใหญ่พร้อมขนาดบัฟเฟอร์เริ่มต้น | พิจารณาประมวลผลไฟล์เป็นชิ้นส่วนหรือใช้ I/O แบบอะซิงโครนัสหากต้องการประสิทธิภาพสูง. |

## สรุป
คุณได้เรียนรู้ **วิธีบีบอัดไฟล์ tar.lz** ด้วย Aspose.Zip สำหรับ .NET แล้ว ไม่ว่าจะเป็นการจัดการเอกสารเดียวหรือคอลเลกชันไฟล์หลายไฟล์ ตัวอย่าง **tar.lz compression** นี้แสดงวิธีที่สะอาดและพร้อมใช้งานในผลิตภัณฑ์เพื่อ **สร้าง tar lz archive** ที่สามารถถ่ายโอนหรือจัดเก็บได้ง่าย คุณสามารถบีบอัดไฟล์เป็น tar.lz ด้วย API เดียวกันโดยเรียก `SaveLzipped` หลังจากเพิ่มรายการที่ต้องการทั้งหมด

## คำถามที่พบบ่อย

**Q:** ฉันสามารถบีบอัดไฟล์ขนาดใดก็ได้ด้วย Aspose.Zip สำหรับ .NET หรือไม่?  
**A:** ใช่, ไลบรารีจัดการไฟล์ขนาดเล็กและขนาดใหญ่มาก; เพียงตรวจสอบว่ามีหน่วยความจำและพื้นที่ดิสก์เพียงพอสำหรับโครงสร้าง TAR ชั่วคราว.

**Q:** โค้ดนี้เข้ากันได้กับรุ่นล่าสุดของ Aspose.Zip หรือไม่?  
**A:** ตัวอย่างมุ่งเป้าไปที่เวอร์ชันปัจจุบัน; ควรอัปเดตแพ็กเกจ NuGet ให้เป็นเวอร์ชันล่าสุดเสมอเพื่อรับการแก้ไขบั๊กและฟีเจอร์ใหม่.

**Q:** มีข้อพิจารณาเรื่องไลเซนส์หรือไม่?  
**A:** ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์. ดูรายละเอียดไลเซนส์ที่ [Aspose website](https://purchase.aspose.com/buy).

**Q:** ฉันสามารถใช้โค้ดนี้ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** ได้ – เมื่อคุณมีไลเซนส์ที่ถูกต้อง, คุณสามารถฝังไลบรารีในแอปพลิเคชันเชิงพาณิชย์ใด ๆ ได้.

**Q:** ฉันจะหาแนวทางช่วยเหลือได้จากที่ไหนหากเจอปัญหา?  
**A:** เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและทีมงานอย่างเป็นทางการ.

**อัปเดตล่าสุด:** 2026-07-04  
**ทดสอบกับ:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง tar archive และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [เพิ่มไฟล์ลงใน tar และสร้าง tarxz archive ด้วย Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}