---
title: บีบอัดเป็น TarZ ด้วย Aspose.Zip สำหรับ .NET
linktitle: บีบอัดเป็น TarZ
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: สำรวจการบีบอัด TarZ ทีละขั้นตอนโดยใช้ Aspose.Zip สำหรับ .NET การจัดการไฟล์ที่มีประสิทธิภาพสำหรับโครงการ .NET ของคุณ
weight: 15
url: /th/net/archive-extraction-and-formats/compress-to-tar-z/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดเป็น TarZ ด้วย Aspose.Zip สำหรับ .NET

## การแนะนำ

หากคุณต้องการบีบอัดไฟล์เป็นรูปแบบ TarZ อย่างมีประสิทธิภาพโดยใช้ Aspose.Zip สำหรับ .NET คุณมาถูกที่แล้ว คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะได้ใช้ประโยชน์จากศักยภาพของ Aspose.Zip สำหรับ .NET อย่างเต็มที่เพื่อจัดการกับความต้องการในการบีบอัดได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่เก็บเอกสารของคุณ ในตัวอย่าง เราจะใช้ "Your Document Directory" เป็นตัวยึดตำแหน่ง แทนที่ด้วยเส้นทางไดเรกทอรีจริงของคุณ

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Zip รวมบรรทัดต่อไปนี้ไว้ที่ตอนต้นของโค้ดของคุณ:

```csharp
using System;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: เริ่มต้นไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "Your Document Directory";
```

ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่มีไฟล์ของคุณ

## ขั้นตอนที่ 2: บีบอัดไฟล์เป็น TarZ

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:

### ขั้นตอนที่ 2.1: การสร้างไฟล์เก็บถาวร Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // รหัสของคุณสำหรับการสร้างไฟล์เก็บถาวร Tar อยู่ที่นี่
}
```

### ขั้นตอนที่ 2.2: การเพิ่มไฟล์ลงในไฟล์เก็บถาวร

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

ตัวอย่างนี้จะเพิ่มไฟล์สองไฟล์ "alice29.txt" และ "lcet10.txt" ลงในไฟล์เก็บถาวร Tar แก้ไขชื่อไฟล์และเส้นทางตามความต้องการของคุณ

### ขั้นตอนที่ 2.3: บันทึกไฟล์บีบอัดที่บีบอัด

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

บรรทัดนี้จะบันทึกไฟล์เก็บถาวร Tar ที่บีบอัดด้วยชื่อ "archive.tar.z" ในไดเร็กทอรีที่ระบุ ปรับชื่อไฟล์และเส้นทางตามต้องการ

## บทสรุป

ยินดีด้วย! คุณบีบอัดไฟล์เป็นรูปแบบ TarZ ได้สำเร็จโดยใช้ Aspose.Zip สำหรับ .NET ไลบรารีอันทรงพลังนี้ทำให้กระบวนการบีบอัดง่ายขึ้น ทำให้มีประสิทธิภาพและเชื่อถือได้สำหรับโปรเจ็กต์ .NET ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถบีบอัดโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET ได้หรือไม่

A1: แน่นอน! Aspose.Zip สำหรับ .NET ช่วยให้คุณสามารถบีบอัดทั้งไฟล์เดี่ยวและทั้งโฟลเดอร์ได้อย่างง่ายดาย

### คำถามที่ 2: Aspose.Zip สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ 2: ได้ คุณสามารถสำรวจความสามารถของ Aspose.Zip สำหรับ .NET ได้ด้วยการดาวน์โหลดรุ่นทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน

 A3: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/zip/net/)โดยให้ข้อมูลเชิงลึกโดยละเอียดเกี่ยวกับคุณสมบัติและการใช้งานของห้องสมุด

### คำถามที่ 4: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร

 A4: เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือ แบ่งปันประสบการณ์ของคุณ และเชื่อมต่อกับชุมชน

### คำถามที่ 5: ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้หรือไม่

A5: ได้ หากคุณต้องการใบอนุญาตชั่วคราว คุณสามารถขอรับได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
