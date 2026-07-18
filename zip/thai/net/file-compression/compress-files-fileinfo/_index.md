---
date: 2026-07-18
description: เรียนรู้วิธีเพิ่มโฟลเดอร์ลงใน zip และเพิ่มไฟล์ลงใน zip ด้วย Aspose.Zip
  สำหรับ .NET คู่มือขั้นตอนนี้แสดงวิธีบีบอัดไฟล์ด้วย FileInfo ในโครงการ ASP.NET
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: บีบอัดไฟล์ด้วย FileInfo
og_description: เพิ่มโฟลเดอร์ลงใน zip ด้วย Aspose.Zip สำหรับ .NET เรียนรู้วิธีสร้างไฟล์
  zip, เพิ่มไฟล์ลงใน zip, และบีบอัดโฟลเดอร์อย่างมีประสิทธิภาพใน ASP.NET
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: เพิ่มโฟลเดอร์ลงใน Zip – บีบอัดไฟล์ด้วย Aspose.Zip สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: เพิ่มโฟลเดอร์ลงใน Zip ด้วย Aspose.Zip สำหรับ .NET – บีบอัดไฟล์ด้วย FileInfo
url: /th/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มโฟลเดอร์ลงใน Zip ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **เพิ่มโฟลเดอร์ลงใน zip** อย่างอัตโนมัติ Aspose.Zip สำหรับ .NET มี API ที่สะอาดและมีประสิทธิภาพสูงซึ่งทำงานได้ในแอปพลิเคชัน .NET ใด ๆ (รวมถึง ASP.NET) ในบทแนะนำนี้เราจะอธิบายขั้นตอนการบีบอัดไฟล์ด้วยคลาส `FileInfo` แสดงวิธี **เพิ่มไฟล์ลงใน zip** และอธิบายว่าทำไมวิธีนี้จึงเหมาะกับโครงการ .NET สมัยใหม่ เราจะครอบคลุมขั้นตอนที่แน่นอนเพื่อ **เพิ่มโฟลเดอร์ลงใน zip** เพื่อให้คุณสามารถบรรจุไดเรกทอรีทั้งหมดในหนึ่งการดำเนินการ เริ่มกันเลย!

## คำตอบสั้น
- **วิธีที่ง่ายที่สุดในการสร้างไฟล์ zip archive คืออะไร?** ใช้คลาส `Archive` ของ Aspose.Zip ร่วมกับอ็อบเจ็กต์ `FileInfo`.  
- **ฉันสามารถเพิ่มหลายไฟล์พร้อมกันได้หรือไม่?** ได้ – เพียงสร้าง `FileInfo` สำหรับแต่ละไฟล์และเรียก `CreateEntry`.  
- **ฉันต้องการใบอนุญาตพิเศษสำหรับ ASP.NET หรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Zip แบบเชิงพาณิชย์สำหรับการใช้งานจริง; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** ใช่ ตราบใดที่แต่ละเธรดทำงานกับอินสแตนซ์ `Archive` ของตนเอง.

## Zip Archive คืออะไรและทำไมต้องสร้าง?
Zip archive จะรวมไฟล์หนึ่งหรือหลายไฟล์ไว้ในคอนเทนเนอร์เดียวที่ถูกบีบอัด ซึ่งช่วยลดพื้นที่จัดเก็บ เร่งความเร็วการส่งข้อมูลผ่านเครือข่าย และทำให้การแจกจ่ายง่ายขึ้น ไม่ว่าจะเป็นการส่งบันทึก, การส่งออกรายงาน, หรือการบรรจุสินทรัพย์สำหรับลูกค้า การรู้ **วิธีสร้าง zip archive** อย่างโปรแกรมเมติกเป็นทักษะที่มีคุณค่าสำหรับนักพัฒนา .NET ทุกคน.

## ทำไมต้องใช้ Aspose.Zip เพื่อเพิ่มไฟล์ลงใน Zip?
Aspose.Zip ให้โซลูชัน pure‑.NET ที่กำจัดการพึ่งพาไลบรารีภายนอกในขณะที่ให้ผู้พัฒนาควบคุมการบีบอัด, การเข้ารหัส, และความปลอดภัยได้อย่างละเอียด รองรับไฟล์ขนาดใหญ่, การป้องกันด้วยรหัสผ่าน, และทำงานอย่างสม่ำเสมอในทุกเวอร์ชัน .NET ที่สนับสนุน ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับแอปพลิเคชันทั้งแบบเก่าและสมัยใหม่.  
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – การทำงานแบบ pure .NET.  
- **ควบคุมระดับการบีบอัดและการเข้ารหัสได้เต็มที่** (ASCII, UTF‑8 ฯลฯ).  
- **รองรับไฟล์ที่ใหญ่กว่า 4 GB** และการป้องกันด้วยรหัสผ่าน.  
- **API สม่ำเสมอในกว่า 50 เวอร์ชัน .NET** – ตั้งแต่ .NET Framework 2.0 จนถึง .NET 10.  

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมี:

1. ติดตั้ง **Aspose.Zip for .NET**. ดาวน์โหลดแพคเกจล่าสุดจาก [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด (เช่น `alice29.txt` และ `fields.c`).  

## นำเข้า Namespaces

ในไฟล์ C# ใด ๆ ที่คุณจะทำงานกับ zip archive ให้เพิ่ม `using` statements ต่อไปนี้:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Namespaces เหล่านี้ทำให้คุณเข้าถึงคลาส `Archive`, ตัวเลือกการบันทึก, และยูทิลิตี้ I/O มาตรฐาน.

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ

ก่อนอื่นกำหนดโฟลเดอร์ที่เก็บไฟล์ต้นทาง แทนที่ตัวแปร placeholder ด้วยพาธแบบ absolute หรือ relative บนระบบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เพื่อสร้างเส้นทางแบบข้ามแพลตฟอร์ม.

### ขั้นตอนที่ 2: เปิดไฟล์ Zip เพื่อเขียน

สร้าง `FileStream` ที่ชี้ไปยังไฟล์ zip ผลลัพธ์ สตรีมจะเปิดในโหมด **Create** ซึ่งจะเขียนทับไฟล์ที่มีชื่อเดียวกันใด ๆ:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ขั้นตอนที่ 3: เตรียมอ็อบเจ็กต์ `FileInfo` สำหรับไฟล์ต้นทางแต่ละไฟล์

`FileInfo` ให้ Aspose.Zip เข้าถึงไฟล์จริงบนดิสก์โดยตรง สร้างอินสแตนซ์หนึ่งต่อไฟล์ที่ต้องการบีบอัด:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **ทำไมต้องใช้ `FileInfo`?** มันช่วยหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ซึ่งเป็นประโยชน์อย่างยิ่งสำหรับไฟล์ขนาดใหญ่.

### ขั้นตอนที่ 4: สร้าง Archive และเพิ่มรายการ

คลาส `Archive` เป็นอ็อบเจ็กต์หลักของ Aspose.Zip ที่แสดง zip container ในหน่วยความจำ สร้างอ็อบเจ็กต์ `Archive` แล้วเรียก `CreateEntry` สำหรับแต่ละ `FileInfo` อาร์กิวเมนต์แรกคือชื่อไฟล์ภายใน zip, อาร์กิวเมนต์ที่สองคือ `FileInfo` ต้นทาง:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

เมธอด `CreateEntry` จะเพิ่มรายการไฟล์ใหม่ลงใน archive โดยเชื่อมชื่อรายการกับ `FileInfo` ต้นทางเพื่อให้ข้อมูลถูกสตรีมโดยตรงจากดิสก์เมื่อบันทึก archive.

### ขั้นตอนที่ 5: บันทึก Zip Archive ด้วยการเข้ารหัสที่ต้องการ

สุดท้ายบันทึก archive ไปยัง `FileStream` ที่เปิดไว้ก่อนหน้านี้ ที่นี่เราใช้การเข้ารหัส ASCII สำหรับชื่อรายการ แต่คุณสามารถสลับเป็น UTF‑8 หากชื่อไฟล์ของคุณมีอักขระที่ไม่ใช่ ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

เมื่อบล็อก `using` สิ้นสุด สตรีมจะถูกปิดโดยอัตโนมัติและไฟล์ zip จะพร้อมใช้งาน.

## วิธีเพิ่มโฟลเดอร์ลงใน Zip ด้วย Aspose.Zip?

โหลดไดเรกทอรีเป้าหมาย, แยกรายการไฟล์ทั้งหมด, แล้วเพิ่มแต่ละไฟล์พร้อมพาธสัมพันธ์ที่รวมชื่อโฟลเดอร์ วิธีนี้ทำให้คุณ **เพิ่มโฟลเดอร์ลงใน zip** โดยไม่ต้องระบุไฟล์แต่ละไฟล์ด้วยตนเอง โดยการรักษาโครงสร้างโฟลเดอร์ในชื่อรายการ, archive ที่ได้สามารถแตกออกพร้อมโครงสร้างไดเรกทอรีเดิมซึ่งสำคัญสำหรับหลายสถานการณ์การปรับใช้.

1. ใช้ `DirectoryInfo` เพื่อระบุโฟลเดอร์ที่ต้องการบีบอัด.  
2. เรียก `GetFiles("*", SearchOption.AllDirectories)` เพื่อดึงไฟล์ทั้งหมดแบบเรียกซ้ำ.  
3. สำหรับแต่ละไฟล์ สร้าง `FileInfo` และเรียก `CreateEntry` ด้วยเส้นทางเช่น `"MyFolder/Report.pdf"`.  

เนื่องจาก API ทำงานกับ `FileInfo` มันสตรีมไฟล์แต่ละไฟล์โดยตรงจากดิสก์ ทำให้การใช้หน่วยความจำน้อยแม้โฟลเดอร์จะมีข้อมูลหลายร้อยเมกะไบต์.

## ปัญหาทั่วไปและวิธีแก้

| Issue | Cause | Fix |
|-------|-------|-----|
| **ไฟล์ zip ว่าง** | `FileInfo` ชี้ไปยังเส้นทางที่ไม่มีอยู่ | ตรวจสอบ `dataDir` และชื่อไฟล์; ใช้ `File.Exists` เพื่อตรวจสอบก่อนสร้างรายการ. |
| **การเข้ารหัสชื่อไฟล์ไม่ถูกต้อง** | ใช้การเข้ารหัสเริ่มต้นกับชื่อที่ไม่ใช่ ASCII | ตั้งค่า `Encoding = Encoding.UTF8` ใน `ArchiveSaveOptions`. |
| **OutOfMemoryException กับไฟล์ขนาดใหญ่** | โหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ | `FileInfo` สตรีมไฟล์; ตรวจสอบว่าคุณไม่ได้อ่านไฟล์เป็นอาร์เรย์ไบต์ที่อื่น. |
| **การปฏิเสธสิทธิ์** | แอปพลิเคชันไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่สามารถเขียนได้. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มโฟลเดอร์ทั้งหมดลงใน zip archive ด้วยการเรียกครั้งเดียวได้หรือไม่?**  
A: ไม่มีเมธอดเรียกครั้งเดียว แต่การแยกรายการไฟล์ด้วย `DirectoryInfo` แล้วเพิ่มแต่ละไฟล์ผ่าน `CreateEntry` จะให้ผลลัพธ์เดียวกันอย่างมีประสิทธิภาพ.

**Q: Aspose.Zip รองรับการป้องกันด้วยรหัสผ่านหรือไม่?**  
A: ใช่ คุณสามารถตั้งรหัสผ่านบนอ็อบเจ็กต์ `Archive` ก่อนบันทึกเพื่อเข้ารหัส archive ทั้งหมด.

**Q: Aspose.Zip สามารถจัดการไฟล์ zip ขนาดเท่าไหร่?**  
A: ไลบรารีสามารถประมวลผลไฟล์ที่ใหญ่กว่า 4 GB และสร้าง archive ที่เกิน 10 GB ได้โดยไม่ต้องโหลด archive ทั้งหมดเข้าสู่หน่วยความจำ.

**Q: API นี้เข้ากันได้กับ .NET 6 และ .NET 8 หรือไม่?**  
A: แน่นอน Aspose.Zip รองรับ .NET 5 ถึง .NET 10 ครอบคลุมทุกเวอร์ชัน LTS ปัจจุบัน.

**Q: มีระดับการบีบอัดใดบ้าง?**  
A: คุณสามารถเลือก `CompressionLevel.NoCompression`, `Fast`, `Normal`, หรือ `Maximum` เพื่อปรับสมดุลระหว่างความเร็วและขนาด.

## แหล่งข้อมูลเพิ่มเติม

- ดาวน์โหลดแพคเกจ Aspose.Zip ล่าสุด: [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/zip/net/)  
- ซื้อใบอนุญาตสำหรับการใช้งานจริง: [หน้าซื้อ](https://purchase.aspose.com/buy)  
- รับความช่วยเหลือจากชุมชน: [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37)  
- ทดลอง Aspose.Zip ฟรี: [ทดลองฟรีที่นี่](https://releases.aspose.com/)  
- รับใบอนุญาตชั่วคราวเพื่อการประเมิน: [ลิงก์นี้](https://purchase.aspose.com/temporary-license/)

## สรุป

คุณตอนนี้รู้แล้ว **วิธีเพิ่มโฟลเดอร์ลงใน zip** และ **วิธีสร้าง zip archive** ด้วย Aspose.Zip สำหรับ .NET, วิธี **เพิ่มไฟล์ลงใน zip**, และทำไมวิธีนี้จึงเหมาะกับ ASP.NET และแอปพลิเคชัน .NET อื่น ๆ ทดลองใช้ระดับการบีบอัด, การเข้ารหัส, และตัวเลือกการเข้ารหัสต่าง ๆ เพื่อปรับ archive ให้ตรงกับความต้องการของคุณ Happy compressing!

---

**อัปเดตล่าสุด:** 2026-07-18  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.12 (latest)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [บีบอัดหลายไฟล์ c# – การบีบอัดที่ง่ายดายด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-compression/compress-multiple-files/)
- [สร้าง Zip Archive .NET – การบีบอัดไฟล์ด้วย Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}