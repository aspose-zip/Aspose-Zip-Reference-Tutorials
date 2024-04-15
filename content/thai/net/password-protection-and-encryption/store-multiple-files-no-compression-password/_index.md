---
title: Aspose.Zip สำหรับ .NET - บทช่วยสอนการจัดเก็บไฟล์ที่ปลอดภัย
linktitle: จัดเก็บหลายไฟล์โดยไม่ต้องบีบอัดด้วยรหัสผ่าน
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: สำรวจวิธีใช้ Aspose.Zip สำหรับ .NET เพื่อจัดเก็บไฟล์หลายไฟล์อย่างปลอดภัยโดยไม่มีการบีบอัด ขั้นตอนง่ายๆ ในการป้องกันด้วยรหัสผ่าน ปลดล็อกพลังของการจัดการไฟล์!
type: docs
weight: 13
url: /th/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

ในโลกของการพัฒนา .NET การจัดการและการจัดการไฟล์ถือเป็นงานทั่วไป Aspose.Zip สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถบีบอัด ขยายขนาด และจัดการไฟล์ zip ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกสถานการณ์เฉพาะ: การจัดเก็บหลายไฟล์โดยไม่มีการบีบอัดและการป้องกันด้วยรหัสผ่าน ในตอนท้ายของคู่มือนี้ คุณจะมีความรู้ในการใช้งานฟังก์ชันนี้โดยใช้ Aspose.Zip สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/zip/net/).

-  ไดเร็กทอรีเอกสาร: เตรียมไดเร็กทอรีที่มีไฟล์ต้นฉบับของคุณอยู่ ในตัวอย่างที่ให้มา ตัวแปร`dataDir` แสดงถึงไดเร็กทอรีเอกสารของคุณ

## นำเข้าเนมสเปซ

ในการเริ่มต้น เรามานำเข้าเนมสเปซที่จำเป็นสำหรับโค้ดของเรา:

```csharp
// เส้นทางไปยังไดเร็กทอรีทรัพยากร
string dataDir = "Your Document Directory"

// นำเข้าเนมสเปซ Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## ขั้นตอนที่ 1: เปิดไฟล์ซิป

```csharp
//ExStart: StoreMutlipleFiles ไม่มีการบีบอัดด้วยรหัสผ่าน
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 ขั้นตอนนี้เกี่ยวข้องกับการสร้างไฟล์ zip ใหม่โดยใช้`FileStream`. ไฟล์จะมีชื่อว่า "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"

## ขั้นตอนที่ 2: เปิดไฟล์ต้นฉบับ

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

ที่นี่ เราจะเปิดไฟล์ต้นฉบับแรก "alice29.txt" ซึ่งจะถูกจัดเก็บไว้ในไฟล์ zip

## ขั้นตอนที่ 3: สร้างไฟล์เก็บถาวร

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 ในขั้นตอนนี้ เราจะสร้างอินสแตนซ์ของ`Archive` คลาส ระบุการตั้งค่าการบีบอัดและการเข้ารหัส เราใช้`StoreCompressionSettings` เพื่อจัดเก็บไฟล์โดยไม่มีการบีบอัดและ`AesEcryptionSettings` เพื่อใช้การเข้ารหัส AES ด้วยรหัสผ่าน ("p@s$")

## ขั้นตอนที่ 4: สร้างรายการเก็บถาวรและบันทึก

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

ขั้นตอนสุดท้ายนี้เกี่ยวข้องกับการสร้างรายการในไฟล์เก็บถาวรสำหรับ "alice29.txt" และบันทึกไฟล์เก็บถาวร เสร็จสิ้นกระบวนการจัดเก็บไฟล์โดยไม่มีการบีบอัดและมีการป้องกันด้วยรหัสผ่าน

สรุปบทช่วยสอนของคุณโดยสรุปประเด็นสำคัญและสนับสนุนให้ผู้อ่านสำรวจความเป็นไปได้เพิ่มเติมด้วย Aspose.Zip สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีใช้ Aspose.Zip สำหรับ .NET เพื่อจัดเก็บไฟล์หลายไฟล์โดยไม่มีการบีบอัดและรักษาความปลอดภัยด้วยรหัสผ่าน เมื่อคุณเดินทางต่อไปด้วยการพัฒนา .NET ให้ใช้ประโยชน์จากความสามารถของ Aspose.Zip เพื่อปรับปรุงงานการจัดการไฟล์และปรับปรุงความปลอดภัยของแอปพลิเคชันของคุณ

---

### คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ด้วยวิธีการเข้ารหัสอื่นๆ ได้หรือไม่
 ใช่ Aspose.Zip รองรับวิธีการเข้ารหัสที่หลากหลาย ตรวจสอบเอกสาร[ที่นี่](https://reference.aspose.com/zip/net/) เพื่อดูรายละเอียด

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### มี Aspose.Zip สำหรับ .NET ให้ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร
 ขอใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).

### ฉันจะซื้อ Aspose.Zip สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Zip สำหรับ .NET[ที่นี่](https://purchase.aspose.com/buy).
