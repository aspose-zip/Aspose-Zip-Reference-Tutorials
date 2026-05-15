---
date: 2026-03-08
description: เรียนรู้วิธีสร้างไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่าน, ป้องกันโฟลเดอร์
  zip ด้วยรหัสผ่าน, และเปลี่ยนรหัสผ่านของ zip ด้วย Aspose.Zip สำหรับ .NET.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้างไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่านสำหรับไดเรกทอรี .NET – บทแนะนำ Aspose.Zip
url: /th/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่านสำหรับไดเรกทอรี .NET – Aspose.Zip Tutorial

ในคู่มือนี้คุณจะ **สร้างไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่าน** สำหรับไดเรกทอรีทั้งหมดโดยใช้ไลบรารี Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะต้องการ **เข้ารหัสโฟลเดอร์**, ปกป้องไฟล์สำรอง, หรือเพียงแค่จำกัดการเข้าถึงข้อมูลที่สำคัญ คู่มือขั้นตอนต่อขั้นตอนนี้จะแสดงให้คุณเห็นวิธีทำอย่างชัดเจนด้วยโค้ด C# ที่เรียบง่าย

## Quick Answers
- **ไลบรารีที่แนะนำคืออะไร?** Aspose.Zip for .NET  
- **ฉันสามารถเข้ารหัสโฟลเดอร์ทั้งหมดได้หรือไม่?** ใช่ – เพียงแค่ชี้ API ไปที่โฟลเดอร์ที่ต้องการบีบอัด  
- **การเปลี่ยนรหัสผ่านของ zip รองรับหรือไม่?** แน่นอน, ใช้ `TraditionalEncryptionSettings`  
- **ต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Zip ที่ถูกต้องสำหรับการใช้เชิงพาณิชย์  
- **ทำงานกับ .NET Core/5/6 หรือไม่?** ใช่, API เข้ากันได้อย่างเต็มที่กับรันไทม์ .NET สมัยใหม่  

## What is “create password protected zip”?
การสร้าง zip ที่มีการป้องกันด้วยรหัสผ่านหมายถึงการบีบอัดไฟล์หรือไดเรกทอรีเป็นไฟล์ ZIP พร้อมกับการเข้ารหัสเพื่อให้ไฟล์ที่บีบอัดสามารถเปิดได้เฉพาะเมื่อใส่รหัสผ่านที่ถูกต้อง การทำเช่นนี้ช่วยปกป้องเนื้อหาจากการเข้าถึงโดยไม่ได้รับอนุญาต

## How to create password protected zip for a directory
ต่อไปนี้เป็นขั้นตอนการทำ walkthrough ที่อ่านง่าย ครอบคลุมตั้งแต่การตั้งค่าโปรเจกต์จนถึงการเปลี่ยนรหัสผ่านในภายหลัง

## Why use Aspose.Zip for password protect directory .NET?
Aspose.Zip มี API ที่ตรงไปตรงมาและประสิทธิภาพสูง รองรับ **c# zip password protection**, การเข้ารหัส ZipCrypto แบบดั้งเดิม, และการเข้ารหัส AES มันจัดการกับไดเรกทอรีขนาดใหญ่ได้อย่างมีประสิทธิภาพและรวมเข้ากับโปรเจกต์ .NET ใดก็ได้อย่างราบรื่น

## Common use cases
- **การปกป้องสำเนาสำรอง:** บีบอัดโฟลเดอร์สำเนาสำรองประจำวันและล็อกด้วยรหัสผ่านที่แข็งแรง  
- **การแลกเปลี่ยนไฟล์อย่างปลอดภัย:** ส่งรหัสผ่านของโฟลเดอร์ zip ให้กับลูกค้าโดยไม่เปิดเผยเนื้อหา  
- **การปฏิบัติตามกฎระเบียบ:** เก็บข้อมูลส่วนบุคคล (PII) ในไฟล์ zip ที่เข้ารหัสเพื่อให้เป็นไปตามมาตรฐานการปกป้องข้อมูล  

## Prerequisites
ก่อนเริ่มทำโปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานการเขียนโปรแกรม C#  
- Visual Studio (เวอร์ชันล่าสุดใดก็ได้)  
- Aspose.Zip for .NET library – ดาวน์โหลดได้ **[here](https://releases.aspose.com/zip/net/)**  
- โฟลเดอร์บนดิสก์ที่คุณต้องการป้องกันด้วยรหัสผ่าน  

## Import Namespaces
เพิ่ม namespace ที่จำเป็นในไฟล์ C# ของคุณเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาส Aspose.Zip จากที่ไหน

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Step 1: Set the Path to the Resource Directory
กำหนดเส้นทางที่ชี้ไปยังไดเรกทอรีที่คุณต้องการบีบอัดและป้องกัน

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Password Protect the Directory
ใช้ `TraditionalEncryptionSettings` เพื่อระบุรหัสผ่านและสร้างไฟล์ที่เข้ารหัส นี่คือหัวใจของ **c# zip password protection**

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Step 3: Explanation of the Code
- **การสร้างไฟล์ผลลัพธ์:** `File.Open(..., FileMode.Create)` เปิด (หรือสร้าง) ไฟล์ ZIP ที่จะเก็บข้อมูลที่เข้ารหัส  
- **การเลือกโฟลเดอร์ต้นทาง:** `new DirectoryInfo(".\\CanterburyCorpus")` บอก Aspose.Zip ว่าไดเรกทอรีใดจะบีบอัด  
- **การตั้งรหัสผ่าน:** `new TraditionalEncryptionSettings("p@s$")` กำหนดรหัสผ่านที่จะปกป้องไฟล์บีบอัด  
- **การเพิ่มรายการและบันทึก:** `archive.CreateEntries(corpus)` เพิ่มไฟล์ทุกไฟล์ในโฟลเดอร์, และ `archive.Save(zipFile)` เขียนไฟล์ ZIP ที่เข้ารหัสลงดิสก์  

## How to change zip password later?
หากคุณต้องการ **เปลี่ยนรหัสผ่านของ zip**, เพียงสร้างไฟล์บีบอัดใหม่ด้วยอินสแตนซ์ `TraditionalEncryptionSettings` ที่มีรหัสผ่านใหม่ แล้วบันทึกอีกครั้ง วิธีนี้ยังใช้ได้เมื่อคุณต้องการ **สร้างไฟล์ zip ที่เข้ารหัส** จากโฟลเดอร์ที่มีอยู่โดยใช้รหัสผ่านที่แตกต่าง

## Tips for a strong zip folder password
- ใช้การผสมระหว่างตัวอักษรพิมพ์ใหญ่, พิมพ์เล็ก, ตัวเลข, และสัญลักษณ์  
- ตั้งเป้าหมายอย่างน้อย 12 ตัวอักษร; รหัสผ่านที่ยาวกว่าจะยากต่อการถอดรหัสอย่างมาก  
- หลีกเลี่ยงคำหรือรูปแบบที่พบบ่อย; พิจารณาใช้ประโยครหัสผ่าน  

## Common Issues & Tips
- **โฟลเดอร์ขนาดใหญ่:** Aspose.Zip สตรีมข้อมูล ทำให้การใช้หน่วยความจำน้อยแม้กับไดเรกทอรีขนาดใหญ่  
- **ความซับซ้อนของรหัสผ่าน:** ใช้รหัสผ่านที่แข็งแรง (ผสมตัวอักษร, ตัวเลข, สัญลักษณ์) เพื่อเพิ่มความปลอดภัย  
- **ข้อผิดพลาดไลเซนส์:** ตรวจสอบว่าคุณได้ใส่ไฟล์ไลเซนส์ที่ถูกต้อง; หากไม่เช่นนั้นไลบรารีจะทำงานในโหมดทดลองพร้อมข้อจำกัด  
- **รหัสผ่านของโฟลเดอร์ zip ไม่ถูกต้อง:** ตรวจสอบว่าคุณใช้วิธีการเข้ารหัสเดียวกัน (`TraditionalEncryptionSettings`) เมื่อเปิดไฟล์บีบอัด  

## Frequently Asked Questions

### Aspose.Zip for .NET เหมาะกับไดเรกทอรีขนาดใหญ่หรือไม่?
ใช่, Aspose.Zip for .NET ถูกออกแบบมาเพื่อจัดการไดเรกทอรีขนาดใหญ่อย่างมีประสิทธิภาพ, ให้ประสิทธิภาพที่ดีที่สุด

### ฉันสามารถเปลี่ยนรหัสผ่านของไดเรกทอรีที่ป้องกันแล้วได้หรือไม่?
ใช่, คุณสามารถแก้ไขรหัสผ่านโดยปรับ `TraditionalEncryptionSettings` ในโค้ดตามที่ต้องการ

### มีข้อกำหนดด้านไลเซนส์สำหรับการใช้ Aspose.Zip for .NET หรือไม่?
ใช่, จำเป็นต้องมีไลเซนส์ที่ถูกต้องสำหรับการใช้ Aspose.Zip for .NET ในสภาพแวดล้อมการผลิต คุณสามารถรับไลเซนส์ **[here](https://purchase.aspose.com/buy)**

### มีการทดลองใช้ฟรีสำหรับ Aspose.Zip for .NET หรือไม่?
ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรี **[here](https://releases.aspose.com/)**

### จะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Zip for .NET ได้จากที่ไหน?
คุณสามารถเยี่ยมชม **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** เพื่อขอความช่วยเหลือหรือสอบถามข้อมูลเพิ่มเติม

## Quick FAQ (AI‑friendly)

**Q: ฉันจะเข้ารหัสโฟลเดอร์ด้วย zip โดยใช้ Aspose.Zip อย่างไร?**  
A: ใช้ `TraditionalEncryptionSettings` เมื่อสร้างอ็อบเจกต์ `Archive`, จากนั้นเรียก `CreateEntries` กับโฟลเดอร์เป้าหมาย

**Q: ฉันสามารถตั้งรหัสผ่านของโฟลเดอร์ zip หลังจากที่ไฟล์บีบอัดสร้างแล้วได้หรือไม่?**  
A: ไม่, รหัสผ่านต้องกำหนดในขณะสร้างไฟล์; หากต้องการเปลี่ยนให้สร้างไฟล์บีบอัดใหม่ด้วยรหัสผ่านใหม่

**Q: Aspose.Zip รองรับการเข้ารหัส AES เพื่อความปลอดภัยที่สูงขึ้นหรือไม่?**  
A: ใช่, คุณสามารถสลับไปใช้ `AesEncryptionSettings` สำหรับการเข้ารหัส AES‑256 แทน ZipCrypto แบบดั้งเดิม

**Q: ไลบรารีนี้เข้ากันได้กับ .NET 6 และ .NET 7 หรือไม่?**  
A: แน่นอน – รุ่นปัจจุบันทำงานกับรันไทม์ .NET สมัยใหม่ทั้งหมด

**Q: จะเกิดอะไรขึ้นหากพยายามเปิด zip ที่ป้องกันด้วยรหัสผ่านโดยไม่มีรหัสผ่าน?**  
A: Aspose.Zip จะโยน `PasswordRequiredException` เพื่อแจ้งให้คุณใส่รหัสผ่านที่ถูกต้อง

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}