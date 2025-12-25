---
date: 2025-12-25
description: เรียนรู้วิธีสร้างไฟล์ 7z ด้วย Aspose.Zip สำหรับ .NET ครอบคลุมวิธีการบีบอัดแบบ
  Seven Zip เช่น LZMA2, BZip2 และ Store เหมาะสำหรับการบีบอัดโฟลเดอร์เป็น 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีสร้างไฟล์ 7z – บทเรียน Aspose.Zip สำหรับ .NET
url: /th/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไฟล์ 7z – คู่มือ Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **วิธีสร้าง 7z** แบบโปรแกรมในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว Aspose.Zip สำหรับ .NET ทำให้การสร้างไฟล์ Seven Zip ด้วยอัลกอริทึมการบีบอัดที่รองรับเป็นเรื่องง่าย ไม่ว่าคุณจะต้องการ **compress folder to 7z** เพื่อแจกจ่ายหรือแค่ต้องการโซลูชัน **seven zip archive .net** ที่เชื่อถือได้ ในคู่มือนี้เราจะอธิบายวิธีการบีบอัดสามแบบที่เป็นที่นิยม — LZMA2, BZip2, และ Store (ไม่มีการบีบอัด) — และแสดงให้คุณเห็นว่าการสร้างไฟล์ 7z สามารถทำได้ด้วยไม่กี่บรรทัดของโค้ด C# เท่านั้น

## คำตอบสั้น
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip สำหรับ .NET มีฟีเจอร์ Seven Zip ครบถ้วนที่สุด  
- **วิธีบีบอัดแบบไหนให้ได้อัตราส่วนดีที่สุด?** LZMA2 มักให้การบีบอัดสูงสุดสำหรับข้อมูลผสม  
- **สามารถสร้าง 7z โดยไม่มีการบีบอัดได้หรือไม่?** ได้ — ใช้วิธี Store (ไม่มีการบีบอัด)  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์จริง  
- **รองรับ .NET 6/7 หรือไม่?** แน่นอน — Aspose.Zip รองรับ .NET Framework, .NET Core, และ .NET 5+

## วิธีบีบอัด Seven Zip มีอะไรบ้าง?

Seven Zip รองรับอัลกอริทึมหลายแบบ แต่ละแบบถูกออกแบบให้เหมาะกับสถานการณ์ต่าง ๆ:

* **LZMA2** – อัตราการบีบอัดสูง เหมาะกับไฟล์ขนาดใหญ่และประเภทผสม  
* **BZip2** – บีบอัดดีแต่ช้ากว่า LZMA2; มีประโยชน์เมื่อจำเป็นต้องเข้ากันได้กับเครื่องมือเก่า  
* **Store** – ไม่บีบอัด; เหมาะเมื่อต้องการเก็บไฟล์โดยไม่ลดขนาด (เช่น ต้องการรักษา timestamp ดั้งเดิม)

การเข้าใจ **seven zip compression methods** จะช่วยให้คุณเลือกตั้งค่าที่เหมาะกับโครงการของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมี:

- ความรู้พื้นฐานเกี่ยวกับ C# และ Visual Studio  
- ไลบรารี Aspose.Zip สำหรับ .NET ที่ติดตั้งแล้ว ดาวน์โหลดได้จากหน้า **[ที่นี่](https://releases.aspose.com/zip/net/)**  
- โฟลเดอร์ (`dataDir`) ที่บรรจุไฟล์ที่ต้องการทำเป็นอาร์ไคฟ์

## นำเข้า Namespaces

เพิ่ม namespaces ที่จำเป็นลงในไฟล์ C# ของคุณก่อน:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

คลาสเหล่านี้ให้คุณเข้าถึงการตั้งค่าการบีบอัดและการจัดการอาร์ไคฟ์ได้

## การบีบอัด LZMA2 – วิธีสร้าง 7z ด้วยอัตราส่วนสูงสุด

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **เคล็ดลับ:** LZMA2 ทำงานได้ดีที่สุดเมื่อไฟล์ต้นทางมีขนาดมากกว่า 1 MB หากไฟล์หลายไฟล์มีขนาดเล็ก BZip2 อาจเร็วกว่า

## การบีบอัด BZip2 – ตัวเลือกที่สมดุล

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 ให้การบีบอัดที่ค่อนข้างดีพร้อมความเร็วที่เหมาะสม ทำให้เป็นตัวเลือกสำรองที่ดีเมื่อสภาพแวดล้อมเป้าหมายไม่รองรับ LZMA2

## Store (ไม่มีการบีบอัด) – เมื่อขนาดไม่สำคัญ

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

ใช้วิธี Store หากคุณต้องการรวมไฟล์เข้าด้วยกันโดยไม่เปลี่ยนขนาด — เหมาะสำหรับการรักษา timestamp ดั้งเดิมหรือเมื่ออาร์ไคฟ์จะถูกแตกออกโดยตรง

## กรณีการใช้งานทั่วไป

| สถานการณ์ | วิธีที่แนะนำ |
|----------|--------------------|
| แจกจ่ายตัวติดตั้งขนาดใหญ่ | LZMA2 |
| แชร์ล็อกกับเครื่องมือเก่า | BZip2 |
| แพ็คไฟล์เพื่อการสกัดเร็ว | Store (ไม่มีการบีบอัด) |
| ต้อง **compress folder to 7z** แบบเรียลไทม์ในเว็บเซอร์วิส | LZMA2 (เพื่ออัตราส่วนสูงสุด) |

## การแก้ไขปัญหาและเคล็ดลับ

- **ไฟล์หายจากอาร์ไคฟ์?** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและกระบวนการมีสิทธิ์อ่านไฟล์  
- **อาร์ไคฟ์เปิดไม่ได้ในเวอร์ชัน 7‑Zip เก่า?** ใช้ BZip2 หรือ Store แทน เนื่องจาก LZMA2 อาจต้องไลบรารีการแตกใหม่กว่า  
- **เป็นคอขวดด้านประสิทธิภาพ?** สำหรับชุดข้อมูลขนาดใหญ่ ควรสตรีมอาร์ไคฟ์แทนการโหลดทุกรายการเข้าหน่วยความจำ

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.Zip สำหรับ .NET กับไฟล์ประเภทใดก็ได้หรือไม่?**  
ตอบ: ใช่, Aspose.Zip รองรับรูปแบบไฟล์หลายประเภท ทำให้คุณบีบอัดและแตกไฟล์ได้เกือบทุกชนิด

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดรุ่นทดลอง **[ที่นี่](https://releases.aspose.com/)**

**ถาม: จะหาเอกสารสำหรับ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
ตอบ: เอกสาร API เต็มรูปแบบมีให้ **[ที่นี่](https://reference.aspose.com/zip/net/)**

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?**  
ตอบ: สามารถขอรับลิขสิทธิ์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**

**ถาม: จะหาแหล่งสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
ตอบ: คุณสามารถสอบถามได้ใน **[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37)**

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**อัปเดตล่าสุด:** 2025-12-25  
**ทดสอบกับ:** Aspose.Zip สำหรับ .NET 24.12  
**ผู้เขียน:** Aspose  

---