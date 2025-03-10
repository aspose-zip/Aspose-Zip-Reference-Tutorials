---
title: Aspose.Zip สำหรับ .NET - การถอดรหัสไฟล์ที่เข้ารหัส AES
linktitle: คลายการบีบอัดไฟล์ที่เก็บไว้ที่เข้ารหัส AES
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีคลายการบีบอัดไฟล์ที่เข้ารหัส AES ที่จัดเก็บไว้ใน Aspose.Zip สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนที่ครอบคลุมนี้ เสริมทักษะการพัฒนา .NET ของคุณวันนี้!
weight: 19
url: /th/net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip สำหรับ .NET - การถอดรหัสไฟล์ที่เข้ารหัส AES


## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการขยายขนาดไฟล์ที่เข้ารหัส AES ที่จัดเก็บไว้โดยใช้ Aspose.Zip สำหรับ .NET Aspose.Zip เป็นไลบรารี .NET อันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับไฟล์บีบอัดได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่การขยายขนาดไฟล์ที่เข้ารหัส AES เพื่อให้คุณเข้าใจกระบวนการได้ชัดเจน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip แล้ว คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/zip/net/).

-  ตัวอย่างไฟล์ที่เข้ารหัส AES: ดาวน์โหลดไฟล์ตัวอย่างที่เข้ารหัส AES จาก[ลิงค์นี้](https://releases.aspose.com/zip/net/).

- ไดเร็กทอรีเอกสารของคุณ: ตั้งค่าไดเร็กทอรีที่คุณต้องการจัดเก็บไฟล์ที่คลายการบีบอัด แทนที่ "ไดเรกทอรีเอกสารของคุณ" ในข้อมูลโค้ดด้วยเส้นทางไดเรกทอรีจริงของคุณ

## นำเข้าเนมสเปซ

ในข้อมูลโค้ดที่ให้มา คุณจะสังเกตเห็นการใช้เนมสเปซต่างๆ อย่าลืมรวมสิ่งเหล่านี้ในโครงการของคุณ:

```csharp
using System.IO;
using Aspose.Zip;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีทรัพยากร

ตรวจสอบให้แน่ใจว่าคุณระบุเส้นทางไปยังไดเร็กทอรีทรัพยากรของคุณ ในตัวอย่าง ให้แทนที่ "Your Document Directory" ด้วยเส้นทางจริง

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เปิดไฟล์เก็บถาวรที่เข้ารหัส

```csharp
using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
{
    using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
    {
        using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
        {
            // ทำตามขั้นตอนต่อไป...
        }
    }
}
```

## ขั้นตอนที่ 3: ขยายรายการที่เข้ารหัส

```csharp
using (var decompressed = archive.Entries[0].Open())
{
    byte[] b = new byte[8192];
    int bytesRead;
    while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
    {
        extracted.Write(b, 0, bytesRead);
    }
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีขยายขนาดไฟล์ที่เข้ารหัส AES ที่จัดเก็บไว้โดยใช้ Aspose.Zip สำหรับ .NET เรียบร้อยแล้ว กระบวนการนี้ช่วยให้คุณทำงานกับไฟล์เก็บถาวรที่เข้ารหัสในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับอัลกอริธึมการเข้ารหัสอื่นๆ ได้หรือไม่
Aspose.Zip รองรับการเข้ารหัส AES เป็นหลัก ตรวจสอบเอกสารสำหรับการอัพเดตล่าสุด

### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุน Aspose.Zip สำหรับ .NET ได้อย่างไร
 เยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชน

### ไฟล์รูปแบบใดบ้างที่รองรับการบีบอัดและคลายการบีบอัด?
Aspose.Zip รองรับรูปแบบต่างๆ รวมถึง ZIP, 7z และ TAR โปรดดูเอกสารประกอบสำหรับรายการที่ครอบคลุม

### ฉันสามารถใช้ Aspose.Zip เพื่อจุดประสงค์เชิงพาณิชย์ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy) เพื่อใช้ในเชิงพาณิชย์


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
