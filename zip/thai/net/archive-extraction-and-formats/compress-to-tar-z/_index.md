---
date: 2026-05-30
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for
  .NET – คู่มือขั้นตอนต่อขั้นตอนสำหรับการจัดการไฟล์ .NET อย่างมีประสิทธิภาพ
keywords:
- add files to tar
- add directory to tar
- compress folders to tar
- compress files .net
linktitle: การบีบอัดเป็น TarZ
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to add files to tar and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: Add files to tar and compress to TarZ with Aspose.Zip for .NET
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
title: เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspose.Zip for .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarZ ด้วย Aspise.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **add files to tar** แล้วบีบอัดไฟล์เก็บเป็นรูปแบบ TarZ, Aspose.Zip สำหรับ .NET ทำให้กระบวนการทั้งหมดเป็นเรื่องง่าย ในบทแนะนำนี้เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าโปรเจกต์ของคุณ การสร้าง tar archive การเพิ่มไฟล์ และสุดท้ายการบันทึกไฟล์ .tar.z ที่บีบอัดแล้ว เมื่อเสร็จคุณจะมีโค้ดสั้นที่สามารถนำไปใช้ในแอปพลิเคชัน .NET ใดก็ได้ ไม่ว่าจะเป็นการจัดการไฟล์กำหนดค่าจำนวนไม่กี่ไฟล์หรือโครงสร้างไดเรกทอรีทั้งหมด

## คำตอบสั้น
- **ไลบรารีที่จัดการการสร้าง tar คืออะไร?** Aspose.Zip สำหรับ .NET  
- **จำนวนบรรทัดของโค้ด?** ประมาณ 15 บรรทัด (ไม่รวมคอมเมนต์)  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10  
- **สามารถบีบอัดโฟลเดอร์ได้หรือไม่, ไม่ใช่แค่ไฟล์?** ได้ – คุณสามารถเพิ่มไดเรกทอรีทั้งหมดด้วยลูป  

## อะไรคือ **add files to tar**?
การดำเนินการ **add files to tar** จะรวมไฟล์ที่เลือกไว้เป็นคอนเทนเนอร์ tar เดียวที่ไม่ได้บีบอัด พร้อมคงลำดับโครงสร้างไดเรกทอรีและเมตาดาต้า  
การโหลดไฟล์เข้าสู่ tar archive เป็นขั้นตอนแรกก่อนการบีบอัดเพิ่มเติมเช่น TarZ เนื่องจากรูปแบบ tar ให้แพคเกจที่กำหนดผลลัพธ์ได้และเป็นอิสระจากแพลตฟอร์ม ซึ่งอัลกอริทึมการบีบอัดสามารถทำงานได้อย่างมีประสิทธิภาพ  

## ทำไมต้องเพิ่มไฟล์ลงใน tar ก่อนบีบอัดเป็น TarZ?
การสร้างคอนเทนเนอร์ tar ก่อนจะทำให้ตรรกะการแพคเกจแยกจากขั้นตอนการบีบอัด ซึ่งให้ประโยชน์ที่วัดได้สามประการ การแยกขั้นตอนเหล่านี้ทำให้คุณได้ archive ที่คาดการณ์ได้และทำซ้ำได้ ซึ่งสามารถบีบอัดแยกกันได้ ทำให้การวัดอัตราการบีบอัดง่ายขึ้นและสามารถใช้ tar เดียวสำหรับอัลกอริทึมบีบอัดต่าง ๆ  
1. **พกพาได้** – ไฟล์ `.tar` สามารถแตกออกได้บนระบบ Unix‑like ใดก็ได้โดยไม่ต้องใช้ไลบรารีเพิ่มเติม  
2. **ความเร็ว** – การสร้าง tar โดยพื้นฐานเป็นการคัดลอกสตรีม; การบีบอัด Z ต่อมาจะมุ่งเน้นที่การลดขนาดเท่านั้น โดยทั่วไปจะลดลง 30‑70 % ของข้อมูลต้นฉบับ  
3. **ความเข้ากันได้** – เครื่องมือเก่าหลายตัว (เช่น `tar`, `gzip`) คาดหวังไฟล์ `.tar` ก่อนทำการบีบอัดแบบ gzip ซึ่งตรงกับนามสกุล `.tar.z`  

### ทำไมเรื่องนี้ถึงสำคัญสำหรับนักพัฒนา .NET
การใช้คอนเทนเนอร์ tar ทำให้คุณสามารถรักษา **โค้ด .NET ของคุณ** ให้เรียบง่ายและกำหนดผลลัพธ์ได้ คุณสามารถสร้าง archive ในหน่วยความจำ สตรีมโดยตรงไปยังการตอบกลับ หรือบันทึกลงดิสก์โดยไม่ต้องจัดการไฟล์ zip ชั่วคราว รูปแบบนี้มีประโยชน์อย่างยิ่งสำหรับ pipeline การสร้าง, การรวมบันทึก, หรือเมื่อคุณต้องส่งชุดไฟล์กำหนดค่าไปยังบริการที่ทำงานบน Linux  

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:
- **Aspose.Zip for .NET** ติดตั้งแล้ว ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/zip/net/)  
- โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการเก็บเป็น archive. แทนที่เส้นทางตัวอย่างด้วยไดเรกทอรีจริงของคุณ  

## นำเข้า Namespaces

เพิ่มคำสั่ง `using` ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณ:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **เคล็ดลับ:** ใช้ `Path.Combine` หากคุณต้องสร้างเส้นทางแบบไดนามิก; มันช่วยหลีกเลี่ยงการขาดเครื่องหมายแยกเส้นทางบนระบบปฏิบัติการต่าง ๆ  

## วิธีเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET?

โหลดไดเรกทอรีต้นทาง, สร้างอินสแตนซ์ `TarArchive`, เพิ่มไฟล์แต่ละไฟล์ (หรือไดเรกทอรีย่อยทั้งหมด), และสุดท้ายเรียก `Save` พร้อมกับแฟล็กการบีบอัด TarZ. กระบวนการครบวงจรนี้ต้องใช้เพียงไม่กี่บรรทัดของโค้ดและทำงานบน .NET runtime ที่รองรับทั้งหมด  

### คำนิยาม anchor
คลาส `TarArchive` เป็นอ็อบเจ็กต์หลักของ Aspose.Zip ที่แสดงถึงคอนเทนเนอร์ tar ที่คุณสามารถเติมข้อมูลเข้าได้  

### คู่มือขั้นตอนต่อขั้นตอน  

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสารของคุณ

```csharp
string dataDir = "Your Document Directory";
```

> **ทำไมขั้นตอนนี้สำคัญ:** `dataDir` ทำหน้าที่เป็นตำแหน่งฐานสำหรับไฟล์ทุกไฟล์ที่คุณจะเพิ่ม การเก็บไว้ในตัวแปรเดียวทำให้โค้ดง่ายต่อการบำรุงรักษาและนำกลับใช้ในหลาย archive  

### ขั้นตอนที่ 2: สร้าง Tar Archive และเพิ่มไฟล์

#### 2.1: สร้างอินสแตนซ์ Tar archive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> บล็อก `using` รับประกันว่าอ็อบเจ็กต์ `TarArchive` จะถูกทำลายอย่างเหมาะสม, ปล่อยตัวจัดการไฟล์หรือบัฟเฟอร์หน่วยความจำ  

#### 2.2: เพิ่มไฟล์ลงใน archive  

`CreateEntry` เพิ่มไฟล์ไปยัง tar archive, ระบุชื่อและสตรีมเนื้อหา  

ภายในบล็อก `using`, เพิ่มไฟล์แต่ละไฟล์ที่คุณต้องการรวม:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

คุณสามารถเรียก `CreateEntry` ซ้ำได้ตามจำนวนไฟล์ที่ต้องการ, หรือใช้ลูปผ่านไดเรกทอรีเพื่อเพิ่มไฟล์โดยอัตโนมัติ ตัวอย่างเช่นลูป `foreach (var file in Directory.GetFiles(dataDir))` จะช่วยให้คุณจัดการไฟล์จำนวนใดก็ได้พร้อมคงเส้นทางสัมพันธ์ของไฟล์  

#### 2.3: บันทึกไฟล์ TarZ ที่บีบอัด  

`Save` เขียน archive ลงดิสก์และใช้รูปแบบการบีบอัดที่เลือก  

หลังจากเพิ่มรายการทั้งหมดแล้ว, บีบอัด tar archive เป็นรูปแบบ `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

ไฟล์ `archive.tar.z` ที่ได้จะอยู่ในโฟลเดอร์เดียวกับที่คุณระบุใน `dataDir`. ตอนนี้คุณสามารถส่งแพคเกจบีบอัดเดียวนี้ไปยังระบบใดก็ได้ที่รองรับ TarZ  

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไฟล์ไม่พบ** | เส้นทางผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบว่า `dataDir` ลงท้ายด้วยเครื่องหมายแยกเส้นทางและชื่อไฟล์ถูกต้อง |
| **การเข้าถึงถูกปฏิเสธ** | สิทธิ์ไม่เพียงพอบนโฟลเดอร์เป้าหมาย | รันแอปพลิเคชันด้วยสิทธิ์ที่เหมาะสมหรือเลือกไดเรกทอรีที่สามารถเขียนได้ |
| **ไฟล์ที่บีบอัดใหญ่กว่าที่คาด** | ไฟล์ต้นฉบับถูกบีบอัดแล้ว (เช่น รูปภาพ, วิดีโอ) | TarZ ทำงานได้ดีที่สุดกับไฟล์ข้อความหรือบันทึก; พิจารณาเก็บไฟล์ที่บีบอัดแล้วไว้โดยไม่เปลี่ยน |

### ข้อผิดพลาดทั่วไปที่ควรระวัง
- **ขาดเครื่องหมายสแลชท้าย** – หาก `dataDir` ไม่ลงท้ายด้วย `\` หรือ `/` การต่อสตริงจะทำให้เส้นทางไม่ถูกต้อง  
- **ไดเรกทอรีขนาดใหญ่** – การเพิ่มไฟล์หลายพันไฟล์อาจใช้หน่วยความจำมาก; พิจารณาการสตรีมรายการหรือใช้ overload ของ `TarArchive` ที่เขียนโดยตรงไปยังสตรีมไฟล์  
- **ปัญหา encoding** – ชื่อไฟล์ที่ไม่ใช่ ASCII อาจต้องจัดการ encoding อย่างชัดเจน; Aspose.Zip รองรับ UTF‑8 เป็นค่าเริ่มต้น, แต่ควรตรวจสอบบนแพลตฟอร์มเป้าหมาย  

## คำถามที่พบบ่อย

**Q: ฉันสามารถบีบอัดโฟลเดอร์ทั้งหมดด้วย Aspose.Zip สำหรับ .NET ได้หรือไม่?**  
A: แน่นอน. ใช้ลูป `Directory.GetFiles` และเรียก `CreateEntry` สำหรับแต่ละไฟล์, คงเส้นทางสัมพันธ์ไว้  

**Q: มีรุ่นทดลองสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?**  
A: มี, คุณสามารถสำรวจความสามารถของ Aspose.Zip สำหรับ .NET โดยดาวน์โหลดรุ่นทดลองฟรี [ที่นี่](https://releases.aspose.com/)  

**Q: ฉันจะหาเอกสารประกอบที่ครอบคลุมสำหรับ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
A: เอกสารพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/zip/net/), ให้ข้อมูลเชิงลึกเกี่ยวกับฟีเจอร์และการใช้งานของไลบรารี  

**Q: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือ, แบ่งปันประสบการณ์, และเชื่อมต่อกับชุมชน  

**Q: ฉันสามารถขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้หรือไม่?**  
A: ได้, หากคุณต้องการไลเซนส์ชั่วคราว, คุณสามารถรับได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

## สรุป

ตอนนี้คุณได้เรียนรู้วิธี **add files to tar** และบีบอัดผลลัพธ์เป็น archive TarZ ด้วย Aspose.Zip สำหรับ .NET วิธีนี้ให้แพคเกจที่สะอาดและพกพาได้ง่าย สามารถถ่ายโอน, เก็บหรือประมวลผลต่อได้อย่างง่ายดาย อย่าลังเลที่จะแก้ไขโค้ดสั้นนี้เพื่อประมวลผลไดเรกทอรีเป็นชุด, ผสานเข้ากับ pipeline การสร้าง, หรือรวมกับคอมโพเนนต์ Aspose อื่น ๆ เพื่อเวิร์กโฟลว์เอกสารที่สมบูรณ์ยิ่งขึ้น  

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง tar archive และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}