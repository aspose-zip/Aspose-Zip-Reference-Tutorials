---
date: 2025-12-18
description: เรียนรู้วิธีเข้ารหัสไฟล์ zip ด้วยรหัสผ่านที่แตกต่างกันโดยใช้ Aspose.Zip
  สำหรับ .NET คู่มือนี้จะแสดงวิธีบีบอัดไฟล์ด้วยรหัสผ่านและสร้างไฟล์ 7z ใน C#
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีเข้ารหัสไฟล์ ZIP ด้วยรหัสผ่านที่แตกต่างกันใน Aspose.Zip สำหรับ .NET
url: /th/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการเข้ารหัสไฟล์ ZIP ด้วยรหัสผ่านที่แตกต่างกันใน Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **วิธีการเข้ารหัส zip** ไฟล์อาร์ไคฟ์โดยให้แต่ละรายการมีรหัสผ่านของตนเอง คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อสร้างไฟล์ 7‑zip ที่แต่ละไฟล์ได้รับการปกป้องด้วยรหัสผ่านที่เป็นเอกลักษณ์โดยใช้ไลบรารี Aspose.Zip สำหรับ .NET เมื่อเสร็จสิ้นคุณจะเข้าใจว่าทำไมการเข้ารหัสต่อรายการจึงสำคัญ วิธีการตั้งค่า และวิธีตรวจสอบผลลัพธ์ในโครงการของคุณเอง

## คำตอบอย่างรวดเร็ว
- **“encrypt zip” หมายถึงอะไร?** หมายถึงการใช้การปกป้องด้วยรหัสผ่าน (AES หรือ ZipCrypto) กับเนื้อหาของไฟล์ ZIP/7z.  
- **แต่ละรายการสามารถมีรหัสผ่านที่แตกต่างกันได้หรือไม่?** ได้—Aspose.Zip ให้คุณกำหนดรหัสผ่านที่แตกต่างกันต่อไฟล์.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** ทั้ง .NET Framework, .NET Core, และ .NET 5/6 รุ่นใหม่ทั้งหมด.  
- **ต้องใช้ไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์; มีการทดลองใช้ฟรี.  
- **รูปแบบการบีบอัดที่ใช้ในตัวอย่างคืออะไร?** ตัวอย่างสร้างไฟล์ 7z พร้อมการเข้ารหัส AES‑256.

## “how to encrypt zip” คืออะไรกับ Aspose.Zip?

การเข้ารหัสไฟล์ ZIP (หรือ 7z) หมายถึงการทำให้รายการต่าง ๆ ภายในไฟล์ไม่สามารถเปิดได้หากไม่มีรหัสผ่านที่ถูกต้อง Aspose.Zip สำหรับ .NET รองรับทั้ง ZipCrypto แบบคลาสสิกและการเข้ารหัส AES ที่แข็งแกร่งกว่า และยังอนุญาตให้คุณกำหนดการตั้งค่าการเข้ารหัสต่อรายการ ทำให้คุณควบคุมความปลอดภัยได้อย่างละเอียด

## ทำไมต้องใช้รหัสผ่านที่แตกต่างกันสำหรับแต่ละรายการ?

- **การแบ่งส่วนความปลอดภัย:** หากรหัสผ่านหนึ่งถูกเปิดเผย ไฟล์อื่น ๆ ยังคงได้รับการปกป้อง.  
- **การปฏิบัติตามกฎระเบียบ:** บางอุตสาหกรรมต้องการข้อมูลประจำตัวแยกต่างหากสำหรับหมวดข้อมูลที่ต่างกัน.  
- **การเข้าถึงตามผู้ใช้:** คุณสามารถแจกจ่ายไฟล์เก็บเดียวให้หลายผู้ใช้ แต่ละคนจะสามารถปลดล็อกเฉพาะไฟล์ที่ได้รับอนุญาตให้ดูเท่านั้น.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มทำตามขั้นตอน โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** ที่ติดตั้งแล้ว – ดู [documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการสำหรับคำแนะนำการดาวน์โหลดและการติดตั้ง.  
- โฟลเดอร์บนเครื่องของคุณที่คุณจะเก็บไฟล์ต้นทาง (เรียกว่า “Document Directory”).  
- ความคุ้นเคยพื้นฐานกับ C# และ Visual Studio (หรือ IDE .NET ที่คุณชื่นชอบ).

## นำเข้า Namespaces

เราจะเริ่มโดยการดึง Namespaces ที่มีคลาสที่เราต้องการใช้.

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

กำหนดเส้นทางที่เก็บไฟล์ที่คุณต้องการบีบอัด.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างรายการด้วยรหัสผ่านที่แตกต่างกัน

นี่คือหัวใจของบทแนะนำ เราจะเปิดไฟล์ 7z ใหม่ สร้างอ็อบเจ็กต์ `FileInfo` จำนวนสามตัว และเพิ่มแต่ละไฟล์เป็นรายการพร้อมรหัสผ่าน AES ของตนเอง.

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

- `SevenZipArchive` เป็นคอนเทนเนอร์สำหรับไฟล์ 7‑z.  
- `CreateEntry` รับชื่อรายการ, ไฟล์ต้นทาง, ธงการเขียนทับ, และอ็อบเจ็กต์ `SevenZipEntrySettings`.  
- ภายใน `SevenZipEntrySettings` เราให้สองอ็อบเจ็กต์ตั้งค่า: หนึ่งสำหรับการบีบอัด (`SevenZipStoreCompressionSettings`) และหนึ่งสำหรับการเข้ารหัส (`SevenZipAESEncryptionSettings`).  
- แต่ละการเรียกใช้จะระบุ **รหัสผ่านที่แตกต่างกัน** (`"test1"`, `"test2"`, `"test3"`), ทำให้แต่ละรายการได้รับการปกป้องแยกกัน.

## ขั้นตอนที่ 3: การตรวจสอบ

หลังจากบันทึกไฟล์เก็บแล้ว คุณสามารถแสดงข้อความยืนยันง่าย ๆ ได้.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

เรียกใช้โปรแกรม จากนั้นลองเปิด `archive.7z` ด้วยเครื่องมือเช่น 7‑Zip โปรแกรมจะขอรหัสผ่านสำหรับแต่ละรายการ ยืนยันว่ารหัสผ่านต่างกันจริง ๆ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ข้อผิดพลาดรหัสผ่านไม่ถูกต้อง** | สตริงรหัสผ่านมีช่องว่างหรืออักขระที่มองไม่เห็นอยู่ | ตัดช่องว่างออกจากสตริงรหัสผ่าน (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **ไม่สามารถเปิดไฟล์เก็บในเครื่องมือเก่า** | เครื่องมือ ZIP เก่าบางตัวไม่รองรับการเข้ารหัส AES‑256 ที่ใช้ใน 7z. | ใช้โปรแกรมสกัดไฟล์สมัยใหม่ (7‑Zip 19.00+). |
| **ไฟล์ไม่ถูกเพิ่มเข้าไปในไฟล์เก็บ** | เส้นทางไฟล์ต้นทางผิดหรือไฟล์ไม่มีอยู่ | ตรวจสอบ `dataDir` และชื่อไฟล์ หรือใช้ `Path.Combine(dataDir, "data1.bin")`. |

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Zip for .NET รองรับทุกเวอร์ชันของ .NET หรือไม่?

**A1:** ใช่, Aspose.Zip for .NET ถูกออกแบบให้ทำงานร่วมกับทุกเวอร์ชันของ .NET Framework อย่างไม่มีปัญหา.

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Zip for .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่?

**A2:** แน่นอน! Aspose.Zip for .NET มีไลเซนส์เชิงพาณิชย์ และคุณสามารถดูข้อมูลเพิ่มเติมเกี่ยวกับการซื้อได้ [ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 3: มีการทดลองใช้ฟรีหรือไม่?

**A3:** มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.Zip for .NET ด้วยการทดลองใช้ฟรี. เริ่มต้นได้ [ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Zip for .NET ได้อย่างไร?

**A4:** สำหรับคำถามหรือความช่วยเหลือใด ๆ โปรดเยี่ยมชม [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### คำถามที่ 5: ฉันสามารถใช้ Aspose.Zip for .NET ได้โดยไม่มีไลเซนส์ถาวรหรือไม่?

**A5:** ได้, คุณสามารถขอรับไลเซนส์ชั่วคราวสำหรับความต้องการระยะสั้นของคุณ. ดูรายละเอียดเพิ่มเติม [ที่นี่](https://purchase.aspose.com/temporary-license/).

## สรุป

คุณได้เรียนรู้ **วิธีการเข้ารหัส zip** ด้วยรหัสผ่านต่อรายการโดยใช้ Aspose.Zip สำหรับ .NET เทคนิคนี้ให้ความยืดหยุ่นในการปกป้องแต่ละไฟล์แยกกัน เพื่อตอบสนองข้อกำหนดความปลอดภัยที่เข้มงวดและทำให้การแจกจ่ายตามผู้ใช้เป็นเรื่องง่าย อย่าลังเลที่จะทดลองตั้งค่าการบีบอัดอื่น ๆ ชุดไฟล์ขนาดใหญ่กว่า หรือรวมตรรกะนี้เข้าไปในเว็บเซอร์วิสที่สร้างไฟล์เก็บที่ปลอดภัยแบบเรียลไทม์

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}