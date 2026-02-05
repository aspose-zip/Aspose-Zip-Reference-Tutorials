---
date: 2026-02-05
description: เรียนรู้วิธีบีบอัดหลายไฟล์ด้วย C# และสร้างไฟล์ zip archive ใน .NET โดยใช้
  Aspose.Zip คู่มือขั้นตอนนี้แสดงการบีบอัดไฟล์ด้วย FileInfo ในโครงการ ASP.NET
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดหลายไฟล์ด้วย C# ใช้ Aspose.Zip สำหรับ .NET
url: /th/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดหลายไฟล์ c# ด้วย Aspise.Zip สำหรับ .NET

## คำแนะนำ

หากคุณต้องการ **บีบอัดหลายไฟล์ c#** อย่างโปรแกรมเมติก, Aspose.Zip สำหรับ .NET จะมอบ API ที่สะอาดและมีประสิทธิภาพสูงที่ทำงานได้ในแอปพลิเคชัน .NET ใด ๆ (รวมถึง ASP.NET) ในบทแนะนำนี้เราจะอธิบายขั้นตอนการบีบอัดไฟล์ด้วยคลาส `FileInfo`, แสดงวิธี **เพิ่มไฟล์ลงใน zip**, และอธิบายว่าทำไมวิธีนี้จึงเหมาะกับโครงการ .NET สมัยใหม่ เริ่มกันเลย!

## คำตอบสั้น ๆ
- **วิธีที่ง่ายที่สุดในการสร้างไฟล์ zip คืออะไร?** ใช้คลาส `Archive` ของ Aspose.Zip ร่วมกับอ็อบเจ็กต์ `FileInfo`.  
- **ฉันสามารถเพิ่มหลายไฟล์พร้อมกันได้หรือไม่?** ได้ – เพียงสร้าง `FileInfo` สำหรับแต่ละไฟล์และเรียก `CreateEntry`.  
- **ต้องใช้ไลเซนส์พิเศษสำหรับ ASP.NET หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์ของ Aspose.Zip สำหรับการใช้งานในผลิตภัณฑ์; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน.  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** ใช่, ตราบใดที่แต่ละเธรดทำงานกับอินสแตนซ์ `Archive` ของตนเอง.  
- **จะบีบอัดไฟล์ c# โดยไม่โหลดเข้าเมมโมรีได้อย่างไร?** ใช้อ็อบเจ็กต์ `FileInfo` – พวกมันสตรีมข้อมูลโดยตรง.  

## วิธีบีบอัดหลายไฟล์ c#
ไฟล์ zip จะบรรจุไฟล์หนึ่งหรือหลายไฟล์ไว้ในคอนเทนเนอร์เดียวที่ถูกบีบอัด ซึ่งช่วยลดพื้นที่จัดเก็บ, เร่งความเร็วการถ่ายโอนข้อมูลผ่านเครือข่าย, และทำให้การแจกจ่ายง่ายขึ้น ไม่ว่าคุณจะส่งบันทึก, ส่งออกรายงาน, หรือจัดแพ็คเกจทรัพยากรให้ลูกค้า การ **บีบอัดไฟล์ c#** อย่างโปรแกรมเมติกเป็นทักษะที่มีคุณค่าสำหรับนักพัฒนา .NET ทุกคน.

## ทำไมต้องใช้ Aspose.Zip เพื่อเพิ่มไฟล์ลงใน Zip?
- **ไม่มีการพึ่งพาภายนอก** – การทำงานแบบ .NET แท้ ๆ.  
- **ควบคุมระดับการบีบอัดและการเข้ารหัสได้เต็มที่** (ASCII, UTF‑8, ฯลฯ).  
- **รองรับไฟล์ขนาดใหญ่** (> 4 GB) และการป้องกันด้วยรหัสผ่าน.  
- **API สม่ำเสมอระหว่าง .NET Framework, .NET Core, และ .NET 5+**.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

1. **Aspose.Zip สำหรับ .NET** ติดตั้งแล้ว. ดาวน์โหลดแพคเกจล่าสุดจาก [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด (เช่น `alice29.txt` และ `fields.c`).  

## นำเข้า Namespaces

ในไฟล์ C# ใด ๆ ที่คุณจะทำงานกับไฟล์ zip, เพิ่ม `using` statements ต่อไปนี้:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Namespaces เหล่านี้ทำให้คุณเข้าถึงคลาส `Archive`, ตัวเลือกการบันทึก, และยูทิลิตี้ I/O มาตรฐาน.

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ

แรกสุด, กำหนดโฟลเดอร์ที่เก็บไฟล์ต้นทาง. แทนที่ตัวแปร placeholder ด้วยพาธแบบ absolute หรือ relative บนระบบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เพื่อสร้างพาธแบบข้ามแพลตฟอร์ม.

### ขั้นตอนที่ 2: เปิดไฟล์ Zip เพื่อเขียน

สร้าง `FileStream` ที่ชี้ไปยังไฟล์ zip ผลลัพธ์. สตรีมจะเปิดในโหมด **Create**, ซึ่งจะเขียนทับไฟล์ที่มีอยู่แล้วที่มีชื่อเดียวกัน:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ขั้นตอนที่ 3: เตรียมอ็อบเจ็กต์ `FileInfo` สำหรับไฟล์ต้นทางแต่ละไฟล์

`FileInfo` ให้ Aspose.Zip เข้าถึงไฟล์จริงบนดิสก์โดยตรง. สร้างอินสแตนซ์หนึ่งตัวต่อไฟล์ที่คุณต้องการบีบอัด:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **ทำไมต้องใช้ `FileInfo`?** มันช่วยหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่เมมโมรี, ซึ่งเป็นประโยชน์อย่างยิ่งสำหรับไฟล์ขนาดใหญ่.

### ขั้นตอนที่ 4: สร้าง Archive และเพิ่ม Entry

สร้างอ็อบเจ็กต์ `Archive`, จากนั้นเรียก `CreateEntry` สำหรับแต่ละ `FileInfo`. อาร์กิวเมนต์แรกคือชื่อไฟล์ภายใน zip, อาร์กิวเมนต์ที่สองคือ `FileInfo` ต้นทาง:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ขั้นตอนที่ 5: บันทึก Archive ด้วยการเข้ารหัสที่ต้องการ

สุดท้าย, บันทึก archive ลงใน `FileStream` ที่คุณเปิดไว้ก่อนหน้านี้. ตัวอย่างนี้ใช้การเข้ารหัส ASCII สำหรับชื่อ entry, แต่คุณสามารถเปลี่ยนเป็น UTF‑8 หากชื่อไฟล์ของคุณมีอักขระที่ไม่ใช่ ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

เมื่อบล็อก `using` สิ้นสุด, สตรีมจะถูกปิดโดยอัตโนมัติและไฟล์ zip จะพร้อมใช้งาน.

## ปัญหาที่พบบ่อย & วิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **ไฟล์ zip ว่างเปล่า** | `FileInfo` ชี้ไปยังพาธที่ไม่มีอยู่ | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้ `File.Exists` เพื่อตรวจสอบก่อนสร้าง entry. |
| **การเข้ารหัสชื่อไฟล์ไม่ถูกต้อง** | ใช้การเข้ารหัสเริ่มต้นกับชื่อที่ไม่ใช่ ASCII | ตั้ง `Encoding = Encoding.UTF8` ใน `ArchiveSaveOptions`. |
| **OutOfMemoryException กับไฟล์ขนาดใหญ่** | โหลดไฟล์ทั้งหมดเข้าสู่เมมโมรี | `FileInfo` สตรีมไฟล์; ตรวจสอบว่าคุณไม่ได้อ่านไฟล์เป็นอาร์เรย์ไบต์ที่อื่น. |
| **Permission denied** | แอปไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่เขียนได้. |

## คำถามที่พบบ่อย

**ถาม: สามารถเพิ่มการป้องกันด้วยรหัสผ่านให้กับไฟล์ zip ได้หรือไม่?**  
ตอบ: ได้. หลังจากสร้าง `Archive`, ตั้งค่า `archive.Password = "yourPassword"` ก่อนเรียก `Save`.

**ถาม: สามารถอัปเดตไฟล์ zip ที่มีอยู่แล้วได้หรือไม่?**  
ตอบ: Aspose.Zip รองรับการเปิด archive ที่มีอยู่ด้วย `Archive.Open` แล้วเพิ่ม entry ใหม่.

**ถาม: จะบีบอัดไฟล์ในคอนโทรลเลอร์ ASP.NET MVC อย่างไร?**  
ตอบ: โค้ดเดียวกันทำงานได้; เพียงให้แน่ใจว่า stream ผลลัพธ์ถูกส่งกลับเป็น `FileResult` ให้กับไคลเอนต์.

**ถาม: Aspose.Zip รองรับอัลกอริทึมการเข้ารหัสใดบ้าง?**  
ตอบ: รองรับ ZipCrypto มาตรฐานและการเข้ารหัส AES‑256.

**ถาม: หากต้องการบีบอัดโฟลเดอร์แบบเรียกซ้ำทั้งหมดต้องทำอย่างไร?**  
ตอบ: วนลูป `Directory.GetFiles` (รวมถึงโฟลเดอร์ย่อย) แล้วสร้าง `FileInfo` สำหรับแต่ละไฟล์, จากนั้นเพิ่มลงใน archive.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## สรุป

ตอนนี้คุณรู้แล้วว่า **วิธีบีบอัดหลายไฟล์ c#** ด้วย Aspose.Zip สำหรับ .NET, วิธี **เพิ่มไฟล์ลงใน zip**, และเหตุผลที่วิธีนี้เหมาะกับ ASP.NET และแอปพลิเคชัน .NET อื่น ๆ ทดลองปรับระดับการบีบอัด, การเข้ารหัส, และตัวเลือกการเข้ารหัสต่าง ๆ เพื่อให้ archive ตรงตามความต้องการของคุณเอง ขอให้สนุกกับการบีบอัด!

---

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบด้วย:** Aspose.Zip สำหรับ .NET 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}