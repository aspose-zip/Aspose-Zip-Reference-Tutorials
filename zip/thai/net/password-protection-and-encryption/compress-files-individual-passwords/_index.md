---
date: 2026-03-02
description: เรียนรู้วิธีสร้างไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่านและบีบอัดไฟล์ด้วยรหัสผ่านใน
  .NET โดยใช้ Aspose.Zip. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเรา.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: สร้างไฟล์ ZIP ที่มีการป้องกันด้วยรหัสผ่านใน .NET ด้วย Aspose.Zip
url: /th/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ ZIP ที่มีการป้องกันด้วยรหัสผ่านใน .NET ด้วย Aspose.Zip

## Introduction

เมื่อคุณต้องการแชร์ข้อมูลที่เป็นความลับ, **ไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** เป็นวิธีที่ง่ายที่สุดแต่ก็มีประสิทธิภาพสูงในการรักษาข้อมูลให้ปลอดภัย ในแอปพลิเคชัน .NET, Aspose.Zip ทำให้การ **บีบอัดไฟล์พร้อมรหัสผ่าน** เป็นเรื่องง่าย, โดยให้แต่ละไฟล์มีคีย์การเข้ารหัสของตนเอง ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้าง archive ดังกล่าว, ทำไมจึงสำคัญ, และสามารถนำไปใช้ในโครงการจริงได้อย่างไร

## Quick Answers
- **ควรใช้ไลบรารีอะไร?** Aspose.Zip for .NET มีการสนับสนุนในตัวสำหรับรหัสผ่านต่อไฟล์และหลายวิธีการเข้ารหัส.  
- **ต้องเขียนโค้ดกี่บรรทัด?** ประมาณ 30 บรรทัด, รวมถึงการตั้งค่าและการบันทึก archive.  
- **ไฟล์แต่ละไฟล์สามารถมีรหัสผ่านต่างกันได้หรือไม่?** ได้ – คุณสามารถกำหนดรหัสผ่านเฉพาะให้กับแต่ละ entry.  
- **มีวิธีการเข้ารหัสอะไรบ้าง?** ZipCrypto แบบดั้งเดิม, AES‑128, และ AES‑256.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในโปรดักชัน; มีรุ่นทดลองฟรีให้ใช้.

## What is a password protected zip archive?
ไฟล์ zip ที่ป้องกันด้วยรหัสผ่านคือไฟล์ที่บีบอัด (ZIP) ซึ่งต้องใช้รหัสผ่านในการแตกไฟล์ออกจาก archive รหัสผ่านสามารถป้องกันทั้ง archive หรือแต่ละ entry แยกกัน, และอัลกอริทึมสมัยใหม่อย่าง AES‑128/256 ให้การเข้ารหัสที่แข็งแรง

## Why compress files with passwords using Aspose.Zip?
- **ความปลอดภัยแบบละเอียด** – กำหนดรหัสผ่านที่แตกต่างสำหรับแต่ละไฟล์, เหมาะกับสถานการณ์หลายผู้ใช้.  
- **มาตรฐานการเข้ารหัสหลายแบบ** – เลือกใช้ ZipCrypto แบบเก่า หรือ AES ที่แข็งแรง.  
- **ไม่ต้องใช้เครื่องมือภายนอก** – ทุกอย่างทำได้โดยโปรแกรมเมติกภายในโค้ด .NET ของคุณ.  
- **ประสิทธิภาพ** – การบีบอัดที่เร็วด้วย Deflate พร้อมขนาด archive ที่เล็ก.

## Prerequisites

ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

- **Aspose.Zip for .NET** – ติดตั้งไลบรารีในโปรเจกต์ของคุณ. เอกสารรายละเอียดพร้อมให้ดู [ที่นี่](https://reference.aspose.com/zip/net/).  
- **ดาวน์โหลดแพคเกจล่าสุด** หากคุณยังไม่ได้ทำ, จาก [ลิงก์นี้](https://releases.aspose.com/zip/net/).  
- โฟลเดอร์ที่บรรจุไฟล์ที่คุณต้องการบีบอัด.

## Import Namespaces

เพิ่ม namespace ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณ:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

กำหนดเส้นทางโฟลเดอร์ที่เก็บไฟล์ต้นฉบับ:

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

ต่อไปเราจะสร้าง **ไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** โดยแต่ละไฟล์ใช้รหัสผ่านและวิธีการเข้ารหัสของตนเอง ตัวอย่างใช้ไฟล์ตัวอย่างสามไฟล์ (`alice29.txt`, `asyoulik.txt`, และ `fields.c`) พร้อมรหัสผ่านที่แตกต่างกัน

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How it works
- **CreateEntry** เพิ่มไฟล์เข้าไปใน archive.  
- อาร์กิวเมนต์ที่สี่ (`ArchiveEntrySettings`) ให้คุณระบุทั้งการบีบอัด (`DeflateCompressionSettings`) และการเข้ารหัส (`TraditionalEncryptionSettings` หรือ `AesEcryptionSettings`).  
- โดยการส่งรหัสผ่านที่แตกต่างสำหรับแต่ละ entry, คุณจะได้ **ไฟล์ zip ที่ป้องกันด้วยรหัสผ่าน** ที่แต่ละไฟล์สามารถเปิดได้เฉพาะด้วยคีย์ของมันเองเท่านั้น.

## Common Issues & Troubleshooting

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| การแตกไฟล์ล้มเหลวด้วยข้อความ “Wrong password” | รหัสผ่านไม่ตรงกันหรือใช้วิธีการเข้ารหัสผิด | ตรวจสอบสตริงรหัสผ่านให้ตรงกันและให้แน่ใจว่าใช้ `EncryptionMethod` เดียวกันเมื่อทำการแตกไฟล์ |
| ขนาด archive มากกว่าที่คาด | การใช้ AES‑256 กับไฟล์ข้อความขนาดเล็กอาจเพิ่ม overhead | สำหรับไฟล์ขนาดเล็ก, AES‑128 อาจเพียงพอและทำให้ archive มีขนาดเล็กลง |
| เกิดข้อยกเว้นขณะ `archive.Save` | ไม่มีสิทธิ์เขียนในโฟลเดอร์เป้าหมาย | ตรวจสอบให้แอปพลิเคชันมีสิทธิ์เขียนที่ `dataDir` หรือใช้เส้นทางออกอื่น |

## Frequently Asked Questions (FAQs)

### สามารถใช้วิธีการเข้ารหัสที่แตกต่างกันสำหรับแต่ละไฟล์ได้หรือไม่?
ได้, Aspose.Zip for .NET อนุญาตให้คุณผสมผสานวิธีการเข้ารหัส—ZipCrypto แบบดั้งเดิม, AES‑128, และ AES‑256—บนพื้นฐานต่อไฟล์ได้

### มีรุ่นทดลองให้ใช้หรือไม่?
มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Zip for .NET [ที่นี่](https://releases.aspose.com/)

### จะรับการสนับสนุนได้อย่างไรหากพบปัญหา?
เยี่ยมชม [ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) เพื่อรับความช่วยเหลือจากชุมชนและทีมสนับสนุนของ Aspose

### จะหาเอกสารรายละเอียดของ Aspose.Zip for .NET ได้จากที่ไหน?
เอกสารพร้อมให้ดู [ที่นี่](https://reference.aspose.com/zip/net/)

### สามารถซื้อใบอนุญาตชั่วคราวเพื่อทดสอบได้หรือไม่?
ได้, คุณสามารถขอใบอนุญาตชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose