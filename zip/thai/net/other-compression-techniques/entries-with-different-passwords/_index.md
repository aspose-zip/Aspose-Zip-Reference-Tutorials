---
date: 2026-02-28
description: เรียนรู้วิธีบีบอัดไฟล์ด้วยรหัสผ่านและเข้ารหัสไฟล์ ZIP โดยใช้ Aspose.Zip
  สำหรับ .NET รวมถึงการป้องกันด้วยรหัสผ่านสำหรับไฟล์ 7z และการตั้งรหัสผ่านแยกไฟล์ใน
  ZIP ด้วย C#
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดไฟล์ด้วยรหัสผ่านและเข้ารหัสรายการ ZIP ด้วยรหัสผ่านที่แตกต่างกันโดยใช้
  Aspose.Zip สำหรับ .NET
url: /th/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดไฟล์ด้วยรหัสผ่านและเข้ารหัสรายการ ZIP ด้วยรหัสผ่านที่แตกต่างกันโดยใช้ Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **บีบอัดไฟล์ด้วยรหัสผ่าน** และกำหนดรหัสผ่านให้แต่ละรายการ คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อสร้างไฟล์ 7‑zip ที่แต่ละไฟล์ได้รับการปกป้องด้วยรหัสผ่านที่ไม่ซ้ำกันโดยใช้ไลบรารี Aspose.Zip สำหรับ .NET เมื่อเสร็จสิ้นคุณจะเข้าใจว่าการเข้ารหัสแบบต่อรายการสำคัญอย่างไร วิธีตั้งค่า และวิธีตรวจสอบผลลัพธ์ในโครงการของคุณ

## คำตอบอย่างรวดเร็ว
- **What does “encrypt zip” mean?** หมายถึงการใช้การปกป้องด้วยรหัสผ่าน (AES หรือ ZipCrypto) กับเนื้อหาของไฟล์ ZIP/7z archive.  
- **Can each entry have a different password?** ใช่ — Aspose.Zip ให้คุณกำหนดรหัสผ่านที่แตกต่างกันต่อไฟล์.  
- **Which .NET versions are supported?** รองรับ .NET Framework, .NET Core, และ .NET 5/6 เวอร์ชันล่าสุดทั้งหมด.  
- **Do I need a license for production?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้.  
- **What compression format is used in the example?** ตัวอย่างสร้างไฟล์ 7z ด้วยการเข้ารหัส AES‑256.

## วิธีบีบอัดไฟล์ด้วยรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET
ในส่วนนี้เราจะตอบคำถามหลักโดยตรงและเตรียมพื้นฐานสำหรับคู่มือขั้นตอนต่อไป

## “how to encrypt zip” คืออะไรกับ Aspose.Zip?
การเข้ารหัสไฟล์ ZIP (หรือ 7z) หมายถึงการปกป้องรายการภายในเพื่อไม่ให้เปิดได้หากไม่มีรหัสผ่านที่ถูกต้อง Aspose.Zip สำหรับ .NET รองรับทั้ง ZipCrypto แบบคลาสสิกและการเข้ารหัส AES ที่แข็งแกร่งกว่า และอนุญาตให้คุณกำหนดการตั้งค่าการเข้ารหัสต่อรายการ ทำให้คุณควบคุมความปลอดภัยได้อย่างละเอียด

## ทำไมต้องใช้รหัสผ่านที่แตกต่างกันสำหรับแต่ละรายการ?
- **Security segmentation:** หากรหัสผ่านหนึ่งถูกเปิดเผย ไฟล์อื่น ๆ ยังคงได้รับการปกป้อง.  
- **Regulatory compliance:** บางอุตสาหกรรมต้องการข้อมูลรับรองแยกกันสำหรับประเภทข้อมูลที่ต่างกัน.  
- **User‑specific access:** คุณสามารถแจกจ่ายไฟล์อาร์ไคฟ์เดียวให้หลายผู้ใช้ แต่ละคนจะเปิดได้เฉพาะไฟล์ที่ได้รับอนุญาตเท่านั้น.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** ติดตั้งแล้ว – ดูที่ [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับขั้นตอนการดาวน์โหลดและติดตั้ง.  
- โฟลเดอร์บนเครื่องของคุณที่ใช้เก็บไฟล์ต้นทาง (ที่เรียกว่า “Document Directory”).  
- ความคุ้นเคยพื้นฐานกับ C# และ Visual Studio (หรือ IDE .NET ที่คุณชื่นชอบ).

## นำเข้า Namespaces

เราเริ่มโดยการนำเข้า namespaces ที่มีคลาสที่จำเป็น

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory ของคุณ

กำหนดเส้นทางที่เก็บไฟล์ที่ต้องการบีบอัด

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างรายการด้วยรหัสผ่านที่แตกต่างกัน

นี่คือหัวใจของบทเรียน เราเปิดไฟล์ 7z ใหม่ สร้างอ็อบเจ็กต์ `FileInfo` จำนวนสามตัว และเพิ่มแต่ละไฟล์เป็นรายการพร้อมรหัสผ่าน AES ของตนเอง

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### วิธีการทำงาน

- `SevenZipArchive` คือคอนเทนเนอร์สำหรับอาร์ไคฟ์ 7‑z.  
- `CreateEntry` รับชื่อรายการ, ไฟล์ต้นทาง, ธงการเขียนทับ, และอ็อบเจ็กต์ `SevenZipEntrySettings`.  
- ภายใน `SevenZipEntrySettings` เราให้สองอ็อบเจ็กต์ตั้งค่า: หนึ่งสำหรับการบีบอัด (`SevenZipStoreCompressionSettings`) และหนึ่งสำหรับการเข้ารหัส (`SevenZipAESEncryptionSettings`).  
- แต่ละการเรียกใช้จะระบุ **รหัสผ่านที่แตกต่างกัน** (`"test1"`, `"test2"`, `"test3"`), ทำให้ได้การปกป้องต่อรายการ

## ขั้นตอนที่ 3: การตรวจสอบ

หลังจากบันทึกอาร์ไคฟ์แล้ว คุณสามารถแสดงข้อความยืนยันอย่างง่ายได้

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

เรียกใช้โปรแกรม แล้วลองเปิด `archive.7z` ด้วยเครื่องมือเช่น 7‑Zip ระบบจะขอรหัสผ่านสำหรับแต่ละรายการ ยืนยันว่ารหัสผ่านต่างกันจริง

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **Incorrect password error** | สตริงรหัสผ่านมีช่องว่างหรืออักขระที่มองไม่เห็น. | ตัดช่องว่างออกจากสตริงรหัสผ่าน (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archive not opening in older tools** | เครื่องมือ ZIP เก่าบางตัวไม่รองรับการเข้ารหัส AES‑256 ที่ใช้ใน 7z. | ใช้โปรแกรมสกัดไฟล์สมัยใหม่ (7‑Zip 19.00+). |
| **File not added to archive** | เส้นทางไฟล์ต้นทางผิดหรือไฟล์ไม่มีอยู่. | ตรวจสอบ `dataDir` และชื่อไฟล์, หรือใช้ `Path.Combine(dataDir, "data1.bin")`. |

## คำถามที่พบบ่อย

### Q1: Aspose.Zip สำหรับ .NET รองรับทุกเวอร์ชันของ .NET หรือไม่?

**A1:** ใช่, Aspose.Zip สำหรับ .NET ถูกออกแบบให้ทำงานร่วมกับทุกเวอร์ชันของ .NET framework อย่างไร้รอยต่อ.

### Q2: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่?

**A2:** แน่นอน! Aspose.Zip สำหรับ .NET มีลิขสิทธิ์เชิงพาณิชย์, และคุณสามารถดูข้อมูลเพิ่มเติมเกี่ยวกับการซื้อได้ที่ [here](https://purchase.aspose.com/buy).

### Q3: มีรุ่นทดลองฟรีให้ใช้หรือไม่?

**A3:** มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.Zip สำหรับ .NET ด้วยรุ่นทดลองฟรี. เริ่มต้นได้ที่ [here](https://releases.aspose.com/).

### Q4: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?

**A4:** สำหรับคำถามหรือความช่วยเหลือใด ๆ, เยี่ยมชม [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET โดยไม่มีลิขสิทธิ์ถาวรได้หรือไม่?

**A5:** ได้, คุณสามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับความต้องการระยะสั้นของคุณ. รายละเอียดเพิ่มเติมที่ [here](https://purchase.aspose.com/temporary-license/).

## สรุป

คุณได้เรียนรู้ **วิธีบีบอัดไฟล์ด้วยรหัสผ่าน** และเข้ารหัสอาร์ไคฟ์ ZIP ด้วยรหัสผ่านต่อรายการโดยใช้ Aspose.Zip สำหรับ .NET เทคนิคนี้ให้ความยืดหยุ่นในการปกป้องแต่ละไฟล์แยกกัน, ตอบสนองความต้องการด้านความปลอดภัยที่เข้มงวดและทำให้การแจกจ่ายตามผู้ใช้เป็นเรื่องง่าย อย่าลังเลที่จะทดลองตั้งค่าการบีบอัดอื่น ๆ, ชุดไฟล์ขนาดใหญ่กว่า, หรือรวมตรรกะนี้เข้าในเว็บเซอร์วิสที่สร้างอาร์ไคฟ์ปลอดภัยแบบอัตโนมัติ

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบกับ:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}