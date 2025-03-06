---
title: รักษาความปลอดภัยไฟล์ของคุณ - การเข้ารหัส AES ด้วย Aspose.Zip
linktitle: ป้องกันรหัสผ่านด้วย AES
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีปรับปรุงความปลอดภัยของไฟล์โดยใช้ Aspose.Zip สำหรับ .NET พร้อมการเข้ารหัส AES ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการปกป้องสูงสุด
weight: 11
url: /th/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รักษาความปลอดภัยไฟล์ของคุณ - การเข้ารหัส AES ด้วย Aspose.Zip


## การแนะนำ

การรักษาความปลอดภัยให้กับไฟล์ที่ละเอียดอ่อนของคุณเป็นสิ่งสำคัญในยุคดิจิทัลในปัจจุบัน และ Aspose.Zip สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการป้องกันด้วยรหัสผ่านในการป้องกันไฟล์เก็บถาวรของคุณโดยใช้ Advanced Encryption Standard (AES) ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้การเข้ารหัส AES ที่มีความยาวคีย์สามแบบ ได้แก่ 128 บิต 192 บิต และ 256 บิต เพื่อให้มั่นใจถึงระดับความปลอดภัยสูงสุดสำหรับไฟล์บีบอัดของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Zip ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).

- ไดเร็กทอรีเอกสาร: มีไดเร็กทอรีที่มีไฟล์ต้นฉบับของคุณอยู่

## นำเข้าเนมสเปซ

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## ขั้นตอนที่ 1: ป้องกันรหัสผ่านด้วย AES-128

```csharp
//ExStart:PasswordProtectWithAES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: รหัสผ่านป้องกันด้วย AES128
```

ในขั้นตอนนี้ เราจะสร้างไฟล์ zip และป้องกันด้วยการเข้ารหัส AES-128 รหัสผ่าน "p@s$" ช่วยให้มั่นใจในความปลอดภัยของไฟล์เก็บถาวรของคุณ

## ขั้นตอนที่ 2: ป้องกันรหัสผ่านด้วย AES-192

```csharp
//ExStart:PasswordProtectWithAES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: รหัสผ่านป้องกันด้วย AES192
```

ขั้นตอนนี้สาธิตวิธีการใช้การเข้ารหัส AES-192 เพื่อเพิ่มความปลอดภัย รหัสผ่านเดียวกัน "p@s$" ใช้เพื่อความมั่นคง

## ขั้นตอนที่ 3: ป้องกันรหัสผ่านด้วย AES-256

```csharp
//ExStart:PasswordProtectWithAES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: รหัสผ่านป้องกันด้วย AES256
```

ในขั้นตอนสุดท้ายนี้ เราใช้การเข้ารหัสระดับสูงสุด AES-256 ซึ่งมอบการรักษาความปลอดภัยเพิ่มเติมอีกชั้นสำหรับไฟล์บีบอัดของคุณ

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการป้องกันรหัสผ่านที่เก็บถาวรของคุณโดยใช้การเข้ารหัส AES ใน Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะเลือกการเข้ารหัสแบบ 128 บิต 192 บิต หรือ 256 บิต ไฟล์ของคุณจะปลอดภัยจากการเข้าถึงโดยไม่ได้รับอนุญาต

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Zip ได้รับการออกแบบมาเพื่อแอปพลิเคชัน .NET เป็นหลัก เพื่อให้มั่นใจถึงการบูรณาการที่ราบรื่นและประสิทธิภาพสูงสุด

### วิธีการเข้ารหัส AES ปลอดภัยสำหรับข้อมูลที่ละเอียดอ่อนหรือไม่?
ใช่ การเข้ารหัส AES ได้รับการยอมรับอย่างกว้างขวางว่าเป็นวิธีการที่ปลอดภัยและมีประสิทธิภาพในการปกป้องข้อมูลที่ละเอียดอ่อน

### ฉันสามารถเปลี่ยนรหัสผ่านสำหรับไฟล์เก็บถาวรที่เข้ารหัสแล้วได้หรือไม่
ไม่ได้ รหัสผ่านสำหรับไฟล์เก็บถาวรที่เข้ารหัสไม่สามารถเปลี่ยนได้เมื่อตั้งค่าแล้ว คุณจะต้องสร้างไฟล์เก็บถาวรที่เข้ารหัสใหม่ด้วยรหัสผ่านอื่น

### มีข้อจำกัดเกี่ยวกับประเภทไฟล์ที่สามารถเข้ารหัสโดยใช้ Aspose.Zip หรือไม่
Aspose.Zip รองรับการเข้ารหัสไฟล์ประเภทต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นในการรักษาความปลอดภัยข้อมูลประเภทต่างๆ

### จะเกิดอะไรขึ้นหากฉันลืมรหัสผ่านสำหรับไฟล์เก็บถาวรที่เข้ารหัส
ขออภัย ไม่มีวิธีกู้คืนรหัสผ่านของไฟล์เก็บถาวรที่เข้ารหัสไว้ สิ่งสำคัญคือต้องเก็บรหัสผ่านไว้ในที่ปลอดภัย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
