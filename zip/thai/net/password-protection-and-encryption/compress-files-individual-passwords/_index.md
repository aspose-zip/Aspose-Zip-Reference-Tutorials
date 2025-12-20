---
date: 2025-12-20
description: เรียนรู้วิธีสร้างไฟล์ ZIP ที่ป้องกันด้วยรหัสผ่านใน .NET ด้วย Aspose.Zip
  คู่มือขั้นตอนนี้แสดงวิธีบีบอัดไฟล์ด้วยรหัสผ่าน ตั้งค่ารหัสผ่านสำหรับรายการ ZIP และใช้การเข้ารหัส
  AES
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้างไฟล์ ZIP ที่มีการป้องกันด้วยรหัสผ่านใน .NET ด้วย Aspose.Zip
url: /th/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ ZIP ที่ป้องกันด้วยรหัสผ่านใน .NET ด้วย Aspose.Zip

## บทนำ

หากคุณต้องการ **สร้างไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** ในแอปพลิเคชัน .NET, Aspose.Zip ทำให้กระบวนการนี้ง่ายดาย โดยการกำหนดรหัสผ่านที่แตกต่างกันให้กับแต่ละรายการ คุณสามารถรักษาเอกสารที่สำคัญให้ปลอดภัยได้พร้อมกับความสะดวกของการบีบอัด ZIP ในบทเรียนนี้คุณจะได้เรียนรู้วิธีบีบอัดไฟล์ด้วยรหัสผ่านแยกกัน, เลือกวิธีการเข้ารหัสที่ต่างกัน, และตั้งรหัสผ่านให้กับรายการ zip — ทั้งหมดด้วยโค้ดที่ชัดเจนและพร้อมใช้งานในสภาพแวดล้อมการผลิต

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip สำหรับ .NET
- **ฉันสามารถกำหนดรหัสผ่านที่แตกต่างกันต่อไฟล์ได้หรือไม่?** ได้, แต่ละรายการสามารถมีรหัสผ่านของตนเอง
- **อัลกอริทึมการเข้ารหัสที่รองรับมีอะไรบ้าง?** ZipCrypto แบบดั้งเดิม, AES‑128, และ AES‑256
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการทดสอบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง
- **รองรับ .NET 6+ หรือไม่?** แน่นอน – API รองรับ .NET Standard 2.0 ขึ้นไป

## “สร้างไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน” คืออะไร?
การสร้างไฟล์ zip ที่ป้องกันด้วยรหัสผ่านหมายถึงการเพิ่มการเข้ารหัสให้กับหนึ่งหรือหลายรายการภายในไฟล์ ZIP เพื่อให้เนื้อหาไม่สามารถเปิดได้หากไม่มีรหัสผ่านที่ถูกต้อง วิธีนี้เหมาะสำหรับการส่งไฟล์ที่เป็นความลับ, การเก็บสำรองข้อมูล, หรือการปฏิบัติตามนโยบายการปกป้องข้อมูล

## ทำไมต้องใช้ Aspose.Zip สำหรับไฟล์ที่ป้องกันด้วยรหัสผ่าน?
- **การควบคุมระดับละเอียด** – ตั้งรหัสผ่านที่แตกต่างกันต่อไฟล์
- **ตัวเลือกการเข้ารหัสหลายแบบ** – ตั้งแต่ ZipCrypto แบบเก่าไปจนถึง AES‑128/256 ที่ปลอดภัย
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – ไลบรารี .NET แท้ ๆ, ติดตั้งง่าย
- **เอกสารครบถ้วน** – มี **aspose zip tutorial** สำหรับกรณีการใช้งานที่ลึกซึ้งยิ่งขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามบทเรียนนี้, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- Aspose.Zip สำหรับ .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Zip ในโครงการ .NET ของคุณแล้ว คุณสามารถดูเอกสารที่จำเป็นได้ [ที่นี่](https://reference.aspose.com/zip/net/)  
- ดาวน์โหลด: หากคุณยังไม่ได้ดาวน์โหลด, ดาวน์โหลด Aspose.Zip สำหรับ .NET จาก [ลิงก์นี้](https://releases.aspose.com/zip/net/)  
- โฟลเดอร์เอกสาร: เตรียมโฟลเดอร์ที่มีไฟล์ที่ต้องการบีบอัด

## นำเข้า Namespaces

ในโครงการ .NET ของคุณ, อย่าลืมนำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางโฟลเดอร์ทรัพยากร

กำหนดเส้นทางไปยังโฟลเดอร์ทรัพยากรที่เก็บไฟล์ต้นฉบับของคุณ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: บีบอัดไฟล์ด้วยรหัสผ่านแยกกัน

ต่อไปนี้เป็นการบีบอัดไฟล์ด้วยรหัสผ่านแยกกัน เราจะใช้ไฟล์ตัวอย่างสามไฟล์ (`alice29.txt`, `asyoulik.txt`, และ `fields.c`) พร้อมรหัสผ่านที่แตกต่างกันสำหรับแต่ละไฟล์ ซึ่งจะแสดงวิธี **บีบอัดไฟล์ด้วยรหัสผ่าน** และวิธี **ตั้งรหัสผ่านให้รายการ zip** ด้วยรูปแบบการเข้ารหัสที่หลากหลาย รวมถึง **zip archive with aes** ด้วย

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### วิธีการทำงาน
- **TraditionalEncryptionSettings** ใช้อัลกอริทึม ZipCrypto รุ่นเก่า (เข้ากันได้กับเครื่องมือ ZIP ส่วนใหญ่)
- **AesEcryptionSettings** ให้คุณเลือก AES‑128 หรือ AES‑256 เพื่อความปลอดภัยที่สูงขึ้น
- แต่ละการเรียก `CreateEntry` จะรับอ็อบเจ็กต์ `ArchiveEntrySettings` ที่เรากำหนดวิธีการบีบอัดและการตั้งค่าการเข้ารหัส ทำให้ **password protect zip archive** รายการได้อย่างมีประสิทธิภาพ

## ปัญหาที่พบบ่อยและวิธีแก้ไข

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| “Invalid password” เมื่อเปิด ZIP | รหัสผ่านที่ใช้ในโค้ดไม่ตรงกับที่ใส่ในโปรแกรมสกัดไฟล์ | ตรวจสอบสตริงที่ส่งให้ `TraditionalEncryptionSettings` หรือ `AesEcryptionSettings` อย่างละเอียด |
| เครื่องมือสกัดไฟล์เก่าไม่สามารถเปิดรายการที่เข้ารหัสด้วย AES | ไม่ใช่ทุกเครื่องมือ ZIP รองรับการเข้ารหัส AES | ใช้วิธี ZipCrypto แบบดั้งเดิมเพื่อความเข้ากันได้สูงสุด, หรือแนะนำให้ผู้ใช้ใช้เครื่องมือสมัยใหม่ (เช่น 7‑Zip) |
| ไฟล์ขนาดใหญ่ทำให้เกิด `OutOfMemoryException` | โหลดไฟล์ขนาดใหญ่เข้าเมมโมรีก่อนบีบอัด | สตรีมไฟล์โดยตรงด้วย `FileStream` แทนการโหลดไฟล์ทั้งหมดเข้าอ็อบเจ็กต์ `FileInfo` |

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถใช้วิธีการเข้ารหัสที่แตกต่างกันสำหรับแต่ละไฟล์ได้หรือไม่?
ได้, Aspose.Zip สำหรับ .NET รองรับการใช้วิธีการเข้ารหัสที่แตกต่างกันสำหรับแต่ละไฟล์ระหว่างการบีบอัด

### มีเวอร์ชันทดลองให้ใช้งานหรือไม่?
มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.Zip สำหรับ .NET ได้ [ที่นี่](https://releases.aspose.com/)

### จะขอรับการสนับสนุนเมื่อเจอปัญหาได้อย่างไร?
เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชนและทีมสนับสนุนของ Aspose

### จะหาเอกสารรายละเอียดของ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?
เอกสารพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/zip/net/)

### สามารถซื้อใบอนุญาตชั่วคราวเพื่อทดสอบได้หรือไม่?
ได้, คุณสามารถขอรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

## คำถามเพิ่มเติมแบบรวดเร็ว

**ถาม: ไลบรารีรองรับ .NET Core และ .NET 5/6 หรือไม่?**  
ตอบ: รองรับ, Aspose.Zip ตั้งเป้าหมายที่ .NET Standard ทำให้ทำงานร่วมกับ .NET Framework, .NET Core, และ .NET 5/6 ได้อย่างไม่มีปัญหา

**ถาม: สามารถเพิ่มคอมเมนต์ให้แต่ละรายการ ZIP ได้หรือไม่?**  
ตอบ: แม้ Aspose.Zip จะเน้นที่การบีบอัดและการเข้ารหัส, คุณสามารถเก็บข้อมูลเมตาดาต้าในไฟล์ manifest แยกต่างหากภายใน archive ได้

**ถาม: สามารถเข้ารหัสทั้ง archive ด้วยรหัสผ่านเดียวได้หรือไม่?**  
ตอบ: คุณสามารถตั้งรหัสผ่านให้แต่ละรายการแยกกัน (ตามที่แสดง) หรือใช้รหัสผ่านเดียวสำหรับทุกรายการเพื่อสร้าง “zip archive with aes” อย่างง่ายได้เช่นกัน

## สรุป

คุณได้เรียนรู้วิธี **สร้างไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** ใน .NET ด้วย Aspose.Zip แล้ว การกำหนดรหัสผ่านแยกต่อไฟล์และเลือกวิธีการเข้ารหัสที่เหมาะสมช่วยให้ข้อมูลของคุณปลอดภัยโดยไม่สูญเสียความสะดวกของการบีบอัด ZIP สำรวจคุณสมบัติอื่น ๆ ของ Aspose.Zip เช่น การสตรีมไฟล์ขนาดใหญ่, การเพิ่มเมตาดาต้าตามต้องการ, และการผสานรวมกับคลาวด์สตอเรจเพื่อสร้างสถานการณ์การใช้งานที่ทรงพลังยิ่งขึ้น

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Zip for .NET 23.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}