---
title: การเก็บถาวรอย่างปลอดภัยใน .NET ด้วย Aspose.Zip
linktitle: เก็บถาวรด้วยรายการที่เข้ารหัส
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: สำรวจโลกแห่งการเก็บถาวรที่ปลอดภัยใน .NET ด้วย Aspose.Zip สร้างไฟล์ Seven Zip ด้วยการเข้ารหัส AES ได้อย่างง่ายดาย เพิ่มทักษะการพัฒนาของคุณทันที!
type: docs
weight: 15
url: /th/net/password-protection-and-encryption/archive-with-encrypted-entry/
---

## การแนะนำ

ในโลกของการพัฒนาซอฟต์แวร์ที่มีการพัฒนาอยู่ตลอดเวลา การเรียนรู้เทคนิคการบีบอัดและการเข้ารหัสที่มีประสิทธิภาพถือเป็นสิ่งสำคัญ Aspose.Zip สำหรับ .NET กลายเป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์เก็บถาวรด้วยรายการที่เข้ารหัสได้อย่างราบรื่น ในบทช่วยสอนที่ครอบคลุมนี้ เราจะเจาะลึกกระบวนการสร้างไฟล์ Seven Zip ด้วยการตั้งค่าการเข้ารหัส AES โดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้นการเดินทางนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
-  Aspose.Zip สำหรับ .NET: ติดตั้งไลบรารี Aspose.Zip คุณสามารถค้นหาเอกสารที่จำเป็นได้[ที่นี่](https://reference.aspose.com/zip/net/).
-  ดาวน์โหลด: รับไลบรารี Aspose.Zip สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/zip/net/).
- ความรู้พื้นฐาน: ทำความคุ้นเคยกับแนวคิดพื้นฐานของการพัฒนา C# และ .NET

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ C# ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีทรัพยากร

```csharp
// เส้นทางไปยังไดเร็กทอรีทรัพยากร
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างไฟล์ Seven Zip ด้วยการเข้ารหัส AES

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ตัวอย่าง: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

คำอธิบาย: ในขั้นตอนนี้ เราสร้างไฟล์ Seven Zip ชื่อ "archive.7z" และเพิ่มรายการที่เข้ารหัส "entry1.bin" พร้อมข้อมูลตัวอย่าง การตั้งค่าการเข้ารหัสใช้อัลกอริธึม AES พร้อมคีย์ "test1"

ทำซ้ำขั้นตอนข้างต้นเพื่อดูรายการเพิ่มเติมหากจำเป็น

## บทสรุป

ยินดีด้วย! คุณสร้างไฟล์ Seven Zip ด้วยการตั้งค่าการเข้ารหัส AES โดยใช้ Aspose.Zip สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้ความเข้าใจพื้นฐานเกี่ยวกับวิธีการใช้งานการเก็บถาวรที่ปลอดภัยในโครงการ .NET ของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการที่ไม่ใช่เชิงพาณิชย์ได้หรือไม่
ใช่ Aspose.Zip สำหรับ .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และไม่ใช่เชิงพาณิชย์

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).

### มีการสนับสนุนจากชุมชนสำหรับ Aspose.Zip สำหรับ .NET หรือไม่
 ใช่แล้ว แวะมาที่.[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อสนับสนุนชุมชน

### มีอัลกอริธึมการบีบอัดอื่น ๆ ที่รองรับนอกเหนือจาก LZMA หรือไม่
Aspose.Zip สำหรับ .NET รองรับอัลกอริธึมการบีบอัดที่หลากหลาย โปรดดูเอกสารประกอบสำหรับรายละเอียด

### ฉันสามารถปรับแต่งการตั้งค่าการเข้ารหัสเพิ่มเติมได้หรือไม่
อย่างแน่นอน! สำรวจเอกสารประกอบสำหรับตัวเลือกการปรับแต่งการเข้ารหัสขั้นสูง

