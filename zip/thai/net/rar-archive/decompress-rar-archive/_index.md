---
date: 2025-12-23
description: เรียนรู้วิธีการแยกไฟล์ RAR ใน .NET ด้วย Aspose.Zip คู่มือขั้นตอนต่อขั้นตอนในการแตกไฟล์
  RAR, แยกไฟล์ RAR ไปยังโฟลเดอร์, และอ่านไฟล์ RAR ด้วย C#
linktitle: Decompressing a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีแยกไฟล์ RAR ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/rar-archive/decompress-rar-archive/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ RAR ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในการพัฒนา .NET การรู้ **วิธีการแยกไฟล์ RAR** อย่างรวดเร็วสามารถช่วยประหยัดเวลาและทำให้การจัดการไฟล์ง่ายขึ้น Aspose.Zip สำหรับ .NET มี API ที่ใช้งานง่ายเพื่อ **แตกไฟล์ RAR**, **แยกไฟล์ RAR ไปยังโฟลเดอร์**, และแม้กระทั่ง **อ่านไฟล์ RAR ด้วย C#** คู่มือฉบับนี้จะพาคุณผ่านแต่ละขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการแยกไฟล์ลงดิสก์.

## คำตอบสั้น
- **ไลบรารีใดที่รองรับการแยกไฟล์ RAR ใน .NET?** Aspose.Zip for .NET.  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัดเพื่อแยกไฟล์ RAR?** ประมาณ 10 บรรทัด รวมการตั้งค่า.  
- **ฉันสามารถแยกไฟล์ RAR ไปยังโฟลเดอร์เฉพาะได้หรือไม่?** ใช่, ใช้ `ExtractToDirectory` เพื่อระบุโฟลเดอร์ปลายทาง.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในเชิงพาณิชย์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มบทเรียนนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

- Visual Studio: ตรวจสอบว่าคุณมีการติดตั้ง Visual Studio ที่ทำงานได้, เนื่องจากเราจะใช้มันในการเขียนและรันโค้ด .NET ของเรา.  
- Aspose.Zip for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Zip for .NET คุณสามารถหาได้จาก [here](https://releases.aspose.com/zip/net/).  
- Resource Directory: สร้างไดเรกทอรีบนระบบของคุณเพื่อเก็บทรัพยากรที่จำเป็นสำหรับบทเรียนนี้ ซึ่งจะถูกอ้างอิงเป็น "Your Document Directory" ในตัวอย่างโค้ด.  
- RAR Archive: เตรียมไฟล์ RAR ที่คุณต้องการแตกสำหรับบทเรียนนี้ คุณสามารถใช้ไฟล์ของคุณเองหรือหาไฟล์ทดสอบได้.

## นำเข้า Namespaces

ก่อนจะลงลึกในโค้ด, ให้แน่ใจว่าเราได้ทำการนำเข้า namespaces ที่จำเป็นแล้ว:

```csharp
using System.IO;
using Aspose.Zip;
using Aspose.Zip.Rar;
```

## ขั้นตอนที่ 1: ตั้งค่า Resource Directory (c# extract rar archive)

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เปิดไฟล์ RAR Archive

```csharp
//ExStart: DecompressRarArchive
using (FileStream fs = File.OpenRead(dataDir + "your_archive.rar"))
{
    using (RarArchive archive = new RarArchive(fs))
    {
        // Rest of the code goes here.
    }
}
//ExEnd: DecompressRarArchive 
```

## ขั้นตอนที่ 3: แยกไฟล์ไปยัง Directory (extract rar to folder)

```csharp
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
```

ในสามขั้นตอนง่าย ๆ นี้ คุณได้ **แตกไฟล์ RAR** อย่างสำเร็จโดยใช้ Aspose.Zip สำหรับ .NET! อย่าลืมปรับเปลี่ยนเส้นทางไฟล์และชื่อไฟล์ให้ตรงกับการตั้งค่าของคุณ.

## ทำไมเรื่องนี้สำคัญ

การแยกไฟล์ RAR ด้วยโปรแกรมเป็นความต้องการทั่วไปเมื่อทำการนำเข้าข้อมูลเป็นชุด, การสร้างรายงานอัตโนมัติ, หรือการย้ายเนื้อหา โดยการใช้ Aspose.Zip คุณจะหลีกเลี่ยงการพึ่งพาไลบรารีภายนอกและทำให้กระบวนการทั้งหมดอยู่ภายในโซลูชัน .NET ของคุณ.

## สรุป

ขอแสดงความยินดี! คุณได้เพิ่มเครื่องมือที่มีคุณค่าเข้าสู่ชุดเครื่องมือการเขียนโปรแกรมของคุณโดยเชี่ยวชาญการ **วิธีการแยกไฟล์ RAR** ด้วย Aspose.Zip สำหรับ .NET อย่าลังเลที่จะสำรวจคุณลักษณะและฟังก์ชันเพิ่มเติมที่ Aspose.Zip สำหรับ .NET มีให้ใน [documentation](https://reference.aspose.com/zip/net/).

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET กับรูปแบบไฟล์อาร์ไคฟ์อื่นได้หรือไม่?
ในขณะนี้ Aspose.Zip สำหรับ .NET รองรับรูปแบบไฟล์ ZIP และ RAR เป็นหลัก.

### มีรุ่นทดลองให้ใช้หรือไม่?
ใช่, คุณสามารถรับรุ่นทดลองฟรีได้จาก [here](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนจากชุมชนได้อย่างไร?
เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชน.

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?
ใช่, คุณสามารถซื้อไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy).

### มีไลเซนส์ชั่วคราวหรือไม่?
ใช่, คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

## คำถามที่พบบ่อย

**Q:** ฉันจะอ่านไฟล์ RAR ด้วย C# โดยไม่ต้องแยกไฟล์อย่างไร?  
**A:** คุณสามารถ enumerate entries ด้วย `RarArchive` และอ่านสตรีมโดยตรง, แต่แนะนำให้ทำการแยกไฟล์เต็มรูปแบบสำหรับสถานการณ์ส่วนใหญ่.

**Q:** ถ้าไฟล์ RAR ถูกป้องกันด้วยรหัสผ่านจะทำอย่างไร?  
**A:** ปัจจุบัน Aspose.Zip ไม่รองรับไฟล์ RAR ที่เข้ารหัส; คุณต้องถอดรหัสไฟล์ก่อนใช้งาน.

**Q:** ฉันสามารถแยกไฟล์ RAR หลายไฟล์ในลูปได้หรือไม่?  
**A:** ใช่, ให้ใส่ตรรกะการแยกไฟล์ไว้ในลูป `foreach` ที่วนผ่านรายการไฟล์ของคุณ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบกับ:** Aspose.Zip for .NET 24.11 (latest)  
**ผู้เขียน:** Aspose