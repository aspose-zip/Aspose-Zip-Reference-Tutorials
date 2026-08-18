---
date: 2026-06-14
description: เรียนรู้วิธีอ่านไฟล์ GZIP และแยกออกเป็น MemoryStream ด้วย Aspose.Zip
  สำหรับ .NET – บทแนะนำสั้น ๆ สำหรับนักพัฒนา C#
keywords:
- how to read gzip
- how to extract zip
- extract zip to stream
- c# extract zip stream
linktitle: การแยกออกเป็น Memory Stream
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read GZIP files and extract them to a MemoryStream using
    Aspose.Zip for .NET – a concise tutorial for C# developers.
  headline: How to Read GZIP and Extract to MemoryStream with Aspose.Zip
  type: TechArticle
- description: Learn how to read GZIP files and extract them to a MemoryStream using
    Aspose.Zip for .NET – a concise tutorial for C# developers.
  name: How to Read GZIP and Extract to MemoryStream with Aspose.Zip
  steps:
  - name: Set Up Your Document Directory
    text: Define the path where your sample archive resides.
  - name: Initialize a MemoryStream
    text: Create an empty `MemoryStream` that will receive the extracted data.
  - name: Open the GZIP Archive and Extract
    text: The `CopyTo` method **copies the archive to MemoryStream**, giving you an
      in‑memory representation of the original file. `CopyTo` copies data from one
      stream to another efficiently.
  - name: Verify the Extraction
    text: A simple console message confirms success.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10, making it versatile for modern applications.
    question: Is Aspose.Zip compatible with all versions of .NET?
  - answer: Absolutely. The library provides both extraction and creation APIs, allowing
      you to build ZIP files programmatically.
    question: Can I use Aspose.Zip to create ZIP archives as well?
  - answer: Visit the [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) for community
      help and official guidance.
    question: Where can I find additional support or examples?
  - answer: Yes, you can start a free trial by downloading from the Aspose website
      [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: A temporary license can be requested from the Aspose portal [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีอ่านไฟล์ GZIP และแยกออกเป็น MemoryStream ด้วย Aspose.Zip
url: /th/net/other-compression-techniques/extract-to-memory-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่านไฟล์ GZIP และแยกออกเป็น MemoryStream ด้วย Aspose.Zip

## บทนำ

หากคุณกำลังมองหาวิธีที่เชื่อถือได้ในการ **how to read gzip** อาร์ไคฟ์โดยตรงเข้าสู่หน่วยความจำ Aspose.Zip สำหรับ .NET ทำให้กระบวนการง่ายขึ้น ในบทเรียนนี้เราจะอธิบายขั้นตอนการแยกไฟล์ GZIP ไปยัง `MemoryStream` ซึ่งคุณสามารถใช้งานได้เช่นเดียวกับแหล่งข้อมูลในหน่วยความจำอื่น ๆ — เหมาะสำหรับการประมวลผลไฟล์แบบเรียลไทม์ การส่งข้อมูลผ่านเครือข่าย หรือการหลีกเลี่ยงไฟล์ชั่วคราวบนดิสก์.  
`MemoryStream` คือสตรีมของ .NET ที่เก็บข้อมูลในหน่วยความจำ ทำให้การอ่าน/เขียนเร็วโดยไม่ต้องใช้ I/O ของดิสก์.

## คำตอบสั้น
- **ไลบรารีที่จัดการการแยก ZIP/GZIP คืออะไร?** Aspose.Zip for .NET  
- **ฉันสามารถแยกไปยัง MemoryStream ได้หรือไม่?** ใช่ – ใช้ `CopyTo` บน archive ที่เปิดไว้.  
- **รูปแบบที่รองรับ?** ZIP, GZIP, TAR, และอื่น ๆ.  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่เข้ากันได้คืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10

## Aspose.Zip คืออะไร

Aspose.Zip คือไลบรารีของ .NET ที่ทำให้การทำงานกับไฟล์บีบอัดง่ายขึ้น มันซ่อนรายละเอียดระดับต่ำของรูปแบบ ZIP และ GZIP ให้คุณมุ่งเน้นที่ตรรกะธุรกิจ — เช่น **copy archive to memorystream** — แทนที่จะต้องจัดการกับระบบไฟล์.

## ทำไมต้องแยกไปยัง MemoryStream

การแยกไปยัง `MemoryStream` ช่วยหลีกเลี่ยงค่าใช้จ่ายของการสร้างไฟล์ชั่วคราว ลดความหน่วงของ I/O และทำให้ส่งข้อมูลไปยัง API ที่คาดหวังสตรีมได้ง่าย (เช่น การตอบสนอง HTTP, ตัวประมวลผลภาพ, หรือฐานข้อมูลในหน่วยความจำ) สิ่งนี้เป็นประโยชน์อย่างยิ่งในสถาปัตยกรรมคลาวด์‑เนทีฟหรือไมโครเซอร์วิส.

## ข้อกำหนดเบื้องต้น
- **Visual Studio** (รุ่นล่าสุดใดก็ได้).  
- **Aspose.Zip for .NET** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์ที่มีไฟล์ตัวอย่าง GZIP ชื่อ `sample.gz`.

## นำเข้า Namespace

เพิ่ม Namespace ที่จำเป็นลงในไฟล์ C# ของคุณ:

```csharp
using Aspose.Zip.Gzip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ฉันจะอ่านไฟล์ GZIP ใน .NET อย่างไร

โหลดอาร์ไคฟ์ GZIP ด้วย `GzipArchive.Open` แล้วคัดลอกรายการของมันไปยัง `MemoryStream` รูปแบบสองขั้นตอนนี้จะอ่านข้อมูลที่บีบอัดโดยตรงเข้าสู่หน่วยความจำโดยไม่ต้องสัมผัสระบบไฟล์ ทำให้คุณเข้าถึงไบต์ที่ไม่ได้บีบอัดได้ทันที วิธี `GzipArchive.Open` จะเปิดไฟล์ GZIP และคืนค่าอ็อบเจกต์ GzipArchive เพื่ออ่านรายการของมัน คุณยังสามารถระบุเส้นทางแบบสัมพัทธ์หรือแบบเต็มได้ และไลบรารีจะจัดการเปิดสตรีมไฟล์ภายในโดยอัตโนมัติ พร้อมรับประกันการปล่อยทรัพยากรอย่างเหมาะสมหลังการแยก.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ

กำหนดเส้นทางที่ไฟล์อาร์ไคฟ์ตัวอย่างของคุณอยู่.

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้าง MemoryStream

สร้าง `MemoryStream` ว่างเปล่าที่จะรับข้อมูลที่แยกออกมา.

```csharp
var ms = new MemoryStream();
```

### ขั้นตอนที่ 3: เปิดอาร์ไคฟ์ GZIP และแยกข้อมูล

เมธอด `CopyTo` **คัดลอกอาร์ไคฟ์ไปยัง MemoryStream** ทำให้คุณได้การแสดงผลในหน่วยความจำของไฟล์ต้นฉบับ `CopyTo` จะคัดลอกข้อมูลจากสตรีมหนึ่งไปยังอีกสตรีมหนึ่งอย่างมีประสิทธิภาพ.

```csharp
//ExStart: ExtractToMemoryStream
using (GzipArchive archive = new GzipArchive(File.OpenRead(dataDir + "sample.gz")))
{
    archive.Open().CopyTo(ms);
    Console.WriteLine(archive.Name);
}
//ExEnd: ExtractToMemoryStream
```

### ขั้นตอนที่ 4: ตรวจสอบการแยกข้อมูล

ข้อความคอนโซลง่าย ๆ จะยืนยันว่าการแยกสำเร็จ.

```csharp
Console.WriteLine("Successfully Extracted to Memory Stream");
```

## วิธีแยกไฟล์ ZIP ไปยัง Stream ใน C#?

ใช้ขั้นตอนเดียวกัน — แทนที่ `GzipArchive` ด้วย `ZipArchive` `ZipArchive` แทนไฟล์ ZIP และให้เมธอดสำหรับอ่านหรือแยกรายการของมัน เรียก `zipArchive.ExtractAllToStream(memoryStream)` (หรือวนลูปรายการและ `CopyTo`) แล้วคุณจะมีเนื้อหา ZIP ทั้งหมดอยู่ใน `MemoryStream` `ExtractAllToStream` จะทำการแยกรายการทั้งหมดของอาร์ไคฟ์โดยตรงไปยังสตรีมที่ให้ไว้ นอกจากนี้คุณยังสามารถตั้งค่าระดับการบีบอัดหรือรักษาโครงสร้างไดเรกทอรีโดยกำหนดตัวเลือกของอาร์ไคฟ์ก่อนการแยก วิธีนี้ทำงานกับประเภทอาร์ไคฟ์ใด ๆ ที่ Aspose.Zip รองรับ.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **การรีเซ็ต MemoryStream:** หลังจากแยกแล้ว ให้ตั้งค่า `ms.Position = 0` ก่อนอ่านสตรีมจากที่อื่น.  
- **ไฟล์ขนาดใหญ่:** สำหรับอาร์ไคฟ์ขนาดใหญ่มาก ให้พิจารณาประมวลผลสตรีมเป็นชิ้น ๆ เพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง Aspose.Zip สามารถจัดการอาร์ไคฟ์ที่มี **500+ ไฟล์** และขนาดรวมสูงสุด **2 GB** โดยไม่ต้องโหลดอาร์ไคฟ์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **การปล่อยทรัพยากร:** บล็อก `using` ทำให้แน่ใจว่าการจัดการไฟล์อาร์ไคฟ์ถูกปล่อยอย่างรวดเร็ว.

## คำถามที่พบบ่อย
**Q: Aspose.Zip รองรับทุกเวอร์ชันของ .NET หรือไม่?**  
A: ใช่, Aspose.Zip รองรับ .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10 ทำให้ใช้งานได้หลากหลายสำหรับแอปพลิเคชันสมัยใหม่.

**Q: ฉันสามารถใช้ Aspose.Zip เพื่อสร้างไฟล์ ZIP ได้ด้วยหรือไม่?**  
A: แน่นอน. ไลบรารีนี้มี API สำหรับการแยกและการสร้าง ทำให้คุณสามารถสร้างไฟล์ ZIP ด้วยโค้ดได้.

**Q: Where can I find additional support or examples?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชนและคำแนะนำอย่างเป็นทางการ.

**Q: มีรุ่นทดลองฟรีหรือไม่?**  
A: มี, คุณสามารถเริ่มรุ่นทดลองฟรีได้โดยดาวน์โหลดจากเว็บไซต์ Aspose [ที่นี่](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: สามารถขอไลเซนส์ชั่วคราวจากพอร์ทัลของ Aspose [ที่นี่](https://purchase.aspose.com/temporary-license/).

## สรุป

ใน **aspose zip tutorial** นี้เราได้อธิบายกระบวนการเต็มรูปแบบของการอ่านอาร์ไคฟ์ GZIP และแยกออกไปยัง `MemoryStream` ด้วย Aspose.Zip สำหรับ .NET โดยทำตามขั้นตอนเหล่านี้คุณจะสามารถ **copy archive to memorystream** อย่างมีประสิทธิภาพ หลีกเลี่ยงไฟล์ชั่วคราว และรวมข้อมูลที่แยกออกเข้ากับตรรกะของแอปพลิเคชันของคุณได้โดยตรง อย่าลังเลที่จะสำรวจรูปแบบอาร์ไคฟ์อื่น ๆ และคุณลักษณะขั้นสูงเช่นการป้องกันด้วยรหัสผ่านหรือการแยกแบบหลายเธรด.

---

**อัปเดตล่าสุด:** 2026-06-14  
**ทดสอบด้วย:** Aspose.Zip 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีเปิดอาร์ไคฟ์ GZip และเทคนิคการบีบอัดอื่น ๆ ด้วย Aspose.Zip สำหรับ .NET](/zip/net/other-compression-techniques/)
- [วิธีแยกไฟล์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/)
- [แยกไฟล์ AES - บทเรียน Aspose.Zip .NET](/zip/net/password-protection-and-encryption/decompress-aes-encrypted-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}