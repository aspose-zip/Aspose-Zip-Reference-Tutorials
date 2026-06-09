---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บีบอัดหลายไฟล์ c# ด้วย Aspose.Zip Parallel Compression

## บทนำ

หากคุณต้องการ **zip multiple files c#** อย่างรวดเร็วและมีประสิทธิภาพ การใช้การประมวลผลแบบขนานเป็นวิธีที่ดีที่สุด ในแอปพลิเคชัน .NET สมัยใหม่ การสร้างไฟล์ zip ขนาดใหญ่สามารถเป็นคอขวด—โดยเฉพาะเมื่อจัดการกับหลายสิบหรือหลายร้อยไฟล์ Aspose.Zip สำหรับ .NET ขจัดปัญหานี้โดยให้ **parallel zip compression** ในตัวที่กระจายงานไปยังคอร์ CPU ทั้งหมดที่มีอยู่ ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด: ตั้งค่าสภาพแวดล้อมจนถึงการบันทึก zip archive พร้อมเปิดใช้งานการทำงานแบบขนาน และเราจะยังแสดงวิธี **create zip archive c#** ที่ทำงานได้อย่างราบรื่นบน .NET Core.

## คำตอบสั้น
- **การบีบอัด zip แบบขนานคืออะไร?** มันบีบอัดหลายไฟล์พร้อมกันโดยใช้หลายเธรดเพื่อลดเวลาการประมวลผลโดยรวม.  
- **ไลบรารี .NET ใดที่รองรับ?** Aspose.Zip for .NET ให้ API ง่ายสำหรับการบีบอัดแบบขนาน.  
- **ฉันต้องการไลเซนส์สำหรับการผลิตหรือไม่?** ใช่—ต้องมีไลเซนส์เต็ม; มีไลเซนส์ชั่วคราวสำหรับการทดสอบ.  
- **ฉันสามารถเพิ่มไฟล์ลงใน zip ระหว่างทำงานได้หรือไม่?** แน่นอน—ใช้ `Archive.CreateEntry` สำหรับแต่ละไฟล์ที่ต้องการรวม.  
- **รองรับ .NET 6/7 หรือไม่?** ใช่, API ทำงานได้กับ .NET runtime สมัยใหม่ทั้งหมด.

## zip multiple files c# คืออะไร?
`zip multiple files c#` หมายถึงการสร้างไฟล์ ZIP เดียวที่บรรจุไฟล์หลายไฟล์โดยใช้โค้ด C#. เมื่อคุณผสานกับ **parallel zip compression** ไลบรารีจะประมวลผลแต่ละไฟล์บนเธรดแยกกัน ทำให้เวลาที่ใช้ในการสร้างไฟล์ archive สุดท้ายลดลงอย่างมาก.

## ทำไมต้องใช้ Aspose.Zip สำหรับการบีบอัดแบบขนาน?
การบีบอัดแบบขนานช่วยให้คุณใช้ทุกคอร์ของเครื่องหลายโปรเซสเซอร์ได้อย่างเต็มที่ โดยมักให้ประสิทธิภาพ **2‑3× เร็วกว่า** วิธีแบบใช้เธรดเดียว นอกจากนี้ยังขยายได้อย่างราบรื่น: การเพิ่มไฟล์ไม่ทำให้เวลาในการประมวลผลเพิ่มตามเชิงเส้น และ API จะจัดการการจัดการเธรดให้คุณ ทำให้คุณสามารถมุ่งเน้นที่ตรรกะธุรกิจได้  

- **ความเร็ว:** ใช้ทุก logical processor เพื่อลดเวลาในการสร้าง zip สูงสุดถึง 70 % ในงานทั่วไป.  
- **ความสามารถในการขยาย:** จัดการชุดไฟล์ 500+ ไฟล์โดยไม่เพิ่มเวลา CPU อย่างสัดส่วน.  
- **ความเรียบง่าย:** เมธอดระดับสูงซ่อนความซับซ้อนของ `System.Threading.Tasks`.  
- **ความยืดหยุ่น:** รองรับ .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, และ .NET 5–10 รวมถึง .NET 6/7 สำหรับบริการคลาวด์‑เนทีฟ.

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET.  
- ติดตั้ง Aspose.Zip for .NET คุณสามารถดาวน์โหลดได้ **[here](https://releases.aspose.com/zip/net/)**.  
- มีไลเซนส์ชั่วคราวหรือเต็ม (ไลเซนส์ชั่วคราวเพียงพอสำหรับบทแนะนำนี้).  

## นำเข้า Namespaces

`Aspose.Zip` namespace มีประเภททั้งหมดที่คุณต้องการใช้ทำงานกับ ZIP archive.

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

ขั้นแรก ให้นำ Namespaces ที่จำเป็นเข้าไปในไฟล์ C# ของคุณ เพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสที่คุณจะใช้ได้จากที่ไหน.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ

กำหนดโฟลเดอร์ที่บรรจุไฟล์ที่ต้องการบีบอัด พาธนี้จะถูกเก็บในตัวแปร `dataDir` ซึ่งคุณสามารถชี้ไปยังตำแหน่งใดก็ได้บนดิสก์.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เริ่มต้นกระบวนการบีบอัด

เปิดไฟล์ ZIP ใหม่สำหรับการเขียน คำสั่ง `using` จะทำให้สตรีมไฟล์ถูกทำลายอย่างถูกต้องหลังจากทำงานเสร็จ ลดการรั่วของ file‑handle.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## ขั้นตอนที่ 3: อ่านและบีบอัดไฟล์แบบขนาน

`Parallel.ForEach` ทำงานลูป foreach ที่อาจรันพร้อมกันบนหลายเธรด.

เปิดไฟล์ต้นฉบับแต่ละไฟล์ที่ต้องการเพิ่มลงใน archive ในตัวอย่างนี้เราทำงานกับข้อความคลาสสิกสองไฟล์ แต่คุณสามารถ **add files to zip** สำหรับเอกสารจำนวนใดก็ได้ ลูป `Parallel.ForEach` จะกระจายงานไปยังเธรดโดยอัตโนมัติ.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## ขั้นตอนที่ 4: สร้างรายการใน Archive

คลาส `Archive` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Zip ที่แทน ZIP container ที่คุณกำลังสร้าง.

`CreateEntry` สร้างรายการใหม่ใน ZIP archive สำหรับไฟล์ที่ระบุ ทุกการเรียก `CreateEntry` จะเพิ่มไฟล์ใหม่ลงใน archive.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## ขั้นตอนที่ 5: กำหนดเกณฑ์การทำงานแบบขนาน

`ParallelOptions` เป็นประเภทของ .NET ที่ควบคุมวิธีการทำงานของลูปแบบขนาน.

กำหนดการบีบอัดให้ทำงานแบบขนานโดยตั้งค่า `ParallelOptions` ธง `ParallelCompressInMemory` บอก Aspose.Zip ให้ใช้การประมวลผลแบบขนานเสมอ, ส่วน `MaxDegreeOfParallelism` ให้คุณจำกัดจำนวนเธรดที่ทำงานพร้อมกัน.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## ขั้นตอนที่ 6: บันทึก Archive ที่บีบอัดแล้ว

สุดท้าย เขียน archive ลงดิสก์พร้อมตัวเลือกที่ต้องการ รวมถึงการเข้ารหัส, คอมเมนต์, และการตั้งค่าขนานที่กำหนดไว้ก่อนหน้านี้ เมธอด `Save` จะสรุปไฟล์ ZIP.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** หากคุณกำลังบีบอัดไฟล์ขนาดใหญ่มาก ให้พิจารณาตั้งค่า `ParallelOptions.MaxDegreeOfParallelism` ให้ต่ำกว่าจำนวน logical processor. วิธีนี้ช่วยให้เซิร์ฟเวอร์ของคุณตอบสนองได้ดีขึ้นภายใต้โหลด.

### กรณีการใช้งานทั่วไป

- **Batch reporting:** สร้าง zip bundle ของรายงาน CSV รายวันสำหรับระบบ downstream.  
- **Document archiving:** เก็บคอลเลกชันขนาดใหญ่ของ PDF, รูปภาพ หรือ log ใน archive เดียวเพื่อสำรองข้อมูล.  
- **Data export APIs:** ส่งคืนไฟล์ zip ที่มีหลายไฟล์ข้อมูลให้กับไคลเอนต์ใน HTTP response เดียว.  

## ปัญหาทั่วไปและเคล็ดลับ

- **Memory pressure on huge files:** แทนที่จะโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้สตรีมไฟล์เป็นชิ้นส่วนหรือใช้โหมด `ParallelCompressInMemory` อย่างเลือกสรร.  
- **Thread safety:** API ของ Aspose.Zip ปลอดภัยต่อเธรดในโหมดขนาน แต่ควรหลีกเลี่ยงการแก้ไข `FileStream` เดียวกันจากภายนอกขณะบีบอัด.  
- **Performance tuning:** ทดลองปรับ `ParallelOptions.MaxDegreeOfParallelism` หากต้องการจำกัดการใช้ CPU บนเซิร์ฟเวอร์ที่แชร์.  

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Zip for .NET together with other compression libraries?**  
A: ใช่, Aspose.Zip สามารถทำงานร่วมกับไลบรารี .NET อื่นได้; เพียงแค่แยก namespace ของแต่ละอันให้ชัดเจน.

**Q: Is a temporary license available for testing purposes?**  
A: ใช่, คุณสามารถรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้จาก **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I ask for help if I run into problems?**  
A: เยี่ยมชม **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

**Q: Where can I find more code examples and detailed API docs?**  
A: สำรวจ **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** เพื่อดูตัวอย่างที่ครอบคลุม.

**Q: How do I purchase a full license for Aspose.Zip?**  
A: คุณสามารถซื้อ Aspose.Zip for .NET **[here](https://purchase.aspose.com/buy)**.

---

**อัปเดตล่าสุด:** 2026-06-09  
**ทดสอบด้วย:** Aspose.Zip 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [zip multiple files c# – การบีบอัดอย่างง่ายดายด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-compression/compress-multiple-files/)
- [วิธีสร้าง Zip Archive และเพิ่มไฟล์ลงใน Zip ด้วย Aspose.Zip สำหรับ .NET](/zip/net/file-compression/compress-single-file/)
- [บีบอัดหลายไฟล์พร้อมการเข้ารหัสใน Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}