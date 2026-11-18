---
date: 2026-11-18
description: تعلم كيفية إنشاء أرشيفات tar وضغطها إلى TarZ باستخدام Aspose.Zip for
  .NET – دليل خطوة بخطوة لمعالجة ملفات .NET بكفاءة.
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: ضغط إلى TarZ
og_description: تعلم كيفية إنشاء أرشيفات tar وضغطها إلى TarZ باستخدام Aspose.Zip for
  .NET. يوضح لك هذا الدليل كيفية إضافة الملفات والمجلدات والضغط بكفاءة.
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: كيفية إنشاء أرشيف tar وضغطه إلى TarZ باستخدام Aspose.Zip for .NET
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: كيفية إنشاء أرشيف tar وضغطه إلى TarZ باستخدام Aspose.Zip for .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات إلى tar وضغطها إلى TarZ باستخدام Aspose.Zip لـ .NET

## مقدمة

إذا كنت بحاجة إلى **add files to tar** ثم ضغط الأرشيف إلى تنسيق TarZ، فإن Aspose.Zip لـ .NET يجعل العملية بأكملها سهلة. في هذا الدرس سنستعرض كل خطوة — من إعداد مشروعك إلى إنشاء أرشيف tar، إضافة الملفات، وأخيرًا حفظ ملف .tar.z مضغوط. في النهاية ستحصل على مقتطف قابل لإعادة الاستخدام يمكنك إدراجه في أي تطبيق .NET، سواء كنت تتعامل مع عدد قليل من ملفات التكوين أو شجرة دليل كاملة.

## إجابات سريعة

- **ما المكتبة التي تتعامل مع إنشاء tar؟** Aspose.Zip for .NET  
- **كم عدد أسطر الشيفرة؟** About 15 lines (excluding comments)  
- **هل أحتاج إلى ترخيص للاختبار؟** A free trial is available; a license is required for production.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **هل يمكنني ضغط المجلدات، وليس فقط الملفات؟** Yes – you can add entire directories with a loop.

## ما هو **add files to tar**؟

**Add files to tar** هي عملية تجميع الملفات المختارة في حاوية tar واحدة غير مضغوطة مع الحفاظ على هيكل الدليل والبيانات الوصفية. تنسيق tar يُنشئ حزمة حتمية وغير مرتبطة بمنصة معينة يمكن لخوارزميات الضغط اللاحقة العمل عليها بفعالية، مما يجعلها مثالية للتوزيع عبر المنصات.

## كيفية إنشاء أرشيفات tar باستخدام Aspose.Zip لـ .NET؟

تمثل الفئة `TarArchive` حاوية tar يمكنها احتواء عدة إدخالات ملفات. قم بتحميل دليل المصدر، أنشئ كائنًا من `TarArchive`, أضف كل ملف (أو دليل فرعي كامل)، وأخيرًا استدعِ `Save` مع علم ضغط TarZ. العملية بسيطة، تتطلب فقط بضع أسطر من الشيفرة، وتعمل بشكل ثابت عبر جميع أوقات تشغيل .NET المدعومة، بما في ذلك .NET Framework و .NET Core.

الفئة `TarArchive` هي الكائن الأساسي في Aspose.Zip الذي يمثل حاوية tar يمكنك ملؤها بالإدخالات. يتيح لك استخدامها إنشاء ملفات tar بالكامل في الذاكرة، بثها مباشرةً إلى الاستجابة، أو كتابتها إلى القرص دون ملفات zip مؤقتة.

## لماذا إضافة ملفات إلى tar قبل الضغط إلى TarZ؟

إنشاء حاوية tar أولاً يعزل عملية التعبئة عن الضغط، مما ينتج ثلاثة فوائد قابلة للقياس. من خلال فصل هذه المراحل تحصل على أرشيف قابل للتنبؤ وإعادة الاستخدام يمكن ضغطه بشكل مستقل، مما يسهل قياس نسب الضغط وإعادة استخدام نفس tar لخوارزميات ضغط مختلفة.

1. **قابلية النقل** – يمكن فك ضغط ملف `.tar` على أي نظام شبيه بـ Unix دون الحاجة إلى مكتبات إضافية.  
2. **السرعة** – إنشاء tar هو في الأساس عملية نسخ تدفق؛ ثم يركز ضغط Z اللاحق فقط على تقليل الحجم، عادةً يقتطع **30‑70 %** من البيانات الأصلية.  
3. **التوافق** – تتوقع العديد من الأدوات القديمة (مثل `tar`، `gzip`) وجود ملف `.tar` قبل تطبيق ضغط بنمط gzip، وهذا بالضبط ما تمثله امتداد `.tar.z`.

### لماذا هذا مهم لمطوري .NET

استخدام حاوية tar يتيح لك الحفاظ على شفرة .NET بسيطة وحتمية. يمكنك إنشاء الأرشيف في الذاكرة، بثه مباشرةً إلى الاستجابة، أو تخزينه على القرص دون التعامل مع ملفات zip مؤقتة. هذا النمط مفيد بشكل خاص لخطوط بناء البرمجيات، تجميع السجلات، أو عندما تحتاج إلى إرسال مجموعة من ملفات التكوين إلى خدمة تعمل على Linux.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك:

- **Aspose.Zip for .NET** مثبتًا. قم بتنزيله من الموقع الرسمي [here](https://releases.aspose.com/zip/net/).  
- مجلد على جهازك يحتوي على الملفات التي تريد أرشفتها. استبدل مسار العنصر النائب بمسار الدليل الفعلي الخاص بك.

## استيراد مساحات الأسماء

أضف عبارات `using` المطلوبة في أعلى ملف C# الخاص بك:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **نصيحة احترافية:** استخدم `Path.Combine` إذا كنت بحاجة إلى بناء المسارات ديناميكيًا؛ فهو يتجنب فقدان فواصل المسار على أنظمة تشغيل مختلفة.

## كيفية إضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET؟

طريقة `CreateEntry` تضيف إدخال ملف جديد إلى أرشيف tar باسم ومحتوى محددين. قم بتحميل دليل المصدر، أنشئ كائنًا من `TarArchive`, أضف كل ملف (أو دليل فرعي كامل), وأخيرًا استدعِ `Save` مع علم ضغط TarZ. هذه سير العمل يظل مختصرًا، عادةً أقل من 20 سطرًا، ويعمل عبر جميع أوقات تشغيل .NET المدعومة، موفرًا طريقة موثوقة لتجميع وضغط البيانات.

طريقة `Save` تكتب الأرشيف إلى القرص وتطبق الضغط اختياريًا.

### مرساة التعريف

الفئة `TarArchive` هي الكائن الأساسي في Aspose.Zip الذي يمثل حاوية tar يمكنك ملؤها بالإدخالات.

### دليل خطوة بخطوة

#### الخطوة 1: تعريف دليل المستند الخاص بك

```csharp
string dataDir = "Your Document Directory";
```

> **لماذا هذه الخطوة مهمة:** `dataDir` يعمل كموقع أساسي لكل ملف ستضيفه. الحفاظ عليه في متغير واحد يجعل الشيفرة سهلة الصيانة وإعادة الاستخدام عبر أرشيفات متعددة.

#### الخطوة 2: إنشاء أرشيف Tar وإضافة ملفات

##### 2.1: إنشاء كائن أرشيف Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> كتلة `using` تضمن أن كائن `TarArchive` يتم تحريره بشكل صحيح، مما يحرر أي مقبض ملف أو مخازن الذاكرة.

##### 2.2: إضافة ملفات إلى الأرشيف  

`CreateEntry` يضيف ملفًا إلى أرشيف tar، محددًا اسمه وتدفق المحتوى.  

داخل كتلة `using`، أضف كل ملف تريد تضمينه:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

يمكنك تكرار `CreateEntry` لعدد الملفات المطلوبة، أو تنفيذ حلقة عبر دليل لإضافتها برمجيًا. على سبيل المثال، حلقة `foreach (var file in Directory.GetFiles(dataDir))` ستمكنك من معالجة عدد عشوائي من الملفات مع الحفاظ على مساراتها النسبية.

##### 2.3: حفظ ملف TarZ المضغوط  

`Save` يكتب الأرشيف إلى القرص ويطبق تنسيق الضغط المحدد.  

بعد إضافة جميع الإدخالات، اضغط أرشيف tar إلى تنسيق `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

الملف الناتج `archive.tar.z` سيقع في نفس المجلد الذي حددته في `dataDir`. يمكنك الآن إرسال هذه الحزمة المضغوطة الوحيدة إلى أي نظام يفهم TarZ.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **الملف غير موجود** | مسار خاطئ أو امتداد ملف مفقود | تحقق من أن `dataDir` ينتهي بفاصل مسار وأن أسماء الملفات صحيحة. |
| **تم رفض الوصول** | أذونات غير كافية على المجلد المستهدف | شغّل التطبيق بصلاحيات مناسبة أو اختر دليلًا قابلًا للكتابة. |
| **الملف المضغوط أكبر من المتوقع** | الملفات الأصلية مضغوطة بالفعل (مثل الصور، الفيديوهات) | يعمل TarZ بشكل أفضل على ملفات النص أو السجلات؛ فكر في ترك الملفات المضغوطة مسبقًا كما هي. |

### الأخطاء الشائعة التي يجب الانتباه إليها
- **غياب الشرطة المائلة النهائية** – إذا لم ينتهي `dataDir` بـ `\` أو `/`، فإن دمج السلاسل سينتج مسارًا غير صالح.  
- **دليل كبير** – إضافة آلاف الملفات قد تستهلك الذاكرة؛ فكر في بث الإدخالات أو استخدام نسخة `TarArchive` التي تكتب مباشرةً إلى تدفق ملف.  
- **مشكلات الترميز** – قد تحتاج أسماء الملفات غير ASCII إلى معالجة ترميز صريحة؛ Aspose.Zip يحترم UTF‑8 افتراضيًا، لكن تحقق من ذلك على المنصة المستهدفة.

## الأسئلة المتكررة

**س: هل يمكنني ضغط مجلدات كاملة باستخدام Aspose.Zip لـ .NET؟**  
A: بالطبع. استخدم حلقة `Directory.GetFiles` واستدعِ `CreateEntry` لكل ملف، مع الحفاظ على المسارات النسبية.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Zip لـ .NET؟**  
A: نعم، يمكنك استكشاف قدرات Aspose.Zip لـ .NET بتحميل النسخة التجريبية المجانية [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق شاملة لـ Aspose.Zip لـ .NET؟**  
A: الوثائق متاحة [here](https://reference.aspose.com/zip/net/)، وتوفر رؤى مفصلة حول ميزات المكتبة واستخدامها.

**س: كيف يمكنني الحصول على دعم لـ Aspose.Zip لـ .NET؟**  
A: قم بزيارة [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) للحصول على المساعدة، مشاركة التجارب، والتواصل مع المجتمع.

**س: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip لـ .NET؟**  
A: نعم، إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة

لقد تعلمت الآن كيفية **add files to tar** وضغط النتيجة إلى أرشيف TarZ باستخدام Aspose.Zip لـ .NET. يمنحك هذا النهج حزمة نظيفة وقابلة للنقل يمكن نقلها بسهولة، تخزينها، أو معالجتها بشكل إضافي. لا تتردد في تعديل المقتطف لمعالجة الدلائل دفعةً، دمجه في خطوط بناء البرمجيات، أو دمجه مع مكونات Aspose الأخرى لإنشاء تدفقات عمل وثائق أكثر غنى.

---

**آخر تحديث:** 2026-11-18  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إضافة ملفات متعددة إلى tar وإنشاء أرشيف tar.gz باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [كيفية ضغط ملفات tar متعددة باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [استخراج الأرشيف والصيغ](/zip/net/archive-extraction-and-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}