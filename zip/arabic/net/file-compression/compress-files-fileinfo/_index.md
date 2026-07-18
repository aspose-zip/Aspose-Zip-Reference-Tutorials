---
date: 2026-07-18
description: تعرف على كيفية إضافة مجلد إلى ملف zip وإضافة ملفات إلى ملف zip باستخدام
  Aspose.Zip لـ .NET. يوضح هذا الدليل خطوة بخطوة كيفية ضغط الملفات باستخدام FileInfo
  في مشاريع ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: ضغط الملفات باستخدام FileInfo
og_description: إضافة مجلد إلى ملف zip باستخدام Aspose.Zip لـ .NET. تعرف على كيفية
  إنشاء أرشيف zip، وإضافة ملفات إلى zip، وضغط المجلدات بفعالية في ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: إضافة مجلد إلى ملف zip – ضغط الملفات باستخدام Aspose.Zip لـ .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: إضافة مجلد إلى ملف zip باستخدام Aspose.Zip لـ .NET – ضغط الملفات باستخدام FileInfo
url: /ar/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مجلد إلى ملف Zip باستخدام Aspose.Zip لـ .NET

## المقدمة

إذا كنت بحاجة إلى **إضافة مجلد إلى zip** برمجياً، فإن Aspose.Zip لـ .NET يقدم واجهة برمجة تطبيقات نظيفة وعالية الأداء تعمل في أي تطبيق .NET (بما في ذلك ASP.NET). في هذا الدرس سنستعرض ضغط الملفات باستخدام فئة `FileInfo`، نوضح لك كيفية **إضافة ملفات إلى zip**، ونشرح لماذا يعتبر هذا النهج مثالياً لمشاريع .NET الحديثة. سنغطي أيضاً الخطوات الدقيقة لـ **إضافة مجلد إلى zip** حتى تتمكن من تجميع دلائل كاملة في عملية واحدة. لنبدأ!

## إجابات سريعة
- **ما هي أسهل طريقة لإنشاء أرشيف zip؟** استخدم فئة `Archive` في Aspose.Zip مع كائنات `FileInfo`.  
- **هل يمكنني إضافة ملفات متعددة مرة واحدة؟** نعم – فقط أنشئ `FileInfo` لكل ملف واستدعِ `CreateEntry`.  
- **هل أحتاج إلى ترخيص خاص لـ ASP.NET؟** يتطلب الترخيص التجاري لـ Aspose.Zip للإنتاج؛ النسخة التجريبية المجانية تكفي للتقييم.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10.  
- **هل الواجهة برمجة التطبيقات آمنة للاستخدام المتعدد الخيوط؟** نعم، طالما أن كل خيط يستخدم نسخة `Archive` خاصة به.

## ما هو ملف Zip ولماذا إنشاؤه؟
ملف zip يجمع ملفًا أو أكثر في حاوية مضغوطة واحدة. هذا يقلل من مساحة التخزين، يسرّع نقل البيانات عبر الشبكة، ويبسّط عملية التوزيع. سواءً كنت تُرسل سجلات، تُصدّر تقارير، أو تُحزم موارد لعميل، فإن معرفة **كيفية إنشاء ملفات zip** برمجياً مهارة قيمة لأي مطور .NET.

## لماذا تستخدم Aspose.Zip لإضافة ملفات إلى Zip؟
توفر Aspose.Zip حلاً نقيًا لـ .NET يُزيل الاعتماديات الخارجية مع منح المطورين تحكمًا دقيقًا في الضغط، الترميز، والأمان. تدعم ملفات كبيرة، حماية بكلمة مرور، وتعمل بشكل ثابت عبر جميع إصدارات .NET المدعومة، مما يجعلها خيارًا موثوقًا للتطبيقات القديمة والحديثة على حد سواء.  

- **عدم وجود اعتماديات خارجية** – تنفيذ نقي بـ .NET.  
- **تحكم كامل في مستوى الضغط والترميز** (ASCII، UTF‑8، إلخ).  
- **يدعم ملفات أكبر من 4 GB** وحماية بكلمة مرور.  
- **واجهة برمجة تطبيقات موحدة عبر أكثر من 50 نسخة .NET** – من .NET Framework 2.0 حتى .NET 10.  

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

1. **Aspose.Zip لـ .NET** مثبت. حمّل أحدث حزمة من [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. مجلد على جهازك يحتوي على الملفات التي تريد ضغطها (مثل `alice29.txt` و `fields.c`).  

## استيراد مساحات الأسماء

في أي ملف C# ستعمل فيه مع أرشيفات zip، أضف عبارات `using` التالية:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

هذه المساحات تمنحك الوصول إلى فئة `Archive`، خيارات الحفظ، وأدوات الإدخال/الإخراج القياسية.

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل المستند الخاص بك

أولاً، عرّف المجلد الذي يحتوي على الملفات المصدر. استبدل العنصر النائب بالمسار المطلق أو النسبي على نظامك:

```csharp
string dataDir = "Your Document Directory";
```

> **نصيحة احترافية:** استخدم `Path.Combine` لبناء المسارات بطريقة متعددة المنصات.

### الخطوة 2: فتح ملف Zip للكتابة

أنشئ `FileStream` يشير إلى ملف zip الناتج. يُفتح التيار في وضع **Create**، مما يستبدل أي ملف موجود بنفس الاسم:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### الخطوة 3: إعداد كائنات `FileInfo` لكل ملف مصدر

توفر `FileInfo` وصولًا مباشرًا لـ Aspose.Zip إلى الملفات الفعلية على القرص. أنشئ نسخة واحدة لكل ملف تريد ضغطه:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **لماذا نستخدم `FileInfo`؟** يتجنّب تحميل الملف بالكامل إلى الذاكرة، وهو أمر مفيد خصوصًا للملفات الكبيرة.

### الخطوة 4: إنشاء الأرشيف وإضافة الإدخالات

فئة `Archive` هي الكائن الأساسي في Aspose.Zip الذي يمثل حاوية zip في الذاكرة. أنشئ كائن `Archive`، ثم استدعِ `CreateEntry` لكل `FileInfo`. الوسيط الأول هو الاسم الذي سيظهر داخل zip، والوسيط الثاني هو `FileInfo` المصدر:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

طريقة `CreateEntry` تضيف إدخال ملف جديد إلى الأرشيف، ربطًا بين اسم الإدخال و`FileInfo` المصدر بحيث يتم تدفق البيانات مباشرة من القرص عند حفظ الأرشيف.

### الخطوة 5: حفظ أرشيف Zip باستخدام الترميز المطلوب

أخيرًا، احفظ الأرشيف إلى `FileStream` الذي فتحته مسبقًا. هنا نستخدم ترميز ASCII لأسماء الإدخالات، لكن يمكنك التبديل إلى UTF‑8 إذا احتوت أسماء الملفات على أحرف غير ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

عند خروج كتل `using`، تُغلق التيارات تلقائيًا ويصبح ملف zip جاهزًا للاستخدام.

## كيفية إضافة مجلد إلى Zip باستخدام Aspose.Zip؟

حمّل الدليل المستهدف، عدّد كل ملف، وأضف كل واحد بمسار نسبي يتضمن اسم المجلد. يتيح لك هذا النهج **إضافة مجلد إلى zip** دون الحاجة إلى سرد كل ملف يدويًا. من خلال الحفاظ على هيكل المجلد في أسماء الإدخالات، يمكن استخراج الأرشيف مع الحفاظ على بنية الدليل الأصلية، وهو أمر أساسي للعديد من سيناريوهات النشر.

1. استخدم `DirectoryInfo` لتحديد المجلد الذي تريد ضغطه.  
2. استدعِ `GetFiles("*", SearchOption.AllDirectories)` لاسترجاع جميع الملفات بشكل متكرر.  
3. لكل ملف، أنشئ `FileInfo` واستدعِ `CreateEntry` بمسار مثل `"MyFolder/Report.pdf"`.  

نظرًا لأن الواجهة تعمل مع `FileInfo`، فإنها تُدفق كل ملف مباشرة من القرص، مما يحافظ على استهلاك الذاكرة منخفضًا حتى في المجلدات التي تحتوي على مئات الميغابايت.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **ملف zip فارغ** | `FileInfo` يشير إلى مسار غير موجود | تحقق من `dataDir` وأسماء الملفات؛ استخدم `File.Exists` للتحقق قبل إنشاء الإدخالات. |
| **ترميز اسم الملف غير صحيح** | استخدام الترميز الافتراضي مع أسماء غير ASCII | عيّن `Encoding = Encoding.UTF8` في `ArchiveSaveOptions`. |
| **OutOfMemoryException عند ملفات كبيرة** | تحميل الملف بالكامل إلى الذاكرة | `FileInfo` يُدفق الملف؛ تأكد من عدم قراءة الملف إلى مصفوفة بايت في مكان آخر. |
| **رفض الإذن** | التطبيق يفتقر إلى صلاحية كتابة في المجلد الهدف | شغّل التطبيق بصلاحيات مناسبة أو اختر دليلًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة مجلد كامل إلى أرشيف zip في استدعاء واحد؟**  
ج: لا توجد طريقة استدعاء واحدة، لكن عدّ الملفات باستخدام `DirectoryInfo` وإضافتها كلًّا عبر `CreateEntry` يحقق النتيجة نفسها بكفاءة.

**س: هل يدعم Aspose.Zip حماية بكلمة مرور؟**  
ج: نعم، يمكنك تعيين كلمة مرور على كائن `Archive` قبل الحفظ لتشفير الأرشيف بالكامل.

**س: ما الحد الأقصى لحجم ملف zip الذي يمكن لـ Aspose.Zip التعامل معه؟**  
ج: المكتبة تعالج ملفات أكبر من 4 GB ويمكنها إنشاء أرشيفات تتجاوز 10 GB دون تحميل الأرشيف بالكامل إلى الذاكرة.

**س: هل الواجهة متوافقة مع .NET 6 و .NET 8؟**  
ج: بالتأكيد. يدعم Aspose.Zip .NET 5 حتى .NET 10، بما يغطي جميع إصدارات LTS الحالية.

**س: ما مستويات الضغط المتاحة؟**  
ج: يمكنك اختيار `CompressionLevel.NoCompression`، `Fast`، `Normal`، أو `Maximum` لتوازن بين السرعة والحجم.

## موارد إضافية

- حمّل أحدث حزمة Aspose.Zip: [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net/)  
- اشترِ ترخيصًا للاستخدام في الإنتاج: [صفحة الشراء](https://purchase.aspose.com/buy)  
- احصل على مساعدة من المجتمع: [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37)  
- جرّب Aspose.Zip مجانًا: [التجربة المجانية هنا](https://releases.aspose.com/)  
- احصل على ترخيص مؤقت للتقييم: [هذا الرابط](https://purchase.aspose.com/temporary-license/)

## الخاتمة

أنت الآن تعرف **كيفية إضافة مجلد إلى zip** و**كيفية إنشاء ملفات zip** باستخدام Aspose.Zip لـ .NET، وكيفية **إضافة ملفات إلى zip**، ولماذا هذه الطريقة مثالية لتطبيقات ASP.NET وغيرها من تطبيقات .NET. جرّب مستويات ضغط مختلفة، ترميزات، وخيارات تشفير لتخصيص الأرشيف وفق احتياجاتك الدقيقة. ضغطًا سعيدًا!

---

**آخر تحديث:** 2026-07-18  
**تم الاختبار مع:** Aspose.Zip لـ .NET 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Effortless Compression with Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Archive .NET – File Compression with Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}