---
date: 2026-02-23
description: تعلم كيفية إضافة الملفات إلى أرشيف tar وضغط الملفات إلى أرشيف tarxz باستخدام
  .NET وAspose.Zip. اتبع هذا الدليل خطوة بخطوة لتخزين ونقل فعال.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip
url: /ar/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip

## المقدمة

إذا كنت بحاجة إلى **add files to tar** ثم **create a tarxz archive .net**، فإن Aspose.Zip for .NET يجعل العملية مباشرة وموثوقة. سواءً كنت تقوم بتجميع سجلات، ملفات إعدادات، أو أي أصول أخرى للتخزين أو النقل، فإن الضغط إلى صيغة TarXz يمنحك نسبة ضغط عالية مع الحفاظ على بنية tar المألوفة. في هذا الدرس سنستعرض الخطوات الدقيقة—مع مقتطفات الشيفرة—حتى تتمكن من دمج إنشاء tarxz في تطبيقات .NET بثقة.

## إجابات سريعة
- **ما هي الفئة الأساسية؟** `TarArchive` from `Aspose.Zip.Tar`
- **كيف يتم ضغط tarxz؟** Use `SaveXzCompressed` after adding entries
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **هل تحتاج إلى ترخيص؟** Yes, a valid Aspose.Zip license for production
- **الوقت النموذجي للتنفيذ؟** ~5‑10 minutes

## ما هو أرشيف TarXz؟

أرشيف **TarXz** يجمع بين حاوية Unix التقليدية `tar` مع ضغط XZ. جزء الـ tar يجمع ملفات متعددة في تدفق واحد، بينما يوفر XZ ضغطًا قويًا غير فقدان للبيانات. هذه الصيغة شائعة لتوزيع الشيفرات المصدرية، النسخ الاحتياطية، ومجموعات البيانات الكبيرة لأنها تحتفظ بهياكل الأدلة وتحقق أحجام ملفات أصغر من tar أو zip العادي.

## لماذا إنشاء أرشيف tarxz .net باستخدام Aspose.Zip؟

- **نسبة ضغط عالية** – XZ غالبًا ما يضغط بنسبة 30‑50 % أصغر من gzip.  
- **توافق متعدد المنصات** – يمكن فتح ملفات TarXz على Linux و macOS و Windows.  
- **واجهة برمجة تطبيقات بسيطة** – Aspose.Zip يخفّف تفاصيل المستوى المنخفض، مما يتيح لك التركيز على منطق عملك.  
- **بدون أدوات خارجية** – كل شيء يعمل داخل عملية .NET الخاصة بك، مثالي للسحابة أو خطوط CI.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود:

- **Aspose.Zip for .NET** مثبت (حمّل من [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة أدناه يُشار إلى هذا المجلد بالمتغير `dataDir`.  
- ترخيص Aspose.Zip صالح (اختياري للتقييم، مطلوب للإنتاج).

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تُظهر وظائف TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## كيفية إضافة ملفات إلى tar باستخدام Aspose.Zip

فيما يلي دليل خطوة بخطوة يوضح بالضبط كيف **add files to tar** قبل ضغطها.

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

أخيرًا، اكتب أرشيف tar إلى القرص باستخدام ضغط XZ. الملف الناتج سيكون بامتداد `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **النتيجة:** لديك الآن ملف `archive.tar.xz` مضغوط بالكامل يمكن نقله، تخزينه، أو فك ضغطه على أي منصة تدعم TarXz.

## كيفية ضغط ملفات tarxz باستخدام Aspose.Zip

العملية الموضحة أعلاه هي في الأساس **how to compress tarxz**: أولاً تضيف الملفات إلى حاوية tar (`add files to tar`) ثم تستدعي `SaveXzCompressed`. هذه الطريقة ذات الاستدعاء الواحد تلغي الحاجة إلى أدوات سطر أوامر خارجية وتبقي كل شيء داخل قاعدة شفرة .NET الخاصة بك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **استثناء “File not found”** | مسار `dataDir` غير صحيح | تحقق من أن مسار الدليل ينتهي بشرطة مائلة عكسية (`\`) أو استخدم `Path.Combine`. |
| **استهلاك الذاكرة كبير** | ملفات ضخمة تُضغط في الذاكرة | استخدم `TarArchive` في وضع البث (`SaveXzCompressed` overload الذي يقبل `Stream`). |
| **الترخيص غير مُطبق** | ملف الترخيص مفقود | حمّل الترخيص عند بدء التطبيق: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع بيئات .NET؟**  
ج: نعم، Aspose.Zip يعمل مع .NET Framework 4.5+, .NET Core 3.1+, و .NET 5/6+. راجع [documentation](https://reference.aspose.com/zip/net/) للمزيد من التفاصيل.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب ترخيص مؤقت من [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**س: هل هناك أمثلة إضافية لصيغ أرشفة أخرى؟**  
ج: بالتأكيد—استكشف مجموعة الأمثلة الكاملة في [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**س: أين يمكنني الحصول على مساعدة أو مناقشة المشكلات؟**  
ج: انضم إلى النقاش في [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) للحصول على دعم المجتمع والإجابات الرسمية.

**س: هل يمكن تجربة Aspose.Zip مجانًا قبل الشراء؟**  
ج: نعم، نسخة تجريبية مجانية متاحة على [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## الخاتمة

باتباع الخطوات أعلاه، أصبحت الآن تعرف **how to add files to tar** و **compress tarxz**، والأهم من ذلك، **create tarxz archive .net** باستخدام Aspose.Zip. هذه الطريقة تمنحك حزمة مضغوطة ومحمولة يمكن دمجها بسهولة في أي سير عمل .NET—سواءً كنت تبني أداة سطح مكتب، خدمة ويب، أو خط أنابيب CI/CD مؤتمت.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}