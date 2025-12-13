---
date: 2025-12-13
description: เรียนรู้วิธีการแตกไฟล์ zip และจัดการหลายรายการ zip ด้วย Aspose.Zip สำหรับ
  .NET. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดการไฟล์ที่มีประสิทธิภาพ.
linktitle: Decompressing Multiple Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีการแตกไฟล์ ZIP ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/file-decompression/decompress-multiple-files/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ ZIP ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ยินดีต้อนรับสู่บทแนะนำอย่างละเอียดของเราว่า **how to extract zip** ด้วย Aspose.Zip สำหรับ .NET! หากคุณต้องการจัดการไฟล์บีบอัดที่มีหลายรายการอย่างมีประสิทธิภาพ คุณมาถูกที่แล้ว ในคู่มือนี้เราจะพาคุณผ่านทุกขั้นตอนที่คุณต้องการ—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการแยกแต่ละรายการ—เพื่อให้คุณเชี่ยวชาญการแยกหลายรายการ zip อย่างมั่นใจ.

## คำตอบสั้นๆ
- **ไลบรารีที่ดีที่สุดสำหรับการแยก zip ใน .NET คืออะไร?** Aspose.Zip for .NET  
- **สามารถแยกหลายรายการ zip พร้อมกันได้หรือไม่?** ใช่, โดยใช้ Archive API คุณสามารถวนลูปผ่านแต่ละรายการได้.  
- **ต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Zip ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่แบบทดลอง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **มีการทดลองใช้ฟรีหรือไม่?** แน่นอน – ดาวน์โหลดจากเว็บไซต์ของ Aspose.

## “how to extract zip” คืออะไรในโลก .NET?

การแยกไฟล์ ZIP หมายถึงการอ่านไฟล์บีบอัด, ค้นหารายการแต่ละรายการ, และเขียนข้อมูลที่ไม่ได้บีบอัดของแต่ละรายการไปยังโฟลเดอร์หรือสตรีมปลายทาง Aspose.Zip ให้ API ที่ไหลลื่นและมีประสิทธิภาพสูงซึ่งซ่อนรายละเอียดระดับต่ำไว้ ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจได้

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET?

- **Robust performance** – จัดการไฟล์อาร์ไคฟ์ขนาดใหญ่ด้วยการใช้หน่วยความจำน้อยที่สุด.  
- **Full .NET support** – ทำงานกับ .NET Framework, .NET Core, และ .NET 5+.  
- **Advanced features** – การติดตามความคืบหน้า, การป้องกันด้วยรหัสผ่าน, และการแยกระดับรายการ.  
- **No external dependencies** – โค้ดที่จัดการโดยบริหารทั้งหมด, ไม่ต้องใช้ DLL แบบเนทีฟ.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในบทแนะนำ, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- **Aspose.Zip for .NET** – ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Zip สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/zip/net/).  
- **Document Directory** – ตั้งค่าไดเรกทอรีที่เก็บเอกสารของคุณ คุณจะใช้ไดเรกทอรีนี้เป็นไดเรกทอรีฐานในโค้ด.

ตอนนี้, มาเริ่มต้นด้วยคู่มือขั้นตอนต่อขั้นตอนกันเถอะ.

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ, เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นสำหรับ Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้าง ZIP Archive แบบ .NET (ไม่บังคับ)

หากคุณมีไฟล์ ZIP อยู่แล้วคุณสามารถข้ามขั้นตอนนี้ได้ มิฉะนั้น การสร้าง zip archive ด้วย .NET นั้นง่ายและช่วยสาธิตกระบวนการแยกไฟล์อย่างเต็มรูปแบบ.

```csharp
string dataDir = "Your Document Directory";

// Run the compression method
CompressMultipleFiles.Run();
```

## ขั้นตอนที่ 2: แตกไฟล์ (How to Extract ZIP)

### ขั้นตอน 2.1: เปิดไฟล์ที่บีบอัด

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### ขั้นตอน 2.2: แสดงรายการและติดตามความคืบหน้า (Extract Multiple ZIP Entries)

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### ขั้นตอน 2.3: แยกรายการแรก

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Read and write data from decompressed stream to the extracting file.
    }
}
```

### ขั้นตอน 2.4: แยกรายการที่สอง

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

และนั่นแหละ! คุณได้ **แยกหลายรายการ zip** อย่างสำเร็จโดยใช้ Aspose.Zip สำหรับ .NET.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่มีไฟล์ผลลัพธ์ที่สร้าง** | เส้นทาง `dataDir` ผิดหรือไม่มีสิทธิ์การเขียน | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์การเขียน |
| **ความคืบหน้าแสดงเป็น 0%** | ขนาดรายการรายงานเป็น 0 (ไฟล์ว่าง) | ตรวจสอบว่า ZIP ต้นทางมีข้อมูลจริง; สร้างอาร์ไคฟ์ใหม่หากจำเป็น |
| **ข้อยกเว้นเมื่อจัดการอาร์ไคฟ์ขนาดใหญ่** | หน่วยความจำไม่เพียงพอ | ใช้ `ArchiveLoadOptions` พร้อม `ReadOnly = true` เพื่อสตรีมรายการแทนการโหลดทั้งหมดพร้อมกัน |

## คำถามที่พบบ่อย (Aspose.Zip Tutorial)

**Q1: สามารถใช้ Aspose.Zip สำหรับ .NET ในโครงการเชิงพาณิชย์และส่วนบุคคลได้หรือไม่?**  
A1: ใช่, Aspose.Zip สำหรับ .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และส่วนบุคคล สำหรับรายละเอียดการให้ลิขสิทธิ์ ดูที่ [Aspose's licensing information](https://purchase.aspose.com/buy).

**Q2: มีการทดลองใช้ฟรีสำหรับ Aspose.Zip สำหรับ .NET หรือไม่?**  
A2: ใช่, คุณสามารถสำรวจการทดลองใช้ฟรีของ Aspose.Zip สำหรับ .NET ได้จาก [here](https://releases.aspose.com/zip/net).

**Q3: จะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
A3: เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

**Q4: จะซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร?**  
A4: รับไลเซนส์ชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้จาก [here](https://purchase.aspose.com/temporary-license/).

**Q5: มีข้อกำหนดระบบเฉพาะสำหรับการใช้ Aspose.Zip สำหรับ .NET หรือไม่?**  
A5: ดูที่ [documentation](https://reference.aspose.com/zip/net/) สำหรับข้อกำหนดระบบโดยละเอียด.

## สรุป

ในบทแนะนำนี้เราได้ครอบคลุม **how to extract zip** ไฟล์, แสดงการแยกหลายรายการ zip, และเน้นแนวปฏิบัติที่ดีที่สุดสำหรับการใช้ API ที่ทรงพลังของ Aspose.Zip ด้วยการทำตามขั้นตอนเหล่านี้คุณสามารถจัดการอาร์ไคฟ์ ZIP อย่างมีประสิทธิภาพในแอปพลิเคชัน .NET ใดก็ได้ ไม่ว่าจะเป็นการสร้างเครื่องมือเดสก์ท็อป, บริการเว็บ, หรือโปรเซสเซอร์แบบแบตช์อัตโนมัติ

---

**อัปเดตล่าสุด:** 2025-12-13  
**ทดสอบด้วย:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}