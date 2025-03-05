---
title: การสร้างไฟล์ ZIP 7 ไฟล์ - Aspose.Zip สำหรับ .NET Tutorial
linktitle: SevenZip พร้อมวิธีการบีบอัดที่หลากหลาย
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีสร้างไฟล์ Seven Zip ด้วย Aspose.Zip สำหรับ .NET โดยใช้วิธีการบีบอัดแบบต่างๆ ขั้นตอนง่ายๆ สำหรับ LZMA2, BZip2 และ Store (ไม่มีการบีบอัด)
type: docs
weight: 12
url: /th/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## การแนะนำ

ในด้านการพัฒนา .NET การจัดการและการบีบอัดไฟล์ถือเป็นงานทั่วไป Aspose.Zip สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการทำงานกับไฟล์เก็บถาวรที่บีบอัด โดยเสนอวิธีการบีบอัดที่หลากหลาย ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ Aspose.Zip สำหรับ .NET เพื่อสร้างไฟล์ Seven Zip ด้วยวิธีการบีบอัดแบบต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Zip สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ใช้ข้อมูลโค้ดต่อไปนี้เพื่อเริ่มต้น:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## การบีบอัด LZMA2

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ตัวอย่าง: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## การบีบอัด BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## จัดเก็บไม่มีการบีบอัด

```csharp
//จัดเก็บไม่มีการบีบอัด
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจความอเนกประสงค์ของ Aspose.Zip สำหรับ .NET ในการสร้างไฟล์ Seven Zip ด้วยวิธีการบีบอัดที่หลากหลาย ไม่ว่าคุณจะต้องการอัตราส่วนการบีบอัดสูงหรือไม่ต้องการการบีบอัดเลย Aspose.Zip มอบความยืดหยุ่นเพื่อตอบสนองความต้องการของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับไฟล์ประเภทใดก็ได้หรือไม่
ใช่ Aspose.Zip สำหรับ .NET รองรับไฟล์หลายประเภท ทำให้คุณสามารถบีบอัดและขยายขนาดรูปแบบต่างๆ ได้

### Aspose.Zip สำหรับ .NET มีให้ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถขอรับรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะหาเอกสารสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/zip/net/).

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร
 สามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 คุณสามารถขอรับการสนับสนุนได้ที่[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37).
