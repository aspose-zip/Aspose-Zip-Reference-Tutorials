---
date: 2026-02-12
description: เรียนรู้วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET สร้างไฟล์ zip อย่างมีประสิทธิภาพใน
  .NET และลดพื้นที่จัดเก็บในแอปพลิเคชัน .NET ของคุณ
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

ในบทแนะนำนี้คุณจะได้เรียนรู้ **how to zip folder** อย่างรวดเร็วและเชื่อถือได้ด้วย Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้บนเดสก์ท็อป, บริการบนคลาวด์, หรือสคริปต์สำรองข้อมูลอัตโนมัติ การบีบอัดโฟลเดอร์เป็นไฟล์ ZIP สามารถลดขนาดการจัดเก็บได้อย่างมากและเร่งความเร็วการถ่ายโอนข้อมูลผ่านเครือข่าย เราจะเดินผ่านทุกขั้นตอน, อธิบายว่าทำไมแต่ละบรรทัดจึงสำคัญ, และชี้ให้เห็นข้อผิดพลาดทั่วไปเพื่อให้คุณใช้เทคนิคนี้ได้อย่างมั่นใจ

## คำตอบอย่างรวดเร็ว
- **Aspose.Zip ทำอะไร?** มันให้ API .NET ที่ง่ายสำหรับการสร้างและแยกไฟล์ ZIP โดยไม่ต้องพึ่งพาไลบรารีภายนอก.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีสำหรับการบีบอัดโฟลเดอร์พื้นฐาน.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **ต้องการไลเซนส์สำหรับการใช้งานในโปรดักชันหรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในโปรดักชัน.  
- **ฉันสามารถบีบอัดหลายโฟลเดอร์พร้อมกันได้หรือไม่?** ได้แน่นอน—ใช้เมธอด `CreateEntries` บนคอลเลกชัน `DirectoryInfo` ใดก็ได้เพื่อ **zip multiple folders** ในการทำงานครั้งเดียว.

## “how to zip folder” คืออะไร

การบีบอัดโฟลเดอร์หมายถึงการนำไฟล์และโฟลเดอร์ย่อยทั้งหมดภายในไดเรกทอรีที่กำหนดมารวมเป็นไฟล์ ZIP เดียว ซึ่งช่วยลดขนาดโดยรวม, รักษาโครงสร้างต้นฉบับ, และทำให้การถ่ายโอนหรือการจัดเก็บข้อมูลเป็นเรื่องง่ายขึ้น

## ทำไมต้องใช้ Aspose.Zip สำหรับงานนี้

- **ความเร็วและประสิทธิภาพ:** อัลกอริธึมที่ปรับแต่งมาช่วยจัดการโฟลเดอร์ขนาดใหญ่ได้อย่างรวดเร็ว.  
- **Pure .NET:** ไม่ต้องใช้ไบนารีเนทีฟหรือเครื่องมือของบุคคลที่สาม.  
- **Rich Feature Set:** รองรับการป้องกันด้วยรหัสผ่าน (`add password zip`), การสตรีม, และการตั้งค่าระดับการบีบอัดที่กำหนดเอง (`set compression level`).  
- **Consistent API:** ทำงานแบบเดียวกันบน .NET Framework, .NET Core, และ .NET 5/6, ทำให้เหมาะสำหรับสถานการณ์ **create zip archive .net**.

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดได้ที่ [here](https://releases.aspose.com/zip/net/).  
- **Development Environment** – Visual Studio, Rider, หรือ IDE ใดก็ได้ที่รองรับ C#.  
- **Document Directory** – แทนที่ `"Your Document Directory"` ในโค้ดด้วยเส้นทางไปยังโฟลเดอร์ที่คุณต้องการบีบอัด.  
- **Reference Documentation** – ศึกษาเอกสารอย่างเป็นทางการ [here](https://reference.aspose.com/zip/net/).

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็น ซึ่งจะให้คุณเข้าถึงคลาสการบีบอัดหลักได้

```csharp
using Aspose.Zip;
using System.IO;
```

## วิธีบีบอัดโฟลเดอร์ด้วย Aspose.Zip

ด้านล่างเป็นตัวอย่างที่เรียบง่ายซึ่งแสดง **how to zip folder** เนื้อหาแบบเต็ม คุณสามารถต่อยอดเพื่อ **zip multiple files .net** หรือสร้างโครงสร้างอาร์ไคฟ์แบบกำหนดเองได้

### ขั้นตอนที่ 1: กำหนดค่า Document Directory ของคุณ

ตั้งค่าตัวแปร `dataDir` ให้เป็นเส้นทางของไดเรกทอรีที่ต้องการบีบอัด

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างไฟล์ ZIP ผลลัพธ์

เปิดออบเจ็กต์ `FileStream` สองตัวสำหรับไฟล์ ZIP ผลลัพธ์ นี่แสดงวิธีการสร้างอาร์ไคฟ์หลายไฟล์จากแหล่งเดียวกัน—มีประโยชน์สำหรับการสำรองข้อมูลเวอร์ชันต่าง ๆ

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### ขั้นตอนที่ 3: บีบอัดไดเรกทอรี

ใช้คลาส `Archive` เพื่อเพิ่มทุกรายการจากโฟลเดอร์เป้าหมาย ตัวอย่างใช้โฟลเดอร์ตัวอย่างชื่อ **CanterburyCorpus**, แต่คุณสามารถชี้ไปยังไดเรกทอรีใดก็ได้

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

> **เคล็ดลับ:** หากคุณต้องการ **create zip archive .net** ด้วยระดับการบีบอัดที่กำหนด, ตั้งค่า `archive.CompressionLevel` ก่อนเรียก `Save`.

## ปัญหาที่พบบ่อยและวิธีแก้

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| ไฟล์ ZIP ว่างเปล่า | `dataDir` ชี้ไปยังโฟลเดอร์ที่ผิดหรือขาดสแลชท้าย | ตรวจสอบเส้นทางและให้แน่ใจว่าโฟลเดอร์มีไฟล์อยู่ |
| `UnauthorizedAccessException` | แอปพลิเคชันไม่มีสิทธิ์เข้าถึงระบบไฟล์ | เรียก Visual Studio ด้วยสิทธิ์ผู้ดูแลหรือให้สิทธิ์อ่าน/เขียน |
| การใช้หน่วยความจำสูงสำหรับไดเรกทอรีขนาดใหญ่ | โหลดรายการทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน | ใช้ `Archive.CreateEntryFromFile` ในลูปเพื่อสตรีมไฟล์ทีละไฟล์ |

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: ฉันสามารถเพิ่มรหัสผ่านให้กับไฟล์ ZIP ได้หรือไม่?**  
A: ได้. ตั้งค่า `archive.Password = "yourPassword";` ก่อนเรียก `Save`.

**Q: ฉันจะรวมเฉพาะไฟล์ประเภทใดประเภทหนึ่งเท่านั้นได้อย่างไร?**  
A: กรองคอลเลกชัน `DirectoryInfo` ด้วย `GetFiles("*.txt")` หรือวิธีที่คล้ายกันก่อนเรียก `CreateEntries`.

**Q: มีวิธีอัปเดตไฟล์ ZIP ที่มีอยู่โดยไม่ต้องสร้างใหม่หรือไม่?**  
A: Aspose.Zip รองรับการอัปเดตแบบเพิ่มขั้นผ่าน `Archive.UpdateEntry`.

## FAQ's

### Q1: ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์และส่วนบุคคลได้หรือไม่?

A1: ใช่, Aspose.Zip สำหรับ .NET มีไลเซนส์สำหรับการใช้ทั้งเชิงพาณิชย์และส่วนบุคคล.

### Q2: มีการทดลองใช้ฟรีหรือไม่?

A2: มี, คุณสามารถสำรวจการทดลองใช้ฟรี [here](https://releases.aspose.com/zip/net).

### Q3: ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?

A3: เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนหรือพิจารณาซื้อ [temporary license](https://purchase.aspose.com/temporary-license/) เพื่อรับการช่วยเหลือโดยเฉพาะ.

### Q4: มีตัวอย่างและบทแนะนำอื่น ๆ ให้เลือกหรือไม่?

A4: มี, [documentation](https://reference.aspose.com/zip/net/) มีตัวอย่างและบทแนะนำที่ครอบคลุม.

### Q5: ฉันสามารถซื้อ Aspose.Zip สำหรับ .NET ได้หรือไม่?

A5: แน่นอน, คุณสามารถทำการซื้อได้ [here](https://purchase.aspose.com/buy).

---

**อัปเดตล่าสุด:** 2026-02-12  
**ทดสอบกับ:** Aspose.Zip 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
