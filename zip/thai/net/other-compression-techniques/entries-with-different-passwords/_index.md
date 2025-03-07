---
title: รายการที่มีรหัสผ่านต่างกันใน Aspose.Zip สำหรับ .NET
linktitle: รายการที่มีรหัสผ่านต่างกัน
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: สำรวจพลังของ Aspose.Zip สำหรับ .NET ด้วยคำแนะนำทีละขั้นตอนเกี่ยวกับการจัดการไฟล์ ZIP ด้วยรหัสผ่านที่แตกต่างกัน เพิ่มความปลอดภัยและความยืดหยุ่นในแอปพลิเคชันของคุณ
weight: 13
url: /th/net/other-compression-techniques/entries-with-different-passwords/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รายการที่มีรหัสผ่านต่างกันใน Aspose.Zip สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่โลกของ Aspose.Zip สำหรับ .NET ซึ่งเป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการและจัดการไฟล์ ZIP ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกคุณลักษณะเฉพาะ: การทำงานกับรายการที่มีรหัสผ่านต่างกัน ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อปลดล็อกศักยภาพของ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำดิ่งสู่โลกที่น่าตื่นเต้นของการจัดการไฟล์ ZIP ด้วยรหัสผ่านที่แตกต่างกัน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว ถ้าไม่เช่นนั้น คุณสามารถค้นหาข้อมูลที่จำเป็นได้ใน[เอกสารประกอบ](https://reference.aspose.com/zip/net/).
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสารของคุณ
- ความรู้พื้นฐานของ C#: ความคุ้นเคยกับ C# จะเป็นประโยชน์เนื่องจากเราจะนำไปใช้ในการเขียนโค้ด

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชันการทำงานของ Aspose.Zip สำหรับ .NET ได้

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

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างรายการด้วยรหัสผ่านที่แตกต่างกัน

ตอนนี้ มาดูฟังก์ชันหลักในการสร้างรายการด้วยรหัสผ่านที่แตกต่างกันใน Aspose.Zip สำหรับ .NET กัน

```csharp
//ExStart: รายการด้วยรหัสผ่านที่แตกต่างกัน
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
//ตัวอย่าง: รายการด้วยรหัสผ่านที่แตกต่างกัน
```

## ขั้นตอนที่ 3: การยืนยัน

หลังจากรันโค้ดแล้ว ให้ตรวจสอบคอนโซลของคุณเพื่อให้แน่ใจว่าไฟล์ Seven Zip ที่มีการตั้งค่าการเข้ารหัส AES ถูกสร้างขึ้นสำเร็จแล้ว

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

## บทสรุป

ยินดีด้วย! ตอนนี้คุณเชี่ยวชาญศิลปะในการทำงานกับรายการที่มีรหัสผ่านต่างกันใน Aspose.Zip สำหรับ .NET แล้ว ความสามารถอันทรงพลังนี้เปิดประตูสู่การรักษาความปลอดภัยและความยืดหยุ่นที่เพิ่มขึ้นเมื่อจัดการไฟล์ ZIP ในแอปพลิเคชันของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Zip สำหรับ .NET เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่

ตอบ 1: ใช่ Aspose.Zip สำหรับ .NET ได้รับการออกแบบมาเพื่อผสานรวมกับ .NET Framework ทุกเวอร์ชันได้อย่างราบรื่น

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่

A2: แน่นอน! Aspose.Zip สำหรับ .NET เสนอใบอนุญาตเชิงพาณิชย์ และคุณสามารถค้นหาข้อมูลเพิ่มเติมเกี่ยวกับวิธีการซื้อได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 3: มีการทดลองใช้ฟรีหรือไม่?

 ตอบ 3: ได้ คุณสามารถสำรวจคุณสมบัติของ Aspose.Zip สำหรับ .NET ได้ด้วยการทดลองใช้ฟรี เริ่ม[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร

 A4: หากมีข้อสงสัยหรือความช่วยเหลือ โปรดไปที่[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37).

### คำถามที่ 5: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET โดยไม่มีใบอนุญาตถาวรได้หรือไม่

 A5: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับความต้องการระยะสั้นของคุณได้ ค้นหารายละเอียดเพิ่มเติม[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
