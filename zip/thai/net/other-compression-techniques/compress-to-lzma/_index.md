---
date: 2025-12-17
description: เรียนรู้วิธีบีบอัด LZMA ใน Aspose.Zip สำหรับ .NET เพื่อเพิ่มประสิทธิภาพการจัดเก็บและการถ่ายโอนข้อมูล
linktitle: Compress to Lzma
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัด LZMA ใน Aspose.Zip สำหรับ .NET
url: /th/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัด LZMA ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีบีบอัด LZMA** ด้วย Aspose.Zip สำหรับ .NET ซึ่งเป็นทักษะสำคัญสำหรับการเพิ่มประสิทธิภาพการใช้พื้นที่จัดเก็บและเพิ่มประสิทธิภาพการถ่ายโอนข้อมูล Aspose.Zip สำหรับ .NET ให้โซลูชันที่ทรงพลังสำหรับการบีบอัดไฟล์ โดยมีอัลกอริทึมหลายแบบรวมถึง LZMA เพื่อให้คุณเลือกใช้ตามความต้องการของคุณ

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Zip for .NET  
- **อัลกอริทึมใดที่คู่มือนี้ครอบคลุม?** LZMA compression  
- **ฉันต้องการไลเซนส์หรือไม่?** A temporary license is sufficient for testing; a full license is required for production.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** Typically under 10 minutes for a basic file.

## วิธีบีบอัด LZMA

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Zip for .NET: ตรวจสอบให้แน่ใจว่าได้ติดตั้งไลบรารี Aspose.Zip แล้ว คุณสามารถค้นหาเอกสารได้ [ที่นี่](https://reference.aspose.com/zip/net/).
- Document Directory: เลือกหรือสร้างโฟลเดอร์ที่มีไฟล์ที่คุณต้องการบีบอัด

## นำเข้า Namespaces

เพิ่ม Namespaces ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณ เพื่อให้สามารถเข้าถึงฟังก์ชัน LZMA ของ Aspose.Zip ได้:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory

```csharp
string dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงของโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบีบอัด

## ขั้นตอนที่ 2: บีบอัดไฟล์ด้วย LZMA

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

ที่นี่เราจะสร้างอินสแตนซ์ของ `LzmaArchive` ชี้ไปที่ไฟล์ต้นทาง (`alice29.txt`) แล้วบันทึกผลลัพธ์ที่บีบอัดเป็น `archive.lzma`

## ขั้นตอนที่ 3: แสดงข้อความสำเร็จ

```csharp
Console.WriteLine("Successfully Compressed a File");
```

หลังจากการบีบอัดเสร็จสิ้น บรรทัดนี้จะแจ้งให้ผู้ใช้ทราบว่าการดำเนินการสำเร็จ

## สรุป

ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีบีบอัด LZMA** ด้วย Aspose.Zip สำหรับ .NET อย่างสำเร็จ เทคนิคการบีบอัดที่มีประสิทธิภาพนี้ช่วยลดพื้นที่จัดเก็บและเร่งความเร็วการถ่ายโอนข้อมูล ทำให้แอปพลิเคชันของคุณตอบสนองได้ดีขึ้นและคุ้มค่ามากยิ่งขึ้น

## คำถามที่พบบ่อย

### Q1: Aspose.Zip รองรับอัลกอริทึมการบีบอัดอื่น ๆ หรือไม่?

A1: Yes, Aspose.Zip for .NET supports various compression algorithms, including Lzma, Deflate, and BZip2.

### Q2: ฉันจะหาเอกสารของ Aspose.Zip สำหรับ .NET ได้ที่ไหน?

A2: The documentation is available [here](https://reference.aspose.com/zip/net/).

### Q3: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?

A3: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q4: มีตัวอย่างโค้ดสำหรับอัลกอริทึมการบีบอัดต่าง ๆ ไหม?

A4: Yes, you can find code samples in the documentation for different compression algorithms.

### Q5: ฉันจะขอรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Zip สำหรับ .NET ได้ที่ไหน?

A5: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for support and discussions.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถบีบอัดหลายไฟล์เป็นไฟล์ LZMA เดียวได้หรือไม่?**  
**ตอบ:** Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.

**ถาม: มีวิธีตั้งค่าระดับการบีบอัดสำหรับ LZMA หรือไม่?**  
**ตอบ:** The `LzmaArchive` class uses the default compression level, which provides a good balance between speed and size. Advanced settings are available through the `LzmaEncoder` if you need fine‑tuned control.

**ถาม: ไฟล์ .lzma ที่ได้จะทำงานบนแพลตฟอร์มที่ไม่ใช่ Windows หรือไม่?**  
**ตอบ:** Absolutely. The LZMA format is platform‑agnostic, so the archive can be decompressed on any OS with an LZMA‑compatible tool.

**ถาม: ฉันจะทำการแตกไฟล์ LZMA ด้วย Aspose.Zip อย่างไร?**  
**ตอบ:** Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()` to extract its contents.

**ถาม: Aspose.Zip รองรับการบีบอัดแบบสตรีมเพื่อหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำหรือไม่?**  
**ตอบ:** Yes. You can work with streams by passing `Stream` objects to `SetSource()` and `Save()` methods.

---

**อัปเดตล่าสุด:** 2025-12-17  
**ทดสอบกับ:** Aspose.Zip for .NET (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}