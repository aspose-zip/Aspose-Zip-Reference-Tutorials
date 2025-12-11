---
date: 2025-12-10
description: ปลดล็อกศักยภาพของ Aspose.Zip สำหรับ .NET! เรียนรู้วิธีการแตกโฟลเดอร์อย่างง่ายดายด้วยคู่มือขั้นตอนนี้
  ดำดิ่งสู่โลกของการบีบอัดและการสกัดที่ราบรื่น
linktitle: Decompress Compressed Folder to Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: แตกโฟลเดอร์ที่บีบอัดเป็นไดเรกทอรีใน Aspose.Zip สำหรับ .NET
url: /th/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ ZIP ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ยินดีต้อนรับสู่โลกของ Aspose.Zip สำหรับ .NET, ไลบรารีที่แข็งแกร่งซึ่งช่วยให้นักพัฒนาจัดการโฟลเดอร์ที่บีบอัดได้อย่างง่ายดาย หากคุณกำลังสงสัย **how to extract zip** ไฟล์ใน .NET, คู่มือนี้ครอบคลุมทุกอย่าง ในบทเรียนนี้ เราจะเจาะลึกกระบวนการแตกโฟลเดอร์ที่บีบอัดไปยังไดเรกทอรีโดยใช้ Aspose.Zip สำหรับ .NET เตรียมพร้อมเดินตามขั้นตอนอย่างละเอียดเพื่อทำความเข้าใจเครื่องมือที่ทรงพลังนี้

## คำตอบอย่างรวดเร็ว
- **What is the primary purpose of Aspose.Zip?** เพื่อสร้าง, อ่าน, และแยกไฟล์ ZIP archive ในแอปพลิเคชัน .NET.  
- **How to extract zip** with a password? ใช้ `ArchiveLoadOptions` กับ property `DecryptionPassword`.  
- **Can I unzip encrypted archive** without a password? ไม่ – คุณต้องระบุรหัสผ่านที่ถูกต้อง.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is a license required for production?** ใช่, จำเป็นต้องมีใบอนุ้งานเชิงพาณิชย์.

## อะไรคือ **how to extract zip**?
การแยกไฟล์ ZIP หมายถึงการอ่านข้อมูลที่บีบอัดและเขียนไฟล์ต้นฉบับไปยังไดเรกทอรีเป้าหมาย Aspose.Zip จะซ่อนรายละเอียดระดับต่ำ ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจแทนการจัดการ archive.

## ทำไมต้องใช้ Aspose.Zip สำหรับงาน **how to unzip folder**?
- **Straightforward API** – โค้ดขั้นต่ำสำหรับเปิด, ถอดรหัส, และแยก archive.  
- **Supports encrypted archives** – เหมาะสำหรับการแลกเปลี่ยนข้อมูลที่ปลอดภัย.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core/.NET 5+.  
- **No external dependencies** – ไม่จำเป็นต้องติดตั้งยูทิลิตี้ zip แบบเนทีฟ.

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มการเดินทางนี้, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.Zip for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/).

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ, ให้ import namespaces ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

ตอนนี้, เราจะแบ่งตัวอย่างที่ให้มาเป็นหลายขั้นตอนเพื่อความเข้าใจที่ครอบคลุม.

## วิธี **unzip folder** – คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: เปิดโฟลเดอร์ที่บีบอัด

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

เริ่มต้นด้วยการเปิดโฟลเดอร์ที่บีบอัดโดยใช้ `FileStream`. ปรับเส้นทางไฟล์ให้สอดคล้องกับโครงสร้างของโปรเจกต์ของคุณ.

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ Archive (ถอดรหัส ZIP)

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

สร้างอ็อบเจ็กต์ `Archive` โดยส่งสตรีม `zipFile` และให้ตัวเลือกการโหลดเพิ่มเติม เช่น รหัสผ่านการถอดรหัสในกรณีนี้ นี่คือขั้นตอนสำคัญเมื่อคุณต้องการ **unzip encrypted archive** ไฟล์.

### ขั้นตอนที่ 3: แยกไฟล์ไปยังไดเรกทอรี

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

สุดท้าย, ใช้เมธอด `ExtractToDirectory` เพื่อแตกและแยกเนื้อหาของโฟลเดอร์ที่บีบอัดไปยังไดเรกทอรีที่ระบุ ขั้นตอนนี้เสร็จสิ้นกระบวนการ **how to decompress zip**.

ทำซ้ำขั้นตอนเหล่านี้สำหรับโฟลเดอร์ที่บีบอัดอื่น ๆ เพื่อให้การผสานกับ Aspose.Zip สำหรับ .NET เป็นไปอย่างราบรื่น.

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **Incorrect password** – หากรหัสผ่านการถอดรหัสไม่ถูกต้อง, Aspose.Zip จะโยนข้อยกเว้นการตรวจสอบสิทธิ์ ตรวจสอบรหัสผ่านอีกครั้ง.  
- **Path not found** – ตรวจสอบให้แน่ใจว่าไดเรกทอรีเป้าหมายมีอยู่หรือให้ `ExtractToDirectory` สร้างโดยอัตโนมัติ.  
- **Large archives** – สำหรับไฟล์ ZIP ขนาดใหญ่มาก, พิจารณาแยกเป็นชิ้นส่วนหรือใช้ streaming API เพื่อลดภาระหน่วยความจำ.

## คำถามที่พบบ่อย

**Q: Is Aspose.Zip for .NET compatible with various compression formats?**  
A: ใช่, Aspose.Zip for .NET รองรับรูปแบบการบีบอัดที่นิยมเช่น ZIP, GZIP, และอื่น ๆ.

**Q: Can I use Aspose.Zip for .NET in both commercial and non‑commercial projects?**  
A: แน่นอน, คุณสามารถใช้ Aspose.Zip for .NET ได้ทั้งในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์.

**Q: Is there a free trial available for Aspose.Zip for .NET?**  
A: ใช่, คุณสามารถสำรวจคุณสมบัติต่าง ๆ ด้วยการทดลองใช้งานฟรีโดยไปที่ [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Zip for .NET?**  
A: ขอความช่วยเหลือจากชุมชน Aspose.Zip ที่ [support forum](https://forum.aspose.com/c/zip/37).

**Q: Do I need a temporary license for testing Aspose.Zip for .NET?**  
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวจาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบ.

---

**Last Updated:** 2025-12-10  
**Tested With:** ทดสอบกับ: Aspose.Zip for .NET (รุ่นล่าสุด)  
**Author:** ผู้เขียน: Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}