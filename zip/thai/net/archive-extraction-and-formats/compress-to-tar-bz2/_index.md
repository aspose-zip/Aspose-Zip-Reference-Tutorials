---
date: 2025-11-29
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน tar และบีบอัดไฟล์เป็นรูปแบบ tarbz2 ใน .NET
  ด้วย Aspose.Zip คู่มือแบบขั้นตอนนี้แสดงวิธีสร้างไฟล์เก็บข้อมูล tarbz2 อย่างมีประสิทธิภาพ
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarBz2 โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฟล์ลงใน tar และบีบอัดเป็น TarBz2 ด้วย Aspose.Zip สำหรับ .NET

## คำแนะนำ

ยินดีต้อนรับสู่คู่มือฉบับสมบูรณ์ของเราว่า **วิธีเพิ่มไฟล์ลงใน tar** และบีบอัดเป็นรูปแบบ TarBz2 ด้วย Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างเครื่องมือสำรองข้อมูล, จัดส่งแพ็คเกจการปรับใช้, หรือเพียงต้องการไฟล์บีบอัดที่กะทัดรัดสำหรับการแจกจ่าย, บทเรียนนี้จะพาคุณผ่านทุกขั้นตอนด้วยคำอธิบายที่ชัดเจนและเคล็ดลับจากโลกจริง

ก่อนที่เราจะเริ่ม, ให้แน่ใจว่าคุณมีทุกอย่างที่ต้องการแล้ว

## คำตอบด่วน
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาที
- **ต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการใช้งานจริง; มีรุ่นทดลองฟรี
- **ฉันสามารถบีบอัดหลายไฟล์ได้หรือไม่?** ได้ – เพิ่มรายการเท่าที่ต้องการลงใน Tar archive
- **รองรับ .NET 6+ หรือไม่?** แน่นอน, Aspose.Zip รองรับ .NET Framework และ .NET Core/5/6

## “การเพิ่มไฟล์ลงใน tar” คืออะไร?
การเพิ่มไฟล์ลงใน **tar** (Tape Archive) จะสร้างคอนเทนเนอร์ที่ไม่ได้บีบอัดเป็นไฟล์เดียวที่คงโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์ไว้ เมื่อคุณนำไปบีบอัดด้วย Bzip2 ผลลัพธ์จะเป็นไฟล์ **tar.bz2** (TarBz2) – เหมาะสำหรับการจัดเก็บและการถ่ายโอนที่มีประสิทธิภาพ

## ทำไมต้องบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip?
- **ความเร็วและความเรียบง่าย** – การเรียก API เพียงบรรทัดเดียวจัดการการสร้าง tar และการบีบอัด Bzip2
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS .NET runtimes
- **การควบคุมระดับละเอียด** – เลือกไฟล์ที่ต้องการรวม, ตั้งชื่อรายการแบบกำหนดเอง, และสตรีมโดยตรงไปยังดิสก์

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดแพคเกจล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – โฟลเดอร์ที่มีไฟล์ที่คุณต้องการบันทึกเป็น archive. ในตัวอย่างเราจะอ้างอิงด้วยตัวแปร `dataDir`.

> **เคล็ดลับ:** เก็บไฟล์ต้นฉบับของคุณในโฟลเดอร์เฉพาะเพื่อหลีกเลี่ยงการรวมไฟล์ที่ไม่ต้องการโดยบังเอิญ.

## นำเข้า Namespaces

ก่อนอื่น, นำเข้า namespaces ที่จำเป็นเพื่อให้คุณสามารถเข้าถึงคลาส Tar และ Bzip2 ของ Aspose.Zip

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory

กำหนดเส้นทางที่ชี้ไปยังโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบันทึกเป็น archive.

```csharp
string dataDir = "Your Document Directory";
```

> แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ไปยังโฟลเดอร์ต้นฉบับของคุณ.

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน tar และสร้าง TarBz2 archive

หัวใจของกระบวนการคือการสร้าง `TarArchive`, เพิ่มรายการ, แล้วห่อหุ้มด้วย `Bzip2Archive`. โค้ดด้านล่างแสดง **วิธีสร้าง tarbz2** ด้วยสไตล์แบบ clean, disposable‑pattern.

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

- `CreateEntry` เพิ่มไฟล์แต่ละไฟล์ลงในคอนเทนเนอร์ **tar**.  
- `bz2.SetSource(archive)` บอกให้ Bzip2 archive บีบอัดสตรีม tar ทั้งหมด.  
- `bz2.Save(...)` เขียนไฟล์ **tar.bz2** สุดท้ายลงดิสก์.

**เคล็ดลับ:** เพื่อ **บีบอัดไฟล์เป็น tarbz2** เป็นจำนวนมาก, เพียงทำซ้ำ `archive.CreateEntry` สำหรับทุกไฟล์ที่คุณต้องการ.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไฟล์ไม่พบ** error | เส้นทาง `dataDir` ผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบเส้นทางเต็มและให้แน่ใจว่าไฟล์มีอยู่ |
| **Archive ว่าง** | ไม่มีรายการใดถูกเพิ่มก่อน `bz2.Save` | เพิ่มอย่างน้อยหนึ่งการเรียก `CreateEntry` |
| **Permission denied** | แอปพลิเคชันไม่มีสิทธิ์เขียนในโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกโฟลเดอร์ที่สามารถเขียนได้ |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับแอปพลิเคชัน .NET ทั้งหมดหรือไม่?**  
A: ใช่. มันทำงานกับ .NET Framework, .NET Core, .NET 5/6, และ runtime รุ่นใหม่

**Q: ฉันสามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?**  
A: แน่นอน. เรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก archive.

**Q: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารโดยละเอียดมีให้ที่ [here](https://reference.aspose.com/zip/net/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอได้ที่ [here](https://purchase.aspose.com/temporary-license/).

**Q: มีรุ่นทดลองฟรีหรือไม่?**  
A: มี, ดาวน์โหลดรุ่นทดลองได้ที่ [here](https://releases.aspose.com/).

## สรุป

คุณได้เรียนรู้วิธี **เพิ่มไฟล์ลงใน tar**, ห่อหุ้มด้วยสตรีม Bzip2, และสร้าง archive **TarBz2** ด้วย Aspose.Zip สำหรับ .NET แล้ว เทคนิคนี้เร็ว, เชื่อถือได้, และทำงานได้บนทุกแพลตฟอร์ม .NET สมัยใหม่ อย่าลังเลที่จะทดลองกับชุดไฟล์ขนาดใหญ่, ชื่อรายการแบบกำหนดเอง, หรือผสานโค้ดนี้เข้ากับกระบวนการสำรองข้อมูลหรือการปรับใช้ของคุณ

หากคุณเจออุปสรรคใด ๆ, ชุมชน Aspose.Zip พร้อมให้ความช่วยเหลือ—เพียงไปที่ [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**อัปเดตล่าสุด:** 2025-11-29  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}