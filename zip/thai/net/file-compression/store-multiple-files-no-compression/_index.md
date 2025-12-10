---
date: 2025-12-10
description: เรียนรู้วิธีจัดเก็บไฟล์โดยไม่บีบอัดด้วย Aspose.Zip สำหรับ .NET คู่มือนี้จะแสดงวิธีสร้างไฟล์
  zip ที่ไม่บีบอัด, บันทึกไฟล์ลงใน zip, และจัดการคลังข้อมูลอย่างมีประสิทธิภาพ
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีจัดเก็บไฟล์โดยไม่บีบอัดด้วย Aspose.Zip สำหรับ .NET
url: /th/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเก็บไฟล์โดยไม่บีบอัดด้วย Aspose.Zip สำหรับ .NET

ในการพัฒนา .NET สมัยใหม่, **วิธีเก็บไฟล์** อย่างมีประสิทธิภาพสามารถสร้างความแตกต่างอย่างมากในด้านประสิทธิภาพและค่าใช้จ่ายในการจัดเก็บ เมื่อคุณต้องการเก็บไฟล์ไว้ในรูปแบบเดิมโดยไม่บีบอัด—Aspose.Zip สำหรับ .NET ให้ API ที่เรียบง่ายและตรงไปตรงมา ในบทแนะนำนี้เราจะอธิบายขั้นตอนการสร้างไฟล์ ZIP ที่ไม่บีบอัด, บันทึกไฟล์ลงใน ZIP, และผสานโซลูชันนี้เข้ากับแอปพลิเคชันของคุณ

## คำตอบสั้น
- **“uncompressed zip” หมายถึงอะไร?** เป็นไฟล์ ZIP ที่แต่ละรายการถูกเก็บโดยใช้วิธี “store” ทำให้ไบต์ของไฟล์ต้นฉบับไม่ถูกเปลี่ยนแปลง.  
- **ทำไมต้องหลีกเลี่ยงการบีบอัด?** เพื่อเร่งความเร็วในการทำ archive, รักษาขนาดไฟล์ต้นฉบับสำหรับการประมวลผลต่อไป, หรือปฏิบัติตามข้อกำหนดกฎระเบียบที่ห้ามการเปลี่ยนแปลงข้อมูล.  
- **คลาส Aspose.Zip ใดที่จัดการเรื่องนี้?** `ArchiveEntrySettings` ร่วมกับ `StoreCompressionSettings`.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework, .NET Core, .NET 5/6/7 และรุ่นต่อไป.

## การเก็บหลายไฟล์โดยไม่บีบอัดคืออะไร?
การเก็บหลายไฟล์โดยไม่บีบอัดหมายถึงการเพิ่มแต่ละไฟล์ลงในคอนเทนเนอร์ ZIP ด้วยวิธีการบีบอัด *store* ไฟล์จะคงความเหมือนเดิมแบบไบต์ต่อไบต์กับต้นฉบับ ซึ่งเหมาะเมื่อคุณต้องการทำ archive อย่างรวดเร็วหรือจำเป็นต้องรักษาข้อมูลให้ไม่เปลี่ยนแปลง.

## ทำไมต้องใช้ Aspose.Zip สำหรับ Archive ที่ไม่บีบอัด?
- **ความเร็ว:** ไม่ต้องใช้อัลกอริทึมบีบอัดที่ใช้ CPU มาก.  
- **ขนาดที่คาดการณ์ได้:** ขนาดของ archive เท่ากับผลรวมของไฟล์ต้นฉบับบวกกับโอเวอร์เฮดของ ZIP ที่น้อยที่สุด.  
- **ความเข้ากันได้:** ZIP ที่ได้ทำงานได้กับเครื่องมือ unzip มาตรฐานใด ๆ.  
- **ความยืดหยุ่น:** คุณยังสามารถผสมรายการที่บีบอัดและไม่บีบอัดใน archive เดียวกันได้หากต้องการ.

## ข้อกำหนดเบื้องต้น
- **Aspose.Zip for .NET** – ผสานเข้ากับโปรเจกต์ของคุณ ดู [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับขั้นตอนการติดตั้ง.  
- **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, VS Code หรือ IDE ใด ๆ ที่คุณชอบ.  
- **Document Directory** – โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่คุณต้องการทำ archive (เช่น “Your Document Directory”).

## นำเข้า Namespaces
ก่อนเขียนโค้ดใด ๆ ให้ทำการนำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสของ Aspose จากที่ไหน.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory
กำหนดพาธที่ไฟคุณอยู่ แทนที่ placeholder ด้วยโฟลเดอร์จริงบนระบบของคุณ.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง Zip Archive โดยไม่บีบอัด
ส่วนสำคัญของบทแนะนำ – เราจะสร้างอินสแตนซ์ `Archive` ที่กำหนดค่าโดยใช้ `StoreCompressionSettings` ซึ่งบอก Aspose.Zip ให้ *store* (คือ ไม่บีบอัด) แต่ละรายการ.

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

> **เคล็ดลับ:** หากคุณต้องการ **บันทึกไฟล์ลง zip** พร้อมกับบีบอัดบางไฟล์และไม่บีบอัดไฟล์อื่น ๆ ให้สร้างอินสแตนซ์ `ArchiveEntrySettings` แยกต่างหากสำหรับแต่ละไฟล์และเพิ่มลงใน `Archive` เดียวกัน.

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **ไม่พบไฟล์** | พาธ `dataDir` ไม่ถูกต้องหรือขาดส่วนต่อท้ายของไฟล์. | ตรวจสอบพาธและให้แน่ใจว่าไฟล์มีอยู่ ใช้ `Path.Combine` เพื่อรวมพาธอย่างปลอดภัย. |
| **การเข้าถึงถูกปฏิเสธ** | กระบวนการไม่มีสิทธิ์อ่านไฟล์ต้นทางหรือเขียน ZIP. | เรียกใช้งานแอปพลิเคชันด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่มีสิทธิ์เขียน. |
| **ขนาดไฟล์ใน ZIP ไม่คาดคิด** | Archive ถูกสร้างด้วยการบีบอัดค่าเริ่มต้น. | ตรวจสอบให้แน่ใจว่าได้ส่ง `new StoreCompressionSettings()` ไปยัง `ArchiveEntrySettings`. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถบีบอัดไฟล์ประเภทเฉพาะในขณะที่เก็บไฟล์อื่นโดยไม่บีบอัดได้หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถสร้าง `ArchiveEntrySettings` ที่แตกต่างกันสำหรับแต่ละไฟล์และผสมรายการที่บีบอัดและไม่บีบอัดใน archive เดียวกันได้.

**ถาม: Aspose.Zip for .NET รองรับ .NET Core และ .NET 5/6 หรือไม่?**  
**ตอบ:** แน่นอน. ไลบรารีนี้รองรับ .NET Framework, .NET Core, .NET Standard, และเวอร์ชัน .NET ล่าสุด.

**ถาม: ฉันควรจัดการกับข้อยกเว้นระหว่างกระบวนการทำ archive อย่างไร?**  
**ตอบ:** ห่อโค้ดการทำ archive ด้วยบล็อก `try‑catch` และบันทึกรายละเอียดของข้อยกเว้น เพื่อให้การล้มเหลวเป็นไปอย่างราบรื่นและง่ายต่อการดีบัก.

**ถาม: Aspose.Zip รองรับการทำ archive แบบหลายเธรดหรือไม่?**  
**ตอบ:** ใช่, คุณสามารถประมวลผลหลายไฟล์พร้อมกันและเพิ่มลงใน archive ได้ แต่ต้องจำว่าอ็อบเจ็กต์ `Archive` ไม่ปลอดภัยต่อการทำงานหลายเธรด; ควรซิงโครไนซ์การเข้าถึงเมื่อเพิ่มรายการ.

**ถาม: ฉันสามารถผสาน Aspose.Zip เข้าในโปรเจกต์ที่มีอยู่โดยไม่ต้องเปลี่ยนโค้ดมากหรือไม่?**  
**ตอบ:** แน่นอน. API ถูกออกแบบให้ใช้งานแบบ drop‑in อย่างง่าย ดู [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับคำแนะนำการย้าย.

---

**อัปเดตล่าสุด:** 2025-12-10  
**ทดสอบกับ:** Aspose.Zip for .NET 24.12 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}