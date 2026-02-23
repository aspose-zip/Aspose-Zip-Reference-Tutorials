---
date: 2026-02-23
description: เรียนรู้วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip สำหรับ .NET และสร้างไฟล์
  tar.lz อย่างมีประสิทธิภาพ
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดหลายไฟล์เป็น tar ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดหลายไฟล์ tar ด้วย Aspose.Zip สำหรับ .NET

ในงานพัฒนา .NET สมัยใหม่ การจัดแพ็กไฟล์อย่างมีประสิทธิภาพสามารถลดขนาดการปรับใช้และเวลาในการถ่ายโอนเครือข่ายได้อย่างมาก **Compress multiple files tar** เป็นความต้องการที่พบบ่อยเมื่อคุณต้องการไฟล์ TAR ที่บีบอัดด้วย LZ‑lightweight สำหรับการสำรองข้อมูล การแจกจ่าย หรือการอัปโหลดไปยังคลาวด์ ในบทเรียนนี้เราจะพาคุณผ่านตัวอย่าง **tar.lz compression example** อย่างชัดเจน ทีละขั้นตอนโดยใช้ไลบรารี Aspose.Zip เพื่อให้คุณสร้าง **tar.lz archive** ได้อย่างรวดเร็วในแอปพลิเคชันของคุณเอง

## คำตอบอย่างรวดเร็ว
- **What library should I use?** Aspose.Zip for .NET.  
- **How long does the implementation take?** About 5‑10 minutes for a basic example.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I compress multiple files at once?** Yes – just add more entries before saving.

## วิธีบีบอัดหลายไฟล์ tar
ส่วนนี้ตอบตรงกับคีย์เวิร์ดหลักและแสดงขั้นตอนที่แม่นยำเพื่อ **compress multiple files tar** ด้วย Aspose.Zip วิธีการทำงานได้กับไฟล์จำนวนใดก็ได้และคุณสามารถปรับให้เข้ากับโครงสร้างโฟลเดอร์ของคุณได้อย่างง่ายดาย

## tar.lz compression คืออะไร?
`tar.lz` คือไฟล์ TAR ที่ถูกบีบอัดด้วยอัลกอริทึม LZMA (มักเรียกสั้น ๆ ว่า **LZ**) มันผสานความเรียบง่ายของการจัดกลุ่มไฟล์ของ TAR กับอัตราการบีบอัดสูงของ LZ ทำให้เหมาะสำหรับไฟล์สำรอง การแจกจ่ายแพคเกจ หรือสถานการณ์ใด ๆ ที่แบนด์วิธเป็นสิ่งสำคัญ

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?
Aspose.Zip แยกรายละเอียดระดับล่างของการสร้างอาร์ไคฟ์เวอร์ออกให้คุณด้วย API แบบวัตถุ‑ออเรียนต์ที่สะอาด คุณจะได้:

* **Zero external dependencies** – pure .NET implementation.  
* **Cross‑platform support** – works on Windows, Linux, and macOS.  
* **Built‑in LZ compression** – no need to install additional native tools.  
* **Strong error handling** – exceptions are descriptive, making debugging easier.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้แน่ใจว่าคุณมี:

- **Aspose.Zip for .NET** library – download it from [here](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการทำอาร์ไคฟ์เวอร์ เส้นทางของโฟลเดอร์นี้จะถูกเก็บไว้ในตัวแปร `dataDir` (คุณจะตั้งค่าในขั้นตอน 3)

## นำเข้า Namespaces
เพิ่ม Namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสที่เราจะใช้จากที่ไหน

```csharp
using System;
using Aspose.Zip.Tar;
```

## วิธีสร้าง tar.lz archive – คู่มือขั้นตอน

### ขั้นตอน 1: บีบอัดไฟล์เดียว
ตัวอย่างแรกแสดงสถานการณ์พื้นฐานที่สุด – การเพิ่มไฟล์หนึ่งไฟล์ลงในอาร์ไคฟ์เวอร์ TAR แล้วบันทึกเป็นไฟล์ **tar.lz**

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**คำอธิบาย**

- `new TarArchive()` creates an empty TAR container.  
- `CreateEntry` adds the file `alice29.txt` from your `dataDir`.  
- `SaveLzipped` writes the archive to disk and applies LZ compression, producing `archive.tar.lz`.

### ขั้นตอน 2: บีบอัดหลายไฟล์ใน archive เดียว
บ่อยครั้งที่คุณต้องรวมไฟล์หลายไฟล์เข้าด้วยกัน เพียงเรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก ตัวอย่างนี้แสดง **add files to tar lz** และทำให้ **compress multiple files tar** สำเร็จ

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**คำอธิบาย**

- The code follows the same pattern as Step 1, but adds a second entry (`lcet10.txt`).  
- You can repeat `CreateEntry` as many times as needed; the library handles the internal TAR structure automatically.

### ขั้นตอน 3: ระบุไดเรกทอรีเอกสารของคุณ
แทนที่ตัวแปร placeholder ด้วยเส้นทางจริงที่ไฟล์ต้นฉบับของคุณอยู่ เส้นทางนี้จะถูกใช้โดยตัวอย่างข้างต้น

```csharp
string dataDir = "Your Document Directory";
```

**คำอธิบาย**

- Set `dataDir` to a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`.  
- Keeping the directory in a variable makes the code reusable and easier to maintain.

## ข้อผิดพลาดทั่วไป & การแก้ไขปัญหา
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `FileNotFoundException` when running the sample | `dataDir` points to a non‑existent folder or the file name is misspelled | Verify the path and file names; use `Path.Combine` for safety. |
| Output file is **0 KB** | `archive.SaveLzipped` was called before any entries were added | Ensure at least one `CreateEntry` call precedes `SaveLzipped`. |
| Compression seems slow | Large files with default buffer size | Consider processing files in chunks or using asynchronous I/O if performance is critical. |

## สรุป
คุณได้เรียนรู้ **how to compress tar.lz** ด้วย Aspose.Zip สำหรับ .NET แล้ว ไม่ว่าจะเป็นการจัดการเอกสารเดียวหรือหลายไฟล์ ตัวอย่าง **tar.lz compression example** นี้แสดงวิธีที่สะอาดและพร้อมใช้งานในระดับ production เพื่อ **create tar lz archive** ที่สามารถถ่ายโอนหรือเก็บรักษาได้อย่างง่ายดาย

## คำถามที่พบบ่อย

**Q:** สามารถบีบอัดไฟล์ขนาดใดก็ได้ด้วย Aspose.Zip สำหรับ .NET?  
**A:** ได้, ไลบรารีรองรับไฟล์ขนาดเล็กและขนาดใหญ่มาก; เพียงตรวจสอบว่ามีหน่วยความจำและพื้นที่ดิสก์เพียงพอสำหรับโครงสร้าง TAR ชั่วคราว

**Q:** โค้ดนี้เข้ากันได้กับรุ่นล่าสุดของ Aspose.Zip หรือไม่?  
**A:** ตัวอย่างนี้ตั้งเป้าหมายที่เวอร์ชันปัจจุบัน; ควรอัปเดตแพ็กเกจ NuGet อย่างสม่ำเสมอเพื่อรับการแก้บั๊กและฟีเจอร์ใหม่

**Q:** มีข้อพิจารณาเรื่องลิขสิทธิ์หรือไม่?  
**A:** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานใน production. ดูรายละเอียดลิขสิทธิ์ได้ที่ [Aspose website](https://purchase.aspose.com/buy).

**Q:** สามารถใช้ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** แน่นอน – เมื่อคุณมีลิขสิทธิ์ที่ถูกต้อง คุณสามารถฝังไลบรารีนี้ในแอปพลิเคชันเชิงพาณิชย์ใดก็ได้

**Q:** จะหาความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?  
**A:** เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและทีมงานอย่างเป็นทางการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-02-23  
**ทดสอบด้วย:** Aspose.Zip for .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose