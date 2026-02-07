---
date: 2026-02-07
description: เรียนรู้วิธีการบีบอัดโฟลเดอร์ใน .NET โดยการบีบอัดไดเรกทอรีเป็นไฟล์ zip
  และการแตกไฟล์กลับมา คู่มือนี้แสดงวิธีการบีบอัดโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดโฟลเดอร์ – บีบอัดไดเรกทอรีด้วย Aspose.Zip
url: /th/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดโฟลเดอร์ – บีบอัดไดเรกทอรีด้วย Aspose.Zip สำหรับ .NET

หากคุณกำลังมองหาโซลูชัน **how to zip folder** ที่ชัดเจนในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—แรกเราจะ **compress directory to zip**, จากนั้นเราจะแสดงขั้นตอนที่แน่นอนเพื่อ **extract zip to directory** (หรือที่เรียกว่า how to unzip folder) เมื่อเสร็จคุณจะมีรูปแบบโปรแกรมที่สามารถนำกลับมาใช้ใหม่สำหรับการทำงาน zip folder ที่ทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6+.

## Quick Answers
- **What does “compress directory to zip” mean?** หมายถึงการแปลงเนื้อหาของโฟลเดอร์ให้เป็นไฟล์ .zip ไฟล์เดียว  
- **How do I extract zip to directory?** ใช้เมธอด `Archive.ExtractToDirectory` ตามที่แสดงในคู่มือ  
- **Which .NET versions are supported?** รองรับ .NET Framework, .NET Core, และ .NET 5/6+ รุ่นสมัยใหม่ทั้งหมด  
- **Is a license required for production?** ใช่, จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์ของ Aspose.Zip สำหรับการใช้งานที่ไม่ใช่การทดลอง  
- **Can I automate this in CI/CD pipelines?** แน่นอน—เพียงเพิ่มโค้ดเดียวกันนี้ลงในสคริปต์การสร้างของคุณ  

## What is “how to zip folder”?
**How to zip folder** หมายถึงการนำไฟล์และโฟลเดอร์ย่อยทั้งหมดภายในไดเรกทอรีมารวมกันเป็นไฟล์บีบอัดเดียว ซึ่งช่วยลดขนาดการจัดเก็บ, เร่งความเร็วในการถ่ายโอน, และสร้างแพคเกจพกพาสำหรับการปรับใช้  

## Why use Aspose.Zip for .NET?
Aspose.Zip ให้ API **pure‑managed** ที่ไม่ต้องอาศัย DLL แบบเนทีฟ, รองรับไฟล์อาร์ไคฟ์ขนาดใหญ่, และจัดการกรณีพิเศษเช่น **zip archive password protection** และชื่อไฟล์ Unicode โดยอัตโนมัติ นอกจากนี้ยังได้รับการปรับให้ทำงานได้อย่างมีประสิทธิภาพ ทำให้เหมาะสมเมื่อคุณต้องการ zip folder ด้วยโปรแกรมในสถานการณ์ที่ต้องการประมวลผลจำนวนมาก  

## Prerequisites
- **Aspose.Zip for .NET** library installed (ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/zip/net/)).  
- โฟลเดอร์บนดิสก์ที่คุณต้องการบีบอัด – กำหนดพาธของมันในตัวแปร `dataDir`  
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, หรือ IDE ใดก็ได้ที่คุณชอบ)  

## Import Namespaces
ก่อนอื่น นำเนมสเปซที่จำเป็นเข้าสู่สโคป:

```csharp
using Aspose.Zip;
using System.IO;
```

## Step‑by‑Step Guide

### Step 1: Compress Directory to Zip (zip folder programmatically)
เราจะสร้างไฟล์ zip จากไดเรกทอรีที่คุณวางแผนจะทำการแตกไฟล์ในภายหลัง ตัวช่วย `CompressDirectory.Run()` จะทำหน้าที่หลัก

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** ตัวอย่าง `CompressDirectory` จะบรรจุไฟล์ทุกไฟล์ใน `dataDir` ไปยัง `CompressDirectory_out.zip`. คุณสามารถเปลี่ยนชื่อไฟล์ผลลัพธ์ให้ตรงกับแนวทางการตั้งชื่อของคุณได้ตามต้องการ.

### Step 2: Decompress the Folder – How to Unzip Folder in .NET

#### Step 2.1: Open the Zip File
เปิดอาร์ไคฟ์ที่สร้างขึ้นด้วย `FileStream`. การทำเช่นนี้เตรียมไฟล์สำหรับการอ่าน

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Step 2.2: Create Archive Instance
สร้างอินสแตนซ์ของอ็อบเจกต์ `Archive` ซึ่งเป็นตัวแทนของคอนเทนเนอร์ zip

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Step 2.3: Extract to Directory
สุดท้าย ให้แตกเนื้อหาไปยังโฟลเดอร์ใหม่ นี่คือขั้นตอน **extract zip to directory**

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Why This Matters
- **Consistency:** การใช้ไลบรารีเดียวกันสำหรับการบีบอัดและการแตกไฟล์รับประกันรูปแบบอาร์ไคฟ์ที่เข้ากันได้  
- **Performance:** Aspose.Zip สตรีมข้อมูลอย่างมีประสิทธิภาพ ทำให้แม้ไฟล์อาร์ไคฟ์หลายกิกะไบต์ก็สามารถจัดการได้โดยใช้หน่วยความจำต่ำ  
- **Security:** การสนับสนุนการป้องกันด้วยรหัสผ่านในตัวหมายความว่าคุณสามารถรักษาความปลอดภัยของอาร์ไคฟ์ zip ได้โดยไม่ต้องเขียนโค้ดเพิ่มเติม  

## Common Use Cases
- **Automated backups** – บีบอัดโฟลเดอร์บันทึกประจำคืนและเก็บไว้ในคลาวด์สตอเรจ  
- **Deployment packages** – รวมไฟล์ทรัพยากรเว็บแบบสแตติกก่อนทำการเผยแพร่ไปยังเซิร์ฟเวอร์  
- **Data exchange** – ส่งคอลเลกชันของไฟล์ระหว่างบริการเป็นอาร์ไคฟ์เดียว  

## Common Issues & Solutions
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `UnauthorizedAccessException` when extracting | โฟลเดอร์เป้าหมายเป็นแบบอ่านอย่างเดียวหรือกำลังถูกใช้งาน | ตรวจสอบให้แน่ใจว่าพาธปลายทางสามารถเขียนได้และไม่ได้ถูกล็อก |
| Empty output folder after extraction | พาธ zip ต้นทางผิดพลาด | ตรวจสอบอีกครั้งว่า `dataDir + "CompressDirectory_out.zip"` ชี้ไปยังไฟล์ที่ถูกต้อง |
| Large files cause OutOfMemoryException | ใช้ขนาดบัฟเฟอร์เริ่มต้นกับอาร์ไคฟ์ขนาดใหญ่มาก | ใช้ `ArchiveOptions` เพื่อเพิ่มขนาดบัฟเฟอร์หรือสตรีมไฟล์เป็นชิ้นส่วน |

## Frequently Asked Questions

**Q: Can I use Aspose.Zip for .NET with any type of file?**  
A: ใช่, Aspose.Zip รองรับไฟล์ทุกประเภท—ข้อความ, ไบนารี, รูปภาพ, PDF, ตามที่คุณต้องการ  

**Q: Is Aspose.Zip suitable for large‑scale applications?**  
A: แน่นอน. มันถูกออกแบบมาสำหรับการบีบอัด zip ที่มีประสิทธิภาพสูงในสถานการณ์ .NET, จัดการอาร์ไคฟ์หลายกิกะไบต์ด้วยหน่วยความจำต่ำ  

**Q: Where can I find comprehensive documentation for Aspose.Zip for .NET?**  
A: สำรวจเอกสารรายละเอียดได้ที่ [ที่นี่](https://reference.aspose.com/zip/net/)  

**Q: Can I try Aspose.Zip before purchasing?**  
A: ใช่, มีการทดลองใช้งานฟรีที่ [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/)  

**Q: How can I get support for Aspose.Zip for .NET?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ  

---

**อัปเดตล่าสุด:** 2026-02-07  
**ทดสอบด้วย:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}