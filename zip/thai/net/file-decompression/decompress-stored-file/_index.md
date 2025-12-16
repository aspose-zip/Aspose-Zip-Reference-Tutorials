---
date: 2025-12-16
description: เรียนรู้วิธีสร้างไฟล์ zip โดยไม่มีการบีบอัดและการแตกไฟล์ zip หลายไฟล์โดยใช้
  Aspose.Zip สำหรับ .NET คู่มือนี้ครอบคลุมวิธีเปิดไฟล์ zip, อ่านรายการ zip, และขั้นตอนการแตกไฟล์
  zip ด้วย C#
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้าง Zip โดยไม่มีการบีบอัดและแตกไฟล์ – Aspose.Zip
url: /th/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การแตกไฟล์ที่เก็บไว้โดยใช้ Aspose.Zip สำหรับ .NET

## Introduction

ในแอปพลิเคชัน .NET สมัยใหม่, **create zip without compression** เป็นเทคนิคที่มีประโยชน์เมื่อคุณต้องการการบีบอัดที่เร็วโดยไม่มีภาระของการลดขนาดข้อมูล. Aspose.Zip สำหรับ .NET ทำให้การสร้าง archive แบบนี้และจากนั้น **extract multiple zip files** ในภายหลังเป็นเรื่องง่าย. ในบทแนะนำนี้คุณจะได้เห็นวิธีเปิด zip, อ่านข้อมูล entry ของ zip, และทำการ **C# extract zip** ทีละขั้นตอน.

## Quick Answers
- **What is “create zip without compression”?** หมายถึงการเพิ่มไฟล์ลงใน ZIP archive ด้วยวิธี “store” ซึ่งทำให้ข้อมูลคงเดิมไม่ถูกบีบอัด.
- **Which library handles this in .NET?** Aspose.Zip for .NET.
- **Do I need a license to run the sample?** การทดลองใช้ฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.
- **Can I extract several files at once?** ใช่ – บทแนะนำแสดงวิธี **extract multiple zip files** ในลูป.
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create zip without compression”?

เมื่อคุณสร้าง ZIP archive ด้วยวิธีการบีบอัด **store**, ไฟล์แต่ละไฟล์จะถูกเพิ่มโดยไม่มีการเปลี่ยนแปลงใด ๆ ซึ่งทำให้ archive มีขนาดใหญ่กว่า ZIP ที่บีบอัด, แต่การดำเนินการเร็วกว่าอย่างมากและไบต์ของไฟล์ต้นฉบับยังคงไม่ถูกแก้ไข – เหมาะสำหรับสถานการณ์ที่ความเร็วหรือความสมบูรณ์ของข้อมูลสำคัญกว่าขนาด.

## Why use Aspose.Zip for .NET?
- **Full control** ในระดับการบีบอัด (store vs. deflate).  
- **Simple API** สำหรับอ่าน entry, เปิดไฟล์ zip, และดึงข้อมูล.  
- **Cross‑platform** รองรับ .NET Framework, .NET Core, และ .NET 5+.

## Prerequisites

ก่อนที่เราจะเริ่มบทแนะนำนี้, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.Zip for .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Zip for .NET คุณสามารถหาไลบรารีได้จาก [here](https://releases.aspose.com/zip/net/).
- Document Directory: สร้างไดเรกทอรีในระบบของคุณเพื่อเก็บไฟล์ที่จำเป็นสำหรับบทแนะนำนี้.

## Import Namespaces

เพื่อเริ่มต้น, ให้เรานำเข้า namespaces ที่จำเป็นสำหรับโปรเจกต์ของเรา:

```csharp
using Aspose.Zip;
using System.IO;
```

## How to Create Zip Without Compression

ก่อนอื่นเราต้องการ ZIP archive ที่ใช้วิธี **store** (คือไม่มีการบีบอัด). โค้ดตัวอย่างด้านล่างสร้าง archive ดังกล่าวและจัดทำโดย Aspose.Zip เป็นเมธอดช่วยเหลือ. การรันโค้ดนี้จะสร้างไฟล์ `StoreMultipleFilesWithoutCompression_out.zip` ในไดเรกทอรีของคุณ.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** เมธอดช่วยเหลือนี้ตั้งค่า `CompressionMethod.Store` สำหรับแต่ละ entry ภายใน, ทำให้ archive ถูกสร้างโดยไม่มีการบีบอัดข้อมูลใด ๆ.

## How to Open Zip and Extract Multiple Files

เมื่อเรามี ZIP ที่เก็บไว้แล้ว, มาดู **how to open zip** และดึงไฟล์ออก.

### Step 2.1: Opening the Zip File

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

อ็อบเจกต์ `Archive` แสดงถึง ZIP ที่เปิดและให้คุณเข้าถึงแต่ละ entry ผ่านคอลเลกชัน `Entries`.

### Step 2.2: Creating Extracted Files

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

ที่นี่เรา **read zip entry** 0, คัดลอกไบต์ของมันไปยังไฟล์ใหม่, และปิดสตรีมโดยอัตโนมัติด้วย `using` statements.

### Step 2.3: Repeating the Process for Another File

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

โดยการวนลูปผ่าน `archive.Entries`, คุณสามารถ **extract multiple zip files** (หรือหลาย entry) ด้วยเพียงไม่กี่บรรทัดของโค้ด.

## Common Issues and Solutions

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `FileNotFoundException` เมื่อเปิด ZIP | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่า `dataDir` ลงท้ายด้วยเครื่องหมายทับ `/` หรือใช้ `Path.Combine`. |
| ไฟล์ที่ดึงออกเป็นไฟล์ว่าง | บัฟเฟอร์ไม่ได้ flush | `using` block จะทำการ flush อัตโนมัติ; ตรวจสอบว่าคุณอ่านสตรีมจนกว่า `bytesRead` จะเป็น 0 (ตามที่แสดง). |
| License exception | รันโดยไม่มีลิขสิทธิ์ที่ถูกต้อง | ใช้ลิขสิทธิ์ทดลองหรือถาวรก่อนการปรับใช้. |

## Frequently Asked Questions

### Q1: Aspose.Zip for .NET รองรับทุก .NET framework หรือไม่?

**A:** ใช่, Aspose.Zip for .NET ถูกออกแบบให้เข้ากันได้กับหลาย .NET framework, ให้ความยืดหยุ่นแก่ผู้พัฒนา.

### Q2: ฉันสามารถใช้ Aspose.Zip for .NET ในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์ได้หรือไม่?

**A:** ใช่, Aspose.Zip for .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์. ดูรายละเอียดลิขสิทธิ์ที่ [purchase page](https://purchase.aspose.com/buy).

### Q3: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip for .NET อย่างไร?

**A:** สำหรับการสนับสนุน, เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37), ที่ซึ่งชุมชนของนักพัฒนาและผู้เชี่ยวชาญจะช่วยเหลือคุณ.

### Q4: มีการทดลองใช้ฟรีสำหรับ Aspose.Zip for .NET หรือไม่?

**A:** มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.Zip for .NET โดยรับการทดลองใช้ฟรี [here](https://releases.aspose.com/).

### Q5: ฉันสามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้หรือไม่?

**A:** ได้, คุณสามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบโดยไปที่ [this link](https://purchase.aspose.com/temporary-license/).

### Q6: ฉันจะอ่าน zip entry โดยไม่ต้องแตก archive ทั้งหมดได้อย่างไร?

**A:** ใช้ `archive.Entries[index].Open()` เพื่อรับสตรีมของ entry เฉพาะ, แล้วอ่านไบต์ที่ต้องการตามที่แสดงในโค้ดข้างต้น.

### Q7: วิธีที่ดีที่สุดในการ **extract multiple zip files** ในลูปคืออะไร?

**A:** วนลูป `archive.Entries` ด้วย `foreach`, เปิดสตรีมของแต่ละ entry และเขียนลงไฟล์ปลายทาง, คล้ายกับรูปแบบที่แสดงในขั้นตอน 2.2 และ 2.3.

## Conclusion

การเชี่ยวชาญ **create zip without compression** และกระบวนการดึงข้อมูลต่อไปเป็นสิ่งสำคัญสำหรับแอปพลิเคชัน .NET ที่มีประสิทธิภาพสูง. Aspose.Zip for .NET ให้ API ที่สะอาดและใช้งานง่ายเพื่อ **how to open zip**, อ่านแต่ละ **zip entry**, และทำการ **C# extract zip** ด้วยโค้ดที่น้อยที่สุด. ด้วยการทำตามคู่มือนี้, คุณได้เรียนรู้วิธีสร้าง archive ที่เก็บไว้, เปิดมัน, และดึงเนื้อหาออกอย่างมีประสิทธิภาพ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-16  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.12  
**ผู้เขียน:** Aspose