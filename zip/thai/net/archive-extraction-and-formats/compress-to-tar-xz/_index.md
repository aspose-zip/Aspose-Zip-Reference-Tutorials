---
date: 2026-02-05
description: เรียนรู้วิธีเพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarxz ใน .NET ด้วย Aspose.Zip
  คู่มือนี้แสดงวิธีบีบอัดไฟล์เป็น tarxz อย่างมีประสิทธิภาพสูง
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: เพิ่มไฟล์ลงใน tar, สร้างไฟล์ tarxz ด้วย .NET และ Aspose.Zip
url: /th/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มไฟล์ลงใน tar, สร้างไฟล์เก็บ tarxz ด้วย .NET และ Aspise.Zip

## บทนำ

หากคุณต้องการ **add files to tar** แล้วบีบอัดเป็นไฟล์ tarxz ด้วย .NET, Aspose.Zip for .NET ทำให้กระบวนการง่ายและเชื่อถือได้ ไม่ว่าคุณจะกำลังบรรจุบันทึก, ไฟล์การกำหนดค่า หรือทรัพยากรอื่น ๆ เพื่อการจัดเก็บหรือการส่งต่อ การบีบอัดเป็นรูปแบบ TarXz จะให้ระดับการบีบอัดสูงพร้อมคงโครงสร้าง tar ที่คุ้นเคย ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนอย่างละเอียด—พร้อมตัวอย่างโค้ด—เพื่อให้คุณสามารถผสานการสร้าง tarxz เข้าไปในแอปพลิเคชัน .NET ของคุณได้อย่างมั่นใจ.

## คำตอบอย่างรวดเร็ว
- **คลาสหลักคืออะไร?** `TarArchive` from `Aspose.Zip.Tar`
- **วิธีบีบอัด tarxz?** Use `SaveXzCompressed` after adding entries
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **ต้องการใบอนุญาตหรือไม่?** Yes, a valid Aspose.Zip license for production
- **ระยะเวลาในการทำงานโดยทั่วไป?** ~5‑10 minutes

## TarXz archive คืออะไร?

**TarXz archive** ผสานคอนเทนเนอร์ Unix แบบดั้งเดิม `tar` กับการบีบอัด XZ ส่วน tar จะรวมหลายไฟล์เป็นสตรีมเดียว ในขณะที่ XZ ให้การบีบอัดที่แข็งแรงและไม่มีการสูญเสียรูปแบบนี้เป็นที่นิยมสำหรับการแจกจ่ายซอร์สโค้ด, การสำรองข้อมูล, และชุดข้อมูลขนาดใหญ่ เนื่องจากคงโครงสร้างไดเรกทอรีและทำให้ไฟล์มีขนาดเล็กกว่าการใช้ tar หรือ zip ธรรมดา

## ทำไมต้องเพิ่มไฟล์ลงใน tar แล้วบีบอัดเป็น tarxz ด้วย Aspose.Zip?

- **อัตราการบีบอัดสูง** – XZ มักบีบอัดให้เล็กลง 30‑50 % เมื่อเทียบกับ gzip.  
- **ความเข้ากันได้ข้ามแพลตฟอร์ม** – ไฟล์ TarXz สามารถเปิดได้บน Linux, macOS, และ Windows.  
- **API ที่ง่าย** – Aspose.Zip ทำให้รายละเอียดระดับล่างเป็นนามธรรม ช่วยให้คุณโฟกัสที่ตรรกะธุรกิจของคุณ.  
- **ไม่มีเครื่องมือภายนอก** – ทุกอย่างทำงานภายในกระบวนการ .NET ของคุณ เหมาะสำหรับคลาวด์หรือ pipeline CI.  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** ที่ติดตั้งแล้ว (ดาวน์โหลดจาก [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) อย่างเป็นทางการ).  
- โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการเก็บไว้ใน archive. ในตัวอย่างด้านล่าง โฟลเดอร์นี้ถูกอ้างอิงด้วยตัวแปร `dataDir`.  
- ใบอนุญาต Aspose.Zip ที่ถูกต้อง (ไม่บังคับสำหรับการประเมินผล, จำเป็นสำหรับการใช้งานจริง).

## นำเข้า Namespaces

ก่อนอื่น ให้นำเข้า namespaces ที่เปิดเผยฟังก์ชันการทำงานของ TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## วิธีเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip

### ขั้นตอนที่ 1: เริ่มต้น `TarArchive`

สร้างอินสแตนซ์ `TarArchive` ใหม่ที่จะเก็บไฟล์ที่คุณต้องการบีบอัด.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **เคล็ดลับ:** คำสั่ง `using` ทำให้แน่ใจว่า archive ถูกทำลายอย่างถูกต้อง ปล่อยทรัพยากรที่ไม่ได้จัดการออก.

### ขั้นตอนที่ 2: เพิ่มไฟล์ลงใน Archive

เพิ่มไฟล์แต่ละไฟล์ที่คุณต้องการรวมไว้ ในตัวอย่างนี้เราจะเพิ่มไฟล์ข้อความสองไฟล์ แต่คุณสามารถเพิ่มรายการได้ตามต้องการ.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **ทำไมเรื่องนี้สำคัญ:** การเพิ่มรายการก่อนการบีบอัดทำให้ Aspose.Zip สร้างคอนเทนเนอร์ tar ก่อน แล้วจึงใช้การบีบอัด XZ ในขั้นตอนเดียว.

### ขั้นตอนที่ 3: บันทึก Archive ด้วยการบีบอัด XZ

สุดท้าย ให้เขียน tar archive ลงดิสก์โดยใช้การบีบอัด XZ ไฟล์ที่ได้จะมีส่วนขยาย `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **ผลลัพธ์:** ตอนนี้คุณมีไฟล์ `archive.tar.xz` ที่บีบอัดเต็มรูปแบบ ซึ่งสามารถถ่ายโอน, เก็บ, หรือแตกไฟล์บนแพลตฟอร์มใดก็ได้ที่รองรับ TarXz.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **“File not found” exception** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าเส้นทางไดเรกทอรีลงท้ายด้วยแบ็คสแลช (`\`) หรือใช้ `Path.Combine`. |
| **Large memory usage** | ไฟล์ขนาดใหญ่มากถูกบีบอัดในหน่วยความจำ | ใช้ `TarArchive` ในโหมดสตรีมมิ่ง (`SaveXzCompressed` overload ที่รับ `Stream`). |
| **License not applied** | ไฟล์ใบอนุญาตหายไป | โหลดใบอนุญาตเมื่อเริ่มแอปพลิเคชัน: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับทุกสภาพแวดล้อม .NET หรือไม่?**  
A: ใช่, Aspose.Zip ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+. ดู [documentation](https://reference.aspose.com/zip/net/) สำหรับรายละเอียด.

**Q: ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอใบอนุญาตชั่วคราวจาก [หน้าใบอนุญาตชั่วคราวของ Aspose](https://purchase.aspose.com/temporary-license/).

**Q: มีตัวอย่างเพิ่มเติมสำหรับรูปแบบ archive อื่น ๆ หรือไม่?**  
A: แน่นอน—สำรวจชุดตัวอย่างทั้งหมดใน [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: ฉันจะหาความช่วยเหลือหรือพูดคุยเกี่ยวกับปัญหาได้จากที่ไหน?**  
A: เข้าร่วมการสนทนาที่ [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและคำตอบจากทีมงาน.

**Q: ฉันสามารถทดลองใช้ Aspose.Zip ฟรีก่อนซื้อได้หรือไม่?**  
A: ได้, มีการทดลองใช้ฟรีที่ [หน้าดาวน์โหลด Aspose.Zip](https://releases.aspose.com/zip/net).

## สรุป

โดยทำตามขั้นตอนข้างต้น คุณจะทราบ **วิธีเพิ่มไฟล์ลงใน tar** และ **สร้าง tarxz archive** ด้วย Aspose.Zip ใน .NET วิธีนี้ให้แพ็คเกจที่กะทัดรัดและพกพาได้ ซึ่งสามารถผสานเข้ากับเวิร์กโฟลว์ .NET ใด ๆ ได้อย่างราบรื่น ไม่ว่าจะเป็นการสร้างยูทิลิตี้เดสก์ท็อป, เว็บเซอร์วิส, หรือ pipeline CI/CD อัตโนมัติ.

---

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** Aspose.Zip for .NET 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}