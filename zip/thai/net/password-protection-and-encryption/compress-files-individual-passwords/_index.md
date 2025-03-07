---
title: บีบอัดไฟล์อย่างปลอดภัยใน .NET ด้วย Aspose.Zip
linktitle: บีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคล
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีปรับปรุงความปลอดภัยของไฟล์ในแอปพลิเคชัน .NET! ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเกี่ยวกับการบีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคลโดยใช้ Aspose.Zip สำหรับ .NET
weight: 16
url: /th/net/password-protection-and-encryption/compress-files-individual-passwords/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดไฟล์อย่างปลอดภัยใน .NET ด้วย Aspose.Zip


## การแนะนำ

ในโลกของการพัฒนา .NET การจัดการและการบีบอัดไฟล์อย่างมีประสิทธิภาพถือเป็นงานที่สำคัญ Aspose.Zip สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการบีบอัดไฟล์ โดยนำเสนอคุณสมบัติที่หลากหลายเพื่อปรับปรุงแอปพลิเคชันของคุณ คุณสมบัติที่โดดเด่นอย่างหนึ่งคือความสามารถในการบีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคล ซึ่งช่วยเพิ่มระดับความปลอดภัย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการบีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคลโดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip ในโปรเจ็กต์ .NET ของคุณ คุณสามารถค้นหาเอกสารที่จำเป็นได้[ที่นี่](https://reference.aspose.com/zip/net/).

-  ดาวน์โหลด: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดไลบรารี Aspose.Zip สำหรับ .NET จาก[ลิงค์นี้](https://releases.aspose.com/zip/net/).

- Document Directory: เตรียมไดเร็กทอรีที่มีไฟล์ที่คุณต้องการบีบอัด

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีทรัพยากร

กำหนดเส้นทางไปยังไดเร็กทอรีทรัพยากรที่มีไฟล์ของคุณอยู่

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: บีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคล

ตอนนี้เรามาบีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคลกัน เราจะใช้ไฟล์ตัวอย่างสามไฟล์ (`alice29.txt`, `asyoulik.txt` , และ`fields.c`) โดยมีรหัสผ่านที่แตกต่างกันสำหรับแต่ละรายการ

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // บีบอัดแต่ละไฟล์ด้วยรหัสผ่านส่วนบุคคล
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // บันทึกไฟล์บีบอัด
        archive.Save(zipFile);
    }
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการบีบอัดไฟล์ด้วยรหัสผ่านส่วนบุคคลโดยใช้ Aspose.Zip สำหรับ .NET เรียบร้อยแล้ว คุณสมบัตินี้เพิ่มการรักษาความปลอดภัยอีกชั้นพิเศษให้กับไฟล์บีบอัดของคุณเพื่อให้มั่นใจถึงการรักษาความลับ

## คำถามที่พบบ่อย (FAQ)

### ฉันสามารถใช้วิธีการเข้ารหัสที่แตกต่างกันสำหรับแต่ละไฟล์ได้หรือไม่?
ใช่ Aspose.Zip สำหรับ .NET อนุญาตให้คุณใช้วิธีการเข้ารหัสที่แตกต่างกันสำหรับแต่ละไฟล์ระหว่างการบีบอัด

### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถเข้าถึง Aspose.Zip สำหรับ .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนได้อย่างไรหากฉันประสบปัญหา
 เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือจากชุมชนและการสนับสนุน Aspose

### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/zip/net/).

### ฉันสามารถซื้อใบอนุญาตชั่วคราวเพื่อการทดสอบได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
