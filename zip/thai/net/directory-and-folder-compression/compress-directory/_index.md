---
date: 2026-05-30
description: เรียนรู้วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET, สร้างไฟล์ zip
  archive อย่างมีประสิทธิภาพ, และลดพื้นที่จัดเก็บในแอปพลิเคชัน .NET ของคุณ.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: วิธีบีบอัดโฟลเดอร์
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการบีบอัดโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีบีบอัดโฟลเดอร์** อย่างรวดเร็วและเชื่อถือได้ด้วย Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้เดสก์ท็อป, บริการบนคลาวด์, หรือสคริปต์สำรองข้อมูลอัตโนมัติ การบีบอัดโฟลเดอร์เป็นไฟล์ ZIP สามารถลดขนาดการจัดเก็บได้อย่างมากและเร่งความเร็วการถ่ายโอนข้อมูลบนเครือข่าย เราจะเดินผ่านทุกขั้นตอน, อธิบายว่าทำไมแต่ละบรรทัดถึงสำคัญ, และชี้ให้เห็นข้อผิดพลาดทั่วไปเพื่อให้คุณนำเทคนิคนี้ไปใช้ด้วยความมั่นใจ

## คำตอบสั้น
- **Aspose.Zip ทำอะไร?** มันให้ API .NET ที่ง่ายสำหรับการสร้างและสกัดไฟล์ ZIP โดยไม่ต้องพึ่งพาไลบรารีภายนอก  
- **การทำงานนี้ใช้เวลานานแค่ไหน?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับการบีบอัดโฟลเดอร์พื้นฐาน  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, และ .NET 5‑10  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่, จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถบีบอัดหลายโฟลเดอร์พร้อมกันได้หรือไม่?** แน่นอน—ใช้เมธอด `CreateEntries` กับคอลเลกชัน `DirectoryInfo` ใดก็ได้เพื่อ **บีบอัดหลายโฟลเดอร์** ในการทำงานครั้งเดียว  

`CreateEntries` เพิ่มไฟล์ทั้งหมดจากไดเรกทอรีไปยังอาร์ไคฟ์

## “วิธีบีบอัดโฟลเดอร์” คืออะไร

การบีบอัดโฟลเดอร์หมายถึงการนำไฟล์และโฟลเดอร์ย่อยทั้งหมดภายในไดเรกทอรีที่กำหนดมาจัดเก็บในไฟล์ ZIP ไฟล์เดียว ซึ่งช่วยลดขนาดโดยรวม, รักษาโครงสร้างต้นฉบับ, และทำให้การถ่ายโอนหรือการจัดเก็บข้อมูลง่ายขึ้น ไฟล์ ZIP ที่ได้สามารถเปิดได้บนทุกแพลตฟอร์มโดยไม่ต้องใช้ซอฟต์แวร์พิเศษ และยังคงโครงสร้างโฟลเดอร์ไว้เพื่อให้เมื่อทำการแตกไฟล์แล้วรูปแบบเดิมจะถูกกู้คืนอย่างแม่นยำ

## ทำไมต้องใช้ Aspose.Zip สำหรับงานนี้

Aspose.Zip ให้คุณ **สร้างไฟล์ zip archive** โดยตรงจากโค้ด .NET ด้วย API ที่สอดคล้องกันในทุก runtime ที่รองรับ โหลดคลาส `Archive`, เพิ่ม entry, ตั้งค่า `CompressionLevel`, กำหนดรหัสผ่าน (ถ้าต้องการ), แล้วเรียก `Save` ไลบรารีนี้สามารถประมวลผลโฟลเดอร์ที่มีไฟล์หลายพันไฟล์ได้ภายในไม่กี่วินาทีบนฮาร์ดแวร์ทั่วไป และรองรับรูปแบบการบีบอัดและอัลกอริทึมการเข้ารหัสกว่า 50 แบบ

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/zip/net/) หรือ [ที่นี่](https://releases.aspose.com/zip/net)  
- **Development Environment** – Visual Studio, Rider, หรือ IDE ใดก็ได้ที่รองรับ C#  
- **Document Directory** – แทนที่ `"Your Document Directory"` ในโค้ดด้วยเส้นทางของโฟลเดอร์ที่คุณต้องการบีบอัด  
- **Reference Documentation** – ดูเอกสารอย่างเป็นทางการ [ที่นี่](https://reference.aspose.com/zip/net/)

## นำเข้า Namespaces

เริ่มต้นโดยการนำเข้า namespaces ที่จำเป็น ซึ่งจะทำให้คุณเข้าถึงคลาสการบีบอัดหลักได้

```csharp
using Aspose.Zip;
using System.IO;
```

## วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip

ด้านล่างเป็นตัวอย่างที่ตรงไปตรงมาซึ่งแสดง **วิธีบีบอัดโฟลเดอร์** เนื้อหาแบบเดียวกันสามารถต่อยอดเพื่อ **บีบอัดหลายไฟล์ .net** หรือสร้างโครงสร้างอาร์ไคฟ์แบบกำหนดเองได้

### ขั้นตอนที่ 1: กำหนดค่า Document Directory ของคุณ

ตั้งค่าตัวแปร `dataDir` ให้เป็นเส้นทางของไดเรกทอรีที่ต้องการบีบอัด

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างไฟล์ ZIP ผลลัพธ์

เปิดอ็อบเจกต์ `FileStream` สองตัวสำหรับไฟล์ ZIP ผลลัพธ์ การทำเช่นนี้แสดงให้เห็นว่าคุณสามารถสร้างอาร์ไคฟ์มากกว่าหนึ่งไฟล์จากแหล่งเดียวกันได้—มีประโยชน์สำหรับการสำรองข้อมูลแบบเวอร์ชัน

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### ขั้นตอนที่ 3: บีบอัดไดเรกทอรี

คลาส `Archive` แทนไฟล์ ZIP และมีเมธอดสำหรับเพิ่ม entry และบันทึกไฟล์ ใช้เพื่อเพิ่ม entry ทุกอย่างจากโฟลเดอร์เป้าหมาย ตัวอย่างใช้โฟลเดอร์ตัวอย่างชื่อ **CanterburyCorpus** แต่คุณสามารถชี้ไปยังไดเรกทอรีใดก็ได้

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **เคล็ดลับ:** หากต้องการ **สร้าง zip archive .net** ด้วยระดับการบีบอัดที่กำหนด, ตั้งค่า `archive.CompressionLevel` ก่อนเรียก `Save`

## ปัญหาที่พบบ่อยและวิธีแก้

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| ไฟล์ ZIP ว่างเปล่า | `dataDir` ชี้ไปยังโฟลเดอร์ผิดหรือขาดเครื่องหมาย `/` ที่ท้าย | ตรวจสอบเส้นทางและให้แน่ใจว่าโฟลเดอร์มีไฟล์อยู่ |
| `UnauthorizedAccessException` | แอปพลิเคชันไม่มีสิทธิ์เข้าถึงระบบไฟล์ | รัน Visual Studio ในฐานะผู้ดูแลระบบหรือให้สิทธิ์อ่าน/เขียน |
| ใช้หน่วยความจำมากสำหรับไดเรกทอรีขนาดใหญ่ | โหลด entry ทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน | ใช้ `Archive.CreateEntryFromFile` ในลูปเพื่อสตรีมไฟล์ทีละไฟล์ |

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: สามารถเพิ่มรหัสผ่านให้กับไฟล์ ZIP ได้หรือไม่?**  
A: ได้. ตั้งค่า `archive.Password = "yourPassword";` ก่อนเรียก `Save`

**Q: จะรวมเฉพาะไฟล์ประเภทใดประเภทหนึ่งอย่างไร?**  
A: กรองคอลเลกชัน `DirectoryInfo` ด้วย `GetFiles("*.txt")` หรือวิธีที่คล้ายกันก่อนเรียก `CreateEntries`

**Q: มีวิธีอัปเดต ZIP ที่มีอยู่โดยไม่ต้องสร้างใหม่หรือไม่?**  
A: Aspose.Zip รองรับการอัปเดตแบบเพิ่มส่วนได้ผ่าน `Archive.UpdateEntry`

## คำถามที่พบบ่อย

### Q1: สามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์และส่วนบุคคลได้หรือไม่?

A1: ใช่, Aspose.Zip สำหรับ .NET มีลิขสิทธิ์สำหรับการใช้งานทั้งเชิงพาณิชย์และส่วนบุคคล

### Q2: มีรุ่นทดลองฟรีหรือไม่?

A2: มี, คุณสามารถทดลองใช้รุ่นฟรีได้ [ที่นี่](https://releases.aspose.com/zip/net)

### Q3: จะขอรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET อย่างไร?

A3: เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชน หรือพิจารณาซื้อ [temporary license](https://purchase.aspose.com/temporary-license/) เพื่อรับความช่วยเหลือโดยตรง

### Q4: มีตัวอย่างและบทเรียนอื่น ๆ ให้ดูหรือไม่?

A4: มี, [documentation](https://reference.aspose.com/zip/net/) มีตัวอย่างและบทเรียนอย่างครบถ้วน

### Q5: สามารถซื้อ Aspose.Zip สำหรับ .NET ได้หรือไม่?

A5: แน่นอน, คุณสามารถทำการซื้อได้ [ที่นี่](https://purchase.aspose.com/buy)

## สรุป

คุณมีรูปแบบที่พร้อมใช้งานในระดับผลิตภัณฑ์สำหรับ **วิธีบีบอัดโฟลเดอร์** ด้วย Aspose.Zip สำหรับ .NET แล้ว ด้วยการใช้คลาส `Archive` ของไลบรารี คุณสามารถ **สร้าง zip archive** ตั้งค่าระดับการบีบอัด (`CompressionLevel`) ที่กำหนดเอง, เพิ่มการป้องกันด้วยรหัสผ่าน, และแม้กระทั่ง **บีบอัดหลายโฟลเดอร์** ในการทำงานเดียว—ทำให้เหมาะสำหรับการทำงานอัตโนมัติสำรองข้อมูลโฟลเดอร์ ทดลองใช้ API เพื่อเพิ่มการเข้ารหัส, แบ่งไฟล์อาร์ไคฟ์, หรือสตรีมโดยตรงไปยังคลาวด์สตอเรจ แล้วคุณจะมีโซลูชันที่แข็งแกร่งสำหรับความต้องการบีบอัดใน .NET ใด ๆ

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
