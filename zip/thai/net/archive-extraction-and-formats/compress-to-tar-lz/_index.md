---
title: บีบอัดเป็น TarLz ด้วย Aspose.Zip สำหรับ .NET
linktitle: บีบอัดเป็น TarLz
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: บีบอัดไฟล์ใน .NET ได้อย่างง่ายดายด้วย Aspose.Zip เรียนรู้การสร้างไฟล์เก็บถาวร TarLz ทีละขั้นตอน
weight: 13
url: /th/net/archive-extraction-and-formats/compress-to-tar-lz/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดเป็น TarLz ด้วย Aspose.Zip สำหรับ .NET

## การแนะนำ

ในสภาพแวดล้อมการพัฒนา .NET ที่เปลี่ยนแปลงตลอดเวลา ความจำเป็นในการจัดการและบีบอัดไฟล์อย่างมีประสิทธิภาพเป็นสิ่งสำคัญยิ่ง Aspose.Zip สำหรับ .NET กลายเป็นเครื่องมืออันทรงพลังที่ให้ความสามารถในการบีบอัดไฟล์ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกแง่มุมหนึ่ง นั่นคือการบีบอัดเป็น TarLz โดยใช้ Aspose.Zip ปฏิบัติตามในขณะที่เราแจกแจงรายละเอียดแต่ละขั้นตอน ทำให้นักพัฒนาทุกระดับสามารถเข้าใจกระบวนการนี้ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้นการเดินทางนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[ที่นี่](https://releases.aspose.com/zip/net/).

-  ไดเร็กทอรีเอกสาร: มีไดเร็กทอรีที่กำหนดสำหรับเอกสารของคุณ และตรวจสอบให้แน่ใจว่าได้ตั้งค่าอย่างเหมาะสมใน`dataDir` ตัวแปรในโค้ดตัวอย่างที่ให้มา

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น ขั้นตอนนี้มีความสำคัญอย่างยิ่งในการเข้าถึงฟังก์ชันการทำงานที่นำเสนอโดย Aspose.Zip เพิ่มเนมสเปซต่อไปนี้ลงในโค้ดของคุณ:

```csharp
using System;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: การบีบอัดไฟล์เดียว

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### คำอธิบาย:

- `using (TarArchive archive = new TarArchive())` : เริ่มต้นอินสแตนซ์ใหม่ของ`TarArchive` คลาสซึ่งเป็นตัวแทนของไฟล์เก็บถาวร TAR

- `archive.CreateEntry("alice29.txt", dataDir + "alice29.txt")`: สร้างรายการในไฟล์เก็บถาวรสำหรับไฟล์ที่ระบุ

- `archive.SaveLzipped(dataDir + "archive.tar.lz")`: บันทึกไฟล์เก็บถาวร TAR ที่บีบอัดในรูปแบบ LZ

## ขั้นตอนที่ 2: การบีบอัดไฟล์หลายไฟล์

```csharp
//ExStart: บีบอัดหลายไฟล์
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### คำอธิบาย:

- ทำตามโครงสร้างเดียวกับขั้นตอนที่ 1 แต่ขยายฟังก์ชันการทำงานให้รวมไฟล์หลายไฟล์

## ขั้นตอนที่ 3: ระบุไดเร็กทอรีเอกสารของคุณ


```csharp
string dataDir = "Your Document Directory";
```

### คำอธิบาย:

-  แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีบีบอัดไฟล์ไปยัง TarLz โดยใช้ Aspose.Zip สำหรับ .NET เรียบร้อยแล้ว ฟังก์ชันนี้ไม่เพียงแต่เพิ่มความคล่องตัวในการจัดการไฟล์ แต่ยังเพิ่มประสิทธิภาพของแอปพลิเคชัน .NET ของคุณอีกด้วย

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถบีบอัดไฟล์ทุกขนาดโดยใช้ Aspose.Zip สำหรับ .NET ได้หรือไม่

ตอบ 1: ได้ Aspose.Zip สำหรับ .NET สามารถจัดการไฟล์ขนาดต่างๆ ได้อย่างมีประสิทธิภาพ ทำให้มั่นใจได้ถึงการบีบอัดที่เหมาะสมที่สุด

### คำถามที่ 2: รหัสที่ให้มาเข้ากันได้กับ Aspose.Zip สำหรับ .NET เวอร์ชันล่าสุดหรือไม่

A2: ใช่ รหัสได้รับการออกแบบให้ทำงานกับเวอร์ชันล่าสุด ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี่ที่ทันสมัยที่สุดเสมอ

### คำถามที่ 3: มีข้อควรพิจารณาในการอนุญาตให้ใช้สิทธิ์สำหรับการใช้ Aspose.Zip สำหรับ .NET หรือไม่

 A3: ใช่ ตรวจสอบให้แน่ใจว่าได้ตรวจสอบรายละเอียดใบอนุญาตใน[เว็บไซต์กำหนด](https://purchase.aspose.com/buy).

### คำถามที่ 4: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์ได้หรือไม่

ตอบ 4: ได้ Aspose.Zip สำหรับ .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และโครงการส่วนตัว

### คำถามที่ 5: ฉันจะรับการสนับสนุนได้ที่ไหนหากฉันประสบปัญหา

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) สำหรับการสนับสนุนและการแก้ไขปัญหาของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
