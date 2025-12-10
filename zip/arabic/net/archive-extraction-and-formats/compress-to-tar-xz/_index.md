---
date: 2025-12-05
description: تعلم كيفية إنشاء أرشيف tarxz في .NET وكيفية ضغط ملفات tarxz باستخدام
  Aspose.Zip لـ .NET. اتبع هذا الدليل خطوة بخطوة للتخزين والنقل الفعال.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية إنشاء أرشيف tarxz في .net باستخدام Aspose.Zip
url: /ar/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء أرشيف tarxz في .net باستخدام Aspose.Zip

## المقدمة

إذا كنت بحاجة إلى **إنشاء أرشيف tarxz في .net**، فإن Aspose.Zip for .NET يجعل العملية بسيطة وموثوقة. سواءً كنت تُعبئ سجلات، ملفات إعدادات، أو أي أصول أخرى للتخزين أو النقل، فإن الضغط إلى صيغة TarXz يمنحك نسبة ضغط عالية مع الحفاظ على بنية tar المألوفة. في هذا الدرس سنستعرض الخطوات الدقيقة—متضمنة مقتطفات الشيفرة—حتى تتمكن من دمج إنشاء tarxz في تطبيقات .NET الخاصة بك بثقة.

## إجابات سريعة
- **ما هو الصنف الأساسي؟** `TarArchive` من `Aspose.Zip.Tar`
- **كيف يتم ضغط tarxz؟** استخدم `SaveXzCompressed` بعد إضافة الإدخالات
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6
- **هل تحتاج إلى ترخيص؟** نعم، ترخيص Aspose.Zip صالح للإنتاج
- **الوقت التقريبي للتنفيذ؟** ~5‑10 دقائق

## ما هو أرشيف TarXz؟

أرشيف **TarXz** يجمع بين حاوية Unix التقليدية `tar` مع ضغط XZ. الجزء tar يجمع ملفات متعددة في تدفق واحد، بينما يوفر XZ ضغطًا قويًا غير فقدان للبيانات. تُستخدم هذه الصيغة كثيرًا لتوزيع الشيفرات المصدرية، النسخ الاحتياطية، ومجموعات البيانات الكبيرة لأنها تحتفظ بهياكل الدليل وتنتج أحجام ملفات أصغر من tar أو zip العادي.

## لماذا ننشئ أرشيف tarxz في .net باستخدام Aspose.Zip؟

- **نسبة ضغط عالية** – عادةً ما يكون XZ أصغر بنسبة 30‑50 % مقارنةً بـ gzip.  
- **توافق متعدد المنصات** – يمكن فتح ملفات TarXz على Linux و macOS و Windows.  
- **واجهة برمجة تطبيقات بسيطة** – Aspose.Zip يخفّف التفاصيل منخفضة المستوى، مما يتيح لك التركيز على منطق عملك.  
- **بدون أدوات خارجية** – كل شيء يُنفّذ داخل عملية .NET الخاصة بك، مثالي للسحابة أو خطوط CI.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Zip for .NET** مثبت (حمّله من [توثيق Aspose.Zip الرسمي](https://reference.aspose.com/zip/net/)).  
- مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة أدناه يُشار إلى هذا المجلد بالمتغيّر `dataDir`.  
- ترخيص Aspose.Zip صالح (اختياري للتقييم، مطلوب للإنتاج).

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية التي تُظهر وظائف TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## دليل خطوة بخطوة لإنشاء أرشيف tarxz في .net

### الخطوة 1: تهيئة `TarArchive`

أنشئ كائنًا جديدًا من `TarArchive` سيحمل الملفات التي تريد ضغطها.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **نصيحة احترافية:** يضمن بيان `using` التخلص الصحيح من الأرشيف، مما يحرّر أي موارد غير مُدارة.

### الخطوة 2: إضافة ملفات إلى الأرشيف

أضف كل ملف تريد تضمينه. في هذا المثال نضيف ملفين نصيين، لكن يمكنك إضافة أي عدد من الإدخالات حسب الحاجة.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **لماذا هذا مهم:** إضافة الإدخالات قبل الضغط يسمح لـ Aspose.Zip بإنشاء حاوية tar أولاً، ثم تطبيق ضغط XZ في خطوة واحدة.

### الخطوة 3: حفظ الأرشيف مع ضغط XZ

أخيرًا، اكتب أرشيف tar إلى القرص باستخدام ضغط XZ. سيكون للملف الناتج امتداد `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **النتيجة:** لديك الآن ملف `archive.tar.xz` مضغوط بالكامل يمكن نقله، تخزينه، أو فك ضغطه على أي منصة تدعم TarXz.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **استثناء “File not found”** | مسار `dataDir` غير صحيح | تحقق من أن مسار الدليل ينتهي بشرطة مائلة عكسية (`\`) أو استخدم `Path.Combine`. |
| **استهلاك ذاكرة كبير** | ملفات ضخمة تُضغط في الذاكرة | استخدم `TarArchive` في وضع البث (`SaveXzCompressed` overload الذي يقبل `Stream`). |
| **عدم تطبيق الترخيص** | ملف الترخيص مفقود | حمّل الترخيص عند بدء التطبيق: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع بيئات .NET؟**  
ج: نعم، يعمل Aspose.Zip مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+. راجع [التوثيق](https://reference.aspose.com/zip/net/) للمزيد من التفاصيل.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب ترخيص مؤقت من [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).

**س: هل هناك أمثلة إضافية لصيغ أرشفة أخرى؟**  
ج: بالتأكيد—استكشف مجموعة الأمثلة الكاملة في [مرجع API الخاص بـ Aspose.Zip](https://reference.aspose.com/zip/net/).

**س: أين يمكنني الحصول على مساعدة أو مناقشة المشكلات؟**  
ج: انضم إلى النقاش في [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على دعم المجتمع والإجابات الرسمية.

**س: هل يمكن تجربة Aspose.Zip مجانًا قبل الشراء؟**  
ج: نعم، تتوفر نسخة تجريبية مجانية على [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net).

## الخاتمة

باتباع الخطوات السابقة، أصبحت الآن تعرف **كيفية ضغط ملفات tarxz**، والأهم **كيفية إنشاء أرشيف tarxz في .net** باستخدام Aspose.Zip. تمنحك هذه الطريقة حزمة مضغوطة ومحمولة يمكن دمجها بسلاسة في أي سير عمل .NET—سواءً كنت تبني أداة سطح مكتب، خدمة ويب، أو خط أنابيب CI/CD مؤتمت.

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}