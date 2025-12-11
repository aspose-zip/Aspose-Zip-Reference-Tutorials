---
date: 2025-12-10
description: تعلم ضغط الملفات المتوازي في .NET باستخدام Aspose.Zip. اضغط عدة ملفات
  بكفاءة مع دليلنا خطوة بخطوة.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: ضغط الملفات المتوازي باستخدام Aspose.Zip لـ .NET
url: /ar/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضغط الملفات المتوازي باستخدام Aspose.Zip لـ .NET

## المقدمة

في عالم تطوير .NET، يُعد **ضغط الملفات المتوازي** أمرًا حيويًا لتحسين مساحة التخزين وتسريع نقل البيانات. توفر Aspose.Zip لـ .NET حلاً قويًا، وإحدى ميزاتها البارزة هي القدرة على الاستفادة من التوازي في ضغط الملفات. في هذا البرنامج التعليمي، سنرشدك إلى كيفية استخدام التوازي **لضغط ملفات متعددة** بكفاءة باستخدام Aspose.Zip لـ .NET.

## إجابات سريعة
- **ما هو ضغط الملفات المتوازي؟** تقنية تقوم بضغط عدة ملفات في آنٍ واحد، باستخدام نوى CPU متعددة لتقليل الوقت الإجمالي للمعالجة.  
- **أي مكتبة تدعم ذلك في .NET؟** Aspose.Zip لـ .NET يقدم خيارات ضغط متوازية مدمجة.  
- **هل أحتاج إلى ترخيص؟** يتوفر ترخيص مؤقت للاختبار؛ يلزم الحصول على ترخيص كامل للإنتاج.  
- **هل يمكنني إضافة ملفات إلى zip أثناء الإنشاء؟** نعم—استخدم `Archive.CreateEntry` لكل ملف تريد تضمينه.  
- **هل هو متوافق مع .NET Core/5/6؟** بالتأكيد، تعمل الواجهة البرمجية عبر جميع إصدارات .NET الحديثة.

## ما هو ضغط الملفات المتوازي؟
يعني ضغط الملفات المتوازي تقسيم عبء الضغط على عدة خيوط أو نوى، مما يسمح بضغط عدة ملفات (أو أجزاء من ملف كبير) في نفس الوقت. يساهم هذا النهج في تقليل الوقت اللازم لإنشاء **zip archive c#** مقارنةً بالضغط التسلسلي التقليدي.

## لماذا استخدام Aspose.Zip للضغط المتوازي؟
- **السرعة:** يستفيد بالكامل من معالجات متعددة النوى.  
- **القابلية للتوسع:** يتعامل مع دفعات كبيرة من الملفات دون زيادة متناسبة في وقت المعالجة.  
- **البساطة:** API عالية المستوى تُجرد تعقيدات الخيوط.  
- **المرونة:** يعمل مع أي نسخة من .NET ويتكامل بسلاسة مع قواعد الشيفرة الحالية.

## المتطلبات المسبقة

قبل المتابعة، تأكد من وجود ما يلي:

- معرفة أساسية بـ C# وتطوير .NET.  
- مكتبة Aspose.Zip لـ .NET مثبتة. يمكنك تنزيلها **[هنا](https://releases.aspose.com/zip/net/)**.  
- فهم لمفاهيم ضغط الملفات القياسية.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء المطلوبة في ملف C# حتى يعرف المترجم أين يجد الفئات التي ستستخدمها.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## الخطوة 1: إعداد دليل المستندات

عرّف المجلد الذي يحتوي على الملفات التي تريد ضغطها. يتم تخزين هذا المسار في المتغيّر `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: تهيئة عملية الضغط

افتح ملف ZIP جديد للكتابة. يضمن بيان `using` التخلص الصحيح من تدفق الملف بعد الانتهاء من العملية.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## الخطوة 3: قراءة وضغط الملفات بشكل متوازي

افتح كل ملف مصدر ترغب في إضافته إلى الأرشيف. في هذا المثال نعمل مع نصين كلاسيكيين، لكن يمكنك **إضافة ملفات إلى zip** لأي عدد من المستندات.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## الخطوة 4: إنشاء إدخالات الأرشيف

أنشئ كائن `Archive` وأضف كل ملف كإدخال منفصل. هنا يحدث خطوة **create zip archive c#**.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## الخطوة 5: تعريف معيار التوازي

قم بتكوين الضغط ليعمل بشكل متوازي عن طريق ضبط `ParallelOptions`. تُشير العلامة `ParallelCompressInMemory` إلى أن Aspose.Zip يجب أن يستخدم المعالجة المتوازية دائمًا.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## الخطوة 6: حفظ الأرشيف المضغوط

أخيرًا، اكتب الأرشيف إلى القرص مع الخيارات المطلوبة، بما في ذلك الترميز، التعليق، وإعدادات التوازي التي عُرّفت مسبقًا.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

تهانينا! لقد قمت الآن بأداء **ضغط الملفات المتوازي** باستخدام Aspose.Zip لـ .NET، وضغط **ملفات متعددة** بكفاءة في أرشيف واحد.

## المشكلات الشائعة والنصائح

- **الملفات الكبيرة:** إذا واجهت ضغطًا على الذاكرة، فكر في ضغط الملفات على دفعات بدلاً من تحميل الملف بالكامل في الذاكرة.  
- **سلامة الخيوط:** API Aspose.Zip آمن للخيوط في وضعية التوازي؛ تجنّب تعديل نفس التدفق من خيوط متعددة خارج المكتبة.  
- **تحسين الأداء:** جرّب تعديل `ParallelOptions.MaxDegreeOfParallelism` إذا كنت بحاجة لتقييد استهلاك CPU على الخوادم المشتركة.  

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Zip لـ .NET مع مكتبات .NET أخرى؟

ج1: نعم، تم تصميم Aspose.Zip لـ .NET ليتكامل بسلاسة مع مكتبات .NET الأخرى.

### س2: هل يتوفر ترخيص مؤقت لأغراض الاختبار؟

ج2: نعم، يمكنك الحصول على ترخيص مؤقت للاختبار من **[هنا](https://purchase.aspose.com/temporary-license/)**.

### س3: أين يمكنني العثور على دعم إضافي أو طرح أسئلة؟

ج3: زر **[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37)** للحصول على دعم المجتمع والنقاشات.

### س4: هل هناك أمثلة أو وثائق متاحة؟

ج4: استكشف **[وثائق Aspose.Zip](https://reference.aspose.com/zip/net/)** للحصول على أمثلة شاملة ووثائق مفصلة.

### س5: كيف يمكنني شراء Aspose.Zip لـ .NET؟

ج5: يمكنك شراء Aspose.Zip لـ .NET **[هنا](https://purchase.aspose.com/buy)**.

**آخر تحديث:** 2025-12-10  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}