---
date: 2025-12-01
description: เรียนรู้วิธีการแตกไฟล์ zip ที่มีรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET
  พร้อมจัดการรายการที่มีการป้องกันด้วยรหัสผ่านหลายรายการอย่างมีประสิทธิภาพ
language: th
linktitle: Extracting Archive Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีการแตกไฟล์ Zip ด้วยรหัสผ่านโดยใช้ Aspise.Zip สำหรับ .NET
url: /net/archive-extraction-and-formats/extract-archive-different-passwords/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ Zip ด้วยรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET

ในแอปพลิเคชัน .NET สมัยใหม่ การปกป้องข้อมูลที่สำคัญภายในไฟล์ ZIP เป็นความต้องการทั่วไป บทแนะนำนี้แสดง **วิธีการแยกไฟล์ zip ด้วยรหัสผ่าน** เมื่อแต่ละรายการใช้รหัสผ่านที่แตกต่างกัน ให้คุณควบคุมความปลอดภัยอย่างละเอียดพร้อมกระบวนการแยกไฟล์ที่ง่ายดาย

## คำตอบด่วน
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET.
- **ฉันสามารถแยกรายการที่มีรหัสผ่านต่างกันได้หรือไม่?** ได้—แต่ละรายการสามารถเปิดด้วยรหัสผ่านของตัวเอง
- **ต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์; มีรุ่นทดลองฟรี
- **แพลตฟอร์มที่รองรับ?** .NET Framework, .NET Core, .NET 5/6+.
- **เวลาในการทำงานโดยประมาณ?** ประมาณ 10 นาทีสำหรับสถานการณ์พื้นฐาน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** ที่ติดตั้งในโปรเจคของคุณ คุณสามารถค้นหาเอกสารอย่างเป็นทางการได้ [ที่นี่](https://reference.aspose.com/zip/net/).
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, Rider หรือ VS Code) ที่กำหนดเป้าหมายเป็น .NET 5 หรือใหม่กว่า.
- ไฟล์ ZIP ที่มีรายการเข้ารหัสด้วย **รหัสผ่านที่แตกต่างกัน** (ตัวอย่างที่ใช้ในที่นี้คือ `different_password.zip`).

## นำเข้า Namespaces

ขั้นแรก ให้นำเข้า namespaces ที่จำเป็นสำหรับการทำงานกับ archive:

```csharp
using Aspose.Zip;
using System.IO;
```

คำสั่ง `using` ทั้งสองนี้ทำให้คุณเข้าถึงคลาส `Archive` และยูทิลิตี้ I/O มาตรฐาน

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีทำงาน

กำหนดโฟลเดอร์ที่ไฟล์ ZIP อยู่และที่ไฟล์ที่แยกออกจะถูกเขียนไปยัง:

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` สำหรับการสร้างเส้นทางแบบข้ามแพลตฟอร์ม หากคุณต้องการสนับสนุน Linux/macOS.

## ขั้นตอนที่ 2: แยกรายการ Archive ด้วยรหัสผ่านที่แตกต่างกัน

ด้านล่างนี้ เราจะอธิบายขั้นตอนที่แน่นอนเพื่อเปิด archive และแยกรายการแต่ละรายการโดยใช้รหัสผ่านของตัวเอง.

### ขั้นตอน 2.1: เปิดไฟล์ Zip

```csharp
using (FileStream zipFile = File.Open(dataDir + "\\different_password.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
        // Continue to the next steps...
    }
}
```

อ็อบเจ็กต์ `Archive` แทนคอนเทนเนอร์ ZIP การเก็บ `FileStream` และ `Archive` ไว้ภายในบล็อก `using` จะทำให้แน่ใจว่าทรัพยากรทั้งหมดถูกปล่อยออกอย่างทันท่วงที.

### ขั้นตอน 2.2: แยกรายการแรก (รหัสผ่าน = “first_pass”)

```csharp
archive.Entries[0].Extract(dataDir + "alice29_extracted_pass_out.txt", "first_pass");
```

ที่นี่เราจะ **แยกรายการ zip หลายรายการ** โดยอ้างอิงผ่านคอลเลกชัน `Entries` รายการแรกจะถูกถอดรหัสด้วยรหัสผ่าน `"first_pass"`.

### ขั้นตอน 2.3: แยกรายการที่สอง (รหัสผ่าน = “second_pass”)

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_pass_out.txt", "second_pass");
```

รายการที่สองใช้รหัสผ่านที่แตกต่างกัน แสดงให้เห็น **การแยกไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** สำหรับแต่ละไฟล์แยกกัน.

## ทำไมวิธีนี้ถึงสำคัญ

- **ความปลอดภัยระดับละเอียด:** แต่ละไฟล์สามารถมีรหัสผ่านของตัวเอง ลดความเสี่ยงหากรหัสผ่านเดียวถูกเปิดเผย.
- **ความยืดหยุ่น:** คุณสามารถกำหนดรหัสผ่านที่ใช้ได้โดยโปรแกรมตามตรรกะธุรกิจ (เช่น บทบาทผู้ใช้).
- **ประสิทธิภาพ:** Aspose.Zip ประมวลผลรายการในหน่วยความจำ ทำให้ไม่ต้องแตกไฟล์ archive ทั้งหมดก่อน.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| *“Invalid password” exception* | รหัสผ่านที่ให้ผิดหรือรายการไม่ได้ถูกเข้ารหัสจริง. | ตรวจสอบสตริงรหัสผ่านและยืนยันว่ารายการถูกป้องกันด้วยรหัสผ่าน. |
| *File not found* | เส้นทาง `dataDir` ไม่ถูกต้อง. | ใช้ `Path.Combine(dataDir, "different_password.zip")` และตรวจสอบโฟลเดอร์อีกครั้ง. |
| *Large archives cause high memory usage* | รายการทั้งหมดถูกโหลดเข้าสู่หน่วยความจำโดยค่าเริ่มต้น. | สตรีมแต่ละรายการแยกกันหรือใช้ `Archive.ExtractToDirectory` พร้อม callback รหัสผ่าน (หากรองรับ). |

## คำถามที่พบบ่อย

**Q1: ฉันสามารถใช้ Aspose.Zip ในโปรเจค .NET Core และ .NET Framework ได้หรือไม่?**  
A1: ใช่, Aspose.Zip รองรับ .NET Framework, .NET Core, และ .NET 5/6+ ทำให้คุณมีความยืดหยุ่นข้ามแพลตฟอร์ม.

**Q2: ฉันสามารถหาแหล่งสนับสนุนเพิ่มเติมหรือการสนทนาชุมชนที่เกี่ยวกับ Aspose.Zip ได้จากที่ไหน?**  
A2: เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อเข้าร่วมกับชุมชน, ถามคำถาม, และแบ่งปันประสบการณ์.

**Q3: มีรุ่นทดลองฟรีสำหรับ Aspose.Zip หรือไม่?**  
A3: มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Zip ได้ [ที่นี่](https://releases.aspose.com/).

**Q4: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A4: สำหรับไลเซนส์ชั่วคราว, เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/).

**Q5: ฉันสามารถซื้อ Aspose.Zip ได้จากที่ไหน?**  
A5: เพื่อซื้อ Aspose.Zip, เยี่ยมชม [หน้าการซื้อ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-01  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.11 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose