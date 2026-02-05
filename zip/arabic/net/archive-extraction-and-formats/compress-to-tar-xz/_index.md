---
date: 2026-02-05
description: تعلم كيفية إضافة ملفات إلى tar وإنشاء أرشيفات tarxz في .NET باستخدام
  Aspose.Zip. يوضح هذا الدليل كيفية ضغط الملفات إلى tarxz بكفاءة عالية.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة ملفات إلى tar، إنشاء أرشيف tarxz باستخدام .NET و Aspose.Zip
url: /ar/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة ملفات إلى tar، وإنشاء أرشيف tarxz باستخدام .NET مع Aspose.Zip

## المقدمة

إذا كنت بحاجة إلى **إضافة ملفات إلى tar** ثم ضغطها في أرشيف tarxz باستخدام .NET، فإن Aspose.Zip for .NET يجعل العملية بسيطة وموثوقة. سواء كنت تُعبئ سجلات، ملفات إعدادات، أو أي أصول أخرى للتخزين أو النقل، فإن الضغط إلى صيغة TarXz يمنحك نسبة ضغط عالية مع الحفاظ على بنية tar المألوفة. في هذا الدرس سنستعرض الخطوات الدقيقة—مع مقتطفات الشيفرة—حتى تتمكن من دمج إنشاء tarxz في تطبيقات .NET الخاصة بك بثقة.

## إجابات سريعة
- **ما هي الفئة الأساسية؟** `TarArchive` من `Aspose.Zip.Tar`
- **كيف يتم ضغط tarxz؟** استخدم `SaveXzCompressed` بعد إضافة الإدخالات
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6
- **هل تحتاج إلى ترخيص؟** نعم، ترخيص صالح لـ Aspose.Zip للإنتاج
- **الوقت التقريبي للتنفيذ؟** ~5‑10 دقائق

## ما هو أرشيف TarXz؟

أرشيف **TarXz** يجمع بين حاوية Unix التقليدية `tar` مع ضغط XZ. جزء الـ tar يجمع ملفات متعددة في تدفق واحد، بينما يوفر XZ ضغطًا قويًا غير فقداني. هذا التنسيق شائع لتوزيع الشيفرات المصدرية، النسخ الاحتياطية، ومجموعات البيانات الكبيرة لأنه يحافظ على هياكل الدلائل ويحقق أحجام ملفات أصغر من tar أو zip العادي.

## لماذا نضيف ملفات إلى tar ونضغطها إلى tarxz باستخدام Aspose.Zip؟

- **نسبة ضغط عالية** – عادةً ما يكون XZ أصغر بنسبة 30‑50 % مقارنةً بـ gzip.  
- **توافق متعدد المنصات** – يمكن فتح ملفات TarXz على Linux، macOS، وWindows.  
- **واجهة برمجة تطبيقات بسيطة** – Aspose.Zip يخفف عنك تفاصيل المستوى المنخفض، لتتمكن من التركيز على منطق عملك.  
- **بدون أدوات خارجية** – كل شيء يُنفّذ داخل عملية .NET الخاصة بك، مثالي للسحابة أو خطوط CI.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Zip for .NET** مثبت (حمّله من [توثيق Aspose.Zip الرسمي](https://reference.aspose.com/zip/net/)).  
- مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة أدناه يُشار إلى هذا المجلد بالمتغيّر `dataDir`.  
- ترخيص صالح لـ Aspose.Zip (اختياري للتقييم، مطلوب للإنتاج).

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية التي تُوفّر وظائف TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## كيفية إضافة ملفات إلى tar باستخدام Aspose.Zip

### الخطوة 1: تهيئة `TarArchive`

أنشئ كائن `TarArchive` جديد سيحمل الملفات التي تريد ضغطها.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **نصيحة احترافية:** يضمن بيان `using` التخلص السليم من الأرشيف، مما يحرّر أي موارد غير مُدارة.

### الخطوة 2: إضافة ملفات إلى الأرشيف

أضف كل ملف ترغب في تضمينه. في هذا المثال نضيف ملفين نصيين، لكن يمكنك إضافة أي عدد من الإدخالات حسب الحاجة.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **لماذا هذا مهم:** إضافة الإدخالات قبل الضغط يسمح لـ Aspose.Zip بإنشاء حاوية tar أولاً، ثم تطبيق ضغط XZ في خطوة واحدة.

### الخطوة 3: حفظ الأرشيف مع ضغط XZ

أخيرًا، اكتب أرشيف tar إلى القرص مع ضغط XZ. سيحمل الملف الناتج امتداد `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **النتيجة:** لديك الآن ملف `archive.tar.xz` مضغوط بالكامل يمكن نقله، تخزينه، أو فك ضغطه على أي منصة تدعم TarXz.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **استثناء “File not found”** | مسار `dataDir` غير صحيح | تحقق من أن مسار الدليل ينتهي بشرطة مائلة عكسية (`\`) أو استخدم `Path.Combine`. |
| **استهلاك كبير للذاكرة** | ملفات ضخمة تُضغط في الذاكرة | استخدم `TarArchive` في وضع البث (`SaveXzCompressed` overload الذي يقبل `Stream`). |
| **عدم تطبيق الترخيص** | ملف الترخيص مفقود | حمّل الترخيص عند بدء التطبيق: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع بيئات .NET؟**  
ج: نعم، يعمل Aspose.Zip مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+. راجع [التوثيق](https://reference.aspose.com/zip/net/) للمزيد من التفاصيل.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب ترخيص مؤقت من [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).

**س: هل هناك أمثلة إضافية لتنسيقات أرشيف أخرى؟**  
ج: بالتأكيد—استكشف مجموعة الأمثلة الكاملة في [مرجع API الخاص بـ Aspose.Zip](https://reference.aspose.com/zip/net/).

**س: أين يمكنني الحصول على مساعدة أو مناقشة المشكلات؟**  
ج: انضم إلى النقاش في [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على دعم المجتمع والإجابات الرسمية.

**س: هل يمكن تجربة Aspose.Zip مجانًا قبل الشراء؟**  
ج: نعم، تتوفر نسخة تجريبية مجانية على [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net).

## الخلاصة

باتباع الخطوات أعلاه، أصبحت الآن تعرف **كيفية إضافة ملفات إلى tar** و**إنشاء أرشيفات tarxz** باستخدام Aspose.Zip في .NET. يوفّر لك هذا النهج حزمة مضغوطة ومحمولة يمكن دمجها بسهولة في أي سير عمل .NET—سواء كنت تبني أداة سطح مكتب، خدمة ويب، أو خط أنابيب CI/CD مؤتمت.

---

**آخر تحديث:** 2026-02-05  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}