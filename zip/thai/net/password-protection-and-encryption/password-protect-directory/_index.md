---
title: รหัสผ่านป้องกันไดเรกทอรีใน .NET ด้วย Aspose.Zip Tutorial
linktitle: ไดเรกทอรีป้องกันรหัสผ่าน
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีการใช้รหัสผ่านป้องกันไดเรกทอรีใน .NET โดยใช้ Aspose.Zip รักษาความปลอดภัยไฟล์ของคุณอย่างง่ายดายด้วยบทช่วยสอนทีละขั้นตอนนี้
weight: 10
url: /th/net/password-protection-and-encryption/password-protect-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รหัสผ่านป้องกันไดเรกทอรีใน .NET ด้วย Aspose.Zip Tutorial


## การแนะนำ

ในโลกของการพัฒนา .NET การจัดการและการรักษาความปลอดภัยไดเร็กทอรีถือเป็นสิ่งสำคัญในการจัดการไฟล์ Aspose.Zip สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการปกป้องไดเรกทอรีด้วยรหัสผ่าน เพื่อให้มั่นใจถึงการรักษาความลับและความสมบูรณ์ของข้อมูลที่ละเอียดอ่อนของคุณ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการใช้รหัสผ่านเพื่อปกป้องไดเรกทอรีทีละขั้นตอน โดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Zip สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).
- ไดเร็กทอรีที่มีไฟล์ที่คุณต้องการป้องกันด้วยรหัสผ่าน

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ เนมสเปซเหล่านี้มีความสำคัญอย่างยิ่งต่อการใช้ฟังก์ชันการทำงานของ Aspose.Zip สำหรับ .NET

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## ขั้นตอนที่ 1: กำหนดเส้นทางไปยังไดเรกทอรีทรัพยากร

ขั้นแรก กำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ที่คุณต้องการป้องกันด้วยรหัสผ่าน

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: รหัสผ่านป้องกันไดเรกทอรี

 ตอนนี้ เรามาเจาะลึกโค้ดที่ใช้ป้องกันรหัสผ่านของไดเร็กทอรีกัน เราใช้`TraditionalEncryptionSettings` คลาสเพื่อตั้งรหัสผ่านและนำไปใช้กับไดเร็กทอรีที่ระบุ

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ตัวอย่าง: PasswordProtectDirectory
    }
}
```

## ขั้นตอนที่ 3: คำอธิบายของหลักจรรยาบรรณ

มาแจกแจงโค้ดเพื่อทำความเข้าใจแต่ละขั้นตอน:

-  การตั้งค่าไฟล์เอาท์พุต:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` สร้างไฟล์ ZIP ใหม่สำหรับเอาต์พุตที่เข้ารหัส

-  การกำหนดไดเร็กทอรี:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` ระบุไดเร็กทอรีที่จะป้องกันด้วยรหัสผ่าน

-  การสร้างและบันทึกรายการ:`archive.CreateEntries(corpus)` สร้างรายการสำหรับไฟล์ในไดเร็กทอรีที่ระบุและ`archive.Save(zipFile)`บันทึกไฟล์เก็บถาวรที่ป้องกันด้วยรหัสผ่าน

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายขั้นตอนการใช้รหัสผ่านเพื่อปกป้องไดเรกทอรีโดยใช้ Aspose.Zip สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถมั่นใจได้ถึงความปลอดภัยของไฟล์สำคัญของคุณในลักษณะที่เป็นมิตรต่อผู้ใช้และมีประสิทธิภาพ

---

## คำถามที่พบบ่อย

### Aspose.Zip สำหรับ .NET เหมาะสำหรับไดเรกทอรีขนาดใหญ่หรือไม่
ใช่ Aspose.Zip สำหรับ .NET ได้รับการออกแบบมาเพื่อจัดการไดเร็กทอรีขนาดใหญ่อย่างมีประสิทธิภาพ โดยให้ประสิทธิภาพสูงสุด

### ฉันสามารถเปลี่ยนรหัสผ่านสำหรับไดเร็กทอรีที่มีการป้องกันอยู่แล้วได้หรือไม่
 ใช่ คุณสามารถแก้ไขรหัสผ่านได้โดยการปรับ`TraditionalEncryptionSettings` ในรหัสตามลำดับ

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Zip สำหรับ .NET หรือไม่
 ใช่ จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้ Aspose.Zip สำหรับ .NET ในสภาพแวดล้อมการใช้งานจริง คุณสามารถขอรับใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).

### มี Aspose.Zip สำหรับ .NET ให้ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะหาการสนับสนุนเพิ่มเติมสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) สำหรับการสนับสนุนหรือข้อสงสัยใด ๆ


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
