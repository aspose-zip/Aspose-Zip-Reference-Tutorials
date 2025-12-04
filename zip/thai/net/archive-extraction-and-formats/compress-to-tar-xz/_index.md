---
date: 2025-12-04
description: เรียนรู้วิธีทำการบีบอัด Aspose Zip เพื่อเพิ่มไฟล์ลงใน tar archive และสร้างไฟล์
  TarXz ใน .NET ด้วย Aspose.Zip. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดเก็บและการส่งข้อมูลที่มีประสิทธิภาพ.
language: th
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 'การบีบอัด Zip ของ Aspose: การบีบอัดเป็น TarXz ด้วย Aspose.Zip สำหรับ .NET'
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การบีบอัด Aspose Zip: การบีบอัดเป็น TarXz ด้วย Aspose.Zip สำหรับ .NET

## คำแนะนำ

ในโลกของการพัฒนา .NET, **aspose zip compression** เป็นเทคนิคสำคัญสำหรับการเพิ่มประสิทธิภาพทั้งขนาดการจัดเก็บและความเร็วในการถ่ายโอนข้อมูล ไม่ว่าคุณจะกำลังสร้างบริการสำรองข้อมูล, ส่งมอบทรัพยากรผ่านเครือข่าย, หรือเพียงแค่เก็บบันทึก, การบีบอัดไฟล์อย่างมีประสิทธิภาพทำให้เกิดความแตกต่างอย่างมาก ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่แน่นอนเพื่อ **add files tar archive** และสร้างแพคเกจ TarXz ด้วยไลบรารี Aspose.Zip

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดจัดการการบีบอัด?** Aspose.Zip for .NET  
- **รูปแบบใดที่ตัวอย่างสร้างขึ้น?** `archive.tar.xz` (TarXz)  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการสร้าง archive เบื้องต้น

## Aspose Zip Compression คืออะไร?

Aspose Zip compression คือชุด API ที่ให้โดยไลบรารี Aspose.Zip สำหรับ .NET ซึ่งทำให้คุณสามารถสร้าง, อ่าน, และแก้ไขไฟล์ archive (ZIP, TAR, GZIP, XZ, เป็นต้น) อย่างโปรแกรมเมติก ไลบรารีนี้แยกรายละเอียดระดับต่ำของสตรีมการบีบอัดออก, ให้คุณมีวิธีการทำงานกับ archive ที่เป็นเชิงวัตถุและสะอาดตา.

## ทำไมต้องใช้ TarXz กับ Aspose Zip Compression?

* **อัตราการบีบอัดสูง** – XZ ใช้อัลกอริทึม LZMA2 ซึ่งมักให้ไฟล์ที่เล็กกว่ามาตรฐาน GZIP.  
* **ความเข้ากันได้ข้ามแพลตฟอร์ม** – TarXz archive ได้รับการสนับสนุนอย่างกว้างขวางบน Linux, macOS, และ Windows.  
* **API ที่เรียบง่าย** – ด้วย Aspose.Zip คุณสามารถสร้างคอนเทนเนอร์ TAR และบีบอัดเป็น XZ ได้ในไม่กี่บรรทัดของโค้ด.  

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Zip for .NET** ติดตั้งแล้ว. คุณสามารถดาวน์โหลดได้จากหน้า [Aspose.Zip documentation page](https://reference.aspose.com/zip/net/) อย่างเป็นทางการ.  
- โฟลเดอร์บนเครื่องของคุณที่มีไฟล์ที่ต้องการบีบอัด. ในตัวอย่างโค้ด โฟลเดอร์นี้ถูกอ้างอิงโดยตัวแปร `dataDir`.

## นำเข้า Namespaces สำหรับ Aspose Zip Compression

Namespaces เหล่านี้ให้คุณเข้าถึงฟังก์ชันการทำงานของ TAR และ XZ.

```csharp
using System;
using Aspose.Zip.Tar;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้าง TarXz Archive

เราจะสร้างคอนเทนเนอร์ TAR ก่อนแล้วจึงบีบอัดด้วย XZ.

#### 1.1 เริ่มต้น TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
```

#### 1.2 เพิ่มไฟล์ลงใน Archive – วิธี **add files tar archive**

เมธอด `CreateEntry` จะเพิ่มแต่ละไฟล์ลงในคอนเทนเนอร์ TAR. ที่นี่เราจะ **add files tar archive** โดยระบุชื่อ entry และเส้นทางไฟล์ต้นทาง.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

#### 1.3 บันทึก Archive ด้วยการบีบอัด XZ

สุดท้าย, เราบอก Aspose.Zip ให้บีบอัดข้อมูล TAR ด้วย XZ และเขียนผลลัพธ์ลงดิสก์.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

เท่านี้เอง—สามการเรียกที่สั้นกระชับและคุณจะได้ไฟล์ TarXz ที่บีบอัดเต็มรูปแบบ.

### ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **เส้นทางไฟล์** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\` หรือ `/`) เพื่อหลีกเลี่ยงเส้นทางที่ผิดรูปแบบ.  
- **ไฟล์ขนาดใหญ่** – สำหรับไฟล์ต้นทางขนาดใหญ่มาก, พิจารณาใช้การสตรีมข้อมูลแทนการโหลดทั้งหมดในครั้งเดียว; Aspose.Zip รองรับการสร้าง entry แบบสตรีม.  
- **ไลเซนส์** – หากคุณรันโค้ดโดยไม่มีไลเซนส์ที่ถูกต้อง, ไลบรารีจะทำงานในโหมดประเมินผลและอาจเพิ่มลายน้ำลงในผลลัพธ์.

## สรุป

ในบทแนะนำนี้เราได้สาธิตว่าการใช้ **aspose zip compression** สามารถ **add files tar archive** และสร้างแพคเกจ TarXz ได้ด้วยไม่กี่บรรทัดของ C#. การนำขั้นตอนเหล่านี้เข้ามาในแอปพลิเคชัน .NET ของคุณจะทำให้คุณได้ความสามารถในการจัดเก็บ archive ที่มีประสิทธิภาพ, รองรับข้ามแพลตฟอร์ม, ลดต้นทุนการจัดเก็บและเพิ่มประสิทธิภาพการถ่ายโอน.

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับสภาพแวดล้อม .NET ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Zip ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7. ดูที่ [documentation](https://reference.aspose.com/zip/net/) สำหรับรายละเอียด.

**Q: ฉันจะขอไลเซนส์ชั่วคราวสำหรับ Aspose.Zip ได้อย่างไร?**  
A: คุณสามารถขอไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

**Q: มีตัวอย่างเพิ่มเติมสำหรับการใช้ Aspose.Zip หรือไม่?**  
A: แน่นอน. เอกสารอย่างเป็นทางการมีชุดตัวอย่างที่หลากหลายครอบคลุม ZIP, TAR, GZIP, XZ, และอื่น ๆ. ตรวจสอบที่ [documentation](https://reference.aspose.com/zip/net/).

**Q: ฉันจะหาแหล่งช่วยเหลือหรือพูดคุยเกี่ยวกับปัญหา Aspose.Zip ได้จากที่ไหน?**  
A: ฟอรั่มชุมชนเป็นที่ที่ดีสำหรับถามคำถาม: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: ฉันสามารถทดลองใช้ Aspose.Zip ฟรีก่อนซื้อได้หรือไม่?**  
A: ได้, มีการทดลองใช้ฟรีที่สามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/zip/net).

---

**อัปเดตล่าสุด:** 2025-12-04  
**ทดสอบด้วย:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}