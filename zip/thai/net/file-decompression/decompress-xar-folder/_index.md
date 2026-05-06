---
date: 2026-02-28
description: เรียนรู้วิธีการแยกไฟล์ xar archive และแตกไฟล์ xar ไปยังโฟลเดอร์โดยใช้
  Aspose.Zip สำหรับ .NET ตามคู่มือขั้นตอนต่อขั้นตอนนี้.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีสกัดไฟล์ Xar Archive ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแตกไฟล์ Xar Archive ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณเป็นนักพัฒนา .NET ที่ต้องการ **แตกไฟล์ xar archive** อย่างรวดเร็วและเชื่อถือได้ Aspose.Zip สำหรับ .NET มี API ที่สะอาดและประสิทธิภาพสูงซึ่งจัดการกระบวนการทั้งหมดโดยไม่ต้องใช้เครื่องมือภายนอก ในบทแนะนำนี้เราจะเดินผ่านทุกขั้นตอนที่จำเป็นในการแตกไฟล์ Xar archive ไปยังโฟลเดอร์ อธิบายว่าทำไมวิธีนี้จึงช่วยประหยัดเวลา และให้โค้ดที่พร้อมรันแล้ว เมื่อเสร็จสิ้นคุณจะเข้าใจว่าเมื่อใดควรใช้วิธีนี้ วิธีการรวมเข้ากับโปรเจกต์ของคุณ และวิธีหลีกเลี่ยงข้อผิดพลาดทั่วไป

## คำตอบอย่างรวดเร็ว
- **ไลบรารีทำอะไร?** อ่านและแตกไฟล์ Xar archive โดยไม่ต้องใช้เครื่องมือภายนอก  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+  
- **ต้องมีลิขสิทธิ์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการผลิต  
- **ใช้เวลาติดตั้งเท่าไหร่?** ปกติไม่เกิน 10 นาที  
- **สามารถแตกไปยังโฟลเดอร์ที่กำหนดเองได้หรือไม่?** ได้ — เพียงระบุเส้นทางเป้าหมายใน `ExtractToDirectory`

## “วิธีการแตก xar” คืออะไร?

การแตกไฟล์ Xar archive หมายถึงการอ่านแพ็กเกจที่บีบอัดและเขียนไฟล์ภายในไปยังไดเรกทอรีบนดิสก์ ซึ่งมีประโยชน์เมื่อคุณได้รับแพ็กเกจ XAR จากตัวติดตั้ง macOS, เครื่องมือสำรองข้อมูล หรือเครื่องมือของบุคคลที่สามและต้องการประมวลผลเนื้อหาเหล่านั้นในแอปพลิเคชัน .NET

## ทำไมต้องใช้ Aspose.Zip สำหรับงานนี้?

- **ไม่มีการพึ่งพาไลบรารีภายนอก** – เป็น .NET แท้ ๆ ไม่ต้องใช้ไบนารีเนทีฟ  
- **API แบบสตรีม** – ทำงานกับไฟล์, MemoryStream หรือ NetworkStream ได้  
- **การจัดการข้อผิดพลาดที่แข็งแรง** – Exception รายละเอียดช่วยให้คุณแก้ไขปัญหาไฟล์ archive ที่เสียหายได้  
- **ความเข้ากันได้เต็มรูปแบบกับ .NET** – ทำงานบน Windows, Linux, และ macOS runtimes

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึก โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Zip สำหรับ .NET** – รวมไว้ในโปรเจกต์ของคุณ คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/zip/net/)  
- **Document Directory** – โฟลเดอร์ในโซลูชันของคุณที่เก็บไฟล์ `.xar` ตัวอย่างและผลลัพธ์ที่จะแตกออกมา

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ ให้เพิ่ม namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## ขั้นตอนที่ 1: กำหนด Document Directory ของคุณ

```csharp
string dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ที่มี `sample.xar` และที่คุณต้องการให้โฟลเดอร์ผลลัพธ์ถูกสร้างขึ้น การใช้ `Path.Combine` ต่อมาจะช่วยหลีกเลี่ยงปัญหาเครื่องหมายแยกเส้นทางระหว่างระบบปฏิบัติการ

## ขั้นตอนที่ 2: แตก Xar Archive

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

โค้ดส่วนนี้เปิดไฟล์ Xar, สร้างอินสแตนซ์ `XarArchive` และแตก **ทั้งไฟล์ xar archive** ไปยัง `DecompressXar_out` การทำงานทั้งหมดเป็นแบบสตรีม ทำให้มีประสิทธิภาพแม้กับแพ็กเกจขนาดใหญ่

## ขั้นตอนที่ 3: รันโค้ด

คอมไพล์และรันแอปพลิเคชันของคุณ หลังจากทำงานเสร็จ คุณจะพบโฟลเดอร์ใหม่ชื่อ `DecompressXar_out` ภายใน Document Directory ของคุณ ซึ่งบรรจุไฟล์ทั้งหมดที่ถูกบรรจุใน archive `.xar` ดั้งเดิม

## ปัญหาที่พบบ่อยและเคล็ดลับ

- **ไฟล์ไม่พบ** – ตรวจสอบให้แน่ใจว่าเส้นทางใน `File.OpenRead` ชี้ไปที่ `sample.xar` อย่างถูกต้อง ใช้ `Path.Combine` เพื่อความปลอดภัยในการจัดการเส้นทาง  
- **การเข้าถึงถูกปฏิเสธ** – รันแอปพลิเคชันด้วยสิทธิ์ไฟล์ระบบที่เพียงพอ โดยเฉพาะเมื่อเขียนไปยังไดเรกทอรีที่มีการป้องกัน  
- **ไฟล์ archive เสียหาย** – Aspose.Zip จะโยน `InvalidDataException`; ตรวจสอบว่าไฟล์ `.xar` ต้นทางสมบูรณ์หรือไม่

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับเวอร์ชัน .NET ล่าสุดหรือไม่?**  
A: ใช่, Aspose.Zip มีการอัปเดตอย่างต่อเนื่องเพื่อให้เข้ากันได้กับเวอร์ชัน .NET ล่าสุด ดูรายละเอียดเพิ่มเติมใน [documentation](https://reference.aspose.com/zip/net/)

**Q: สามารถทดลองใช้ Aspose.Zip ก่อนซื้อได้หรือไม่?**  
A: แน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [here](https://releases.aspose.com/)

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.Zip อย่างไร?**  
A: สำหรับคำถามหรือความช่วยเหลือใด ๆ ให้เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip หรือไม่?**  
A: มี, สามารถรับลิขสิทธิ์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/)

**Q: จะซื้อ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถซื้อ Aspose.Zip สำหรับ .NET ได้จาก [here](https://purchase.aspose.com/buy)

**Q: สามารถแตกไฟล์บางไฟล์จาก Xar archive ได้หรือไม่?**  
A: ได้ — ใช้ `archive.Entries` เพื่อวนลูปรายการและเรียก `ExtractToFile` สำหรับรายการที่ต้องการ

**Q: ไลบรารีรองรับไฟล์ Xar ที่มีการป้องกันด้วยรหัสผ่านหรือไม่?**  
A: ปัจจุบัน Xar archive ไม่รองรับการเข้ารหัส; หากเจอไฟล์ที่ถูกป้องกัน คุณต้องถอดรหัสก่อนใช้ Aspose.Zip

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบกับ:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}