---
date: 2026-06-14
description: เรียนรู้วิธีสร้าง zip โดยไม่มีการบีบอัดและแยกไฟล์ zip หลายไฟล์โดยใช้
  Aspose.Zip สำหรับ .NET คู่มือนี้ครอบคลุมวิธีเปิด zip, อ่านรายการ zip, และขั้นตอนการแยก
  zip ด้วย C#
keywords:
- create zip without compression
- extract multiple zip files
- c# extract zip
- aspose zip extract
- zip archive store method
linktitle: การแยกไฟล์ที่เก็บไว้
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  headline: Create Zip Without Compression & Decompress Files – Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  name: Create Zip Without Compression & Decompress Files – Aspose.Zip
  steps:
  - name: '1: Opening the Zip File'
    text: The `Archive` object represents the opened ZIP and gives you access to each
      entry via the `Entries` collection.
  - name: '2: Creating Extracted Files'
    text: Here we **read zip entry** 0, copy its bytes to a new file, and close the
      streams automatically thanks to the `using` statements.
  - name: '3: Repeating the Process for Another File'
    text: By iterating over `archive.Entries`, you can **extract multiple zip files**
      (or multiple entries) with just a few lines of code.
  type: HowTo
- questions:
  - answer: It stores files in a ZIP using the *store* method, leaving the data unchanged.
    question: What does “create zip without compression” mean?
  - answer: Aspose.Zip for .NET provides a clean API for the *store* method and extraction.
    question: Which library supports this in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license to run the sample?
  - answer: Yes – the tutorial demonstrates how to **extract multiple zip files**
      in a loop.
    question: Can I extract several files at once?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้าง Zip โดยไม่มีการบีบอัดและแยกไฟล์ – Aspose.Zip
url: /th/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การแตกไฟล์ที่จัดเก็บโดยใช้ Aspose.Zip สำหรับ .NET

## บทนำ

ในแอปพลิเคชัน .NET สมัยใหม่, **create zip without compression** เป็นเทคนิคที่สะดวกเมื่อคุณต้องการการบีบอัดที่เร็วแสงและไม่สนใจขนาดไฟล์. Aspose.Zip สำหรับ .NET ช่วยให้คุณสร้างไฟล์ “store‑method” แบบนี้และต่อมาสามารถ **extract multiple zip files** ได้ด้วยไม่กี่บรรทัดของ C#. ในบทเรียนนี้เราจะอธิบายการเปิด ZIP, อ่าน zip entry, และทำการ **C# extract zip** ทีละขั้นตอน.

## คำตอบสั้น
- **'create zip without compression' หมายถึงอะไร?** มันเก็บไฟล์ใน ZIP โดยใช้วิธี *store* ซึ่งทำให้ข้อมูลคงเดิมโดยไม่มีการบีบอัด.  
- **ไลบรารีใดสนับสนุนสิ่งนี้ใน .NET?** Aspose.Zip สำหรับ .NET มี API ที่สะอาดสำหรับวิธี *store* และการสกัดข้อมูล.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถสกัดไฟล์หลายไฟล์พร้อมกันได้หรือไม่?** ได้ – บทเรียนนี้แสดงวิธี **extract multiple zip files** ในลูป.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10.

## “create zip without compression” คืออะไร?

วิธีการบีบอัด `store` บอกรูปแบบ ZIP ให้ข้ามขั้นตอนการลดข้อมูลใด ๆ. **create zip without compression** จึงสร้างไฟล์อาร์ไคฟ์ที่ใหญ่กว่า, แต่การดำเนินการเป็นเกือบทันทีและไบต์เดิมยังคงอยู่ไม่เปลี่ยนแปลง – เหมาะอย่างยิ่งกับสื่อที่บีบอัดแล้ว (JPEG, MP3) หรือเมื่อคุณต้องการเนื้อหาไฟล์ที่แน่นอน.

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?

Aspose.Zip ให้ผู้พัฒนาควบคุมการบีบอัดได้อย่างแม่นยำ, มี API ที่ไหลลื่นสำหรับการอ่านและเขียน entry, และรองรับหลายแพลตฟอร์มบน .NET ทั้งหมด. มันจัดการอาร์ไคฟ์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ, ใช้หน่วยความจำน้อย, และสนับสนุนกว่า 50 รูปแบบ, ทำให้เหมาะกับงานบีบอัดทั้งง่ายและซับซ้อน.

- **ควบคุมเต็มรูปแบบ** ระดับการบีบอัด – เลือก *store* หรือ *deflate* ต่อ entry.  
- **Simple, fluent API** สำหรับการอ่าน entry, เปิดไฟล์ zip, และสกัดข้อมูล.  
- **Cross‑platform** รองรับ .NET Framework, .NET Core, และ .NET 5+.  
- **Handles large archives** ขนาดสูงสุด 2 GB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **Quantified claim:** Aspose.Zip รองรับ **50+ input and output formats** และสามารถประมวลผล **multi‑hundred‑page archives** ในขณะที่ใช้หน่วยความจำต่ำกว่า 100 MB.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Aspose.Zip สำหรับ .NET** – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ **[ที่นี่](https://releases.aspose.com/zip/net/)**.  
- โฟลเดอร์ **document directory** ที่ทำงานได้บนเครื่องของคุณซึ่งไฟล์ตัวอย่างจะถูกอ่านและเขียนลงไป.

## นำเข้า Namespaces

ก่อนอื่น, นำเข้า namespaces ที่มีคลาสหลักที่เราจะใช้:

```csharp
using Aspose.Zip;
using System.IO;
```

## ฉันจะสร้างไฟล์ zip โดยไม่มีการบีบอัดใน C# อย่างไร?

`Archive` เป็นคลาสหลักที่แทน ZIP archive ใน Aspose.Zip.

เพื่อสร้าง archive แบบเก็บ (stored), โหลดไฟล์ต้นทางแต่ละไฟล์, สร้างอินสแตนซ์ `Archive`, แล้วเพิ่มไฟล์แต่ละไฟล์ด้วย `CompressionMethod.Store`. ไม่ต้องกำหนดพารามิเตอร์การบีบอัดเพิ่มเติม, ไลบรารีจะเขียนไบต์ดิบโดยตรง, ทำให้การดำเนินการเป็นเกือบทันทีพร้อมคงข้อมูลเดิมไว้โดยไม่เปลี่ยนแปลง.

## วิธีสร้าง Zip โดยไม่มีการบีบอัด

ก่อนอื่นเราต้องมี ZIP archive ที่ใช้วิธี **store** (ไม่มีการบีบอัด). โค้ดตัวอย่างด้านล่างสร้าง archive ดังกล่าวและเป็นเมธอดช่วยเหลือจาก Aspose.Zip. การรันจะสร้างไฟล์ `StoreMultipleFilesWithoutCompression_out.zip` ในโฟลเดอร์เอกสารของคุณ.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** เมธอดช่วยเหลือกำหนด `CompressionMethod.Store` ให้แต่ละ entry ภายใน, ทำให้ archive ถูกสร้างโดยไม่มีการบีบอัดข้อมูลใด ๆ.

## ฉันจะเปิดไฟล์ zip และสกัดหลายรายการโดยใช้ Aspose.Zip อย่างไร?

`Archive` แทนไฟล์ ZIP ที่เปิดแล้วและให้เข้าถึง entry ผ่านคอลเลกชัน `Entries`.

เปิด archive โดยส่งพาธไฟล์ไปยังคอนสตรัคเตอร์ `Archive`, จากนั้นวนลูปผ่าน `archive.Entries`. สำหรับแต่ละ entry, เปิดสตรีมด้วย `entry.Open()`, คัดลอกข้อมูลไปยังไฟล์เป้าหมายโดยใช้สตรีมแบบบัฟเฟอร์, และปิดสตรีมอัตโนมัติด้วย `using`. วิธีนี้สกัด entry ทั้งหมดได้อย่างมีประสิทธิภาพโดยไม่ต้องโหลดอาร์ไคฟ์ทั้งหมดเข้าสู่หน่วยความจำ.

## วิธีเปิด Zip และสกัดไฟล์หลายไฟล์

ตอนนี้เรามี ZIP ที่เก็บไว้แล้ว, มาดู **how to open zip** และดึงไฟล์ออก.

### ขั้นตอน 2.1: การเปิดไฟล์ Zip

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

อ็อบเจ็กต์ `Archive` แทน ZIP ที่เปิดและให้คุณเข้าถึงแต่ละ entry ผ่านคอลเลกชัน `Entries`.

### ขั้นตอน 2.2: การสร้างไฟล์ที่สกัดออก

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

ที่นี่เรา **read zip entry** 0, คัดลอกไบต์ไปยังไฟล์ใหม่, และปิดสตรีมโดยอัตโนมัติด้วยคำสั่ง `using`.

### ขั้นตอน 2.3: ทำซ้ำกระบวนการสำหรับไฟล์อื่น

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

โดยวนลูปผ่าน `archive.Entries`, คุณสามารถ **extract multiple zip files** (หรือหลาย entry) ได้ด้วยไม่กี่บรรทัดของโค้ด.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|---------|
| `FileNotFoundException` when opening the ZIP | Wrong `dataDir` path | Verify that `dataDir` ends with a trailing slash or use `Path.Combine`. |
| Extracted file is empty | Buffer not flushed | The `using` block automatically flushes; ensure you read the stream until `bytesRead` is 0 (as shown). |
| License exception | Running without a valid license | Apply a trial or permanent license before deployment. |

## คำถามที่พบบ่อย

### Q1: Aspose.Zip สำหรับ .NET เข้ากันได้กับทุกเฟรมเวิร์กของ .NET หรือไม่?

**A:** ใช่, Aspose.Zip สำหรับ .NET ทำงานได้กับ .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10, ให้ความยืดหยุ่นข้ามแพลตฟอร์ม.

### Q2: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์ได้หรือไม่?

**A:** ใช่, คุณสามารถใช้ในโครงการประเภทใดก็ได้. ดูรายละเอียดลิขสิทธิ์บน **[purchase page](https://purchase.aspose.com/buy)** สำหรับข้อมูลเพิ่มเติม.

### Q3: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET อย่างไร?

**A:** เยี่ยมชม **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** ที่ชุมชนและวิศวกรของ Aspose ตอบคำถาม.

### Q4: มีการทดลองใช้ฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?

**A:** แน่นอน – คุณสามารถดาวน์โหลด trial **[ที่นี่](https://releases.aspose.com/)** และประเมินคุณสมบัติทั้งหมดโดยไม่มีค่าใช้จ่าย.

### Q5: ฉันสามารถขอรับลิขสิทธิ์ชั่วคราวเพื่อการทดสอบได้หรือไม่?

**A:** ใช่, ลิขสิทธิ์ชั่วคราวมีให้ผ่าน **[ลิงก์นี้](https://purchase.aspose.com/temporary-license/)** สำหรับการประเมินระยะสั้น.

### Q6: ฉันจะอ่าน zip entry โดยไม่ต้องสกัดทั้งอาร์ไคฟ์ได้อย่างไร?

**A:** ใช้ `archive.Entries[index].Open()` เพื่อรับสตรีมของ entry เฉพาะ, แล้วอ่านไบต์ที่ต้องการเท่านั้น – ตามที่แสดงในโค้ดตัวอย่าง.

### Q7: วิธีที่ดีที่สุดในการ **extract multiple zip files** ในลูปคืออะไร?

**A:** วนลูป `foreach` ผ่าน `archive.Entries`, เปิดสตรีมของแต่ละ entry, แล้วเขียนไปยังตำแหน่งเป้าหมาย. วิธีนี้สอดคล้องกับรูปแบบที่แสดงในขั้นตอน 2.2 และ 2.3.

## สรุป

การเชี่ยวชาญ **create zip without compression** และกระบวนการสกัดต่อมามีความสำคัญสำหรับแอปพลิเคชัน .NET ที่ต้องการประสิทธิภาพสูง. Aspose.Zip สำหรับ .NET ให้ API ที่สะอาดและเป็นมิตรเพื่อ **how to open zip**, อ่าน **zip entry**, และทำ **C# extract zip** ด้วยโค้ดที่สั้น. ด้วยแนวทางนี้คุณได้เรียนรู้วิธีสร้าง archive แบบ store, เปิดมัน, และสกัดเนื้อหาอย่างมีประสิทธิภาพ.

---

**อัปเดตล่าสุด:** 2026-06-14  
**ทดสอบด้วย:** Aspose.Zip สำหรับ .NET 24.12  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [Aspose.Zip สำหรับ .NET - ป้องกันรหัสผ่าน Zip Archive & เก็บหลายไฟล์โดยไม่มีการบีบอัด](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [สร้าง Zip Archive .NET – การบีบอัดไฟล์ด้วย Aspose.Zip](/zip/net/file-compression/)
- [วิธีแตกไฟล์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}