---
date: 2026-06-29
description: تعلم كيفية ضغط مجلد إلى 7z باستخدام Aspose.Zip لـ .NET، مع تغطية طرق
  ضغط Seven Zip مثل LZMA2 و BZip2 و Store. مثالي لإنشاء أرشيفات 7z برمجيًا.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip مع طرق ضغط متعددة
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط مجلد إلى 7z – Aspose.Zip لـ .NET دليل
url: /ar/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط مجلد إلى 7z – Aspose.Zip for .NET Tutorial

## مقدمة

إذا كنت بحاجة إلى **compress folder to 7z** أرشيفات برمجياً في تطبيق .NET، فقد وجدت المكان المناسب. تجعل Aspose.Zip for .NET من السهل إنشاء Seven Zip أرشيفات باستخدام أي من خوارزميات الضغط المدعومة، سواء كنت ترغب في تجميع دليل كامل للتوزيع أو تحتاج ببساطة إلى حل **seven zip archive .net** موثوق. في هذا الدليل سنستعرض ثلاث طرق ضغط شائعة — LZMA2، BZip2، و Store (بدون ضغط) — وسنظهر لك بالضبط كيفية إنشاء ملف 7z ببضع أسطر من كود C#.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip for .NET توفر مجموعة كاملة من ميزات Seven Zip.  
- **أي طريقة ضغط تعطي أفضل نسبة؟** عادةً ما يقدم LZMA2 أعلى نسبة ضغط للبيانات المختلطة.  
- **هل يمكنني إنشاء 7z بدون أي ضغط؟** نعم — استخدم طريقة Store (بدون ضغط).  
- **هل أحتاج إلى ترخيص للتطوير؟** يتوفر نسخة تجريبية مجانية؛ الترخيص مطلوب للاستخدام في الإنتاج.  
- **هل هذا متوافق مع .NET 6/7؟** بالتأكيد — Aspose.Zip يدعم .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10.

## ما هي طرق ضغط Seven Zip؟

يدعم Seven Zip عدة خوارزميات، كل واحدة مُحسّنة لسيناريوهات مختلفة. **LZMA2** يقدم أعلى نسبة ضغط (غالباً أصغر بنسبة 30‑40 % مقارنةً بـ BZip2)، **BZip2** يوفر ضغطاً ثابتاً مع دعم أوسع للأدوات القديمة، و **Store** ببساطة يقوم بأرشفة الملفات دون تقليل حجمها، مع الحفاظ على الطوابع الزمنية الأصلية بدقة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود:

- معرفة أساسية بـ C# و Visual Studio.  
- مكتبة Aspose.Zip for .NET مثبتة. احصل عليها من صفحة التحميل الرسمية **[here](https://releases.aspose.com/zip/net/)**.  
- مجلد (`dataDir`) يحتوي على الملفات التي تريد أرشفتها.

## استيراد المساحات الاسمية

أولاً، أضف المساحات الاسمية المطلوبة إلى ملف C# الخاص بك:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

هذه الفئات تمنحك الوصول إلى إعدادات الضغط ومعالجة الأرشيف.

## ضغط LZMA2 – كيفية إنشاء ملف 7z بأعلى نسبة ضغط

`Archive` تمثل أرشيف 7z يمكنه احتواء ملفات متعددة.  
توفر خوارزمية LZMA2 أعلى نسبة ضغط بين الطرق المدعومة. تعمل عن طريق تقسيم الإدخال إلى كتل وتطبيق ضغط معجم متقدم. في Aspose.Zip تقوم بتعيين `CompressionMethod` إلى `CompressionMethod.Lzma2` على كائن `Archive` قبل إضافة الملفات.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **نصيحة احترافية:** يعمل LZMA2 بأفضل شكل عندما تكون ملفات المصدر أكبر من 1 MB. بالنسبة للعديد من الملفات الصغيرة، قد يكون BZip2 أسرع.

## ضغط BZip2 – خيار متوازن

`Archive` تمثل أرشيف 7z يمكنه احتواء ملفات متعددة.  
BZip2 يوفر ضغطاً ثابتاً مع توافق جيد للأدوات القديمة. يستخدم تحويل Burrows‑Wheeler وترميز Huffman لتقليل الحجم. في Aspose.Zip تختار `CompressionMethod.BZip2` عند تكوين كائن `Archive`، مما يوازن بين السرعة ونسبة الضغط لمعظم الملفات النصية والثنائية.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 يقدم ضغطاً ثابتاً مع الحفاظ على سرعة معقولة، مما يجعله خياراً جيداً كبديل عندما لا يكون LZMA2 مدعوماً في البيئة المستهدفة.

## التخزين (بدون ضغط) – عندما لا يهم الحجم

`Archive` تمثل أرشيف 7z يمكنه احتواء ملفات متعددة.  
طريقة Store تنشئ أرشيفاً دون ضغط البيانات. إنها ببساطة تنسخ الملفات الأصلية إلى حاوية 7z، مع الحفاظ على الطوابع الزمنية وبنية الدليل. لاستخدامها في Aspose.Zip، اضبط `CompressionMethod.Store` على `Archive` قبل إضافة الملفات التي ترغب في تجميعها.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

استخدم طريقة Store إذا كنت تحتاج فقط إلى تجميع الملفات معاً دون تعديل حجمها — مثالية للحفاظ على الطوابع الزمنية الأصلية أو عندما يتم فك ضغط الأرشيف مباشرةً.

## كيف أضيف ملفات إلى 7z؟

أضف ملفات إلى أرشيف 7z بإنشاء مثيل `Archive`، ضبط `CompressionMethod` المطلوب، واستدعاء `AddAllFiles(dataDir)`. تقوم الطريقة بمسح المجلد المحدد بشكل متكرر، مع الحفاظ على هيكل الدليل داخل الأرشيف. يتيح لك هذا النهج **compress folder to 7z** بسطر واحد من الكود بعد الإعداد الأولي.

## حالات الاستخدام الشائعة

| السيناريو | الطريقة الموصى بها |
|----------|--------------------|
| توزيع مثبتات كبيرة | LZMA2 |
| مشاركة السجلات مع الأدوات القديمة | BZip2 |
| حزم الملفات لاستخراج سريع | Store (no compression) |
| الحاجة إلى **compress folder to 7z** مباشرةً في خدمة ويب | LZMA2 (for best ratio) |

## استكشاف الأخطاء وإصلاحها والنصائح

- **ملفات مفقودة في الأرشيف؟** تحقق من أن `dataDir` يشير إلى الدليل الصحيح وأن العملية لديها أذونات قراءة.  
- **فشل الأرشيف في الفتح على إصدارات 7‑Zip القديمة؟** التزم بـ BZip2 أو Store، حيث قد يتطلب LZMA2 مكتبات فك ضغط أحدث.  
- **عنق زجاجة في الأداء؟** لمجموعات بيانات ضخمة، فكر في تدفق الأرشيف بدلاً من تحميل جميع الإدخالات في الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Zip for .NET مع أي نوع من الملفات؟**  
ج: نعم، يدعم Aspose.Zip مجموعة واسعة من تنسيقات الملفات، مما يتيح لك ضغط وفك ضغط أي نوع من الملفات تقريباً.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Zip for .NET؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية **[here](https://releases.aspose.com/)**.

**س: أين يمكنني العثور على وثائق Aspose.Zip for .NET؟**  
ج: المرجع الكامل للـ API متاح **[here](https://reference.aspose.com/zip/net/)**.

**س: كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Zip for .NET؟**  
ج: يمكن الحصول على تراخيص مؤقتة **[here](https://purchase.aspose.com/temporary-license/)**.

**س: أين يمكنني الحصول على الدعم لـ Aspose.Zip for .NET؟**  
ج: يمكنك طلب الدعم في **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**آخر تحديث:** 2026-06-29  
**تم الاختبار مع:** Aspose.Zip for .NET 24.12  
**المؤلف:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [ضغط الملفات c# – إنشاء أرشيف 7z باستخدام Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [كيفية ضغط مجلد باستخدام Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [كيفية ضغط LZMA في Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}