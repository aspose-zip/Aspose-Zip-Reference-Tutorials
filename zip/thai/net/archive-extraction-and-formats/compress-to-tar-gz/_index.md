---
date: 2026-01-28
description: เรียนรู้วิธีสร้างไฟล์ tar.gz, เพิ่มไฟล์ลงใน tar และบีบอัดโดยใช้ Aspose.Zip
  สำหรับ .NET – วิธีที่รวดเร็วและเชื่อถือได้ในการจัดเก็บไฟล์
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้างไฟล์ tar.gz และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และสร้าง TarGz ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในแอปพลิเคชัน .NET สมัยใหม่ การ **add files to tar** อย่างรวดเร็วและเชื่อถือได้เป็นความต้องการทั่วไป—ไม่ว่าจะเป็นการบรรจุไฟล์บันทึก, การเตรียมข้อมูลสำหรับการจัดเก็บบนคลาวด์, หรือการสร้างแพ็คเกจการปรับใช้ Aspose.Zip สำหรับ .NET ให้ API ที่สะอาดและมีประสิทธิภาพสูงเพื่อ **add files to tar**, จากนั้นบีบอัดไฟล์เก็บไว้ในรูปแบบ **tar.gz** ที่ใช้กันอย่างแพร่หลาย ในบทแนะนำนี้คุณจะได้เรียนรู้อย่างละเอียดว่า **create tar.gz archive** จากศูนย์อย่างเป็นขั้นตอนโดยใช้ไลบรารี Aspose.Zip .NET

## คำตอบสั้น
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip สำหรับ .NET  
- **จะเพิ่มไฟล์ลงใน tar อย่างไร?** ใช้ `TarArchive.CreateEntry` สำหรับแต่ละไฟล์  
- **สามารถบีบอัดโดยตรงเป็น tar.gz ได้หรือไม่?** ได้—เรียก `SaveGzipped`  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่แบบทดลอง  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  

## อะไรคือ “add files to tar”?
การเพิ่มไฟล์ลงใน tar archive หมายถึงการรวมหลายไฟล์ไว้ในคอนเทนเนอร์เดียวที่ไม่ได้บีบอัด รูปแบบ tar จะคงโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์ ทำให้เหมาะสำหรับการเก็บสำรองก่อนการบีบอัดเพิ่มเติม (เช่น gzip) เพื่อ **create tar.gz archive**  

## ทำไมต้องใช้ Aspose.Zip เพื่อบีบอัดไฟล์เป็น tar.gz?
- **ไม่ต้องใช้เครื่องมือภายนอก** – ทุกอย่างทำงานภายในโค้ด .NET ของคุณ  
- **ประสิทธิภาพสูง** – API แบบสตรีมจัดการไฟล์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS  
- **ฟีเจอร์ครบครัน** – รองรับการเข้ารหัส, การป้องกันด้วยรหัสผ่าน, และแอตทริบิวต์ของรายการที่กำหนดเอง  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- ประสบการณ์พื้นฐานการพัฒนา .NET  
- Visual Studio (หรือ IDE ที่คุณชื่นชอบ)  
- Aspose.Zip สำหรับ .NET ที่ติดตั้งแล้ว – ดูเอกสารอย่างเป็นทางการ [ที่นี่](https://reference.aspose.com/zip/net/)  
- ไลบรารี Aspose.Zip ที่ดาวน์โหลดจาก [ลิงก์นี้](https://releases.aspose.com/zip/net/)  

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ ให้นำเข้า namespaces ที่เปิดเผยคลาสที่เกี่ยวกับ tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## วิธีสร้าง tar.gz archive ด้วย Aspose.Zip สำหรับ .NET

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ

แรกสุด ให้ชี้โค้ดไปยังโฟลเดอร์ที่มีไฟล์ที่คุณต้องการบรรจุ

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เมื่อสร้างเส้นทางเพื่อหลีกเลี่ยงปัญหาเครื่องหมายคั่นที่แตกต่างกันระหว่างแพลตฟอร์ม  

### ขั้นตอนที่ 2: เริ่มต้น TarArchive

สร้างอินสแตนซ์ `TarArchive` ที่จะเก็บรายการทั้งหมด

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### ขั้นตอนที่ 3: เพิ่มไฟล์ – แกนหลักของ “add files to tar”

ภายในบล็อก `using` ให้เพิ่มไฟล์แต่ละไฟล์ที่ต้องการรวมไว้ใน archive

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

แต่ละการเรียก `CreateEntry` จะรับ **entry name** (ชื่อไฟล์ที่จะแสดงภายใน tar) และ **source file path** บนดิสก์  

### ขั้นตอนที่ 4: บันทึกเป็น Gzipped Tar (วิธีบีบอัดไฟล์เป็น tar.gz)

สุดท้าย ให้เขียนเนื้อหา tar ไปยังสตรีม gzip เพื่อสร้าง `archive.tar.gz` ที่กะทัดรัด

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` จัดการทั้งการบรรจุ tar และการบีบอัด gzip ในคำสั่งเดียวที่ต่อเนื่อง  

## กรณีการใช้งานทั่วไป

| สถานการณ์ | ทำไม “add files to tar” จึงช่วยได้ |
|----------|-----------------------------------|
| **การรวบรวมบันทึก** | รวมบันทึกประจำวันเป็น archive เดียวก่อนอัปโหลดไปยังคลาวด์ |
| **แพ็คเกจการปรับใช้** | สร้าง tar.gz พกพาสำหรับเซิร์ฟเวอร์ Linux จาก pipeline สร้างบน Windows |
| **การสำรองข้อมูล** | คงลำดับชั้นของโฟลเดอร์และเมตาดาต้าในขณะที่ลดขนาดสำรองข้อมูล |

## ปัญหาทั่วไปและวิธีแก้

- **File not found error** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยเครื่องหมายคั่นที่เหมาะสมหรือใช้ `Path.Combine`  
- **Large files cause memory pressure** – ใช้ overload แบบสตรีม (`CreateEntry` พร้อม `Stream`) เพื่อหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ  
- **Gzip output is corrupted** – ยืนยันว่า archive ถูกปิด (`using` block) ก่อนเรียก `SaveGzipped`  

## คำถามที่พบบ่อย

**Q: Aspose.Zip สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET ทุกประเภทหรือไม่?**  
A: ใช่, ทำงานกับโครงการ .NET Framework, .NET Core, และ .NET 5/6/7  

**Q: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?**  
A: เยี่ยมชม [หน้า temporary‑license](https://purchase.aspose.com/temporary-license/) เพื่อขอรับลิขสิทธิ์ทดลอง  

**Q: มีข้อจำกัดเรื่องขนาดไฟล์หรือไม่?**  
A: ไลบรารีได้รับการปรับให้ทำงานกับไฟล์ขนาดใหญ่; ไม่มีขีดจำกัดขนาดที่แน่นอนนอกจากหน่วยความจำของระบบ  

**Q: จะหาการสนับสนุนได้จากที่ไหน?**  
A: ใช้ฟอรั่มสนับสนุนที่ขับเคลื่อนโดยชุมชน [ที่นี่](https://forum.aspose.com/c/zip/37) เพื่อขอความช่วยเหลือจากวิศวกร Aspose และนักพัฒนาคนอื่น  

**Q: สามารถทดลองใช้ Aspose.Zip สำหรับ .NET ได้ฟรีหรือไม่?**  
A: แน่นอน—ดาวน์โหลดเวอร์ชันทดลองฟรีจาก [หน้า releases ของ Aspose Zip](https://releases.aspose.com/zip/net)  

## สรุป

คุณได้เรียนรู้ **วิธีเพิ่มไฟล์ลงใน tar**, สร้าง archive tar, และบีบอัดเป็น **tar.gz** ด้วย Aspose.Zip สำหรับ .NET วิธีนี้ช่วยขจัดการพึ่งพาเครื่องมือภายนอก, ให้คุณควบคุมเนื้อหา archive อย่างละเอียด, และขยายตัวได้กับชุดข้อมูลขนาดใหญ่ อย่าลังเลที่จะสำรวจฟีเจอร์เพิ่มเติมของ Aspose.Zip เช่น การเข้ารหัส, แอตทริบิวต์รายการที่กำหนดเอง, และ API สตรีม เพื่อยกระดับกระบวนการจัดเก็บของคุณต่อไป

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-28  
**ทดสอบด้วย:** Aspose.Zip 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose