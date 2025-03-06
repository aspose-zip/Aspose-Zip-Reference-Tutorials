---
title: บีบอัดหลายไฟล์ด้วยการเข้ารหัสใน Aspose.Zip .NET
linktitle: บีบอัดไฟล์หลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิม
second_title: Aspose.Zip .NET API สำหรับการบีบอัดไฟล์และการเก็บถาวร
description: เรียนรู้วิธีการบีบอัดไฟล์หลายไฟล์อย่างปลอดภัยโดยใช้การเข้ารหัสแบบดั้งเดิมใน Aspose.Zip สำหรับ .NET ปรับปรุงการปกป้องข้อมูลในแอปพลิเคชัน .NET ของคุณ
weight: 17
url: /th/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดหลายไฟล์ด้วยการเข้ารหัสใน Aspose.Zip .NET


## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนทีละขั้นตอนเกี่ยวกับการบีบอัดไฟล์หลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิมโดยใช้ Aspose.Zip สำหรับ .NET Aspose.Zip เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ zip ได้อย่างราบรื่นในแอปพลิเคชัน .NET ของตน ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการบีบอัดไฟล์หลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิม เพื่อให้มั่นใจถึงความปลอดภัยของข้อมูลของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Zip สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Zip สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/zip/net/).

-  ไดเรกทอรีเอกสารของคุณ: แทนที่`"Your Document Directory"`ในข้อมูลโค้ดพร้อมเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## นำเข้าเนมสเปซ

ในแอปพลิเคชัน .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น ซึ่งจะช่วยให้คุณสามารถเข้าถึงฟังก์ชันการทำงานที่ Aspose.Zip มอบให้ได้ นี่คือตัวอย่าง:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไฟล์ซิป

 สร้างไฟล์ zip ใหม่โดยใช้นามสกุล`Archive` ระดับ. ในขั้นตอนนี้ คุณจะต้องกำหนดการตั้งค่าการเข้ารหัสแบบเดิม โดยให้รหัสผ่านเพื่อเพิ่มความปลอดภัย

```csharp
//ExStart: บีบอัดหลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิม
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // สร้างไฟล์เก็บถาวรด้วยการตั้งค่าการเข้ารหัสแบบดั้งเดิม
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // ไปยังขั้นตอนต่อไป...
    }
}
//ExEnd: บีบอัดหลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิม
```

## ขั้นตอนที่ 2: เพิ่มไฟล์ลงในไฟล์เก็บถาวร

ตอนนี้เพิ่มไฟล์ที่คุณต้องการบีบอัดลงในไฟล์เก็บถาวร ในตัวอย่างนี้ เรากำลังเพิ่มไฟล์สามไฟล์: "alice29.txt," "asyoulik.txt" และ "fields.c"

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

## ขั้นตอนที่ 3: บันทึกไฟล์ซิป

บันทึกไฟล์ zip พร้อมรายการที่เพิ่ม ขั้นตอนนี้เป็นการสิ้นสุดกระบวนการบีบอัด

```csharp
archive.Save(zipFile);
```

ยินดีด้วย! คุณได้บีบอัดไฟล์หลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิมโดยใช้ Aspose.Zip สำหรับ .NET สำเร็จ

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ประโยชน์จาก Aspose.Zip สำหรับ .NET เพื่อบีบอัดไฟล์หลายไฟล์ด้วยการเข้ารหัสแบบดั้งเดิม กระบวนการนี้ทำให้มั่นใจในความปลอดภัยของข้อมูลของคุณในขณะที่จัดการไฟล์ zip ในแอปพลิเคชัน .NET ของคุณอย่างมีประสิทธิภาพ

---

## คำถามที่พบบ่อย

### 1. ฉันสามารถใช้ Aspose.Zip สำหรับ .NET ทั้งในสภาพแวดล้อม Windows และ Linux ได้หรือไม่

ใช่ Aspose.Zip สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม Windows และ Linux ให้ความยืดหยุ่นสำหรับนักพัฒนา

### 2. Aspose.Zip สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 ใช่ คุณสามารถทดลองใช้ Aspose.Zip สำหรับ .NET ได้ฟรี[ที่นี่](https://releases.aspose.com/).

### 3. ฉันจะรับการสนับสนุนสำหรับ Aspose.Zip สำหรับ .NET ได้อย่างไร

 สำหรับการสนับสนุนหรือข้อสงสัยใด ๆ คุณสามารถไปที่[ฟอรั่ม Aspose.Zip](https://forum.aspose.com/c/zip/37).

### 4. มีใบอนุญาตชั่วคราวสำหรับ Aspose.Zip สำหรับ .NET หรือไม่

 ใช่ สามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### 5. ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Zip สำหรับ .NET ได้ที่ไหน

โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/zip/net/) เพื่อข้อมูลเชิงลึก

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
