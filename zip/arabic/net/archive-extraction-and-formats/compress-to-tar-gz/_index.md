---
date: 2026-06-19
description: تعلم كيفية إضافة ملفات متعددة إلى tar وضغط الملفات إلى tar.gz باستخدام
  Aspose.Zip for .NET – طريقة سريعة وعبر‑المنصات لإنشاء أرشيفات TarGz.
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: إضافة ملفات إلى tar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة ملفات متعددة إلى tar وإنشاء أرشيف tar.gz باستخدام Aspose.Zip for .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات متعددة إلى tar وإنشاء أرشيف tar.gz باستخدام Aspose.Zip لـ .NET

## مقدمة

في تطبيقات .NET الحديثة، **إضافة ملفات متعددة إلى tar** ثم **ضغط الملفات إلى tar.gz** هو احتياج شائع—سواءً كنت تجمع ملفات السجلات، أو تُعد البيانات للتخزين السحابي، أو تنشئ حزم نشر لخوادم Linux. توفر Aspose.Zip لـ .NET واجهة برمجة تطبيقات نظيفة وعالية الأداء تتيح لك بناء أرشيف tar، وإضافة أي عدد من الملفات، وضغطه اختياريًا إلى ملف tar.gz—كل ذلك دون الحاجة إلى أدوات خارجية. في هذا الدليل سنستعرض سير العمل الكامل، من إعداد المشروع حتى الحصول على `archive.tar.gz` جاهز للإنتاج.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip لـ .NET – تدعم tar، tar.gz، zip والعديد من الصيغ الأخرى.  
- **كيف أضيف ملفات متعددة إلى tar؟** استدعِ `TarArchive.CreateEntry` لكل ملف تريد تضمينه.  
- **هل يمكنني الضغط مباشرة إلى tar.gz؟** نعم—استدعِ `SaveGzipped` على كائن `TarArchive`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب الاستخدام غير التجريبي ترخيص Aspose صالح.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10.

## ما هو “إضافة ملفات متعددة إلى tar”؟
إضافة ملفات متعددة إلى أرشيف tar يعني تجميع عدة ملفات (وبشكل اختياري أدلة) في حاوية واحدة غير مضغوطة مع الحفاظ على الهيكل الأصلي والبيانات الوصفية. يمكن لاحقًا ضغط ملف `.tar` الناتج باستخدام gzip لإنتاج أرشيف `tar.gz`، وهو مستخدم على نطاق واسع للتوزيع والنسخ الاحتياطي.

## لماذا نستخدم Aspose.Zip لضغط الملفات إلى tar.gz؟
يتعامل Aspose.Zip مع عملية tar و gzip بالكامل في الذاكرة، مما يلغي الحاجة إلى الأدوات الأصلية. يمكنه معالجة **أرشيفات تصل إلى 500 GB** دون تحميل الملف بالكامل إلى الذاكرة، بفضل هندسته المعتمدة على التدفقات. تدعم المكتبة **أكثر من 50 صيغة إدخال وإخراج**، وتعمل على Windows و Linux و macOS، وتوفر ميزات إضافية مثل التشفير، وحماية كلمة المرور، وسمات الإدخالات المخصصة—كل ذلك من خلال واجهة .NET واحدة.

## المتطلبات المسبقة

- خبرة أساسية في تطوير .NET.  
- Visual Studio (أو أي بيئة تطوير مفضلة).  
- تم تثبيت Aspose.Zip لـ .NET – راجع الوثائق الرسمية [هنا](https://reference.aspose.com/zip/net/).  
- تحميل مكتبة Aspose.Zip من [هذا الرابط](https://releases.aspose.com/zip/net/).

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، استورد مساحات الأسماء التي تكشف عن الفئات المتعلقة بـ tar:
```csharp
using System;
using Aspose.Zip.Tar;
```

## كيفية إضافة ملفات متعددة إلى tar باستخدام Aspose.Zip لـ .NET

باستخدام Aspose.Zip تقوم أولاً بتحميل المجلد المصدر، وإنشاء كائن `TarArchive`، ثم التكرار على كل ملف، مستدعيًا `CreateEntry` لإضافته إلى الأرشيف. بعد إضافة جميع الإدخالات تستدعي `SaveGzipped` لإنتاج ملف `archive.tar.gz` مضغوط. يتطلب هذا التدفق بأكمله بضع أسطر فقط من شفرة .NET واضحة وآمنة من حيث النوع.

### الخطوة 1: تحديد دليل المستند الخاص بك

حدد المجلد الذي يحتوي على الملفات التي تريد أرشفتها.
```csharp
string dataDir = "Your Document Directory";
```

> **نصيحة احترافية:** استخدم `Path.Combine` عند بناء المسارات لتجنب مشاكل الفواصل الخاصة بالمنصة.  
> طريقة `Path.Combine` تجمع بأمان أسماء الأدلة والملفات باستخدام الفاصل المناسب لنظام التشغيل.

### الخطوة 2: إنشاء أرشيف TarGz

الآن سننشئ أرشيف tar، نضيف الإدخالات، ونضغطه في تدفق واحد سلس.

#### 2.1 تهيئة TarArchive

فئة `TarArchive` هي الكائن الأعلى مستوى في Aspose.Zip الذي يمثل حاوية tar في الذاكرة. إن إنشاء نسخة منه يُعد أرشيفًا فارغًا جاهزًا للإدخالات.
```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 إضافة ملفات – جوهر “إضافة ملفات متعددة إلى tar”

`CreateEntry` ينشئ إدخالًا جديدًا داخل أرشيف tar. تأخذ الطريقة **اسم الإدخال** (المسار داخل tar) و**مسار الملف المصدر** على القرص. استدعها بشكل متكرر لإضافة عدد الملفات المطلوب.
```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

كل استدعاء لـ `CreateEntry` يضيف ملفًا واحدًا؛ يمكنك التكرار على مجموعة من الأدلة لإضافة عشرات أو مئات الملفات بشفرة قليلة.

#### 2.3 حفظ كـ Tar مضغوط بـ Gzip (كيفية ضغط الملفات إلى tar.gz)

`SaveGzipped` يكتب محتويات tar إلى تدفق gzip، منتجًا ملفًا مضغوطًا `archive.tar.gz` جاهزًا للتوزيع أو التخزين.
```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

تتعامل الطريقة تلقائيًا مع رؤوس وتذييلات gzip، لذا تحصل على tar.gz متوافق مع المعايير دون خطوات إضافية.

## حالات الاستخدام الشائعة

| السيناريو | لماذا تساعد “إضافة ملفات متعددة إلى tar” |
|----------|----------------------------------------|
| **تجميع السجلات** | تجميع السجلات اليومية في أرشيف واحد قبل رفعه إلى التخزين السحابي. |
| **حزم النشر** | إنشاء حزم tar.gz محمولة لخوادم Linux من خط تجميع على Windows. |
| **نسخ احتياطي للبيانات** | الحفاظ على هيكل المجلدات والبيانات الوصفية مع الحفاظ على حجم النسخة الاحتياطية منخفضًا. |

## المشكلات الشائعة والحلول

- **خطأ ملف غير موجود** – تأكد من أن `dataDir` ينتهي بفاصل المسار المناسب أو استخدم `Path.Combine`.  
- **الملفات الكبيرة تسبب ضغطًا على الذاكرة** – استخدم النسخة المعتمدة على التدفق من `CreateEntry` (`CreateEntry(string entryName, Stream source)`) لتجنب تحميل الملفات بالكامل إلى الذاكرة.  
- **إخراج gzip تالف** – تحقق من أن كائن `TarArchive` تم تحريره (باستخدام كتلة `using`) قبل استدعاء `SaveGzipped`.  

## الأسئلة المتكررة

**س: هل Aspose.Zip لـ .NET متوافق مع جميع تطبيقات .NET؟**  
ج: نعم، يعمل مع .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، ومشاريع .NET 5–10.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip لـ .NET؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لطلب ترخيص تجريبي.

**س: هل هناك أي قيود على حجم الملفات؟**  
ج: المكتبة مُحسّنة للملفات الكبيرة؛ لا يوجد حد ثابت للحجم سوى الذاكرة المتاحة للنظام، ويمكنها بث أرشيفات أكبر من 100 GB.

**س: أين يمكنني الحصول على الدعم؟**  
ج: استخدم منتدى الدعم المجتمعي [هنا](https://forum.aspose.com/c/zip/37) للحصول على مساعدة من مهندسي Aspose ومطوريين آخرين.

**س: هل يمكنني تجربة Aspose.Zip لـ .NET مجانًا؟**  
ج: بالتأكيد—قم بتحميل النسخة التجريبية المجانية من [صفحة إصدارات Aspose Zip](https://releases.aspose.com/zip/net/).

## الخلاصة

أنت الآن تعرف كيفية **إضافة ملفات متعددة إلى tar**، وإنشاء أرشيف tar، و**ضغط الملفات إلى tar.gz** باستخدام Aspose.Zip لـ .NET. يزيل هذا النهج الاعتماد على الأدوات الخارجية، ويمنحك تحكمًا كاملاً في محتويات الأرشيف، ويتوسع ليتعامل مع مجموعات بيانات ضخمة جدًا. استكشف ميزات إضافية مثل التشفير، وسمات الإدخالات المخصصة، وواجهات برمجة التطبيقات المتدفقة لتعزيز سير عمل الأرشفة الخاص بك.

---

**آخر تحديث:** 2026-06-19  
**تم الاختبار باستخدام:** Aspose.Zip 24.11 for .NET  
**المؤلف:** Aspose

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية ضغط ملفات متعددة إلى tar باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [كيفية ضغط tar وإنشاء TarBz2 باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}