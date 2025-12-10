---
date: 2025-12-05
description: เรียนรู้วิธีสร้างไฟล์ zip และเพิ่มไฟล์ลงใน zip ด้วย Aspose.Zip สำหรับ
  .NET คู่มือแบบขั้นตอนนี้แสดงวิธีบีบอัดไฟล์ด้วย FileInfo ในโครงการ ASP.NET
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีสร้างไฟล์ Zip Archive ด้วย Aspose.Zip สำหรับ .NET – บีบอัดไฟล์ด้วย FileInfo
url: /th/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง Zip Archive ด้วย Aspose.Zip สำหรับ .NET

## Introduction

หากคุณต้องการ **สร้างไฟล์ zip archive** ด้วยโปรแกรม, Aspose.Zip สำหรับ .NET ให้ API ที่สะอาดและประสิทธิภาพสูงที่ทำงานได้ในแอปพลิเคชัน .NET ใด ๆ (รวมถึง ASP.NET) ในบทแนะนำนี้เราจะเดินผ่านการบีบอัดไฟล์ด้วยคลาส `FileInfo`, แสดงวิธี **เพิ่มไฟล์ลงใน zip**, และอธิบายว่าทำไมวิธีนี้จึงเหมาะกับโครงการ .NET สมัยใหม่. เริ่มกันเลย!

## Quick Answers
- **วิธีที่ง่ายที่สุดในการสร้าง zip archive คืออะไร?** Use Aspose.Zip’s `Archive` class together with `FileInfo` objects.  
- **ฉันสามารถเพิ่มหลายไฟล์พร้อมกันได้หรือไม่?** Yes – just create a `FileInfo` for each file and call `CreateEntry`.  
- **ฉันต้องการไลเซนส์พิเศษสำหรับ ASP.NET หรือไม่?** A commercial Aspose.Zip license is required for production; a free trial works for evaluation.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** Yes, as long as each thread works with its own `Archive` instance.

## What is a Zip Archive and Why Create One?
Zip archive จะรวมไฟล์หนึ่งหรือหลายไฟล์ไว้ในคอนเทนเนอร์เดียวที่ถูกบีบอัด ซึ่งช่วยลดพื้นที่จัดเก็บ, เร่งความเร็วการส่งข้อมูลผ่านเครือข่าย, และทำให้การแจกจ่ายง่ายขึ้น ไม่ว่าคุณจะส่งบันทึก, ส่งออกรายงาน, หรือแพ็คเกจทรัพยากรให้ลูกค้า การรู้ **how to create zip archive** ด้วยโปรแกรมเป็นทักษะที่มีคุณค่าสำหรับนักพัฒนา .NET ทุกคน

## Why Use Aspose.Zip to Add Files to Zip?
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – pure .NET implementation.  
- **ควบคุมระดับการบีบอัดและการเข้ารหัสได้เต็มที่** (ASCII, UTF‑8, etc.).  
- **รองรับไฟล์ขนาดใหญ่** (> 4 GB) และการป้องกันด้วยรหัสผ่าน.  
- **API สม่ำเสมอระหว่าง .NET Framework, .NET Core, และ .NET 5+**.

## Prerequisites

ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

1. **Aspose.Zip for .NET** ที่ติดตั้งแล้ว. ดาวน์โหลดแพคเกจล่าสุดจาก [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด (เช่น `alice29.txt` และ `fields.c`).  

## Import Namespaces

ในไฟล์ C# ใด ๆ ที่คุณจะทำงานกับ zip archive, เพิ่ม `using` statements ต่อไปนี้:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Document Directory

กำหนดโฟลเดอร์ที่เก็บไฟล์ต้นทาง. แทนที่ตัวแปร placeholder ด้วยพาธแบบ absolute หรือ relative บนระบบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Use `Path.Combine` to build paths in a cross‑platform way.

### Step 2: Open a Zip File for Writing

สร้าง `FileStream` ที่ชี้ไปยังไฟล์ zip ผลลัพธ์. สตรีมเปิดในโหมด **Create** ซึ่งจะเขียนทับไฟล์ที่มีอยู่ที่ชื่อเดียวกัน:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Step 3: Prepare `FileInfo` Objects for Each Source File

`FileInfo` ให้ Aspose.Zip เข้าถึงไฟล์จริงบนดิสก์โดยตรง. สร้างอินสแตนซ์หนึ่งสำหรับแต่ละไฟล์ที่ต้องการบีบอัด:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** It avoids loading the entire file into memory, which is especially helpful for large files.

### Step 4: Create the Archive and Add Entries

สร้างอ็อบเจกต์ `Archive`, แล้วเรียก `CreateEntry` สำหรับแต่ละ `FileInfo`. อาร์กิวเมนต์แรกคือชื่อไฟล์ภายใน zip, อาร์กิวเมนต์ที่สองคือ `FileInfo` ต้นทาง:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Step 5: Save the Zip Archive with Desired Encoding

บันทึก archive ไปยัง `FileStream` ที่เปิดไว้ก่อนหน้านี้. ตัวอย่างนี้ใช้การเข้ารหัส ASCII สำหรับชื่อ entry, แต่คุณสามารถสลับเป็น UTF‑8 หากชื่อไฟล์ของคุณมีอักขระที่ไม่ใช่ ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

เมื่อบล็อก `using` สิ้นสุด, สตรีมจะถูกปิดโดยอัตโนมัติและไฟล์ zip จะพร้อมใช้งาน

## Common Issues & Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Empty zip file** | `FileInfo` points to a non‑existent path | Verify `dataDir` and file names; use `File.Exists` to check before creating entries. |
| **Incorrect filename encoding** | Using the default encoding with non‑ASCII names | Set `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException on large files** | Loading whole file into memory | `FileInfo` streams the file; ensure you are not reading the file into a byte array elsewhere. |
| **Permission denied** | Application lacks write permission for the output folder | Run the app with appropriate rights or choose a writable directory. |

## Frequently Asked Questions

**Q: Can I add password protection to the zip archive?**  
A: Yes. After creating the `Archive`, set `archive.Password = "yourPassword"` before calling `Save`.

**Q: Is it possible to update an existing zip file?**  
A: Aspose.Zip supports opening an existing archive with `Archive.Open` and then adding new entries.

**Q: How do I compress files in an ASP.NET MVC controller?**  
A: The same code works; just ensure the output stream is sent back as a `FileResult` to the client.

**Q: Does Aspose.Zip support encryption algorithms?**  
A: It supports standard ZipCrypto and AES‑256 encryption.

**Q: What if I need to compress a folder recursively?**  
A: Loop through `Directory.GetFiles` (and sub‑folders) and create a `FileInfo` for each file, then add them to the archive.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusion

คุณได้เรียนรู้ **how to create zip archive** ด้วย Aspose.Zip สำหรับ .NET, วิธี **add files to zip**, และเหตุผลที่วิธีนี้เหมาะกับ ASP.NET และแอปพลิเคชัน .NET อื่น ๆ ทดลองปรับระดับการบีบอัด, การเข้ารหัส, และตัวเลือกการเข้ารหัสเพิ่มเติมเพื่อให้ archive ตรงตามความต้องการของคุณเอง ขอให้สนุกกับการบีบอัด!

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}