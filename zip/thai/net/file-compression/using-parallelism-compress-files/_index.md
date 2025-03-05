---
title: การใช้ Parallelism เพื่อบีบอัดไฟล์ใน Aspose.Zip สำหรับ .NET
linktitle: การใช้ความเท่าเทียมในการบีบอัดไฟล์
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้การบีบอัดไฟล์อย่างมีประสิทธิภาพใน .NET โดยใช้ Aspose.Zip ควบคุมพลังแห่งความเท่าเทียมด้วยบทช่วยสอนแบบทีละขั้นตอนของเรา
type: docs
weight: 17
url: /th/net/file-compression/using-parallelism-compress-files/
---
## การแนะนำ

ในโลกของการพัฒนา .NET การบีบอัดไฟล์อย่างมีประสิทธิภาพเป็นสิ่งสำคัญสำหรับการเพิ่มประสิทธิภาพการจัดเก็บและการส่งข้อมูล Aspose.Zip สำหรับ .NET มอบโซลูชันที่ทรงพลัง และหนึ่งในคุณสมบัติที่โดดเด่นคือความสามารถในการใช้ประโยชน์จากการทำงานแบบขนานสำหรับการบีบอัดไฟล์ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการใช้การทำงานแบบขนานเพื่อบีบอัดไฟล์โดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
-  ติดตั้ง Aspose.Zip สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).
- ความรู้เกี่ยวกับแนวคิดการบีบอัดไฟล์

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

 ตรวจสอบให้แน่ใจว่าคุณมีไดเร็กทอรีเอกสารพร้อมโดยการกำหนดเส้นทางใน`dataDir` ตัวแปร. ไดเร็กทอรีนี้จะมีไฟล์ที่คุณต้องการบีบอัด

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เริ่มต้นกระบวนการบีบอัด

ตอนนี้ เรามาเริ่มต้นกระบวนการบีบอัดด้วยการเปิดไฟล์ ZIP เพื่อเขียน:

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // รหัสสำหรับการบีบอัดของคุณจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 3: อ่านและบีบอัดไฟล์แบบขนาน

 ข้างใน`using` บล็อก ให้เปิดไฟล์ต้นฉบับที่คุณต้องการบีบอัด ในตัวอย่างนี้ เราใช้ "alice29.txt" และ "asyoulik.txt":

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // รหัสสำหรับบีบอัดไฟล์แบบขนานจะอยู่ที่นี่
    }
}
```

## ขั้นตอนที่ 4: สร้างรายการเก็บถาวร

ใช้ Aspose.Zip เพื่อสร้างรายการสำหรับแต่ละไฟล์ภายในไฟล์เก็บถาวร:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // รหัสของคุณสำหรับรายการเพิ่มเติมจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 5: กำหนดเกณฑ์ความเท่าเทียม

 กำหนดเกณฑ์ความเท่าเทียมโดยใช้`ParallelOptions`: :

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## ขั้นตอนที่ 6: บันทึกไฟล์บีบอัดที่บีบอัด

บันทึกไฟล์บีบอัดที่บีบอัดด้วยตัวเลือกที่ระบุ:

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

ยินดีด้วย! คุณใช้การทำงานแบบขนานในการบีบอัดไฟล์โดยใช้ Aspose.Zip สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจคุณสมบัติอันทรงพลังของการบีบอัดไฟล์แบบขนานใน Aspose.Zip สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้ คุณจะเพิ่มประสิทธิภาพกระบวนการบีบอัดไฟล์ได้ ซึ่งจะช่วยปรับปรุงประสิทธิภาพของแอปพลิเคชัน .NET ของคุณได้ในที่สุด

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับไลบรารี .NET อื่นๆ ได้หรือไม่

ตอบ 1: ใช่ Aspose.Zip สำหรับ .NET ได้รับการออกแบบมาให้ทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น

### คำถามที่ 2: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่

 A2: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนเพิ่มเติมหรือถามคำถามได้ที่ไหน

 A3: เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 4: มีตัวอย่างหรือเอกสารประกอบอะไรบ้าง

 A4: สำรวจ[เอกสาร Aspose.Zip](https://reference.aspose.com/zip/net/) สำหรับตัวอย่างและเอกสารที่ครอบคลุม

### คำถามที่ 5: ฉันจะซื้อ Aspose.Zip สำหรับ .NET ได้อย่างไร

 A5: คุณสามารถซื้อ Aspose.Zip สำหรับ .NET ได้[ที่นี่](https://purchase.aspose.com/buy).