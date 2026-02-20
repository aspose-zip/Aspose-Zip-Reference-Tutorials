---
date: 2026-02-20
description: เรียนรู้วิธีบีบอัดไฟล์ tar และสร้างไฟล์ TarBz2 ใน .NET ด้วย Aspose.Zip
  คู่มือแบบทีละขั้นตอนนี้จะแสดงวิธีเพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarbz2 อย่างมีประสิทธิภาพ
linktitle: Compressing to TarBz2
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

ยินดีต้อนรับสู่คู่มือที่ครอบคลุมของเราเกี่ยวกับ **how to compress tar** และการเพิ่มไฟล์ลงใน tar archive, จากนั้นสร้างไฟล์ TarBz2 ด้วย Aspose.Zip สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างยูทิลิตี้สำรองข้อมูล, จัดส่งแพ็กเกจการปรับใช้, หรือเพียงต้องการไฟล์บีบอัดขนาดกะทัดรัดสำหรับการแจกจ่าย, บทแนะนำนี้จะพาคุณผ่านทุกขั้นตอนด้วยคำอธิบายที่ชัดเจน, เคล็ดลับจากโลกจริง, และตัวอย่างที่ใช้งานได้จริง.

ก่อนที่เราจะเริ่ม, ให้แน่ใจว่าคุณมีทุกอย่างที่ต้องการ.

## คำตอบด่วน
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET
- **การดำเนินการใช้เวลานานเท่าไหร่?** About 5‑10 minutes
- **ฉันต้องการใบอนุญาตหรือไม่?** A temporary license is required for production; a free trial is available
- **ฉันสามารถบีบอัดหลายไฟล์ได้หรือไม่?** Yes – add as many entries as you like to the Tar archive
- **รองรับ .NET 6+ หรือไม่?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6

## วิธีบีบอัด tar

การเพิ่มไฟล์ลงใน **tar** (Tape Archive) จะสร้างคอนเทนเนอร์ที่ไม่ได้บีบอัดซึ่งเก็บโครงสร้างไดเรกทอรีและเมตาดาต้าไฟล์ไว้ เมื่อคุณนำการบีบอัด Bzip2 ไปใช้ ผลลัพธ์จะเป็นไฟล์ **tar.bz2** (TarBz2) — เหมาะสำหรับการจัดเก็บและการถ่ายโอนที่มีประสิทธิภาพ Aspose.Zip ทำให้กระบวนการนี้เป็นการดำเนินการบรรทัดเดียว, จัดการทั้งการสร้าง tar และการบีบอัด Bzip2 ภายใน.

## ทำไมต้องบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip?

- **ความเร็วและความง่าย** – One‑line API calls handle both tar creation and Bzip2 compression.  
- **Cross‑platform** – Works on Windows, Linux, and macOS .NET runtimes.  
- **Fine‑grained control** – เลือกไฟล์ที่ต้องการรวม, ตั้งชื่อ entry แบบกำหนดเอง, และสตรีมโดยตรงไปยังดิสก์.  
- **Robust .NET support** – รองรับอย่างเต็มที่กับสถานการณ์ **tar archive .net**, ตั้งแต่แอปคอนโซลจนถึงเว็บเซอร์วิส.

## ข้อกำหนดเบื้องต้น

- **Aspose.Zip for .NET** – ดาวน์โหลดแพคเกจล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการบีบอัด. ในตัวอย่างเราจะอ้างอิงด้วยตัวแปร `dataDir`.

> **Pro tip:** เก็บไฟล์ต้นฉบับของคุณในโฟลเดอร์เฉพาะเพื่อหลีกเลี่ยงการรวมไฟล์ที่ไม่ต้องการโดยบังเอิญ.

## นำเข้า Namespaces

ก่อนอื่น, ให้นำเข้า namespaces ที่จำเป็นเพื่อให้คุณเข้าถึงคลาส Tar และ Bzip2 ของ Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory

กำหนดเส้นทางที่ชี้ไปยังโฟลเดอร์ที่เก็บไฟล์ที่คุณต้องการบีบอัด.

```csharp
string dataDir = "Your Document Directory";
```

> แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ไปยังโฟลเดอร์ต้นฉบับของคุณ.

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน tar และสร้าง TarBz2 archive

หัวใจของกระบวนการคือการสร้าง `TarArchive`, เพิ่ม entry, แล้วห่อหุ้มด้วย `Bzip2Archive`. โค้ดด้านล่างแสดง **how to create tarbz2** ในรูปแบบที่สะอาดและใช้ pattern disposable.

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

**เคล็ดลับ:** เพื่อ **compress files to tarbz2** เป็นกลุ่ม, เพียงทำซ้ำ `archive.CreateEntry` สำหรับทุกไฟล์ที่คุณต้องการ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **File not found** error | เส้นทาง `dataDir` ผิดหรือขาดส่วนขยายไฟล์ | ตรวจสอบเส้นทางเต็มและให้แน่ใจว่าไฟล์มีอยู่. |
| **Empty archive** | ไม่มี entry ถูกเพิ่มก่อน `bz2.Save` | เพิ่มอย่างน้อยหนึ่งการเรียก `CreateEntry`. |
| **Permission denied** | แอปพลิเคชันไม่มีสิทธิ์เขียนไปยังโฟลเดอร์ผลลัพธ์ | รันแอปด้วยสิทธิ์ที่เหมาะสมหรือเลือกไดเรกทอรีที่สามารถเขียนได้. |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับแอปพลิเคชัน .NET ทั้งหมดหรือไม่?**  
A: ใช่. มันทำงานกับ .NET Framework, .NET Core, .NET 5/6, และ runtime รุ่นใหม่.

**Q: ฉันสามารถบีบอัดหลายไฟล์พร้อมกันได้หรือไม่?**  
A: แน่นอน. เรียก `CreateEntry` สำหรับแต่ละไฟล์ก่อนบันทึก archive.

**Q: ฉันสามารถหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารโดยละเอียดสามารถดูได้ที่ [here](https://reference.aspose.com/zip/net/).

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอได้ที่ [here](https://purchase.aspose.com/temporary-license/).

**Q: มีการทดลองใช้ฟรีหรือไม่?**  
A: มี, ดาวน์โหลดรุ่นทดลองได้ที่ [here](https://releases.aspose.com/).

## สรุป

คุณได้เรียนรู้วิธี **add files to tar**, ห่อหุ้มด้วยสตรีม Bzip2, และสร้าง archive **TarBz2** ด้วย Aspose.Zip สำหรับ .NET แล้ว เทคนิคนี้เร็ว, เชื่อถือได้, และทำงานบนแพลตฟอร์ม .NET สมัยใหม่ทั้งหมด อย่าลังเลที่จะทดลองกับชุดไฟล์ขนาดใหญ่, ชื่อ entry แบบกำหนดเอง, หรือผสานโค้ดเข้ากับกระบวนการสำรองข้อมูลหรือการปรับใช้ของคุณ

หากคุณเจออุปสรรคใด ๆ, ชุมชน Aspose.Zip พร้อมให้ความช่วยเหลือ—เพียงไปที่ [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}