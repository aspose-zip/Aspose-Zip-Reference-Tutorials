---
title: แตกไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET
linktitle: การขยายขนาดไฟล์หลายไฟล์
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีขยายขนาดไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการไฟล์ที่มีประสิทธิภาพ
weight: 11
url: /th/net/file-decompression/decompress-multiple-files/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แตกไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมของเราเกี่ยวกับการขยายขนาดไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET! หากคุณต้องการจัดการไฟล์บีบอัดที่มีหลายรายการอย่างมีประสิทธิภาพ คุณมาถูกที่แล้ว ในคู่มือนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่เก็บเอกสารของคุณ คุณจะใช้สิ่งนี้เป็นไดเร็กทอรีฐานในโค้ด

ตอนนี้ เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกันดีกว่า

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นสำหรับ Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: การบีบอัดไฟล์หลายไฟล์

หากต้องการขยายขนาดไฟล์หลายไฟล์ คุณต้องมีไฟล์บีบอัดที่มีหลายรายการก่อน มาสร้างกัน:

```csharp
string dataDir = "Your Document Directory";

// เรียกใช้วิธีการบีบอัด
CompressMultipleFiles.Run();
```

## ขั้นตอนที่ 2: ขยายขนาดไฟล์

ตอนนี้เรามาขยายขนาดไฟล์ทีละขั้นตอน:

### ขั้นตอนที่ 2.1: การเปิดไฟล์บีบอัด

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### ขั้นตอนที่ 2.2: การลงรายการและการติดตามความคืบหน้า

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### ขั้นตอนที่ 2.3: การแยกรายการแรก

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // อ่านและเขียนข้อมูลจากสตรีมที่คลายการบีบอัดไปยังไฟล์ที่แยกออกมา
    }
}
```

### ขั้นตอนที่ 2.4: การแยกรายการที่สอง

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

และคุณก็ได้แล้ว! คุณได้แตกไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการขยายขนาดไฟล์หลายไฟล์โดยใช้ Aspose.Zip สำหรับ .NET เมื่อปฏิบัติตามคำแนะนำนี้ คุณจะจัดการไฟล์บีบอัดได้อย่างง่ายดายอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ทั้งในโครงการเชิงพาณิชย์และโครงการส่วนบุคคลได้หรือไม่

 ตอบ 1: ได้ Aspose.Zip สำหรับ .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และส่วนบุคคล สำหรับรายละเอียดใบอนุญาต โปรดดูที่[ข้อมูลใบอนุญาตของ Aspose](https://purchase.aspose.com/buy).

### คำถามที่ 2: Aspose.Zip สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 ตอบ 2: ได้ คุณสามารถทดลองใช้ Aspose.Zip สำหรับ .NET ได้ฟรี[ที่นี่](https://releases.aspose.com/zip/net).

### คำถามที่ 3: ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน

 A3: เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 4: ฉันจะซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร

 A4: รับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: มีข้อกำหนดระบบเฉพาะสำหรับการใช้ Aspose.Zip สำหรับ .NET หรือไม่

 A5: โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/zip/net/) สำหรับความต้องการของระบบโดยละเอียด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
