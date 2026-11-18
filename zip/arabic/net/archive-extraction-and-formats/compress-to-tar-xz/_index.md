---
date: 2026-11-18
description: تعلم كيفية إضافة ملفات إلى tar وضغطها إلى أرشيف tarxz باستخدام .NET و
  Aspose.Zip. اتبع هذا الدليل خطوة بخطوة لتخزين ونقل فعال.
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: الضغط إلى TarXz
og_description: إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip. تعلم كيفية
  ضغط الملفات إلى TarXz في .NET بسرعة، مع كفاءة ضغط عالية و cross‑platform compatibility.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip
url: /ar/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip

## مقدمة

إذا كنت بحاجة إلى **إضافة ملفات إلى tar** ثم **إنشاء أرشيف tarxz .net**، فإن Aspose.Zip for .NET يجعل العملية بسيطة وموثوقة. سواءً كنت تقوم بتجميع السجلات، ملفات التكوين، أو أي أصول أخرى للتخزين أو النقل، فإن الضغط إلى تنسيق TarXz يمنحك نسبة ضغط عالية مع الحفاظ على بنية tar المألوفة. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة—مع مقتطفات الشيفرة—حتى تتمكن من دمج إنشاء tarxz في تطبيقات .NET الخاصة بك بثقة. في النهاية ستفهم لماذا تُعد “إضافة ملفات إلى tar” الخطوة الأولى نحو حزمة مضغوطة ومتعددة المنصات.

## إجابات سريعة
- **ما هي الفئة الأساسية؟** `TarArchive` from `Aspose.Zip.Tar`
- **كيف أقوم بالضغط إلى tarxz؟** Call `SaveXzCompressed` after adding entries
- **ما إصدارات .NET المدعومة؟** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **هل أحتاج إلى ترخيص؟** نعم، ترخيص Aspose.Zip صالح مطلوب للاستخدام في الإنتاج.
- **مدة التنفيذ؟** حوالي 5‑10 دقائق لأرشيف أساسي.

## ما هو أرشيف TarXz؟

يجمع أرشيف TarXz بين حاوية Unix التقليدية `tar` مع ضغط XZ. الجزء tar يجمع ملفات متعددة في تدفق واحد، بينما يوفر XZ ضغطًا قويًا وغير فقداني. هذا التنسيق شائع لتوزيع شفرة المصدر، النسخ الاحتياطية، ومجموعات البيانات الكبيرة لأنه يحافظ على هياكل الدليل ويحقق أحجام ملفات أصغر مقارنةً بـ tar أو zip العادي.

## لماذا إنشاء أرشيف tarxz .net باستخدام Aspose.Zip؟

إنشاء أرشيف TarXz باستخدام Aspose.Zip يوفر حلاً سريعًا بخطوة واحدة دون الحاجة إلى أدوات خارجية. تكون الملفات أصغر بنسبة 30‑50 % مقارنةً بـ gzip ويمكنك التعامل مع أكثر من 20 تنسيق أرشيف مباشرة في .NET. تقوم المكتبة بمعالجة الأرشيفات الكبيرة دون تحميل الملف بالكامل إلى الذاكرة، مما يجعلها مثالية لخدمات السحابة وأنابيب CI. كما أنها تدعم أكثر من 50 تنسيق إدخال وإخراج.

## المتطلبات المسبقة

- **Aspose.Zip for .NET** مثبت (قم بتنزيله من [توثيق Aspose.Zip الرسمي](https://reference.aspose.com/zip/net/)).  
- مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة أدناه، يتم الإشارة إلى هذا المجلد بواسطة المتغير `dataDir`.  
- ترخيص Aspose.Zip صالح (اختياري للتقييم، مطلوب للإنتاج).

## استيراد مساحات الأسماء

أنت بحاجة فقط إلى استيراد مساحات الأسماء التي تكشف عن وظيفة TarXz. لا توجد حزم إضافية مطلوبة بخلاف مكتبة Aspose.Zip الأساسية.

## كيفية إضافة ملفات إلى tar باستخدام Aspose.Zip

`TarArchive` هي الفئة التي تمثل حاوية tar في Aspose.Zip. تقوم بإضافة ملفات إلى أرشيف tar عن طريق إنشاء مثيل `TarArchive`، ثم استدعاء طريقة `AddEntry` لكل ملف تريد تضمينه، مع تحديد مسار المصدر واسم الإدخال الاختياري. يبني الأرشيف حاوية tar في الذاكرة، جاهزة للضغط بـ XZ لاحقًا.

```csharp
using System;
using Aspose.Zip.Tar;
```

> **نصيحة احترافية:** يضمن بيان `using` التخلص السليم من الأرشيف، وإطلاق أي موارد غير مُدارة.

### الخطوة 1: تهيئة `TarArchive`

أنشئ كائن `TarArchive` داخل كتلة `using` بحيث يتم تحرير جميع الموارد غير المُدارة تلقائيًا عند إكمال العملية.

```csharp
using (TarArchive archive = new TarArchive())
{
```

### الخطوة 2: إضافة ملفات إلى الأرشيف

أضف كل ملف ترغب في تضمينه. في هذا المثال نضيف ملفين نصيين، لكن يمكنك إضافة عدد غير محدود من الإدخالات حسب الحاجة. تقبل طريقة `AddEntry` مسار الملف الكامل واسم إدخال اختياري سيظهر داخل tar.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **لماذا هذا مهم:** إضافة الإدخالات قبل الضغط يسمح لـ Aspose.Zip ببناء حاوية tar أولاً، ثم تطبيق ضغط XZ في خطوة واحدة.

### الخطوة 3: حفظ الأرشيف مع ضغط XZ

تكتب طريقة `SaveXzCompressed` أرشيف tar إلى ملف مع تطبيق ضغط XZ في خطوة واحدة، مما ينتج ملف `.tar.xz` جاهز للتوزيع.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **النتيجة:** لديك الآن ملف `archive.tar.xz` مضغوط بالكامل يمكن نقله، تخزينه، أو فك ضغطه على أي منصة تدعم TarXz.

## كيفية ضغط ملفات tarxz باستخدام Aspose.Zip

ضغط إلى tarxz باستخدام Aspose.Zip هو عملية من خطوتين مغلّفة في استدعاء طريقة واحدة: أولاً تقوم **بإضافة ملفات إلى tar**، ثم تستدعي `SaveXzCompressed`. هذا يلغي الحاجة إلى أدوات سطر أوامر خارجية ويحافظ على سير العمل بالكامل داخل قاعدة شفرة .NET الخاصة بك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **استثناء “File not found”** | مسار `dataDir` غير صحيح | تحقق من أن مسار الدليل ينتهي بشرطة مائلة عكسية (`\`) أو استخدم `Path.Combine`. |
| **استخدام ذاكرة كبير** | ملفات ضخمة جدًا تُضغط في الذاكرة | استخدم `TarArchive` في وضع البث (`SaveXzCompressed` overload الذي يقبل `Stream`). |
| **الترخيص غير مفعّل** | ملف الترخيص مفقود | حمّل الترخيص عند بدء التطبيق: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع بيئات .NET؟**  
ج: نعم، Aspose.Zip يعمل مع .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10. راجع [التوثيق](https://reference.aspose.com/zip/net/) للتفاصيل.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب ترخيص مؤقت من [صفحة الترخيص المؤقتة لـ Aspose](https://purchase.aspose.com/temporary-license/).

**س: هل هناك أمثلة إضافية لتنسيقات أرشيف أخرى؟**  
ج: بالتأكيد—استكشف مجموعة الأمثلة الكاملة في [مرجع API لـ Aspose.Zip](https://reference.aspose.com/zip/net/).

**س: أين يمكنني الحصول على مساعدة أو مناقشة المشكلات؟**  
ج: انضم إلى الحوار في [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على دعم المجتمع والإجابات الرسمية.

**س: هل يمكنني تجربة Aspose.Zip مجانًا قبل الشراء؟**  
ج: نعم، تجربة مجانية متاحة على [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net).

## الخلاصة

باتباع الخطوات أعلاه، أنت الآن تعرف **كيفية إضافة ملفات إلى tar** و **ضغط ملفات tarxz**، والأهم من ذلك، **كيفية إنشاء أرشيف tarxz .net** باستخدام Aspose.Zip. يمنحك هذا النهج حزمة مضغوطة ومحمولة يمكن دمجها بسلاسة في أي سير عمل .NET—سواءً كنت تبني أداة سطح مكتب، خدمة ويب، أو خط أنابيب CI/CD مؤتمت.

---

**آخر تحديث:** 2026-11-18  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose  

## دروس ذات صلة

- [إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [كيفية ضغط tar وإنشاء TarBz2 باستخدام Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [كيفية ضغط ملفات متعددة إلى tar باستخدام Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}