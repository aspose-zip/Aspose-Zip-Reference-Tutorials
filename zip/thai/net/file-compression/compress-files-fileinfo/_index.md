---
date: 2026-02-28
description: เรียนรู้วิธีเพิ่มโฟลเดอร์ลงในไฟล์ zip และเพิ่มไฟล์ลงใน zip ด้วย Aspose.Zip
  สำหรับ .NET คู่มือแบบขั้นตอนนี้แสดงวิธีบีบอัดไฟล์ด้วย FileInfo ในโครงการ ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีเพิ่มโฟลเดอร์ลงในไฟล์ Zip ด้วย Aspose.Zip สำหรับ .NET – บีบอัดไฟล์ด้วย
  FileInfo
url: /th/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มโฟลเดอร์ลงในไฟล์ Zip ด้วย Aspose.Zip สำหรับ .NET

## คำนำ

หากคุณต้องการ **สร้างไฟล์ zip archive** ด้วยโปรแกรม, Aspose.Zip สำหรับ .NET มอบ API ที่สะอาดและมีประสิทธิภาพสูงซึ่งทำงานได้ในแอปพลิเคชัน .NET ใด ๆ (รวมถึง ASP.NET) ในบทแนะนำนี้เราจะอธิบายการบีบอัดไฟล์ด้วยคลาส `FileInfo`, แสดงวิธี **เพิ่มไฟล์ลงใน zip**, และอธิบายว่าทำไมวิธีนี้จึงเหมาะกับโครงการ .NET สมัยใหม่ เราจะครอบคลุมวิธี **เพิ่มโฟลเดอร์ลงใน zip** เพื่อให้คุณสามารถบรรจุไดเรกทอรีทั้งหมดในขั้นตอนเดียว เริ่มกันเลย!

## คำตอบสั้น
- **วิธีที่ง่ายที่สุดในการสร้างไฟล์ zip archive คืออะไร?** ใช้คลาส `Archive` ของ Aspose.Zip ร่วมกับอ็อบเจ็กต์ `FileInfo`.  
- **ฉันสามารถเพิ่มหลายไฟล์พร้อมกันได้หรือไม่?** ได้ – เพียงสร้าง `FileInfo` สำหรับแต่ละไฟล์และเรียก `CreateEntry`.  
- **ฉันต้องการไลเซนส์พิเศษสำหรับ ASP.NET หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์ของ Aspose.Zip สำหรับการใช้งานจริง; รุ่นทดลองฟรีใช้ได้สำหรับการประเมิน.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** ใช่, ตราบใดที่แต่ละเธรดทำงานกับอินสแตนซ์ `Archive` ของตนเอง.

## Zip Archive คืออะไรและทำไมต้องสร้าง?

Zip archive คือการรวมไฟล์หนึ่งหรือหลายไฟล์เข้าเป็นคอนเทนเนอร์เดียวที่ถูกบีบอัด ซึ่งช่วยลดพื้นที่จัดเก็บ, เร่งความเร็วการส่งข้อมูลผ่านเครือข่าย, และทำให้การแจกจ่ายง่ายขึ้น ไม่ว่าคุณจะส่งบันทึก, ส่งออกรายงาน, หรือบรรจุสินทรัพย์ให้ลูกค้า การรู้ **วิธีสร้างไฟล์ zip archive** ด้วยโปรแกรมเป็นทักษะที่มีคุณค่าสำหรับนักพัฒนา .NET ทุกคน.

## ทำไมต้องใช้ Aspose.Zip เพื่อเพิ่มไฟล์ลงใน Zip?

- **ไม่มีการพึ่งพาไลบรารีภายนอก** – การทำงานแบบ .NET แท้.  
- **ควบคุมระดับการบีบอัดและการเข้ารหัสได้เต็มที่** (ASCII, UTF‑8 ฯลฯ).  
- **รองรับไฟล์ขนาดใหญ่** (> 4 GB) และการป้องกันด้วยรหัสผ่าน.  
- **API สม่ำเสมอระหว่าง .NET Framework, .NET Core, และ .NET 5+**.

## ข้อกำหนดเบื้องต้น

1. **Aspose.Zip for .NET** ติดตั้งแล้ว. ดาวน์โหลดแพคเกจล่าสุดจาก [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด (เช่น `alice29.txt` และ `fields.c`).  

## นำเข้า Namespaces

ในไฟล์ C# ใด ๆ ที่คุณจะทำงานกับ zip archive, เพิ่ม `using` statements ต่อไปนี้:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ

แรก, กำหนดโฟลเดอร์ที่เก็บไฟล์ต้นฉบับ. แทนที่ตัวแปร placeholder ด้วยเส้นทางแบบ absolute หรือ relative บนระบบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เพื่อสร้างเส้นทางแบบข้ามแพลตฟอร์ม.

### ขั้นตอนที่ 2: เปิดไฟล์ Zip เพื่อเขียน

สร้าง `FileStream` ที่ชี้ไปยังไฟล์ zip ผลลัพธ์. สตรีมเปิดในโหมด **Create** ซึ่งจะเขียนทับไฟล์ที่มีอยู่แล้วที่มีชื่อเดียวกัน:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ขั้นตอนที่ 3: เตรียมอ็อบเจ็กต์ `FileInfo` สำหรับไฟล์ต้นฉบับแต่ละไฟล์

`FileInfo` ให้ Aspose.Zip เข้าถึงไฟล์จริงบนดิสก์โดยตรง. สร้างอินสแตนซ์หนึ่งต่อไฟล์ที่ต้องการบีบอัด:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **ทำไมต้องใช้ `FileInfo`?** มันช่วยหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ซึ่งเป็นประโยชน์อย่างยิ่งสำหรับไฟล์ขนาดใหญ่.

### ขั้นตอนที่ 4: สร้าง Archive และเพิ่มรายการ

สร้างอ็อบเจ็กต์ `Archive`, จากนั้นเรียก `CreateEntry` สำหรับแต่ละ `FileInfo`. อาร์กิวเมนต์แรกคือชื่อไฟล์ภายใน zip, อาร์กิวเมนต์ที่สองคือ `FileInfo` แหล่งที่มา:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ขั้นตอนที่ 5: บันทึก Zip Archive ด้วยการเข้ารหัสที่ต้องการ

สุดท้าย, บันทึก archive ลงใน `FileStream` ที่เปิดไว้ก่อนหน้า. ที่นี่เราใช้การเข้ารหัส ASCII สำหรับชื่อรายการ, แต่คุณสามารถสลับเป็น UTF‑8 หากชื่อไฟล์ของคุณมีอักขระที่ไม่ใช่ ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

เมื่อบล็อก `using` สิ้นสุด, สตรีมจะถูกปิดโดยอัตโนมัติและไฟล์ zip จะพร้อมใช้งาน.

## วิธีเพิ่มโฟลเดอร์ลงใน Zip ด้วย Aspose.Zip

หากคุณต้องการ **เพิ่มโฟลเดอร์ลงใน zip** แทนไฟล์เดี่ยว, กระบวนการก็ง่ายดาย:

1. **สำรวจโฟลเดอร์** ด้วย `DirectoryInfo.GetFiles` (และอาจใช้ `GetDirectories` สำหรับการทำซ้ำ).  
2. **สร้าง `FileInfo`** สำหรับไฟล์ที่ค้นพบแต่ละไฟล์.  
3. **เรียก `CreateEntry`** ด้วยเส้นทางสัมพันธ์ที่รวมชื่อโฟลเดอร์, เช่น `"MyFolder/Report.pdf"`.

เนื่องจาก API ทำงานกับ `FileInfo`, คุณไม่จำเป็นต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ทำให้ปลอดภัยสำหรับไดเรกทอรีขนาดใหญ่ เทคนิคนี้ยังทำงานได้ในสถานการณ์ **zip multiple files asp.net** ที่คุณสร้างชุดรายงานแบบเรียลไทม์และต้องส่งเป็น archive เดียว.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **ไฟล์ zip ว่าง** | `FileInfo` ชี้ไปยังเส้นทางที่ไม่มีอยู่ | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้ `File.Exists` เพื่อตรวจสอบก่อนสร้างรายการ. |
| **การเข้ารหัสชื่อไฟล์ไม่ถูกต้อง** | ใช้การเข้ารหัสเริ่มต้นกับชื่อที่ไม่ใช่ ASCII | ตั้งค่า `Encoding = Encoding.UTF8` ใน `ArchiveSaveOptions`. |
| **OutOfMemoryException บนไฟล์ขนาดใหญ่** | โหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ | `FileInfo` สตรีมไฟล์; ตรวจสอบว่าคุณไม่ได้อ่านไฟล์เป็นอาร์เรย์ไบต์ที่อื่น. |
| **Permission denied** | แอปไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกไดเรกทอรีที่เขียนได้. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถเพิ่มการป้องกันด้วยรหัสผ่านให้กับ zip archive ได้หรือไม่?**  
ตอบ: ได้. หลังจากสร้าง `Archive`, ตั้งค่า `archive.Password = "yourPassword"` ก่อนเรียก `Save`.

**ถาม: สามารถอัปเดตไฟล์ zip ที่มีอยู่ได้หรือไม่?**  
ตอบ: Aspose.Zip รองรับการเปิด archive ที่มีอยู่ด้วย `Archive.Open` แล้วเพิ่มรายการใหม่.

**ถาม: ฉันจะบีบอัดไฟล์ในคอนโทรลเลอร์ ASP.NET MVC อย่างไร?**  
ตอบ: โค้ดเดียวกันทำงานได้; เพียงให้แน่ใจว่าสตรีมผลลัพธ์ถูกส่งกลับเป็น `FileResult` ให้กับไคลเอนต์.

**ถาม: Aspose.Zip รองรับอัลกอริทึมการเข้ารหัสหรือไม่?**  
ตอบ: รองรับ ZipCrypto มาตรฐานและการเข้ารหัส AES‑256.

**ถาม: ถ้าฉันต้องการบีบอัดโฟลเดอร์แบบเรียกซ้ำลึก (recursive) จะทำอย่างไร?**  
ตอบ: วนลูปผ่าน `Directory.GetFiles` (และโฟลเดอร์ย่อย) แล้วสร้าง `FileInfo` สำหรับแต่ละไฟล์, จากนั้นเพิ่มเข้า archive.

## คำถามเพิ่มเติม

**ถาม: ฉันจะสร้าง zip archive .net สำหรับชุดข้อมูลขนาดใหญ่ได้อย่างไร?**  
ตอบ: ใช้ `FileInfo` เพื่อสตรีมข้อมูลและตั้งค่า `CompressionLevel` ใน `ArchiveSaveOptions` เพื่อประสิทธิภาพที่ดีที่สุด.

**ถาม: ฉันสามารถใช้ Aspose.Zip ใน .NET Core web API (zip files asp.net core) ได้หรือไม่?**  
ตอบ: แน่นอน – ไลบรารีเข้ากันได้เต็มที่กับ .NET Core 3.1 ขึ้นไป.

**ถาม: มีวิธีเพิ่มโฟลเดอร์ลงใน zip โดยไม่ต้องเขียนลูปกำหนดเองหรือไม่?**  
ตอบ: Aspose.Zip ไม่มีเมธอด “add folder” เดียว, แต่การวนลูปด้วย `DirectoryInfo` มีน้ำหนักเบาและให้การควบคุมเต็มที่ต่อชื่อรายการ.

**ถาม: การป้องกันด้วยรหัสผ่านของ zip archive มีผลต่อความเร็วการบีบอัดหรือไม่?**  
ตอบ: การเปิดใช้งานการเข้ารหัสเพิ่มภาระเล็กน้อย, แต่ผลกระทบโดยรวมน้อยสำหรับการใช้งานส่วนใหญ่.

**ถาม: ต้องการไลเซนส์แบบใดสำหรับการใช้งานเชิงพาณิชย์?**  
ตอบ: จำเป็นต้องมีไลเซนส์ Aspose.Zip แบบชำระเงินสำหรับการผลิต; รุ่นทดลองฟรีสามารถใช้สำหรับการพัฒนาและทดสอบ.

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

ตอนนี้คุณรู้แล้วว่า **วิธีเพิ่มโฟลเดอร์ลงใน zip** และ **วิธีสร้างไฟล์ zip archive** ด้วย Aspose.Zip สำหรับ .NET, วิธี **เพิ่มไฟล์ลงใน zip**, และทำไมวิธีนี้จึงเหมาะกับ ASP.NET และแอปพลิเคชัน .NET อื่น ๆ ทดลองใช้ระดับการบีบอัด, การเข้ารหัส, และตัวเลือกการเข้ารหัสต่าง ๆ เพื่อปรับ archive ให้ตรงกับความต้องการของคุณ. ขอให้สนุกกับการบีบอัด!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}