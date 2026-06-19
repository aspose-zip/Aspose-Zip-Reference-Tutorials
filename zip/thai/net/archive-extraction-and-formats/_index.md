---
date: 2026-06-19
description: เรียนรู้วิธีบีบอัดไฟล์ tar, สร้างไฟล์ archive แบบ targz, และแยกไฟล์ zip
  ที่มีการป้องกันด้วยรหัสผ่านโดยใช้ Aspose.Zip สำหรับ .NET – เพิ่มประสิทธิภาพการจัดเก็บและความปลอดภัย
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: การแยกไฟล์ Archive และรูปแบบ
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: วิธีบีบอัดไฟล์ Tar ด้วย Aspose.Zip สำหรับ .NET
url: /th/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบีบอัดไฟล์ Tar ด้วย Aspose.Zip สำหรับ .NET

## บทนำ

ในคู่มือนี้คุณจะได้ค้นพบ **วิธีบีบอัด tar** ไฟล์โดยใช้ Aspose.Zip สำหรับ .NET, เรียนรู้การสร้างไฟล์ TarGz, และดูวิธีการสกัดไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่าน การจัดการไฟล์เก็บข้อมูลอย่างมีประสิทธิภาพเป็นทักษะสำคัญสำหรับนักพัฒนา .NET สมัยใหม่—ไม่ว่าคุณจะสร้างบริการสำรองข้อมูล, ไคลเอนต์คลาวด์สตอเรจ, หรือสายการประมวลผลข้อมูล การเชี่ยวชาญรูปแบบเหล่านี้จะช่วยลดค่าใช้จ่ายในการจัดเก็บ, เร่งความเร็วการถ่ายโอน, และรักษาข้อมูลที่สำคัญให้ปลอดภัย

## คำตอบสั้น
- **TarBz2 คืออะไร?** ไฟล์เก็บข้อมูลที่บีบอัดซึ่งรวมการบรรจุ TAR กับการบีบอัด BZIP2 เพื่ออัตราการบีบอัดสูง  
- **ทำไมต้องเลือก Aspose.Zip สำหรับ .NET?** มอบ API เดียวที่ลื่นไหลสำหรับการสร้างและสกัดไฟล์เก็บข้อมูลหลายรูปแบบโดยไม่ต้องพึ่งพาไลบรารีภายนอก  
- **ฉันสามารถสร้างไฟล์ TarGz ได้หรือไม่?** ได้ – Aspose.Zip รองรับ TarGz, TarLz, TarXz, TarZ และอื่น ๆ อีกมาก  
- **ฉันจะสกัดไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่านอย่างไร?** ใช้คุณสมบัติ `Password` ของอ็อบเจกต์ `ArchiveEntry` ขณะสกัดไฟล์  
- **ฉันต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีสำหรับการประเมิน

## การบีบอัด Tar คืออะไร?
Tar (Tape Archive) เป็นรูปแบบคอนเทนเนอร์ที่รวมหลายไฟล์และไดเรกทอรีเป็นสตรีมเดียวโดยไม่มีการบีบอัด เมื่อคุณนำอัลกอริทึมบีบอัดเช่น BZIP2, GZip, LZMA หรือ XZ มาประยุกต์ใช้ ผลลัพธ์จะเป็นไฟล์ **tar‑based archive** เช่น `.tar.bz2`, `.tar.gz`, `.tar.lz` เป็นต้น รูปแบบเหล่านี้ได้รับการสนับสนุนอย่างกว้างขวางบน Linux, macOS, และ Windows ทำให้เหมาะสำหรับการแลกเปลี่ยนข้อมูลข้ามแพลตฟอร์ม

## ทำไมต้องใช้ Aspose.Zip สำหรับ .NET เพื่อจัดการรูปแบบเหล่านี้?
Aspose.Zip ให้ **API แบบรวมศูนย์ที่ไม่มีการพึ่งพา** รองรับรูปแบบไฟล์เก็บข้อมูลและบีบอัดกว่า 50 รูปแบบ รวมถึง TarBz2, TarGz, TarLz, TarXz, และ TarZ ทำงานบน Windows, Linux, และ macOS สถาปัตยกรรมแบบสตรีมของมันทำให้การใช้หน่วยความจำต่ำกว่า 10 MB แม้กับไฟล์เก็บข้อมูลหลายร้อยเมกะไบต์ การป้องกันด้วยรหัสผ่านเป็นฟีเจอร์ในตัว ช่วยให้เข้ารหัสแต่ละรายการได้โดยไม่ต้องใช้ไลบรารีเพิ่มเติม

## ข้อกำหนดเบื้องต้น
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, หรือ .NET 5–10  
- ติดตั้งแพคเกจ NuGet Aspose.Zip for .NET (`Install-Package Aspose.Zip`)  
- มีความคุ้นเคยพื้นฐานกับการทำ I/O ของ C# และระบบโปรเจกต์ .NET

## คู่มือขั้นตอนต่อขั้นตอน

### วิธีบีบอัดไฟล์ Tar – คำตอบโดยตรง
`Archive` แทนไฟล์เก็บข้อมูลและให้เมธอดสำหรับเพิ่มรายการและบันทึกไฟล์  
สร้างอินสแตนซ์ `Archive`, เพิ่มไฟล์ที่ต้องการบรรจุ, ตั้งค่า `CompressionType.BZip2`, แล้วเรียก `Save` ด้วย `ArchiveFormat.TarBz2` ไลบรารีจะเขียนคอนเทนเนอร์ TAR และบีบอัดในขั้นตอนสตรีมเดียว ทำให้ไม่ต้องโหลดไฟล์เก็บข้อมูลทั้งหมดเข้าสู่หน่วยความจำ

### ขั้นตอนที่ 1: เลือกรูปแบบไฟล์เก็บข้อมูลที่คุณต้องการ
ตัดสินใจเลือกรูปแบบ tar‑based ที่ตรงกับการแลกเปลี่ยนระหว่างอัตราการบีบอัดและความเร็ว:

- **TarBz2** – อัตราการบีบอัดสูงสุด (≈30 % เล็กกว่า TarGz) แต่ช้ากว่า  
- **TarGz** – สมดุลที่ดีระหว่างความเร็วและขนาด; เหมาะสำหรับสถานการณ์คลาวด์สตอเรจส่วนใหญ่  
- **TarLz / TarXz** – การบีบอัดสูงมากพร้อมความเร็วปานกลาง, มีประโยชน์สำหรับการเก็บข้อมูลระยะยาว  
- **TarZ** – รูปแบบเก่าสำหรับความเข้ากันได้กับเครื่องมือ Unix รุ่นเก่า  

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ `Archive` ใหม่
`Archive` เป็นอ็อบเจกต์ระดับบนสุดที่แทนไฟล์เก็บข้อมูลเดียวในหน่วยความจำ  
คลาส `Archive` จัดการกระบวนการบรรจุและบีบอัด, เปิดให้เรียกเมธอดเพื่อเพิ่มรายการและเขียนไฟล์สุดท้าย

### ขั้นตอนที่ 3: เพิ่มไฟล์และโฟลเดอร์
คุณสามารถเพิ่มโครงสร้างไดเรกทอรีทั้งหมดด้วย `AddAll` หรือเพิ่มไฟล์เดี่ยวด้วย `AddFile` การรักษาโครงสร้างโฟลเดอร์เดิมทำได้ง่ายโดยส่งพาธฐานของไดเรกทอรี

### ขั้นตอนที่ 4: ตั้งค่าประเภทการบีบอัดที่ต้องการ
`CompressionType` ระบุอัลกอริทึมที่รองรับ  
`CompressionType` กำหนดอัลกอริทึม (BZip2, GZip, LZMA, XZ ฯลฯ) ที่จะนำไปใช้กับสตรีม TAR ระหว่างการบันทึก

### ขั้นตอนที่ 5: บันทึกไฟล์เก็บข้อมูล
`ArchiveFormat` เป็นชุด enum (เช่น `TarBz2`, `TarGz`) ที่บอกตัวเขียนว่าจะใช้คอนเทนเนอร์และการบีบอัดแบบใด  
การเรียก `Save` จะเขียนไฟล์เก็บข้อมูลลงดิสก์ตามรูปแบบที่เลือก

### ขั้นตอนที่ 6: การสกัดไฟล์เก็บข้อมูลด้วยรหัสผ่าน
`ArchiveEntry` แทนไฟล์หรือโฟลเดอร์รายการเดียวภายในไฟล์เก็บข้อมูล  
เพื่อสกัดไฟล์ zip ที่มีการป้องกันด้วยรหัสผ่าน, เปิดไฟล์เก็บข้อมูล, ค้นหาแต่ละ `ArchiveEntry`, กำหนดคุณสมบัติ `Password` ของมัน, แล้วเรียก `Extract` โมเดลรหัสผ่านต่อรายการนี้ทำให้คุณสามารถป้องกันไฟล์แต่ละไฟล์ภายใน zip เดียวได้

### ขั้นตอนที่ 7: ตรวจสอบผลลัพธ์
หลังการสกัด, เปรียบเทียบขนาดไฟล์และค่าเช็กซัม SHA‑256 เพื่อยืนยันว่าการทำรอบไฟล์เก็บข้อมูลไม่ทำให้ข้อมูลเสียหาย

## กรณีการใช้งานทั่วไป
- **ยูทิลิตี้สำรองข้อมูล** – เก็บสำรองข้อมูลประจำวันเป็น `.tar.bz2` เพื่อลดค่าใช้จ่ายการจัดเก็บสูงสุด 30 %  
- **การแลกเปลี่ยนข้อมูลข้ามแพลตฟอร์ม** – รูปแบบที่อิง Tar ถูกเข้าใจโดยเครื่องมือของ Linux, macOS, และ Windows โดยตรง  
- **การแจกจ่ายอย่างปลอดภัย** – กำหนดรหัสผ่านให้กับรายการที่สำคัญ, ตรงตามข้อกำหนดการปฏิบัติตามโดยไม่ต้องใช้เครื่องมือการเข้ารหัสเพิ่มเติม  

## การแก้ไขปัญหาและเคล็ดลับ
- **ไฟล์เก็บข้อมูลขนาดใหญ่** – ควรใช้ API สตรีม (`Archive.CreateEntryFromFile`) เพื่อรักษาการใช้หน่วยความจำให้น้อยที่สุด  
- **รหัสผ่านไม่ตรงกัน** – รหัสผ่านที่ตั้งบนแต่ละ `ArchiveEntry` ต้องตรงกันอย่างแม่นยำ; หากไม่ตรงจะเกิด `InvalidPasswordException`  
- **ระดับการบีบอัด** – BZIP2 ไม่รองรับระดับที่กำหนดเอง; หากต้องการการควบคุมที่ละเอียดกว่าให้เปลี่ยนเป็น LZMA (`CompressionType.LZMA`) หรือ XZ (`CompressionType.XZ`)  

## คำถามที่พบบ่อย

**ถาม:** ฉันจะสร้างไฟล์ TarGz อย่างไร?  
**ตอบ:** ตั้งค่า `CompressionType.GZip` และใช้ `ArchiveFormat.TarGz` ขณะเรียก `Save` จะได้ไฟล์ `.tar.gz` ในขั้นตอนเดียว

**ถาม:** ฉันสามารถสกัดไฟล์เก็บข้อมูลที่มีการป้องกันด้วยรหัสผ่านโดยไม่รู้รหัสผ่านได้หรือไม่?  
**ตอบ:** ไม่ได้ รายการแต่ละรายการต้องได้รับรหัสผ่านที่ถูกต้อง; หากไม่ตรงการสกัดจะล้มเหลวด้วย `InvalidPasswordException`

**ถาม:** Aspose.Zip รองรับการสกัดไฟล์เก็บข้อมูลโดยมีรหัสผ่านที่แตกต่างกันสำหรับแต่ละรายการหรือไม่?  
**ตอบ:** รองรับ ให้กำหนดรหัสผ่านให้กับแต่ละ `ArchiveEntry` ก่อนเรียก `Extract`

**ถาม:** รูปแบบใดให้การบีบอัดที่ดีที่สุด?  
**ตอบ:** TarBz2 มักให้ขนาดที่เล็กที่สุด ตามด้วย TarLz และ TarXz ส่วน TarGz ให้ความเร็วที่ดีกว่าแต่ยังคงบีบอัดได้ดี

**ถาม:** มีขีดจำกัดจำนวนไฟล์ที่ฉันสามารถเพิ่มลงในไฟล์ TAR หรือไม่?  
**ตอบ:** โดยหลักไม่มีขีดจำกัด, แต่ไฟล์เก็บข้อมูลที่ใหญ่มาก (>10 GB) อาจต้องแบ่งเป็นหลายส่วนเพื่อความสะดวกในการจัดการ

## การสกัดไฟล์เก็บข้อมูลและบทเรียนรูปแบบ

### [การบีบอัดไฟล์เป็น TarBz2 ด้วย Aspose.Zip สำหรับ .NET](./compress-to-tar-bz2/)
เรียนรู้วิธีบีบอัดไฟล์เป็นรูปแบบ TarBz2 ใน .NET ด้วย Aspose.Zip ตามขั้นตอนเพื่อการบีบอัดไฟล์ที่มีประสิทธิภาพ  

### [การบีบอัดเป็น TarGz ด้วย Aspose.Zip สำหรับ .NET](./compress-to-tar-gz/)
สำรวจการบีบอัดไฟล์อย่างมีประสิทธิภาพใน .NET ด้วย Aspose.Zip บีบอัดเป็น TarGz อย่างง่ายดาย  

### [การบีบอัดเป็น TarLz ด้วย Aspose.Zip สำหรับ .NET](./compress-to-tar-lz/)
บีบอัดไฟล์ใน .NET ด้วย Aspose.Zip อย่างไม่มีความยุ่งยาก เรียนรู้การสร้างไฟล์ TarLz ขั้นตอนต่อขั้นตอน  

### [การบีบอัดเป็น TarXz ด้วย Aspose.Zip สำหรับ .NET](./compress-to-tar-xz/)
เรียนรู้วิธีบีบอัดไฟล์เป็นรูปแบบ TarXz ใน .NET ด้วย Aspose.Zip ตามคำแนะนำเพื่อการจัดเก็บและการส่งข้อมูลที่มีประสิทธิภาพ  

### [การบีบอัดเป็น TarZ ด้วย Aspose.Zip สำหรับ .NET](./compress-to-tar-z/)
สำรวจขั้นตอนการบีบอัดเป็น TarZ ด้วย Aspose.Zip สำหรับ .NET การจัดการไฟล์ที่มีประสิทธิภาพสำหรับโปรเจกต์ .NET ของคุณ  

### [การสกัดรายการในไฟล์เก็บข้อมูลด้วยรหัสผ่านที่แตกต่างกันใน Aspose.Zip สำหรับ .NET](./extract-archive-different-passwords/)
เรียนรู้วิธีสกัดรายการในไฟล์เก็บข้อมูลด้วยรหัสผ่านที่แตกต่างกันใน Aspose.Zip สำหรับ .NET เพิ่มความปลอดภัยและความยืดหยุ่นในแอปพลิเคชันของคุณ  

---

**อัปเดตล่าสุด:** 2026-06-19  
**ทดสอบด้วย:** Aspose.Zip for .NET 24.11  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างไฟล์ tar และเพิ่มไฟล์ลงใน tar ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [วิธีบีบอัด tar และสร้าง TarBz2 ด้วย Aspose.Zip สำหรับ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [เพิ่มไฟล์ลงใน tar และสร้างไฟล์ tarxz ด้วย Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}