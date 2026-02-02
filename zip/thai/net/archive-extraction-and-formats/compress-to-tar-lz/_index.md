---
date: 2026-02-02
description: เรียนรู้วิธีบีบอัดไฟล์ tar.lz ใน .NET ด้วย Aspose.Zip – คู่มือขั้นตอนต่อขั้นตอนในการบีบอัดไฟล์
  tar.lz อย่างง่ายดาย.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดไฟล์ tar.lz ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัด tar.lz ด้วย Aspose.Zip สำหรับ .NET

ในการพัฒนา .NET สมัยใหม่ การจัดแพ็กไฟล์อย่างมีประสิทธิภาพสามารถปรับปรุงขนาดการปรับใช้และเวลาในการถ่ายโอนเครือข่ายได้อย่างมาก **วิธีบีบอัด tar.lz** เป็นความต้องการทั่วไปเมื่อคุณต้องการไฟล์ TAR ที่บีบอัดด้วย LZ ที่มีน้ำหนักเบา ในบทแนะนำนี้เราจะอธิบายขั้นตอนอย่างชัดเจน **ตัวอย่างการบีบอัด tar.lz** โดยใช้ไลบรารี Aspose.Zip เพื่อให้คุณสามารถสร้างไฟล์ tar.lz ได้อย่างรวดเร็วในแอปพลิเคชันของคุณ

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET.  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับตัวอย่างพื้นฐาน.  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **สามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?** ได้ – เพียงเพิ่มรายการเพิ่มเติมก่อนบันทึก.

## tar.lz compression คืออะไร?
`tar.lz` คือไฟล์ TAR ที่ถูกบีบอัดด้วยอัลกอริทึม LZMA (มักเรียกสั้น ๆ ว่า **LZ**) มันรวมความเรียบง่ายของการจัดกลุ่มไฟล์ของ TAR กับอัตราการบีบอัดสูงของ LZ ทำให้เหมาะสำหรับไฟล์สำรอง, การแจกจ่ายแพ็กเกจ, หรือสถานการณ์ใด ๆ ที่แบนด์วิดท์เป็นสิ่งสำคัญ.

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?
Aspose.Zip abstracts the low‑level details of archive creation, giving you a clean, object‑oriented API. You get:

* **ไม่มีการพึ่งพาภายนอก** – การทำงานแบบ .NET แท้ ๆ.  
* **รองรับหลายแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS.  
* **บีบอัด LZ ในตัว** – ไม่ต้องติดตั้งเครื่องมือเนทีฟเพิ่มเติม.  
* **การจัดการข้อผิดพลาดที่แข็งแกร่ง** – ข้อยกเว้นมีรายละเอียด ช่วยให้การดีบักง่ายขึ้น.

## ข้อกำหนดเบื้องต้น
Before you start, make sure you have:

- **ไลบรารี Aspose.Zip for .NET** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบีบอัด. เส้นทางของโฟลเดอร์นี้จะถูกเก็บไว้ในตัวแปร `dataDir` (คุณจะตั้งค่าในขั้นตอนที่ 3).

## นำเข้า Namespaces
Add the required namespaces so the compiler knows where to find the classes we’ll use.

```csharp
using System;
using Aspose.Zip.Tar;
```

## วิธีบีบอัด tar.lz ด้วย Aspose.Zip – คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอน 1: สร้าง tar.lz archive – บีบอัดไฟล์เดียว
The first example shows the most basic scenario – adding one file to a TAR archive and then saving it as a **tar.lz** file.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**คำอธิบาย**

- `new TarArchive()` สร้างคอนเทนเนอร์ TAR ว่าง.  
- `CreateEntry` เพิ่มไฟล์ `alice29.txt` จาก `dataDir` ของคุณ.  
- `SaveLzipped` เขียน archive ไปยังดิสก์และใช้ `archive.tar.lz`.

### ขั้นตอน 2: บีบอัดหลายไฟล์ tar.l before saving.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**คำอธิบาย**

- โค้ดทำตามรูปแบบเดียวกับขั้นตอน 1 แต่เพิ่มรายการที่สอง (`lcet10.txt`).  
- คุณสามารถเรียก `CreateEntry` ซ้ำได้ตามต้องการ; ไลบรารีจะจัดการโครงสร้าง TAR ภายในโดยอัตโนมัติ.

### ขั้นตอน 3: ระบุไดเรกทอรีเอกสารของคุณ – สร.lz archive
Replace the placeholder with the actual path where your source files live. This path is used by the examples above.

```csharp
string dataDir = "Your Document Directory";
```

**คำอธิบาย**

- ตั้งค่า `dataDir` ให้เป็นเส้นทางโฟลเดอร์เต็มรูปแบบ เช่น `@"C:\MyFiles\"`.  
- การเก็บไดเรกทอรีในตัวแต่อการบำรุงรักษา.

## | วิธีแก้ไข |
|---------|--------------|-----|
| `FileNotFoundException` เมื่อรันตัวอย่าง | `dataDir` ชี้ไปยังโฟลเดสะกดผิด | ตรวจสอบเส้นทางและชื่อไฟล์; ใช้ `Path.Combine` เพื่อความปลอดภัย. |
| ไฟล์ผลลัพธ์เป็น **0 KB** | `archive.SaveLzipped` ถูกเรียกก่อนที่มีการเพิ่มรายการใด ๆ | ตรวจสอบให้มีการเรียก `บอัดดูช้า | ไฟล์ขนาดใหญ่พร้อมขนาดบัฟเฟอร์เริ่มต้น | พิจารณาประมวลผลไฟล์เป็นชิ้นส่วนหรือใช้ I/O แบบอะซิงโครนัสหากต้องการประสิทธิภาพสูง. |

## คำถามที่พบบ่อย

**Q:** ฉล์ขนาดใดก็ได้ด้วย Aspose.Zip สำหรับ .NET?  
**A:** ได้, ไลบรารีรองรับไฟล์ขนาดเล็กและขนาดใหญ่มาก; เพียงตรวจสอบว่ามีหน่วยความจำและพื้นที่ดิสก์เพียงพอสำหรับโครงสร้าง TAR ชั่วคราว.

**.Zip หรือไม่?  
**A:** ตัวอย่างนี้เกจ NuGet อย่างสม่ำเสมอเพื่อรับการแก้ไขบั๊กและฟีเจอร์ใหม่.

**Q:** มีข้อพิจารณาเรื่องไลเซนส์หรือไม่?  
**A:** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์. ดูรายละเอียดไลเซนส์ได้ที่ [Aspose website](https://purchase.aspose.com/buy).

**Q:** ฉันสามารถใช้สิ่งนี้ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** แน่นอน – เมื่อคุณมีไลเซนส์ที่ถูกต้อง, คุณสามารถฝังไลบรารีนี้ในแอปพลิเคชันเชิงพาณิชย์ใด ๆ.

**Q:** ฉันจะหาแนวทางช่วยเหลือได้จากที่ไหนหากเจอปัญหา?  
**A:** เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและความช่วยเหลืออย่างเป็นทางการ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-02-02  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

---