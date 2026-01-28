---
date: 2026-01-28
description: تعلم كيفية استخراج الأرشيف باستخدام كلمة مرور، وضغط الملفات إلى TarBz2،
  وإنشاء أرشيفات TarGz باستخدام Aspose.Zip لـ .NET. عزّز كفاءة التخزين والأمان.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: استخراج الأرشيف باستخدام كلمة مرور وضغط إلى TarBz2 (.NET)
url: /ar/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج الأرشيف باستخدام كلمة مرور وضغط إلى TarBz2 (.NET)

في هذا الدليل ستكتشف **how to extract archive with password** وتتمكن أيضاً من إتقان **compress files to TarBz2** باستخدام Aspose.Zip for .NET. سواءً كنت تبني خدمة نسخ احتياطي، أو عميل تخزين سحابي، أو خط أنابيب لمعالجة البيانات، فإن هذه التقنيات تتيح لك تقليل حجم التخزين، تسريع النقل، وحماية البيانات الحساسة.

## Quick Answers
- **What is TarBz2?** أرشيف مضغوط يجمع بين حزمة TAR وضغط BZIP2 للحصول على نسب ضغط عالية.  
- **Why choose Aspose.Zip for .NET?** يوفر واجهة برمجة تطبيقات واحدة وسلسة للعديد من صيغ الأرشيف دون الاعتماد على مكوّنات أصلية.  
- **Can I create a TarGz archive?** نعم – يدعم Aspose.Zip صيغ TarGz، TarLz، TarXz، TarZ، وغيرها.  
- **How do I extract a password‑protected archive?** قم بتعيين خاصية `Password` على كل `ArchiveEntry` قبل الاستخراج.  
- **Do I need a license for production use?** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية للتقييم.

## How to extract archive with password using Aspose.Zip for .NET
استخراج أرشيف **password protect zip archive** محمي بكلمة مرور أمر بسيط. تفتح الأرشيف، تحدد العنصر المطلوب، تعيين كلمة المرور له، ثم تستدعي `Extract`. يعمل هذا النهج مع TarBz2، TarGz، وغيرها من الصيغ المدعومة.

## What does “compress files to TarBz2” actually mean?
ضغط الملفات إلى TarBz2 يعني أولاً تجميع ملفات ومجلدات متعددة في حاوية **TAR** واحدة، ثم تطبيق ضغط **BZIP2**. النتيجة هي ملف `.tar.bz2` سهل النقل ومضغوط بشكل كبير.

## Why use Aspose.Zip for .NET to handle these formats?
- **Unified API** – مكتبة واحدة، صيغ متعددة (TarBz2، TarGz، TarLz، TarXz، TarZ).  
- **No native dependencies** – يعمل على Windows، Linux، و macOS مباشرة.  
- **Password support** – حماية واستخراج الأرشيفات بكلمات مرور لكل عنصر.  
- **Performance‑focused** – المعالجة عبر التدفق تقلل من استهلاك الذاكرة.

## Prerequisites
- .NET 6.0 أو أحدث (أو .NET Core 3.1+ / .NET Framework 4.5+).  
- حزمة NuGet الخاصة بـ Aspose.Zip for .NET مثبتة (`Install-Package Aspose.Zip`).  
- معرفة أساسية بـ C# وإدخال/إخراج الملفات.

## Step‑by‑Step Guide

### Step 1: Choose the archive format you need
حدد ما إذا كان **TarBz2**، **TarGz**، **TarLz**، **TarXz** أو **TarZ** هو الأنسب لنسبة الضغط ومتطلبات التوافق الخاصة بك.  
- **TarBz2** – أعلى نسبة ضغط، معالجة أبطأ.  
- **TarGz** – توازن جيد بين السرعة والحجم (يغطي الكلمة المفتاحية الثانوية *compress files to targz*).  
- **TarZ** – صيغة قديمة لأدوات Unix القديمة.

### Step 2: Create a new `Archive` instance
أنشئ كائن من فئة `Archive` وحدد مسار ملف الإخراج. سيتولى هذا الكائن عملية التجميع والضغط.

### Step 3: Add files and folders
استخدم أساليب `AddAll` أو `AddFile` لإضافة الملفات التي تريد ضغطها. حافظ على هيكل المجلدات بإضافة المجلد الأساسي.

### Step 4: Set the desired compression type
حدد خوارزمية الضغط (`CompressionType.BZip2`، `CompressionType.GZip`، إلخ) عند حفظ الأرشيف. هنا تقوم فعلياً بـ **compress files to tarbz2** أو أي صيغة أخرى.

### Step 5: Save the archive
استدعِ `Save` مع تعداد الصيغة المناسب (`ArchiveFormat.TarBz2`، `ArchiveFormat.TarGz`، إلخ). تقوم المكتبة بكتابة حاوية TAR وتطبيق الضغط المختار في خطوة واحدة.

### Step 6: Extract archives with passwords
إذا كنت بحاجة إلى **extract archive entries with different passwords** (الكلمة المفتاحية الثانوية *how to extract password protected archive*), افتح الأرشيف، حدد كل عنصر، عيّن كلمة المرور الخاصة به، ثم استخرج.

### Step 7: Verify the result
بعد الاستخراج، قارن أحجام الملفات والـ checksums للتأكد من أن الأرشيف تم إنشاؤه وفك ضغطه بشكل صحيح.

## Common Use Cases
- **Backup utilities** – احفظ النسخ الاحتياطية اليومية كملفات `.tar.bz2` لتقليل تكاليف التخزين.  
- **Cross‑platform data exchange** – صيغ Tar مفهومة عالمياً على Linux، macOS، و Windows.  
- **Secure distribution** – احمِ العناصر الفردية بكلمات مرور لتلبية متطلبات الامتثال.

## Troubleshooting & Tips
- **Large archives** – استخدم واجهات التدفق (`Archive.CreateEntryFromFile`) لتجنب تحميل الملفات بالكامل في الذاكرة.  
- **Password mismatches** – تأكد من أن كلمة المرور المعينة لكل `ArchiveEntry` تطابق ما تم استخدامه أثناء الاستخراج؛ وإلا ستواجه `InvalidPasswordException`.  
- **Unsupported compression level** – لا يدعم BZIP2 مستويات ضغط مخصصة؛ إذا احتجت تحكمًا أدق، فكر في TarLz أو TarXz.  
- **Performance tip** – عند إنشاء **create tarbz2 archive**، فعّل التخزين المؤقت على الدفق الأساسي لتحسين سرعة الكتابة.

## Frequently Asked Questions

**س: كيف يمكنني إنشاء أرشيف TarGz؟**  
ج: عيّن نوع الضغط إلى `CompressionType.GZip` والصيغة إلى `ArchiveFormat.TarGz` عند استدعاء `Save`.

**س: هل يمكن استخراج أرشيف محمي بكلمة مرور دون معرفة كلمة المرور؟**  
ج: لا. يجب توفير كلمة المرور الصحيحة لكل عنصر؛ وإلا سيفشل الاستخراج.

**س: هل يدعم Aspose.Zip استخراج الأرشيفات بكلمات مرور مختلفة لكل عنصر؟**  
ج: نعم. يمكنك تعيين كلمة مرور لكل `ArchiveEntry` على حدة قبل الاستخراج.

**س: أي صيغة توفر أعلى نسبة ضغط؟**  
ج: عادةً ما توفر TarBz2 أعلى نسبة ضغط، تليها TarLz و TarXz. TarGz تقدم توازناً جيداً بين السرعة والحجم.

**س: هل هناك حد لعدد الملفات التي يمكن إضافتها إلى أرشيف TAR؟**  
ج: عملياً لا يوجد حد، لكن الأرشيفات الضخمة جداً قد تستفيد من تقسيمها إلى أجزاء متعددة لتسهيل التعامل معها.

## Archive Extraction and Formats Tutorials
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
تعلم كيفية ضغط الملفات إلى صيغة TarBz2 في .NET باستخدام Aspose.Zip. اتبع دليلنا خطوة‑بخطوة لضغط فعال للملفات.
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
استكشف ضغط الملفات بكفاءة في .NET باستخدام Aspose.Zip. اضغط إلى TarGz بسهولة.
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
ضغط الملفات في .NET باستخدام Aspose.Zip بسهولة. تعلم إنشاء أرشيفات TarLz خطوة‑بخطوة.
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
تعلم كيفية ضغط الملفات إلى صيغة TarXz في .NET باستخدام Aspose.Zip. اتبع دليلنا خطوة‑بخطوة لتخزين ونقل الملفات بفعالية.
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
استكشف ضغط الملفات إلى TarZ خطوة‑بخطوة باستخدام Aspose.Zip for .NET. معالجة ملفات فعالة لمشروعات .NET الخاصة بك.
### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
تعلم كيفية استخراج عناصر الأرشيف بكلمات مرور مختلفة في Aspose.Zip for .NET. عزز الأمان والمرونة في تطبيقاتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose  

---