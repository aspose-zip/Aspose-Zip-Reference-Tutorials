---
date: 2025-12-20
description: เรียนรู้วิธีป้องกันไฟล์ zip ด้วยรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET
  ด้วยการเข้ารหัสแบบดั้งเดิม คู่มือนี้แสดงวิธีการเข้ารหัสไฟล์ zip และเพิ่มไฟล์ลงใน
  zip อย่างมีประสิทธิภาพ
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: ปกป้องไฟล์ Zip ด้วยรหัสผ่านโดยใช้ Aspose.Zip .NET
url: /th/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ป้องกันรหัสผ่านไฟล์ Zip Archive ด้วย Aspose.Zip .NET

## บทนำ

ยินดีต้อนรับสู่บทแนะนำแบบขั้นตอนเกี่ยวกับ **วิธีป้องกันรหัสผ่านไฟล์ zip archive** ด้วยการเข้ารหัสแบบดั้งเดิมโดยใช้ Aspose.Zip สำหรับ .NET Aspose.Zip เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสร้าง อ่าน และจัดการไฟล์ zip ได้อย่างง่ายดาย ในคู่มือนี้ เราจะพาคุณผ่านการบีบอัดไฟล์หลายไฟล์ การเพิ่มไฟล์เหล่านั้นลงใน zip และการรักษาความปลอดภัยของ archive ด้วยรหัสผ่าน—ทั้งหมดนี้โดยรักษาโค้ดให้สะอาดและดูแลได้ง่าย

## คำตอบสั้น
- **“ป้องกันรหัสผ่าน zip archive” หมายถึงอะไร?** หมายถึงการเข้ารหัสไฟล์ zip เพื่อให้เนื้อหาภายในเปิดได้เฉพาะเมื่อใส่รหัสผ่านที่ถูกต้อง  
- **ไลบรารีใดจัดการเรื่องนี้ใน .NET?** Aspose.Zip สำหรับ .NET มีการสนับสนุนการเข้ารหัสแบบดั้งเดิมโดยตรง  
- **ต้องใช้ลิขสิทธิ์สำหรับการผลิตหรือไม่?** ใช่ ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต; มีรุ่นทดลองฟรีให้ใช้  
- **สามารถรันบน Linux ได้หรือไม่?** แน่นอน—Aspose.Zip รองรับหลายแพลตฟอร์มและทำงานบน Windows, Linux, และ macOS  
- **สามารถเพิ่มไฟล์ได้กี่ไฟล์?** สามารถเพิ่มไฟล์ได้จำนวนไม่จำกัด; ตัวอย่างแสดงสามไฟล์ แต่แนวทางนี้สามารถขยายได้

## “ป้องกันรหัสผ่าน zip archive” คืออะไร?

zip archive ที่ป้องกันด้วยรหัสผ่านใช้การเข้ารหัส (ในที่นี้คือการเข้ารหัส PKZIP แบบดั้งเดิม) เพื่อทำให้ข้อมูลไฟล์ภายใน archive ถูกสลับรหัส เมื่อผู้ใช้พยายามแตกไฟล์ archive จะต้องใส่รหัสผ่านที่ถูกต้องเพื่อถอดรหัสเนื้อหา

## ทำไมต้องใช้ Aspose.Zip สำหรับงานนี้?

- **API ที่ง่าย** – เพียงบรรทัดเดียวก็เปิดใช้งานการเข้ารหัสได้  
- **ไม่มีการพึ่งพาภายนอก** – เป็น .NET แท้ ๆ ไม่ต้องใช้ DLL เนทีฟ  
- **ข้ามแพลตฟอร์ม** – ทำงานกับ .NET Framework, .NET Core, และ .NET 5/6+  
- **ประสิทธิภาพสูง** – จัดการไฟล์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมอยู่:

- **Aspose.Zip สำหรับ .NET** – ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/zip/net/)  
- **โฟลเดอร์ที่มีไฟล์** – แทนที่ `"Your Document Directory"` ในโค้ดตัวอย่างด้วยเส้นทางจริงที่มีไฟล์ที่คุณต้องการบีบอัด

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นเพื่อให้สามารถทำงานกับคลาสของ Aspose.Zip ได้:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## วิธีเข้ารหัส zip ด้วยการเข้ารหัสแบบดั้งเดิม

### ขั้นตอนที่ 1: ตั้งค่าไฟล์ Zip (Password Protect Zip Archive)

สร้างไฟล์ zip และกำหนดค่าการเข้ารหัสแบบดั้งเดิม รหัสผ่าน `"p@s$"` เป็นเพียงตัวอย่าง—ให้เปลี่ยนเป็นรหัสผ่านที่แข็งแรงสำหรับโครงการจริง

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### เพิ่มไฟล์ลงใน zip archive

ต่อไปให้เพิ่มไฟล์แต่ละไฟล์ที่ต้องการรวมไว้ `CreateEntry` จะรับชื่อไฟล์ภายใน zip และสตรีม (`source1`, `source2`, `source3`) ที่ชี้ไปยังข้อมูลไฟล์จริง

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### บันทึกไฟล์ Zip (บีบอัดไฟล์ด้วยรหัสผ่าน)

สุดท้ายให้บันทึก archive ลงดิสก์ ขั้นตอนนี้จะเขียนไฟล์ zip ที่เข้ารหัสไปยังตำแหน่งที่คุณระบุไว้ก่อนหน้า

```csharp
archive.Save(zipFile);
```

> **เคล็ดลับมืออาชีพ:** ควรปิดสตรีม (`using` statements) เสมอเพื่อปล่อย handle ของไฟล์โดยเร็ว โดยเฉพาะเมื่อทำงานกับไฟล์ขนาดใหญ่

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ข้อผิดพลาดรหัสผ่านไม่ถูกต้อง** | รหัสผ่านไม่ตรงกันหรือพิมพ์ผิดใน `TraditionalEncryptionSettings` | ตรวจสอบสตริงรหัสผ่านและให้แน่ใจว่าใช้รหัสเดียวกันเมื่อต้องการแตกไฟล์ |
| **ไฟล์ไม่ถูกเพิ่ม** | สตรีมต้นทาง (`sourceX`) เป็น null หรือถูกทำลาย | เปิดสตรีมต้นทางด้วย `File.OpenRead` ก่อนส่งให้ `CreateEntry` |
| **ประสิทธิภาพช้ากับไฟล์ขนาดใหญ่** | ใช้ระดับการบีบอัดเริ่มต้นกับรายการขนาดใหญ่หลายรายการ | พิจารณาตั้งค่า `CompressionLevel` ใน `ArchiveEntrySettings` เพื่อเร่งการประมวลผล |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ในสภาพแวดล้อม Windows และ Linux ได้หรือไม่?**  
ตอบ: ใช่ Aspose.Zip สำหรับ .NET รองรับข้ามแพลตฟอร์มเต็มรูปแบบและทำงานบน Windows, Linux, และ macOS

**ถาม: มีรุ่นทดลองฟรีหรือไม่?**  
ตอบ: มีแน่นอน—คุณสามารถสำรวจรุ่นทดลองฟรีของ Aspose.Zip สำหรับ .NET [ที่นี่](https://releases.aspose.com/)

**ถาม: จะขอรับการสนับสนุนเมื่อเจอปัญหาได้จากที่ไหน?**  
ตอบ: เยี่ยมชมฟอรั่มอย่างเป็นทางการของ [Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชนและทีมสนับสนุน

**ถาม: มีลิขสิทธิ์ชั่วคราวสำหรับการประเมินหรือไม่?**  
ตอบ: มี คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: จะดูเอกสาร API ฉบับเต็มได้จากที่ไหน?**  
ตอบ: เอกสารอ้างอิงโดยละเอียดพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/zip/net/)

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบด้วย:** Aspose.Zip 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}