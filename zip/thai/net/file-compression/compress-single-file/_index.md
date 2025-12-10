---
date: 2025-12-09
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน zip และบีบอัดไฟล์ด้วย .NET โดยใช้ Aspose.Zip.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างไฟล์ zip ด้วย C# อย่างรวดเร็ว.
linktitle: Compressing a Single File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีเพิ่มไฟล์ลงใน Zip ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/file-compression/compress-single-file/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน Zip ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในงานพัฒนา .NET สมัยใหม่ การ **เพิ่มไฟล์ลงใน zip** อย่างมีประสิทธิภาพสามารถลดค่าใช้จ่ายในการจัดเก็บและปรับปรุงเวลาในการดาวน์โหลดได้อย่างมาก Aspose.Zip สำหรับ .NET มี API ที่สะอาดและมีประสิทธิภาพสูงที่ทำให้คุณ **compress file .NET** โครงการได้ด้วยเพียงไม่กี่บรรทัดของโค้ด ในบทแนะนำนี้ เราจะพาคุณผ่านตัวอย่างเต็มรูปแบบแบบทำมือที่แสดงวิธีสร้างไฟล์ zip สไตล์ C# ด้วยวิธีการที่อิง `FileStream`  

## คำตอบด่วน
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET
- **ฉันสามารถเพิ่มไฟล์ลงใน zip ด้วยบรรทัดเดียวของโค้ดได้หรือไม่?** ใช่ – `archive.CreateEntry(...)` ทำหน้าที่หลัก
- **ฉันต้องการลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานจริง
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7
- **ปลอดภัยสำหรับไฟล์ขนาดใหญ่หรือไม่?** ใช่, ไลบรารีสตรีมข้อมูล, ทำให้การใช้หน่วยความจำต่ำ  

## “เพิ่มไฟล์ลงใน zip” ใน Aspose.Zip คืออะไร?

การเพิ่มไฟล์ลงในอาร์ไคฟ์ zip หมายถึงการนำไฟล์ที่มีอยู่บนดิสก์ (หรือในหน่วยความจำ) แล้วเขียนลงในคอนเทนเนอร์ที่บีบอัดตามสเปคไฟล์ ZIP Aspose.Zip จัดการรายละเอียดระดับต่ำให้คุณโฟกัสที่ตรรกะธุรกิจแทนการคำนวณ checksum หรืออัลกอริทึมการบีบอัด  

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?

- **ประสิทธิภาพสูง**: สตรีมข้อมูลโดยตรง, หลีกเลี่ยงบัฟเฟอร์ชั่วคราว.
- **ชุดคุณสมบัติครบครัน**: รองรับการเข้ารหัส, แบ่งไฟล์อาร์ไคฟ์, และการตั้งค่ารายการแบบกำหนดเอง.
- **API ง่าย**: การสร้างรายการด้วยบรรทัดเดียว (`CreateEntry`) ลดโค้ดซ้ำซ้อน.
- **ข้ามแพลตฟอร์ม**: ทำงานบน Windows, Linux, macOS กับ .NET Core/5+.  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ตรวจสอบให้คุณมี:

- ความรู้พื้นฐานของการเขียนโปรแกรม C#.
- ติดตั้ง Visual Studio (หรือ IDE .NET ที่คุณชื่นชอบ).
- ไลบรารี Aspose.Zip สำหรับ .NET, สามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/zip/net/)**.  

## นำเข้า Namespaces

ก่อนอื่น ให้รวม namespaces ที่จำเป็นในไฟล์ C# ของคุณ:

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

การนำเข้าเหล่านี้ทำให้คุณเข้าถึงคลาส `Archive`, ยูทิลิตี้การทำ I/O ของไฟล์, และตัวเลือกการบันทึก  

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ

กำหนดโฟลเดอร์ที่มีไฟล์ต้นทางที่คุณต้องการบีบอัด แทนที่ตัวแปร placeholder ด้วยพาธจริงบนเครื่องของคุณ

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` สำหรับพาธที่ไม่ขึ้นกับแพลตฟอร์ม, เช่น `Path.Combine(dataDir, "alice29.txt")`.  

## ขั้นตอนที่ 2: สร้างไฟล์ Zip โดยใช้ FileStream

เปิด `FileStream` ที่ชี้ไปยังไฟล์ ZIP ผลลัพธ์ นี้เป็นการสาธิตเทคนิค **zip file using filestream**

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressSingleFile_out.zip", FileMode.Create))
```

คำสั่ง `using` รับประกันว่าการสตรีมจะถูกปิดและไฟล์จะถูก flush อย่างถูกต้อง  

## ขั้นตอนที่ 3: เพิ่มไฟล์ลงในอาร์ไคฟ์

ตอนนี้เปิดไฟล์ต้นทาง (`alice29.txt`) แล้วเพิ่มลงในอาร์ไคฟ์ นี่คือหัวใจของการทำ **c# compress file zip**

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (var archive = new Archive(new ArchiveEntrySettings()))
    {
        archive.CreateEntry("alice29.txt", source1);

        // Save the archive
        archive.Save(zipFile);
    }
}
```

### วิธีการทำงานของโค้ด
- **การตั้งค่า FileStream** – สร้างการเชื่อมต่อกับไฟล์ ZIP ผลลัพธ์.
- **CreateEntry** – รับสตรีมต้นทาง (`source1`) และเขียนลงในอาร์ไคฟ์ภายใต้ชื่อ `"alice29.txt"`.
- **Save** – บันทึกข้อมูลที่บีบอัดลงใน `CompressSingleFile_out.zip`.

คุณสามารถทำซ้ำการเรียก `CreateEntry` สำหรับไฟล์เพิ่มเติม เพื่อเปลี่ยนสคริปต์นี้ให้เป็น **zip archive tutorial c#** ฉบับเต็ม  

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไฟล์ไม่พบ** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบสตริงของไดเรกทอรีหรือใช้ `Path.GetFullPath` เพื่อดีบัก |
| **การเข้าถึงถูกปฏิเสธ** | สิทธิ์ไฟล์ไม่เพียงพอ | รัน Visual Studio ด้วยสิทธิ์ผู้ดูแลหรือให้สิทธิ์การเขียนกับโฟลเดอร์ |
| **ไฟล์ zip ว่างเปล่า** | `archive.Save` ถูกเรียกนอกบล็อก `using` | ตรวจสอบให้แน่ใจว่า `archive.Save(zipFile);` อยู่ภายในบล็อก `using` ภายในตามที่แสดง |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถบีบอัดหลายไฟล์ในอาร์ไคฟ์เดียวโดยใช้ Aspose.Zip สำหรับ .NET ได้หรือไม่?

A1: แน่นอน! คุณสามารถปรับโค้ดที่ให้ไว้เพื่อบีบอัดหลายไฟล์โดยเพิ่มการเรียก `CreateEntry` เพิ่มเติมก่อนเมธอด `Save`.

### Q2: ฉันจะหาเอกสารประกอบที่ครอบคลุมสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน?

A2: สำรวจ **[documentation](https://reference.aspose.com/zip/net/)** เพื่อรับข้อมูลเชิงลึกเกี่ยวกับความสามารถของ Aspose.Zip.

### Q3: มีการทดลองใช้ฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?

A3: มี, คุณสามารถรับ **[free trial](https://releases.aspose.com/)** เพื่อสำรวจฟีเจอร์ก่อนทำการซื้อ.

### Q4: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?

A4: เยี่ยมชม **[this link](https://purchase.aspose.com/temporary-license/)** เพื่อขอรับลิขสิทธิ์ชั่วคราวสำหรับการพัฒนาของคุณ.

### Q5: ฉันจะหาการสนับสนุนหรือเชื่อมต่อกับชุมชนของ Aspose.Zip สำหรับ .NET ได้ที่ไหน?

A5: เข้าร่วมชุมชน Aspose.Zip บน **[support forum](https://forum.aspose.com/c/zip/37)** เพื่อรับความช่วยเหลือจากผู้เชี่ยวชาญและนักพัฒนาคนอื่นๆ.

## สรุป

โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **เพิ่มไฟล์ลงใน zip** อย่างมีประสิทธิภาพ, **compress file .NET** โครงการ, และสร้างอาร์ไคฟ์ zip ที่แข็งแรงด้วย Aspose.Zip ลองใช้ไฟล์ขนาดใหญ่, ตัวเลือกการเข้ารหัส, หรืออาร์ไคฟ์แบบแบ่งเพื่อใช้ประโยชน์สูงสุดจากพลังของไลบรารีนี้

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}