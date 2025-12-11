---
date: 2025-12-10
description: เรียนรู้การบีบอัดไฟล์แบบขนานใน .NET ด้วย Aspose.Zip. บีบอัดหลายไฟล์อย่างมีประสิทธิภาพด้วยคู่มือขั้นตอนต่อขั้นตอนของเรา.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: การบีบอัดไฟล์แบบขนานด้วย Aspose.Zip สำหรับ .NET
url: /th/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การบีบอัดไฟล์แบบขนานด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในโลกของการพัฒนา .NET, **การบีบอัดไฟล์แบบขนาน** มีความสำคัญต่อการเพิ่มประสิทธิภาพการใช้พื้นที่จัดเก็บและเร่งความเร็วการส่งข้อมูล Aspose.Zip สำหรับ .NET ให้โซลูชันที่ทรงพลัง และหนึ่งในคุณสมบัติเด่นของมันคือความสามารถในการใช้การทำงานแบบขนานสำหรับการบีบอัดไฟล์ ในบทเรียนนี้ เราจะพาคุณผ่านการใช้การทำงานแบบขนานเพื่อ **บีบอัดหลายไฟล์** อย่างมีประสิทธิภาพด้วย Aspose.Zip สำหรับ .NET

## คำตอบสั้น
- **การบีบอัดไฟล์แบบขนานคืออะไร?** เทคนิคที่บีบอัดหลายไฟล์พร้อมกันโดยใช้หลายคอร์ของ CPU เพื่อลดเวลาการประมวลผลโดยรวม  
- **ไลบรารีใดสนับสนุนใน .NET?** Aspose.Zip สำหรับ .NET มีตัวเลือกการบีบอัดแบบขนานในตัว  
- **ต้องมีลิขสิทธิ์หรือไม่?** มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **สามารถเพิ่มไฟล์ลงใน zip ระหว่างทำงานได้หรือไม่?** ใช่—ใช้ `Archive.CreateEntry` สำหรับแต่ละไฟล์ที่ต้องการรวม  
- **เข้ากันได้กับ .NET Core/5/6 หรือไม่?** แน่นอน, API ทำงานได้กับรันไทม์ .NET สมัยใหม่ทั้งหมด

## การบีบอัดไฟล์แบบขนานคืออะไร?
การบีบอัดไฟล์แบบขนานหมายถึงการแบ่งภาระการบีบอัดออกเป็นหลายเธรดหรือหลายคอร์, ทำให้หลายไฟล์ (หรือส่วนของไฟล์ขนาดใหญ่) ถูกบีบอัดพร้อมกัน วิธีนี้ช่วยลดเวลาที่ต้องใช้ในการสร้าง **zip archive c#** อย่างมากเมื่อเทียบกับการบีบอัดแบบต่อเนื่องแบบดั้งเดิม

## ทำไมต้องใช้ Aspose.Zip สำหรับการบีบอัดแบบขนาน?
- **ความเร็ว:** ใช้ประโยชน์เต็มที่จาก CPU แบบหลายคอร์  
- **ความสามารถขยาย:** จัดการกับชุดไฟล์ขนาดใหญ่โดยไม่เพิ่มเวลาการประมวลผลอย่างสัดส่วน  
- **ความง่าย:** API ระดับสูงทำให้ไม่ต้องจัดการความซับซ้อนของเธรด  
- **ความยืดหยุ่น:** ทำงานกับ .NET เวอร์ชันใดก็ได้และรวมเข้ากับโค้ดฐานที่มีอยู่ได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมี:

- ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET  
- ไลบรารี Aspose.Zip สำหรับ .NET ที่ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/zip/net/)**  
- ความเข้าใจเกี่ยวกับแนวคิดการบีบอัดไฟล์มาตรฐาน

## นำเข้า Namespaces

แรกเริ่ม, นำเข้า namespaces ที่จำเป็นเข้าสู่ไฟล์ C# ของคุณเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสที่ใช้จากที่ไหน

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ

กำหนดโฟลเดอร์ที่มีไฟล์ที่ต้องการบีบอัด ตัวแปร `dataDir` จะเก็บเส้นทางนี้

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เริ่มต้นกระบวนการบีบอัด

เปิดไฟล์ ZIP ใหม่สำหรับเขียน คำสั่ง `using` จะทำให้สตรีมไฟล์ถูกทำลายอย่างถูกต้องหลังจากทำงานเสร็จ

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## ขั้นตอนที่ 3: อ่านและบีบอัดไฟล์แบบขนาน

เปิดไฟล์ต้นฉบับแต่ละไฟล์ที่ต้องการเพิ่มลงใน archive ตัวอย่างนี้ใช้สองข้อความคลาสสิก, แต่คุณสามารถ **add files to zip** สำหรับจำนวนเอกสารใดก็ได้

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## ขั้นตอนที่ 4: สร้าง Archive Entries

สร้างอินสแตนซ์ `Archive` และเพิ่มแต่ละไฟล์เป็น entry แยกกัน นี่คือขั้นตอน **create zip archive c#** ที่เกิดขึ้น

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## ขั้นตอนที่ 5: กำหนดเกณฑ์การทำงานแบบขนาน

กำหนดการบีบอัดให้ทำงานแบบขนานโดยตั้งค่า `ParallelOptions` ธง `ParallelCompressInMemory` บอก Aspose.Zip ให้ใช้การประมวลผลแบบขนานเสมอ

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## ขั้นตอนที่ 6: บันทึก Archive ที่บีบอัดแล้ว

สุดท้าย, เขียน archive ลงดิสก์พร้อมตัวเลือกที่ต้องการ รวมถึงการเข้ารหัส, คอมเมนต์, และการตั้งค่าขนานที่กำหนดไว้ก่อนหน้า

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

ยินดีด้วย! คุณได้ทำ **การบีบอัดไฟล์แบบขนาน** ด้วย Aspose.Zip สำหรับ .NET แล้ว, โดย **บีบอัดหลายไฟล์** อย่างมีประสิทธิภาพลงใน archive เดียว

## ปัญหาที่พบบ่อย & เคล็ดลับ

- **ไฟล์ขนาดใหญ่:** หากพบปัญหา memory pressure, พิจารณาบีบอัดไฟล์เป็นชิ้นส่วนแทนการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ  
- **ความปลอดภัยของเธรด:** API ของ Aspose.Zip ปลอดภัยต่อเธรดในโหมดขนาน; อย่าแก้ไขสตรีมเดียวกันจากหลายเธรดนอกไลบรารี  
- **การปรับจูนประสิทธิภาพ:** ทดลองปรับค่า `ParallelOptions.MaxDegreeOfParallelism` หากต้องการจำกัดการใช้ CPU บนเซิร์ฟเวอร์ที่แชร์

## คำถามที่พบบ่อย

### Q1: สามารถใช้ Aspose.Zip สำหรับ .NET ร่วมกับไลบรารี .NET อื่นได้หรือไม่?

A1: ใช่, Aspose.Zip สำหรับ .NET ถูกออกแบบให้รวมกับไลบรารี .NET อื่นได้อย่างราบรื่น

### Q2: มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบหรือไม่?

A2: มี, คุณสามารถรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบจาก **[ที่นี่](https://purchase.aspose.com/temporary-license/)**

### Q3: จะหาแหล่งสนับสนุนเพิ่มเติมหรือถามคำถามได้ที่ไหน?

A3: เยี่ยมชม **[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37)** เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

### Q4: มีตัวอย่างหรือเอกสารเพิ่มเติมหรือไม่?

A4: สำรวจ **[เอกสาร Aspose.Zip](https://reference.aspose.com/zip/net/)** เพื่อดูตัวอย่างและเอกสารที่ครบถ้วน

### Q5: จะซื้อ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?

A5: คุณสามารถซื้อ Aspose.Zip สำหรับ .NET **[ที่นี่](https://purchase.aspose.com/buy)**

---

**อัปเดตล่าสุด:** 2025-12-10  
**ทดสอบกับ:** Aspose.Zip 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}