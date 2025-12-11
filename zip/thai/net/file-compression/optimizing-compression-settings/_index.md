---
date: 2025-12-10
description: เรียนรู้วิธีสร้างไฟล์บีบอัด LZMA zip และใช้การบีบอัดแบบ store zip ด้วย
  Aspose.Zip สำหรับ .NET ปรับแต่งวิธีการ Bzip2, LZMA, PPMd, Enhanced Deflate และ Store.
linktitle: Optimizing Compression Settings
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้างไฟล์ Zip แบบ LZMA โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มประสิทธิภาพการตั้งค่าการบีบอัดด้วย Aspose.Zip สำหรับ .NET

ในโลกของการพัฒนา .NET การ **บีบอัดไฟล์** อย่างมีประสิทธิภาพสามารถลดค่าใช้จ่ายในการจัดเก็บและเร่งความเร็วการถ่ายโอนข้อมูลได้อย่างมาก ไม่ว่าคุณจะกำลังสร้างแอปเว็บ ASP.NET, ยูทิลิตี้บนเดสก์ท็อป, หรือบริการคลาวด์ การรู้วิธี **create LZMA zip archive** จะให้คุณได้เปรียบอย่างมากสำหรับการบีบอัดที่อัตราสูง ในบทเรียนนี้เราจะพาคุณผ่านแต่ละวิธีการบีบอัด—Bzip2, LZMA, PPMd, Enhanced Deflate, และ Store—เพื่อให้คุณเลือกอัลกอริทึมที่เหมาะกับสถานการณ์ของคุณและปรับแต่งการตั้งค่าให้ได้ผลลัพธ์ที่ดีที่สุด

## คำตอบอย่างรวดเร็ว
- **ประโยชน์หลักของการบีบอัด LZMA คืออะไร?** อัตราการบีบอัดที่สูงที่สุดพร้อมความเร็วที่สมเหตุสมผลสำหรับไฟล์ส่วนใหญ่  
- **วิธีใดที่เก็บไฟล์โดยไม่บีบอัด?** การบีบอัดแบบ Store (หรือที่เรียกว่า “store compression zip”)  
- **ฉันสามารถใช้การตั้งค่าเหล่านี้ในแอป ASP.NET ได้หรือไม่?** ได้—เพียงแค่อ้างอิง Aspose.Zip ในโปรเจกต์ของคุณและเรียกใช้ API เดียวกัน  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้  
- **เวอร์ชัน .NET ที่รองรับมีอะไรบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “create LZMA zip archive” คืออะไร?
การสร้าง LZMA zip archive หมายถึงการบรรจุไฟล์หนึ่งหรือหลายไฟล์ลงในคอนเทนเนอร์ ZIP พร้อมใช้ алгоритм LZMA เพื่อให้ได้การบีบอัดที่เหนือกว่า Aspose.Zip จะจัดการรายละเอียดระดับต่ำให้คุณ ทำให้คุณโฟกัสที่ตรรกะของธุรกิจได้เต็มที่

## ทำไมต้องใช้ Aspose.Zip สำหรับการบีบอัดไฟล์ .NET?
- **Unified API** – อินเทอร์เฟซเดียวที่สอดคล้องสำหรับ Bzip2, LZMA, PPMd, Enhanced Deflate, และ Store  
- **Performance‑tuned** – การทำงานแบบเนทีฟที่ปรับแต่งเพื่อความเร็วสูง  
- **ASP.NET friendly** – ทำงานได้อย่างราบรื่นในโปรเจกต์เว็บ, บริการพื้นหลัง, และ Azure Functions  
- **Fine‑grained control** – ปรับขนาดพจนานุกรม, ระดับการบีบอัด, และอื่น ๆ ได้ตามต้องการ

## ข้อกำหนดเบื้องต้น
- **Aspose.Zip for .NET Library** – ดาวน์โหลดและติดตั้งจาก [Aspose documentation](https://reference.aspose.com/zip/net/)  
- **Sample Text File** – เตรียมไฟล์ตัวอย่าง (เช่น `sample.txt`) ที่คุณจะทำการบีบอัด  
- **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio 2022 หรือ IDE ที่เข้ากันได้อื่น ๆ

## นำเข้า Namespaces

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้มาดูการตั้งค่าการบีบอัดแต่ละแบบกัน

## การใช้การตั้งค่า Bzip2 Compression

### ขั้นตอนที่ 1: เริ่มต้น Bzip2 Compression

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new Bzip2CompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## วิธีการ create LZMA zip archive ด้วย Aspose.Zip

### ขั้นตอนที่ 1: เริ่มต้น LZMA Compression

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new LzmaCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## การใช้การตั้งค่า PPMd Compression

### ขั้นตอนที่ 1: เริ่มต้น PPMd Compression

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new PPMdCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## การใช้การตั้งค่า Enhanced Deflate Compression

### ขั้นตอนที่ 1: เริ่มต้น Enhanced Deflate Compression

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new EnhancedDeflateCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## การใช้การตั้งค่า Store Compression (store compression zip)

### ขั้นตอนที่ 1: เริ่มต้น Store Compression

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **เคล็ดลับมืออาชีพ:** ปรับตัวแปร `dataDir` ให้ชี้ไปยังไดเรกทอรีทำงานจริงของคุณ, และใช้อินสแตนซ์ `Archive` เดียวกันหากต้องการเพิ่มหลายไฟล์ลงในอาร์ไคฟ์เดียว

## ปัญหาทั่วไป & วิธีแก้
- **ข้อผิดพลาด “File not found”** – ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\` หรือ `/`) และไฟล์ `sample.txt` มีอยู่จริง  
- **การใช้หน่วยความจำสูงกับไฟล์ขนาดใหญ่** – ใช้ `ArchiveEntrySettings` เพื่อเปิดโหมดสตรีมมิ่ง ซึ่งจะเขียนข้อมูลโดยตรงไปยังสตรีมเอาต์พุต  
- **ระดับการบีบอัดที่ไม่เข้ากัน** – อัลกอริทึมบางตัว (เช่น LZMA) มีคุณสมบัติเพิ่มเติมเช่น `DictionarySize` ตรวจสอบเอกสาร API หากต้องการการควบคุมที่ละเอียดกว่า

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Zip for .NET ร่วมกับไลบรารีการบีบอัดอื่นได้หรือไม่?**  
A: Aspose.Zip ถูกออกแบบให้ทำงานกับอัลกอริทึมในตัวของมันเอง การรวมไลบรารีของบุคคลที่สามเป็นไปได้แต่ต้องจัดการด้วยโค้ดนอก API ของ Aspose

**Q: จะเพิ่มการป้องกันด้วยรหัสผ่านให้กับ zip ที่สร้างด้วย Aspose.Zip อย่างไร?**  
A: Aspose.Zip รองรับการป้องกันด้วยรหัสผ่าน ดูรายละเอียดใน [documentation](https://reference.aspose.com/zip/net/) สำหรับเมธอด `SetPassword`

**Q: มีเวอร์ชันทดลองให้ลองใช้หรือไม่?**  
A: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองได้ [ที่นี่](https://releases.aspose.com/)

**Q: จะหาชุมชนช่วยเหลือหรือถามคำถามได้จากที่ไหน?**  
A: สำหรับการสนับสนุนและการสนทนาชุมชน, เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)

**Q: สามารถขอรับลิขสิทธิ์ชั่วคราวเพื่อการประเมินผลได้หรือไม่?**  
A: ได้, คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

**Q: วิธีนี้ช่วยการบีบอัดไฟล์ใน asp.net อย่างไร?**  
A: โดยการเรียกใช้ API เดียวกันจากคอนโทรลเลอร์หรือมิดเดิลแวร์ของ ASP.NET, คุณสามารถบีบอัดไฟล์แบบเรียลไทม์ก่อนส่งให้คลายแคลิฟท์, ลดแบนด์วิธและเพิ่มประสิทธิภาพการรับชมของผู้ใช้

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}