---
date: 2026-02-28
description: เรียนรู้วิธีการแยกไฟล์ WIM ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET.
  ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อแตกไฟล์ WIM อย่างมีประสิทธิภาพในแอป .NET
  ของคุณ.
linktitle: Decompress Wim to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีการแยกไฟล์ WIM ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/file-decompression/decompress-wim-folder/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการสกัดไฟล์ WIM ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ยินดีต้อนรับสู่บทแนะนำที่ครอบคลุมเกี่ยวกับ **วิธีสกัดไฟล์ WIM** ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างเครื่องมือการปรับใช้, ยูทิลิตี้สำรองข้อมูล, หรือเพียงต้องการอ่านเนื้อหาของไฟล์ Windows Imaging Format นี้ คู่มือจะพาคุณผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการสกัดภาพแรกของไฟล์ WIM คุณจะได้เห็นว่าทำไม Aspose.Zip จึงเป็นตัวเลือกที่เชื่อถือได้, API ทำงานอย่างไรภายใน, และสิ่งที่คุณทำได้หลังการสกัด

## คำตอบสั้น
- **แนะนำไลบรารีใด?** Aspose.Zip สำหรับ .NET  
- **สามารถสกัดไฟล์ WIM บน .NET Core ได้หรือไม่?** ได้, API ทำงานกับ .NET Core, .NET 5+ และ .NET 6+  
- **ต้องใช้ลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้  
- **เวอร์ชัน .NET ขั้นต่ำคืออะไร?** .NET Framework 4.5+ หรือ .NET Core 3.1+  
- **การสกัดใช้เวลานานเท่าใด?** ปกติใช้เพียงไม่กี่วินาทีสำหรับภาพ WIM มาตรฐาน; ภาพขนาดใหญ่กว่าอาจใช้เวลานานกว่า

## WIM file คืออะไร?

**WIM (Windows Imaging Format)** เป็นไฟล์อาร์ไคฟ์ที่เก็บหนึ่งหรือหลายภาพดิสก์ไว้ในไฟล์เดียวที่ถูกบีบอัด มักใช้โดย Windows Setup, DISM, และโซลูชันการปรับใช้ ภาพแต่ละภาพภายใน WIM สามารถถือเป็นระบบไฟล์เสมือน ทำให้การสกัดแบบเลือกส่วนเป็นประโยชน์อย่างมาก

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?

Aspose.Zip มี API แบบ pure‑managed, ข้ามแพลตฟอร์ม ที่ไม่ต้องพึ่งพาไลบรารีเนทีฟ รองรับ:

* การเข้าถึงโดยตรงไปยังภาพแต่ละภาพภายในอาร์ไคฟ์ WIM  
* การทำงานแบบ stream ที่ช่วยลดการใช้หน่วยความจำ  
* การบูรณาการอย่างราบรื่นกับโครงการ .NET Framework และ .NET Core  

คุณสมบัติเหล่านี้ทำให้คุณสร้างเครื่องมือสกัดที่เชื่อถือได้โดยไม่ต้องกังวลเรื่องข้อจำกัดของแพลตฟอร์ม

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มเขียนโค้ด ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Zip Library** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [website](https://releases.aspose.com/zip/net/)  
- **อาร์ไคฟ์ WIM** – วางไฟล์ `.wim` ที่ต้องการแตกลงในโฟลเดอร์ที่คุณทราบตำแหน่งบนเครื่อง  
- **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, VS Code หรือเครื่องมือแก้ไขใด ๆ ที่รองรับ C#

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นในโปรเจกต์ C# ของคุณ เพื่อให้เข้าถึงคลาสของ Aspose.Zip ได้

```csharp
using System.IO;
using Aspose.Zip.Wim;
```

## วิธีการสกัด WIM ไปยังโฟลเดอร์

ต่อไปนี้คือขั้นตอนที่แสดง **วิธีสกัดอาร์ไคฟ์ WIM** ด้วย Aspose.Zip โปรดทำตามขั้นตอนอย่างละเอียด

### ขั้นตอนที่ 1: ตั้งค่า Directory ของเอกสารของคุณ

กำหนดเส้นทางโฟลเดอร์ที่ไฟล์อาร์ไคฟ์ WIM ของคุณอยู่ แทนที่ `"Your Document Directory"` ด้วยพาธจริงของโฟลเดอร์ของคุณ

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: แตกไฟล์อาร์ไคฟ์ WIM

เปิดไฟล์อาร์ไคฟ์ WIM ด้วย `FileStream` แล้วสกัดเนื้อหาของภาพแรกไปยังโฟลเดอร์เป้าหมาย

```csharp
using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
{
    using (WimArchive archive = new WimArchive(fs))
    {
        archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
    }
}
```

โค้ดส่วนนี้จะอ่านไฟล์ WIM, เข้าถึงภาพแรก (`Images[0]`) และเขียนไฟล์ทั้งหมดไปยัง **DecompressWim_out** คุณสามารถเปลี่ยนดัชนีเพื่อสกัดภาพอื่นได้หากอาร์ไคฟ์มีหลายภาพ

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Reason | Fix |
|-------|--------|-----|
| **`FileNotFoundException`** | `dataDir` หรือชื่อไฟล์ไม่ถูกต้อง | ตรวจสอบพาธและให้แน่ใจว่า `corpus.wim` มีอยู่ |
| **`UnauthorizedAccessException`** | โฟลเดอร์ปลายทางเป็นแบบอ่าน‑อย่างเดียว | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่เขียนได้ |
| **Extraction is slow** | WIM ขนาดใหญ่มากหรือฮาร์ดแวร์ระดับล่าง | พิจารณาสกัดเฉพาะภาพที่ต้องการแทนการสกัดทั้งหมด, หรือใช้ stream แบบ asynchronous สำหรับไฟล์ขนาดใหญ่ |

## คำถามที่พบบ่อย

### Q1: สามารถใช้ Aspose.Zip สำหรับ .NET กับรูปแบบอาร์ไคฟ์อื่นได้หรือไม่?  
**A:** ใช่, Aspose.Zip รองรับ ZIP, TAR, GZIP, 7z และรูปแบบอื่น ๆ อีกหลายประเภท นอกเหนือจาก WIM

### Q2: จะหา ตัวอย่างและเอกสารเพิ่มเติมสำหรับ Aspose.Zip ได้จากที่ไหน?  
**A:** สำรวจ [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) เพื่อดูตัวอย่างละเอียดและคู่มือครบวงจร

### Q3: มีรุ่นทดลองฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?  
**A:** มี, คุณสามารถเข้าถึงรุ่นทดลองได้ [here](https://releases.aspose.com/)

### Q4: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?  
**A:** รับลิขสิทธิ์ชั่วคราวจาก [this link](https://purchase.aspose.com/temporary-license/)

### Q5: จะหาการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?  
**A:** เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนและพูดคุยกับชุมชน

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบด้วย:** Aspose.Zip สำหรับ .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}