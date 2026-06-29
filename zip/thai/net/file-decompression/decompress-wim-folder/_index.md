---
date: 2026-06-29
description: เรียนรู้วิธีการแยกไฟล์ WIM ไปยังโฟลเดอร์ด้วย Aspose.Zip for .NET. ทำตามคู่มือขั้นตอนต่อขั้นตอนเพื่อแตกไฟล์
  WIM อย่างมีประสิทธิภาพในแอป .NET ของคุณ.
keywords:
- how to extract wim
- asp
- aspose zip
- wim extraction .net
linktitle: แตกไฟล์ Wim ไปยังโฟลเดอร์
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  headline: How to Extract WIM to Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  name: How to Extract WIM to Folder Using Aspose.Zip for .NET
  steps:
  - name: Set Your Document Directory
    text: Define the folder that contains the source `.wim` file and the output folder
      where the extracted files will be written. Replace the placeholder path with
      your actual locations. The `dataDir` variable holds the source directory, while
      `outDir` is the destination for the extracted image.
  - name: Open the WIM Archive
    text: Create a `FileStream` for the `.wim` file and instantiate a `WimArchive`.
      The constructor reads the archive header without loading all image data into
      memory.
  - name: Extract the Desired Image
    text: Select the first image (`Images[0]`) and invoke `ExtractAll`. `ExtractAll`
      extracts all files from the selected image to a directory. If the archive contains
      multiple images, change the index to target a different one. The snippet reads
      the WIM file, accesses its first image, and writes all files to
  type: HowTo
- questions:
  - answer: Yes. Aspose.Zip supports **50+ formats** including ZIP, TAR, GZIP, 7z,
      and WIM, allowing you to handle virtually any compression scenario.
    question: Can I use Aspose.Zip for .NET with other archive formats?
  - answer: Explore the [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)
      for in‑depth guides, code samples, and performance best practices.
    question: Where can I find more examples and detailed API docs?
  - answer: Absolutely. You can download a trial version from the [website](https://releases.aspose.com/zip/net/)
      and evaluate all features without a license.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: Temporary licenses are provided through the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      – use **[this link](https://purchase.aspose.com/temporary-license/)** to request
      one.
    question: How do I obtain a temporary license for testing?
  - answer: The official [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) is
      the best place to interact with other developers and Aspose engineers.
    question: Where can I get community support or ask technical questions?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีการแยกไฟล์ WIM ไปยังโฟลเดอร์โดยใช้ Aspose.Zip for .NET
url: /th/net/file-decompression/decompress-wim-folder/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแยกไฟล์ WIM ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแยกไฟล์ WIM** ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างเครื่องมือการปรับใช้ Windows, โปรแกรมสำรองข้อมูล, หรือเพียงต้องการตรวจสอบเนื้อหาของไฟล์ Windows Imaging Format, ขั้นตอนต่อไปนี้จะพาคุณจากไฟล์ `.wim` ดิบไปสู่ไดเรกทอรีที่เต็มรูปแบบบน .NET runtime ที่รองรับใด ๆ เราจะครอบคลุมการตั้งค่าสภาพแวดล้อม, การเรียก API ที่แม่นยำ, และเคล็ดลับหลังการแยกไฟล์เพื่อให้คุณสามารถนำตรรกะนี้ไปใช้ในโครงการจริงได้อย่างมั่นใจ.

## คำตอบด่วน
- **ห้องสมุดที่แนะนำคืออะไร?** Aspose.Zip for .NET  
- **ฉันสามารถแยกไฟล์ WIM บน .NET Core ได้หรือไม่?** ใช่ – API รองรับ .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการผลิต; มีรุ่นทดลองฟรีสำหรับการประเมินผล.  
- **เวอร์ชัน .NET ขั้นต่ำคืออะไร?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10.  
- **การแยกไฟล์โดยทั่วไปใช้เวลานานเท่าไหร่?** ภาพมาตรฐานเสร็จในไม่กี่วินาที; ภาพหลายร้อยเมกะไบต์อาจต้องใช้เวลานานกว่า, แต่ API สตรีมข้อมูลเพื่อให้การใช้หน่วยความจำน้อย.

## WIM คืออะไร?

ไฟล์ WIM (Windows Imaging Format) เป็นไฟล์เก็บข้อมูลที่บรรจุภาพดิสก์หนึ่งหรือหลายภาพไว้ในคอนเทนเนอร์เดียวที่ถูกบีบอัด มันเป็นรูปแบบหลักที่อยู่เบื้องหลัง Windows Setup, DISM, และหลายกระบวนการปรับใช้ระดับองค์กร, ทำให้สามารถแยกภาพแต่ละภาพได้โดยเลือกส่วนที่ต้องการโดยไม่ต้องแตกไฟล์ทั้งหมด.

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?

Aspose.Zip ให้โซลูชันที่บริหารโดยบริสุทธิ์และข้ามแพลตฟอร์มซึ่งขจัดการพึ่งพา DLL แบบเนทีฟ มันรองรับ **รูปแบบการเข้าและออกกว่า 50 แบบ** (รวมถึง ZIP, TAR, GZIP, 7z, และ WIM) และสามารถประมวลผล **ไฟล์เก็บข้อมูลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ** การแยกไฟล์แบบสตรีมทำให้การใช้ RAM ต่ำกว่า 10 MB สำหรับไฟล์ WIM ปกติ ทำให้เหมาะสำหรับงานฝั่งเซิร์ฟเวอร์หรือคอนเทนเนอร์

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip Library** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [เว็บไซต์](https://releases.aspose.com/zip/net/) หรือจากหน้าปล่อยหลัก [ที่นี่](https://releases.aspose.com/).  
- **ไฟล์ WIM** – วางไฟล์ `.wim` ที่คุณต้องการแตกในโฟลเดอร์ที่รู้จัก (เช่น `C:\Archives`).  
- **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, VS Code, หรือเครื่องมือแก้ไขใด ๆ ที่รองรับ C#.  
- **ใบอนุญาต Aspose.Zip ที่ถูกต้อง** สำหรับการสร้างผลิตภัณฑ์ (รุ่นทดลองฟรีใช้งานได้สำหรับการทดสอบ).

## นำเข้า Namespaces

คำสั่ง `using` ด้านล่างนี้ให้คุณเข้าถึงคลาสหลักของ Aspose.Zip ที่จำเป็นสำหรับการจัดการ WIM.

```csharp
using Aspose.Zip;
using System.IO;
```

สอง namespaces นี้เป็นทั้งหมดที่คุณต้องการ; ไลบรารีจัดการการบีบอัด, การแตกไฟล์, และการนับภาพภายในโดยอัตโนมัติ.

## วิธีแยกไฟล์ WIM ไปยังโฟลเดอร์?

โหลดไฟล์ WIM, เลือกภาพที่ต้องการ, และสตรีมเนื้อหาไปยังไดเรกทอรีเป้าหมาย API ของ Aspose.Zip ทำการแยกไฟล์ในสามขั้นตอนสั้น ๆ, จัดการการบีบอัดภายในและรักษาการใช้หน่วยความจำให้ต่ำแม้กับไฟล์เก็บข้อมูลขนาดใหญ่ วิธีนี้ทำงานบน .NET runtime ที่รองรับทั้งหมดและต้องการเพียงไม่กี่บรรทัดของโค้ด `WimArchive` คือคลาสของ Aspose.Zip ที่แสดงถึงไฟล์ WIM และให้การเข้าถึงภาพที่บรรจุอยู่.

### คำตอบโดยตรง
โหลด WIM ด้วย `new WimArchive(stream)`, เลือกภาพแรกผ่าน `Images[0]`, และเรียก `ExtractAll(destinationPath)`. คำสั่งบรรทัดเดียวนี้จะแยกไฟล์ทั้งหมดในภาพที่เลือกขณะสตรีมข้อมูล, ทำให้การใช้หน่วยความจำอยู่ในระดับต่ำแม้กับไฟล์เก็บข้อมูลขนาดใหญ่.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ

กำหนดโฟลเดอร์ที่บรรจุไฟล์ต้นทาง `.wim` และโฟลเดอร์ผลลัพธ์ที่ไฟล์ที่แยกแล้วจะถูกเขียนลงไป แทนที่เส้นทางตัวอย่างด้วยตำแหน่งจริงของคุณ

ตัวแปร `dataDir` เก็บไดเรกทอรีต้นทาง, ส่วน `outDir` เป็นปลายทางสำหรับภาพที่แยกออก.

```csharp
string dataDir = @"C:\Archives";          // folder with your .wim file
string outDir = Path.Combine(dataDir, "DecompressWim_out"); // extraction target
```

### ขั้นตอนที่ 2: เปิดไฟล์ WIM

สร้าง `FileStream` สำหรับไฟล์ `.wim` และสร้างอินสแตนซ์ของ `WimArchive`. ตัวสร้างอ่านส่วนหัวของไฟล์เก็บข้อมูลโดยไม่โหลดข้อมูลภาพทั้งหมดเข้าสู่หน่วยความจำ.

```csharp
using (FileStream wimStream = File.OpenRead(Path.Combine(dataDir, "corpus.wim")))
{
    WimArchive wim = new WimArchive(wimStream);
```

### ขั้นตอนที่ 3: แยกภาพที่ต้องการ

เลือกภาพแรก (`Images[0]`) และเรียก `ExtractAll`. `ExtractAll` จะทำการแยกไฟล์ทั้งหมดจากภาพที่เลือกไปยังไดเรกทอรี หากไฟล์เก็บข้อมูลมีหลายภาพ, ให้เปลี่ยนดัชนีเพื่อเลือกภาพอื่น.

```csharp
    // Extract the first image to the output directory
    wim.Images[0].ExtractAll(outDir);
}
```

โค้ดส่วนนี้อ่านไฟล์ WIM, เข้าถึงภาพแรก, และเขียนไฟล์ทั้งหมดไปยัง **DecompressWim_out**. ปรับดัชนีเพื่อแยกภาพอื่นใดที่อยู่ในไฟล์เก็บข้อมูล.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`FileNotFoundException`** | `dataDir` หรือชื่อไฟล์ไม่ถูกต้อง | ตรวจสอบเส้นทางและให้แน่ใจว่า `corpus.wim` มีอยู่ในตำแหน่งที่ระบุ. |
| **`UnauthorizedAccessException`** | โฟลเดอร์ปลายทางเป็นแบบอ่าน‑อย่างเดียว | รันแอปพลิเคชันด้วยสิทธิ์ระดับสูงหรือเลือกไดเรกทอรีที่สามารถเขียนได้. |
| **การแยกไฟล์ช้า** | WIM ขนาดใหญ่มากหรือฮาร์ดแวร์ระดับต่ำ | แยกภาพเฉพาะแทนการแยกไฟล์ทั้งหมด, หรือใช้สตรีมแบบอะซิงโครนัสสำหรับไฟล์ขนาดใหญ่. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับรูปแบบไฟล์เก็บข้อมูลอื่นได้หรือไม่?**  
A: ใช่. Aspose.Zip รองรับ **รูปแบบกว่า 50 แบบ** รวมถึง ZIP, TAR, GZIP, 7z, และ WIM, ทำให้คุณจัดการกับสถานการณ์การบีบอัดใด ๆ ได้อย่างแทบทั้งหมด.

**Q: ฉันสามารถหา ตัวอย่างเพิ่มเติมและเอกสาร API รายละเอียดได้จากที่ไหน?**  
A: สำรวจ [เอกสาร Aspose.Zip](https://reference.aspose.com/zip/net/) เพื่อดูคู่มือเชิงลึก, ตัวอย่างโค้ด, และแนวทางปฏิบัติที่ดีที่สุดด้านประสิทธิภาพ.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?**  
A: แน่นอน. คุณสามารถดาวน์โหลดรุ่นทดลองจาก [เว็บไซต์](https://releases.aspose.com/zip/net/) และประเมินคุณสมบัติทั้งหมดโดยไม่ต้องมีใบอนุญาต.

**Q: ฉันจะขอใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: ใบอนุญาตชั่วคราวจะให้ผ่านหน้า [temporary‑license page](https://purchase.aspose.com/temporary-license/) – ใช้ **[ลิงก์นี้](https://purchase.aspose.com/temporary-license/)** เพื่อขอรับ.

**Q: ฉันสามารถรับการสนับสนุนจากชุมชนหรือถามคำถามทางเทคนิคได้จากที่ไหน?**  
A: ฟอรั่มอย่างเป็นทางการของ [Aspose.Zip](https://forum.aspose.com/c/zip/37) เป็นสถานที่ที่ดีที่สุดสำหรับการติดต่อกับนักพัฒนาอื่น ๆ และวิศวกรของ Aspose.

---

**อัปเดตล่าสุด:** 2026-06-29  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

```csharp
using System.IO;
using Aspose.Zip.Wim;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
{
    using (WimArchive archive = new WimArchive(fs))
    {
        archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
    }
}
```

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีบีบอัดไฟล์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/)
- [วิธีแยกไฟล์ zip ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [วิธีแยกไฟล์ Xar ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/decompress-xar-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}