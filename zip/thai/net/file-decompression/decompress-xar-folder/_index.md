---
date: 2025-12-17
description: เรียนรู้วิธีการแยกไฟล์ Xar และแตกไฟล์ Xar ไปยังโฟลเดอร์โดยใช้ Aspose.Zip
  สำหรับ .NET. ทำตามคู่มือแบบทีละขั้นตอนนี้.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีแยกไฟล์ Xar ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET
url: /th/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ Xar ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณเป็นนักพัฒนา .NET ที่กำลังมองหาวิธีที่เชื่อถือได้ **how to extract xar**, Aspose.Zip สำหรับ .NET มี API ที่สะอาดและมีประสิทธิภาพสูง ในบทเรียนนี้เราจะอธิบายขั้นตอนทั้งหมดของการแตกไฟล์ Xar ไปยังโฟลเดอร์, อธิบายว่าทำไมวิธีนี้จึงช่วยประหยัดเวลา, และแสดงโค้ดที่คุณต้องใช้

## คำตอบอย่างรวดเร็ว
- **What does the library do?** มันอ่านและแยกไฟล์ Xar โดยไม่ต้องใช้เครื่องมือภายนอก.  
- **Which .NET versions are supported?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Do I need a license?** ทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **How long does implementation take?** ปกติใช้เวลาน้อยกว่า 10 นาที.  
- **Can I extract to a custom folder?** ใช่—เพียงระบุเส้นทางเป้าหมายใน `ExtractToDirectory`.

## “how to extract xar” คืออะไร?
การแยกไฟล์ Xar หมายถึงการอ่านแพคเกจที่บีบอัดและเขียนไฟล์ภายในไปยังไดเรกทอรีบนดิสก์ สิ่งนี้มีประโยชน์เมื่อคุณได้รับแพคเกจ XAR จากตัวติดตั้ง macOS, เครื่องมือสำรองข้อมูล, หรือเครื่องมือของบุคคลที่สามและต้องการประมวลผลเนื้อหาในแอปพลิเคชัน .NET

## ทำไมต้องใช้ Aspose.Zip สำหรับงานนี้?
- **Zero external dependencies** – .NET แท้, ไม่มีไบนารีเนทีฟ.  
- **Stream‑based API** – ทำงานกับไฟล์, สตรีมหน่วยความจำ, หรือสตรีมเครือข่าย.  
- **Robust error handling** – ข้อยกเว้นที่ละเอียดช่วยคุณแก้ไขปัญหาไฟล์อัดที่เสียหาย.  
- **Full .NET compatibility** – ทำงานบน Windows, Linux, และ macOS runtimes.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Zip for .NET** – รวมไว้ในโปรเจคของคุณ คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/zip/net/).
- **Document Directory** – โฟลเดอร์ในโซลูชันของคุณที่ไฟล์ตัวอย่าง `.xar` และผลลัพธ์ที่แยกจะถูกเก็บไว้.

## นำเข้า Namespaces

ในโปรเจค .NET ของคุณ, ให้รวม namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## ขั้นตอนที่ 1: กำหนด Document Directory ของคุณ

แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบ absolute หรือ relative ที่มี `sample.xar` และที่คุณต้องการให้โฟลเดอร์ผลลัพธ์ถูกสร้างขึ้น.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: แตกไฟล์ Xar Archive

โค้ดส่วนนี้เปิดไฟล์ Xar, สร้างอินสแตนซ์ `XarArchive`, และแยก **the entire decompress xar archive** ไปยัง `DecompressXar_out`. การดำเนินการเป็นแบบ stream‑based อย่างเต็มที่, ทำให้ทำงานได้อย่างมีประสิทธิภาพแม้กับแพคเกจขนาดใหญ่.

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

## ขั้นตอนที่ 3: รันโค้ด

สร้างและรันแอปพลิเคชันของคุณ หลังจากการทำงานเสร็จ, คุณจะพบโฟลเดอร์ใหม่ชื่อ `DecompressXar_out` ภายใน document directory ของคุณ, ซึ่งบรรจุไฟล์ทั้งหมดที่ถูกบรรจุในไฟล์ `.xar` ดั้งเดิม.

## ปัญหาทั่วไป & เคล็ดลับ

- **File not found** – ตรวจสอบให้แน่ใจว่าเส้นทางใน `File.OpenRead` ชี้ไปยัง `sample.xar` อย่างถูกต้อง ใช้ `Path.Combine` เพื่อจัดการเส้นทางอย่างปลอดภัย.  
- **Access denied** – รันแอปพลิเคชันด้วยสิทธิ์ไฟล์ระบบที่เพียงพอ, โดยเฉพาะเมื่อเขียนไปยังไดเรกทอรีที่ได้รับการป้องกัน.  
- **Corrupted archive** – Aspose.Zip จะโยน `InvalidDataException`; ตรวจสอบว่าไฟล์ `.xar` ต้นฉบับสมบูรณ์.

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับเวอร์ชันล่าสุดของ .NET framework หรือไม่?**  
A: ใช่, Aspose.Zip มีการอัปเดตเป็นประจำเพื่อให้เข้ากันได้กับเวอร์ชันล่าสุดของ .NET framework. ดูที่ [documentation](https://reference.aspose.com/zip/net/) สำหรับรายละเอียดเฉพาะ.

**Q: ฉันสามารถทดลองใช้ Aspose.Zip ก่อนซื้อได้หรือไม่?**  
A: แน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จาก [here](https://releases.aspose.com/).

**Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.Zip ได้อย่างไร?**  
A: สำหรับคำถามหรือความช่วยเหลือใด ๆ, เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Zip หรือไม่?**  
A: ใช่, สามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถซื้อ Aspose.Zip สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถซื้อ Aspose.Zip สำหรับ .NET ได้จาก [here](https://purchase.aspose.com/buy).

**Q: ฉันสามารถแยกไฟล์เฉพาะจาก Xar archive ได้หรือไม่?**  
A: ใช่—ใช้ `archive.Entries` เพื่อวนรายการและเรียก `ExtractToFile` กับรายการที่เลือก.

**Q: ไลบรารีนี้รองรับไฟล์ Xar ที่มีการป้องกันด้วยรหัสผ่านหรือไม่?**  
A: ในขณะนี้, Xar archive ไม่รองรับการเข้ารหัส; หากคุณเจอไฟล์ที่ถูกป้องกัน, คุณต้องถอดรหัสก่อนใช้ Aspose.Zip.

---

**อัปเดตล่าสุด:** 2025-12-17  
**ทดสอบด้วย:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}