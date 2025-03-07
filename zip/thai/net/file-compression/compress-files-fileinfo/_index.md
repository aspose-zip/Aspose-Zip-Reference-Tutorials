---
title: บีบอัดไฟล์โดยใช้ FileInfo ใน Aspose.Zip สำหรับ .NET
linktitle: บีบอัดไฟล์โดยใช้ FileInfo
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีการบีบอัดไฟล์โดยใช้ fileinfo ด้วย Aspose.Zip สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการไฟล์ที่มีประสิทธิภาพ
weight: 11
url: /th/net/file-compression/compress-files-fileinfo/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดไฟล์โดยใช้ FileInfo ใน Aspose.Zip สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการบีบอัดไฟล์โดยใช้ Aspose.Zip สำหรับ .NET! หากคุณต้องการเพิ่มประสิทธิภาพการจัดเก็บไฟล์หรือการส่งไฟล์ Aspose.Zip คือโซลูชันที่เหมาะกับคุณ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการบีบอัดไฟล์โดยใช้คลาส FileInfo โดยมีคำแนะนำทีละขั้นตอนโดยละเอียด มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/zip/net/).

2. Document Directory: ตั้งค่าไดเร็กทอรีในระบบของคุณเพื่อจัดเก็บไฟล์ที่คุณต้องการบีบอัด

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็น:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ก่อนอื่น กำหนดไดเร็กทอรีที่เก็บเอกสารของคุณ คุณสามารถใช้รหัสต่อไปนี้:

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: บีบอัดไฟล์โดยใช้ FileInfo

 ตอนนี้เรามาดูแก่นแท้ของกระบวนการกันดีกว่า เราจะใช้`FileInfo` คลาสพร้อมกับ Aspose.Zip เพื่อบีบอัดไฟล์ ทำตามขั้นตอนเหล่านี้:

### ขั้นตอนที่ 2.1: เปิดไฟล์ซิป

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ขั้นตอนที่ 2.2: สร้างวัตถุ FileInfo

 สร้าง`FileInfo` วัตถุสำหรับไฟล์ที่คุณต้องการบีบอัด:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### ขั้นตอนที่ 2.3: สร้างไฟล์เก็บถาวรและเพิ่มรายการ

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ขั้นตอนที่ 2.4: บันทึกไฟล์ซิป

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

ยินดีด้วย! คุณบีบอัดไฟล์ได้สำเร็จโดยใช้คลาส FileInfo ใน Aspose.Zip สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีบีบอัดไฟล์อย่างมีประสิทธิภาพโดยใช้ Aspose.Zip สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มความสามารถในการจัดการไฟล์และปรับการใช้พื้นที่ให้เหมาะสมได้ ทดลองใช้ไฟล์ประเภทและขนาดต่างๆ เพื่อสัมผัสประสบการณ์เต็มศักยภาพของ Aspose.Zip

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Zip เข้ากันได้กับไฟล์ทุกประเภทหรือไม่

A1: Aspose.Zip รองรับไฟล์ได้หลากหลายประเภท จึงมั่นใจได้ถึงความคล่องตัวในการบีบอัด

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Zip สำหรับโครงการเชิงพาณิชย์ได้หรือไม่

 A2: แน่นอน! เยี่ยมชมของเรา[หน้าซื้อ](https://purchase.aspose.com/buy) เพื่อสำรวจตัวเลือกการออกใบอนุญาต

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip ได้อย่างไร

 A3: เข้าร่วมชุมชนของเราบน[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือและหารือ

### คำถามที่ 4: มีการทดลองใช้ฟรีหรือไม่?

 A4: ใช่ คุณสามารถคว้าของคุณ[ทดลองใช้ฟรีที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร

 A5: เยี่ยมเลย[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) สำหรับข้อมูลเกี่ยวกับการขอรับใบอนุญาตชั่วคราว
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
