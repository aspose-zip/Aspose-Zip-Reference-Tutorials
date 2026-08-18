---
date: 2026-07-04
description: تعلم كيفية ضغط ملفات متعددة بصيغة tar باستخدام Aspose.Zip for .NET وإنشاء
  أرشيفات tar.lz بكفاءة.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: الضغط إلى TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط ملفات متعددة بصيغة tar باستخدام Aspose.Zip for .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط ملفات متعددة بصيغة tar باستخدام Aspose.Zip لـ .NET

في تطوير .NET الحديث، يمكن أن يؤدي تجميع الملفات بكفاءة إلى تحسين حجم النشر وأوقات نقل البيانات بشكل كبير. **Compress multiple files tar** هو مطلب شائع عندما تحتاج إلى أرشيف TAR خفيف الوزن ومضغط بـ LZ للنسخ الاحتياطية أو التوزيع أو التحميل إلى السحابة. في هذا البرنامج التعليمي سنستعرض مثالًا واضحًا خطوة بخطوة **tar.lz compression example** باستخدام مكتبة Aspose.Zip، حتى تتمكن من إنشاء **tar.lz archive** بسرعة في تطبيقاتك.

## إجابات سريعة
- **What library should I use?** Aspose.Zip for .NET.  
- **How long does the implementation take?** حوالي 5‑10 دقائق لمثال أساسي.  
- **Do I need a license?** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **Which .NET versions are supported?** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **Can I compress multiple files at once?** نعم – فقط أضف المزيد من الإدخالات قبل الحفظ.

## كيف يمكنني ضغط ملفات متعددة بصيغة tar باستخدام Aspose.Zip لـ .NET؟
حمّل ملفات المصدر الخاصة بك، أنشئ كائن `TarArchive`، أضف كل ملف باستخدام `CreateEntry`، واختتم باستدعاء `SaveLzipped`. تتولى المكتبة معالجة بنية TAR وضغط LZ داخليًا، لذا ستحصل على ملف `*.tar.lz` واحد في بضع أسطر من الشيفرة فقط. يعمل هذا النهج على Windows وLinux وmacOS دون أي تبعيات أصلية.

## ما هو ضغط tar.lz؟
`tar.lz` هو أرشيف TAR تم ضغطه باستخدام خوارزمية LZMA (المعروفة غالبًا ببساطة باسم **LZ**). يجمع بين بساطة تجميع الملفات في TAR ونسبة الضغط العالية التي توفرها LZ، مما يجعله مثاليًا للنسخ الاحتياطية، توزيع الحزم، أو أي سيناريو حيث تكون سعة النطاق مهمة.

## لماذا نستخدم Aspose.Zip لـ .NET؟
توفر Aspose.Zip حلاً مُدارًا بالكامل، متعدد المنصات، يُنشئ أرشيفات TAR وZIP وذات أساس LZ دون الحاجة إلى أدوات خارجية، يدعم أكثر من 30 تنسيق أرشيف، ويقدم ضغطًا يصل إلى 30 % أفضل على الملفات الكبيرة، مع توفير استثناءات مفصلة لمعالجة الأخطاء بشكل قوي. كما يتكامل بسلاسة مع أطر تسجيل .NET ويقدم أحداث تقدم مفصلة.

## المتطلبات المسبقة
- **Aspose.Zip for .NET** library – قم بتنزيله من [here](https://releases.aspose.com/zip/net/).  
- مجلد يحتوي على الملفات التي تريد أرشفتها. سيتم تخزين مسار هذا المجلد في المتغيّر `dataDir` (ستقوم بتعيينه في الخطوة 3).

## استيراد مساحات الأسماء
أضف مساحات الأسماء المطلوبة حتى يعرف المترجم أين يجد الفئات التي سنستخدمها.

```csharp
using System;
using Aspose.Zip.Tar;
```

## كيفية إنشاء أرشيف tar.lz – دليل خطوة بخطوة

### الخطوة 1: ضغط ملف واحد
المثال الأول يوضح أبسط سيناريو – إضافة ملف واحد إلى أرشيف TAR ثم حفظه كملف **tar.lz**.

تمثل الفئة `TarArchive` حاوية TAR يمكنها احتواء ملفات متعددة في أرشيف واحد.

**شرح**

- `new TarArchive()` ينشئ حاوية TAR فارغة.  
- `CreateEntry` يضيف الملف `alice29.txt` من `dataDir` الخاص بك.  
- `SaveLzipped` يكتب الأرشيف إلى القرص ويطبق ضغط LZ، منتجًا `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### الخطوة 2: ضغط ملفات متعددة في أرشيف واحد
غالبًا ما ستحتاج إلى تجميع عدة ملفات معًا. ما عليك سوى استدعاء `CreateEntry` لكل ملف قبل الحفظ. يوضح هذا **add files to tar lz** و**compress multiple files tar** بفعالية.

**شرح**

- يتبع الكود نفس نمط الخطوة 1، لكنه يضيف إدخالًا ثانيًا (`lcet10.txt`).  
- يمكنك تكرار `CreateEntry` عددًا لا نهائيًا من المرات حسب الحاجة؛ تتولى المكتبة معالجة بنية TAR الداخلية تلقائيًا.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### الخطوة 3: تحديد دليل المستند الخاص بك
استبدل العنصر النائب بالمسار الفعلي حيث توجد ملفات المصدر الخاصة بك. يُستخدم هذا المسار في الأمثلة أعلاه.

**شرح**

- عيّن `dataDir` إلى مسار مجلد مؤهل بالكامل، مثال: `@"C:\MyFiles\"`.  
- حفظ الدليل في متغيّر يجعل الشيفرة قابلة لإعادة الاستخدام وأسهل في الصيانة.

```csharp
string dataDir = "Your Document Directory";
```

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| `FileNotFoundException` عند تشغيل العينة | `dataDir` يشير إلى مجلد غير موجود أو اسم الملف مكتوب بشكل خاطئ | تحقق من المسار وأسماء الملفات؛ استخدم `Path.Combine` للسلامة. |
| ملف الإخراج هو **0 KB** | `archive.SaveLzipped` تم استدعاؤه قبل إضافة أي إدخالات | تأكد من وجود استدعاء واحد على الأقل لـ `CreateEntry` قبل `SaveLzipped`. |
| يبدو أن الضغط بطيء | ملفات كبيرة بحجم المخزن المؤقت الافتراضي | فكّر في معالجة الملفات على دفعات أو استخدام I/O غير متزامن إذا كانت الأداء أمرًا حاسمًا. |

## الخلاصة
أنت الآن تعرف **how to compress tar.lz** الملفات باستخدام Aspose.Zip لـ .NET، سواء كنت تتعامل مع مستند واحد أو مجموعة من الملفات. يوضح هذا **tar.lz compression example** طريقة نظيفة وجاهزة للإنتاج **create tar lz archive** الملفات التي يمكن نقلها أو تخزينها بسهولة. يمكنك ضغط الملفات إلى tar.lz باستخدام نفس الـ API عبر استدعاء `SaveLzipped` بعد إضافة جميع الإدخالات المطلوبة.

## الأسئلة المتكررة

**Q:** هل يمكنني ضغط ملفات بأي حجم باستخدام Aspose.Zip لـ .NET؟  
**A:** نعم، تتعامل المكتبة مع الملفات الصغيرة والكبيرة جدًا؛ فقط تأكد من توفر الذاكرة ومساحة القرص الكافية للبنية المؤقتة لـ TAR.

**Q:** هل الشيفرة متوافقة مع أحدث إصدار من Aspose.Zip؟  
**A:** العينة تستهدف الإصدار الحالي؛ احرص دائمًا على تحديث حزمة NuGet للحصول على إصلاحات الأخطاء والميزات الجديدة.

**Q:** هل هناك اعتبارات ترخيص؟  
**A:** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج. راجع تفاصيل الترخيص على [Aspose website](https://purchase.aspose.com/buy).

**Q:** هل يمكنني استخدام هذا في مشروع تجاري؟  
**A:** بالتأكيد – بمجرد حصولك على ترخيص صالح، يمكنك دمج المكتبة في أي تطبيق تجاري.

**Q:** أين يمكنني الحصول على المساعدة إذا واجهت مشاكل؟  
**A:** زر [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) للحصول على دعم المجتمع والمساعدة الرسمية.

**آخر تحديث:** 2026-07-04  
**تم الاختبار مع:** Aspose.Zip for .NET (latest release)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [كيفية ضغط tar وإنشاء TarBz2 باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}