---
date: 2026-06-04
description: เรียนรู้วิธีการแยกไฟล์ zip ไปยังโฟลเดอร์โดยใช้ Aspose.Zip for .NET รวมถึงไฟล์ที่มีการป้องกันด้วยรหัสผ่านและการแยกไฟล์
  zip ที่เข้ารหัส
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: แยก zip ไปยังโฟลเดอร์
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีการแยกไฟล์ zip ไปยังโฟลเดอร์ด้วย Aspose.Zip for .NET
url: /th/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกไฟล์ zip ไปยังโฟลเดอร์ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

หากคุณต้องการ **extract zip to folder** อย่างรวดเร็วและเชื่อถือได้ในแอปพลิเคชัน .NET, Aspose.Zip สำหรับ .NET จะมอบ API ที่สะอาดและข้ามแพลตฟอร์มที่จัดการกับไฟล์เก็บข้อมูลแบบธรรมดาและเข้ารหัสได้อย่างเท่าเทียม ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่คุณต้องการ—ตั้งแต่การตั้งค่าห้องสมุดจนถึงการแยกไฟล์ ZIP ที่มีการป้องกันด้วยรหัสผ่าน—เพื่อให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจของคุณแทนการจัดการไฟล์เก็บข้อมูลระดับต่ำ

## คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักของ Aspose.Zip คืออะไร?** To create, read, and **extract zip to folder** in .NET applications.  
- **ฉันจะทำการ extract zip ด้วยรหัสผ่านอย่างไร?** Pass the password via `ArchiveLoadOptions.DecryptionPassword`.  
- **ฉันสามารถ unzip ไฟล์ที่เข้ารหัสโดยไม่ต้องใช้รหัสผ่านได้หรือไม่?** ไม่—Aspose.Zip requires the correct password to open encrypted archives.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่, a valid Aspose.Zip license is needed for commercial use.

## **extract zip to folder** คืออะไร?

การแยกไฟล์ ZIP หมายถึงการอ่านข้อมูลที่บีบอัดและเขียนไฟล์ต้นฉบับไปยังไดเรกทอรีเป้าหมายบนดิสก์ Aspose.Zip แยกรายละเอียดระดับต่ำออก ทำให้คุณสามารถเรียกใช้เมธอดเดียวเพื่อทำการทั้งหมดนี้ได้พร้อมกับรองรับ **30+ archive formats** และจัดการไฟล์ขนาดสูงสุด **2 GB** โดยไม่ต้องโหลดไฟล์เก็บทั้งหมดเข้าสู่หน่วยความจำ

## ทำไมต้องใช้ Aspose.Zip สำหรับงาน **how to unzip zip** ?

Aspose.Zip มี API ที่ตรงไปตรงมาซึ่งทำให้คุณสามารถ unzip ไฟล์ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด รองรับไฟล์ที่มีการป้องกันด้วยรหัสผ่านและไฟล์ที่เข้ารหัสแบบ AES และทำงานบน Windows, Linux, และ macOS มันประมวลผล **500‑page ZIP archives in under 2 seconds** บนเซิร์ฟเวอร์ทั่วไป ลดความจำเป็นในการใช้ยูทิลิตี้ zip แบบดั้งเดิมและลดความซับซ้อนของการปรับใช้

## ข้อกำหนดเบื้องต้น

- Aspose.Zip for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/).
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, หรือ IDE ใด ๆ ที่คุณต้องการ).
- (Optional) ไฟล์ ZIP ที่ป้องกันด้วยรหัสผ่าน หากคุณต้องการลอง **extract zip with password**.

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ ให้นำเข้า namespaces ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

ตอนนี้เรามาแยกกระบวนการแยกไฟล์เป็นขั้นตอนกัน

## วิธีการ **extract zip to folder** – คู่มือขั้นตอน

โหลดไฟล์ ZIP ของคุณ, หากต้องการให้ระบุรหัสผ่านการถอดรหัส, แล้วเรียก `ExtractToDirectory` – นั่นคือกระบวนการแยกไฟล์ที่สมบูรณ์ในสามขั้นตอนสั้น ๆ API จะสร้างโฟลเดอร์ปลายทางโดยอัตโนมัติหากยังไม่มี และจะสตรีมรายการไปยังดิสก์เพื่อรักษาการใช้หน่วยความจำน้อย แม้สำหรับไฟล์หลายกิกะไบต์

### ขั้นตอนที่ 1: เปิดไฟล์ ZIP (หรือไฟล์ที่เข้ารหัส)

`FileStream` class ให้สตรีมแบบอ่านอย่างเดียวไปยังไฟล์ ZIP จริงบนดิสก์ การใช้สตรีมทำให้ Aspose.Zip สามารถทำงานกับไฟล์ที่อยู่บนแชร์เครือข่ายหรือทรัพยากรที่ฝังอยู่โดยไม่ต้องคัดลอกไปยังตำแหน่งชั่วคราวก่อน

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ `Archive` (ระบุรหัสผ่านเมื่อจำเป็น)

`Archive` class เป็นอ็อบเจ็กต์หลักที่แทนไฟล์ ZIP ในหน่วยความจำ `ArchiveLoadOptions` กำหนดการตั้งค่าที่ใช้เมื่อโหลดไฟล์เก็บข้อมูล เช่น รหัสผ่านการถอดรหัส การส่งอ็อบเจ็กต์ `ArchiveLoadOptions` ที่มีคุณสมบัติ `DecryptionPassword` จะเปิดใช้งานการถอดรหัสของรายการที่เข้ารหัสแบบ AES

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### ขั้นตอนที่ 3: แยกเนื้อหาไปยังโฟลเดอร์ปลายทาง

`ExtractToDirectory` จะวนลูปทุกรายการในไฟล์เก็บข้อมูลและเขียนไปยังเส้นทางเป้าหมายโดยคงโครงสร้างโฟลเดอร์เดิมไว้ เมธอดจะสร้างไดเรกทอรีที่หายไปโดยอัตโนมัติและยังสามารถกรองรายการได้หากคุณต้องการเพียงบางส่วน

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **เคล็ดลับ:** หากคุณต้องการแยกไฟล์บางส่วนเท่านั้น ให้ใช้ overload ที่รับ filter delegate แทนการแยกทั้งหมด

## ปัญหาทั่วไป & การแก้ไขข้อผิดพลาด

- **Incorrect password** – Aspose.Zip จะโยนข้อยกเว้นการตรวจสอบสิทธิ์ ตรวจสอบสตริงรหัสผ่านอีกครั้งหรือดึงมาจากแหล่งกำหนดค่าที่ปลอดภัย  
- **Target path not found** – ตรวจสอบว่าเส้นทางไดเรกทอรีปลายทางถูกต้อง; `ExtractToDirectory` จะสร้างโฟลเดอร์ที่หายไป แต่เส้นทางแม่ต้องเข้าถึงได้  
- **Large archives** – สำหรับไฟล์ ZIP ขนาดใหญ่มาก ให้พิจารณาแยกรายการทีละรายการโดยใช้ streaming API เพื่อรักษาการใช้หน่วยความจำน้อย  

## คำถามที่พบบ่อย

**Q: Aspose.Zip รองรับรูปแบบการบีบอัดอื่น ๆ เช่น GZIP หรือไม่?**  
A: ใช่, Aspose.Zip for .NET รองรับ ZIP, GZIP, และรูปแบบทั่วไปอื่น ๆ หลายรูปแบบ.

**Q: ฉันสามารถใช้ Aspose.Zip ในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์ได้หรือไม่?**  
A: แน่นอน. จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์, แต่คุณสามารถใช้รุ่นทดลองฟรีเพื่อประเมินผล.

**Q: ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบ.

**Q: ฉันสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Zip ได้จากที่ไหน?**  
A: เยี่ยมชมหน้ารุ่นทดลองของ Aspose.Zip [here](https://releases.aspose.com/) เพื่อดาวน์โหลดเวอร์ชันล่าสุด.

**Q: ฉันจะขอความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?**  
A: ฟอรั่มชุมชน Aspose.Zip เป็นสถานที่ที่ดีสำหรับขอความช่วยเหลือ: [support forum](https://forum.aspose.com/c/zip/37).

---

**อัปเดตล่าสุด:** 2026-06-04  
**ทดสอบด้วย:** Aspose.Zip for .NET (latest release)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีการแยกไฟล์ Zip พร้อมรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [วิธีการแยกไฟล์ WIM ไปยังโฟลเดอร์โดยใช้ Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [วิธีการแตกไฟล์ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-decompression/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}