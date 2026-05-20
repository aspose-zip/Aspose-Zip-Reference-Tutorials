---
description: เรียนรู้วิธีการแตกไฟล์ RAR ไปยังโฟลเดอร์และถอดรหัสไฟล์ RAR ที่เข้ารหัสโดยใช้
  Aspose.Zip สำหรับ .NET ทำตามคู่มือขั้นตอนต่อขั้นตอนเพื่ออ่านไฟล์ RAR ที่เข้ารหัสและระบุรหัสผ่านของ
  RAR
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: แตกไฟล์ RAR ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แยกไฟล์ RAR ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

## Introduction

หากคุณต้องการ **extract RAR to folder** และทำงานกับไฟล์ที่มีการป้องกันด้วยรหัสผ่าน, Aspose.Zip สำหรับ .NET จะทำให้กระบวนการเป็นเรื่องง่าย ในบทเรียนนี้เราจะอธิบายขั้นตอนอย่างละเอียดเพื่ออ่านไฟล์ RAR ที่เข้ารหัส, ระบุรหัสผ่านของ RAR, และแยกเนื้อหาของไฟล์บีบอัดไปยังไดเรกทอรีเป้าหมาย ไม่ว่าคุณจะสร้างยูทิลิตี้บนเดสก์ท็อปหรือบริการฝั่งเซิร์ฟเวอร์, คุณจะได้เห็นวิธีผสานตรรกะการถอดรหัสอย่างรวดเร็วและเชื่อถือได้

## Quick Answers
- **What does “extract RAR to folder” mean?** หมายถึงการเปิดไฟล์ RAR แล้วเขียนแต่ละรายการไปยังไดเรกทอรีที่กำหนดบนดิสก์  
- **Which library handles decryption?** Aspose.Zip สำหรับ .NET มีการสนับสนุนในตัวสำหรับไฟล์ RAR ที่เข้ารหัส  
- **Do I need a license for testing?** มีใบอนุญาตชั่วคราวสำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+  
- **How long does the implementation take?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับสถานการณ์การแยกไฟล์พื้นฐาน

## What is “extract RAR to folder”?
การแยกไฟล์ RAR ไปยังโฟลเดอร์หมายถึงการแตกไฟล์ทุกไฟล์ที่เก็บอยู่ในอาร์ไคฟ์และวางไว้ในไดเรกทอรีที่คุณเลือก เมื่อไฟล์บีบอัดถูกเข้ารหัส, คุณต้องระบุรหัสผ่านที่ถูกต้องก่อนการแยกจะดำเนินการได้

## Why use Aspose.Zip to extract encrypted RAR?
Aspose.Zip จัดการความซับซ้อนของรูปแบบ RAR, รองรับทั้งไฟล์มาตรฐานและไฟล์ที่เข้ารหัสโดยไม่ต้องพึ่งพาไลบรารีภายนอก มันมี API แบบวัตถุที่สะอาด, ประสิทธิภาพสูง, และการจัดการข้อผิดพลาดที่ดี—เหมาะสำหรับนักพัฒนา .NET ที่ต้องการโซลูชันที่เชื่อถือได้สำหรับ **how to decrypt RAR** files

## Prerequisites

ก่อนเริ่มบทเรียน, โปรดตรวจสอบว่าคุณมีเงื่อนไขต่อไปนี้พร้อมใช้งาน:

1. Aspose.Zip for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Zip ในโปรเจกต์ .NET ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)

2. Document Directory: ตั้งค่าไดเรกทอรีที่เก็บไฟล์ RAR ที่เข้ารหัสของคุณ แทนที่ "Your Document Directory" ในโค้ดตัวอย่างด้วยพาธจริงของไดเรกทอรีนั้น

## Import Namespaces

เริ่มต้นด้วยการนำเข้า namespace ที่จำเป็นเพื่อใช้ไลบรารี Aspose.Zip อย่างมีประสิทธิภาพ เพิ่มบรรทัดต่อไปนี้ที่ส่วนหัวของไฟล์ .NET ของคุณ:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Step 1 – Open the Encrypted RAR Archive

เปิดสตรีมแบบอ่าน‑อย่างเดียวสำหรับไฟล์ RAR ที่เข้ารหัส นี่เป็นการเตรียมไฟล์สำหรับการถอดรหัสและการแยก

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Step 2 – Specify the RAR Password (how to decrypt RAR)

สร้างอินสแตนซ์ `RarArchive` และบอก Aspose.Zip ว่ารหัสผ่านที่ป้องกันไฟล์บีบอัดคืออะไร แทนที่ `"p@s$"` ด้วยรหัสผ่านจริงที่คุณใช้เมื่อสร้างไฟล์ RAR ที่เข้ารหัส

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Step 3 – Extract Contents to a Folder (extract encrypted RAR)

สุดท้าย, แยกทุกรายการไปยังโฟลเดอร์ที่คุณเลือก การทำเช่นนี้จะเสร็จสิ้นการดำเนินการ **extract RAR to folder**

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

ทำซ้ำขั้นตอนเหล่านี้สำหรับแต่ละไฟล์ RAR ที่ต้องการถอดรหัส เพื่อให้การผสาน Aspose.Zip สำหรับ .NET เข้ากับโปรเจกต์ของคุณเป็นไปอย่างราบรื่น

## Common Pitfalls & Tips

- **Incorrect password** – หากรหัสผ่านไม่ถูกต้อง, Aspose.Zip จะโยน `WrongPasswordException` ตรวจสอบสตริงที่ส่งให้ `DecryptionPassword` อีกครั้ง
- **Large archives** – สำหรับไฟล์ RAR ขนาดใหญ่มาก, ควรแยกไฟล์ไปยังโฟลเดอร์ชั่วคราวก่อนแล้วค่อยย้ายไปยังตำแหน่งสุดท้ายเพื่อหลีกเลี่ยงการเต็มพื้นที่ดิสก์
- **Path safety** – ตรวจสอบ `dataDir` และพาธผลลัพธ์เสมอเพื่อป้องกันช่องโหว่การเดินทางไดเรกทอรี (directory‑traversal)

## Conclusion

ขอแสดงความยินดี! คุณได้ **extract RAR to folder** สำเร็จและเรียนรู้วิธี **read encrypted RAR file** ด้วย Aspose.Zip สำหรับ .NET ไลบรารีที่ทรงพลังนี้ทำให้กระบวนการปลดล็อกไฟล์ที่ป้องกันด้วยรหัสผ่านเป็นเรื่องง่ายและเป็นเครื่องมือที่ขาดไม่ได้สำหรับนักพัฒนาที่ทำงานกับแอปพลิเคชัน .NET

## Frequently Asked Questions (FAQs)

### Is Aspose.Zip for .NET compatible with all RAR archive versions?
Aspose.Zip สำหรับ .NET รองรับหลายเวอร์ชันของไฟล์ RAR, ทำให้เข้ากันได้กับไฟล์หลากหลายประเภท

### Can I use Aspose.Zip for .NET in commercial projects?
ได้, Aspose.Zip สำหรับ .NET สามารถใช้ในโครงการเชิงพาณิชย์ได้ เยี่ยมชม [purchase page](https://purchase.aspose.com/buy) เพื่อดูรายละเอียดการรับใบอนุญาต

### Are temporary licenses available for testing purposes?
ใช่, คุณสามารถรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้จาก [here](https://purchase.aspose.com/temporary-license/)

### Where can I find additional support or community discussions?
เยี่ยมชม [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) เพื่อรับการสนับสนุนและเข้าร่วมการสนทนาชุมชน

### How do I access the documentation for Aspose.Zip for .NET?
ดูข้อมูลครบถ้วนใน [documentation](https://reference.aspose.com/zip/net/)

**Additional Q&A**

**Q:** How can I extract only specific files from an encrypted RAR?  
**A:** ใช้ `RarArchiveEntry` เพื่อค้นหาเอนทรีที่ต้องการและเรียก `ExtractToFile` โดยที่รหัสผ่านการถอดรหัสได้ถูกตั้งค่าไว้บนอาร์ไคฟ์แล้ว

**Q:** What if I need to change the output folder name dynamically?  
**A:** สร้างพาธผลลัพธ์ด้วย `Path.Combine` และตัวแปร runtime ใด ๆ ก่อนเรียก `ExtractToDirectory`

**Q:** Does Aspose.Zip support multi‑volume RAR archives?  
**A:** ใช่, ไลบรารีสามารถเปิดและแยกไฟล์ RAR แบบหลายโวลุ่มได้ ตราบใดที่ทุกส่วนสามารถเข้าถึงได้

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}