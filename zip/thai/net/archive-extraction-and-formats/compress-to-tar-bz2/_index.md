---
date: 2026-04-24
description: เรียนรู้วิธีบีบอัด tar และสร้างไฟล์ TarBz2 ใน .NET ด้วย Aspose.Zip คู่มือขั้นตอนต่อขั้นตอนนี้แสดงวิธีเพิ่มไฟล์ลงใน
  tar และสร้างไฟล์ tarbz2 อย่างมีประสิทธิภาพ
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: บีบอัดเป็น TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีบีบอัด tar** ไฟล์อาร์ไคฟ์และแปลงเป็นไฟล์ **TarBz2** ที่กะทัดรัดโดยใช้ไลบรารี **Aspose.Zip** สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้สำรองข้อมูล, เผยแพร่แพคเกจการปรับใช้, หรือเพียงต้องการชุดไฟล์ขนาดเล็กสำหรับการแจกจ่าย ขั้นตอนต่อไปนี้จะช่วยคุณเพิ่มไฟล์ลงใน tar, ใช้การบีบอัด Bzip2, และสร้างอาร์ไคฟ์ที่พร้อมแชร์

ก่อนที่เราจะเริ่มลงลึก โปรดตรวจสอบว่าคุณมีข้อกำหนดเบื้องต้นที่ระบุไว้ต่อไปในคู่มือนี้เพื่อให้คุณสามารถทำตามได้โดยไม่มีอุปสรรค

## คำตอบสั้น
- **ไลบรารีที่ควรใช้คืออะไร?** Aspose.Zip for .NET  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาที  
- **ฉันต้องการใบอนุญาตหรือไม่?** จำเป็นต้องมีใบอนุญาตชั่วคราวสำหรับการใช้งานจริง; มีรุ่นทดลองฟรีให้ใช้  
- **ฉันสามารถบีบอัดหลายไฟล์ได้หรือไม่?** ได้ – เพิ่มรายการเท่าที่ต้องการลงใน tar archive  
- **รองรับ .NET 6+ หรือไม่?** แน่นอน, Aspose.Zip รองรับ .NET Framework และ .NET Core/5/6  

## TarBz2 archive คืออะไร

ไฟล์ **TarBz2** ผสานคอนเทนเนอร์ **tar** แบบดั้งเดิม (ซึ่งรักษาโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์) กับการบีบอัด **Bzip2**, ทำให้ได้แพคเกจ `.tar.bz2` ที่บีบอัดสูง รูปแบบนี้เป็นที่นิยมในระบบแบบ Unix เนื่องจากให้สมดุลที่ดีระหว่างอัตราการบีบอัดและความเร็วในการแตกไฟล์

## ทำไมต้องบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip?

- **ความเร็วและความเรียบง่าย** – การเรียก API แบบบรรทัดเดียวจัดการการสร้าง tar และการบีบอัด Bzip2 ทั้งหมด  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS .NET runtimes  
- **การควบคุมละเอียด** – เลือกไฟล์ที่ต้องการรวม, ตั้งชื่อรายการแบบกำหนดเอง, และสตรีมโดยตรงไปยังดิสก์  
- **การสนับสนุน .NET ที่แข็งแกร่ง** – เหมาะสำหรับสถานการณ์ **tar archive .net**, ตั้งแต่แอปคอนโซลจนถึงเว็บเซอร์วิส  

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดแพคเกจล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการบันทึกเป็นอาร์ไคฟ์. ในตัวอย่างเราจะอ้างอิงด้วยตัวแปร `dataDir`.

> **เคล็ดลับ:** เก็บไฟล์ต้นฉบับของคุณในโฟลเดอร์เฉพาะเพื่อหลีกเลี่ยงการรวมไฟล์ที่ไม่ต้องการโดยบังเอิญ

## นำเข้า Namespaces

ขั้นแรก ให้นำเข้า Namespaces ที่จำเป็นเพื่อให้คุณสามารถเข้าถึงคลาส Tar และ Bzip2 ของ Aspose.Zip

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory

กำหนดเส้นทางที่ชี้ไปยังโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบันทึกเป็นอาร์ไคฟ์

```csharp
string dataDir = "Your Document Directory";
```

> แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ไปยังโฟลเดอร์ต้นฉบับของคุณ

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน tar และสร้าง TarBz2 archive

หัวใจของกระบวนการคือการสร้าง `TarArchive`, เพิ่มรายการ, แล้วห่อหุ้มด้วย `Bzip2Archive`. โค้ดด้านล่างแสดง **วิธีสร้าง tar** และบีบอัดเป็น **TarBz2** ในรูปแบบที่สะอาดและใช้ pattern แบบ disposable

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **เพิ่มไฟล์ลงใน tar** – คุณสามารถเรียกเมธอดนี้สำหรับทุกไฟล์ที่ต้องการในอาร์ไคฟ์  
- `bz2.SetSource(archive)` บอกให้ Bzip2 archive บีบอัดสตรีม tar ทั้งหมด  
- `bz2.Save(...)` เขียนไฟล์ **TarBz2** สุดท้ายลงดิสก์  

**เคล็ดลับ:** เพื่อ **เพิ่มไฟล์ลงใน tar** เป็นกลุ่ม, เพียงทำซ้ำ `archive.CreateEntry` สำหรับแต่ละไฟล์ก่อนเรียก `bz2.Save`.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **File not found** error | เส้นทาง `dataDir` ผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบเส้นทางเต็มและยืนยันว่าไฟล์มีอยู่ |
| **Empty archive** | ไม่มีรายการใดถูกเพิ่มก่อน `bz2.Save` | เพิ่มการเรียก `CreateEntry` อย่างน้อยหนึ่งครั้ง |
| **Permission denied** | แอปพลิเคชันไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | เรียกใช้แอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกไดเรกทอรีที่สามารถเขียนได้ |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับแอปพลิเคชัน .NET ทั้งหมดหรือไม่?**  
A: ใช่. มันทำงานกับ .NET Framework, .NET Core, .NET 5/6, และ runtime ใหม่ๆ  

**Q: ฉันสามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?**  
A: ได้แน่นอน. เรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึกอาร์ไคฟ์  

**Q: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารรายละเอียดมีให้ที่ [here](https://reference.aspose.com/zip/net/)  

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอได้ที่ [here](https://purchase.aspose.com/temporary-license/)  

**Q: มีรุ่นทดลองฟรีหรือไม่?**  
A: มี, ดาวน์โหลดเวอร์ชันทดลองได้ที่ [here](https://releases.aspose.com/)  

## สรุป

คุณได้เรียนรู้ **วิธีบีบอัด tar** แล้ว, เพิ่มไฟล์ลงในนั้น, และห่อผลลัพธ์ด้วยสตรีม Bzip2 เพื่อสร้างอาร์ไคฟ์ **TarBz2** ด้วย Aspose.Zip สำหรับ .NET วิธีนี้เร็ว, น่าเชื่อถือ, และทำงานได้บนแพลตฟอร์ม .NET สมัยใหม่ทั้งหมด อย่าลังเลที่จะทดลองกับชุดไฟล์ขนาดใหญ่, ชื่อรายการแบบกำหนดเอง, หรือผสานโค้ดนี้เข้ากับกระบวนการสำรองข้อมูลหรือการปรับใช้ของคุณ

หากคุณเจอปัญหาใด ๆ ชุมชน Aspose.Zip พร้อมให้ความช่วยเหลือ—เพียงไปที่ [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}