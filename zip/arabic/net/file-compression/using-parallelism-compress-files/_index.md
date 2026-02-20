---
date: 2026-02-15
description: تعلم كيفية ضغط ملفات متعددة باستخدام C# و Aspose.Zip لـ .NET باستخدام
  الضغط المتوازي. دليل خطوة‑بخطوة، عينات كود، ونصائح لإنشاء أرشيفات سريعة وقابلة للتوسع.
linktitle: Using Parallelism to Zip Multiple Files in C#
second_title: Aspose.Zip .NET API – zip multiple files c# with Parallel Processing
title: كيفية ضغط ملفات متعددة في C# باستخدام Aspose.Zip والضغط المتوازي
url: /ar/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضغط ملفات متعددة c# باستخدام Aspose.Zip وضغط متوازي

## المقدمة

إذا كنت بحاجة إلى **ضغط ملفات متعددة c#** بسرعة وكفاءة، فإن الاستفادة من المعالجة المتوازية هي الطريقة المثلى. في تطبيقات .NET الحديثة، يمكن أن يصبح إنشاء أرشيفات ZIP كبيرة عنق زجاجة—خاصةً عند التعامل مع عشرات أو مئات الملفات. يزيل Aspose.Zip لـ .NET هذه المشكلة من خلال تقديم **ضغط ZIP متوازي** مدمج يوزع العمل على جميع أنوية المعالج المتاحة. في هذا الدرس سنستعرض العملية بالكامل: من إعداد البيئة إلى حفظ أرشيف ZIP مع تمكين التوازي.

## إجابات سريعة
- **ما هو ضغط ZIP المتوازي؟** يضغط عدة ملفات في الوقت نفسه، باستخدام خيوط متعددة لتقليل الوقت الكلي للمعالجة.  
- **أي مكتبة .NET تدعمه؟** Aspose.Zip لـ .NET يوفر واجهة برمجة تطبيقات بسيطة للضغط المتوازي.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم—يُطلب ترخيص كامل؛ يتوفر ترخيص مؤقت للاختبار.  
- **هل يمكن إضافة ملفات إلى ZIP أثناء الإنشاء؟** بالتأكيد—استخدم `Archive.CreateEntry` لكل ملف تريد تضمينه.  
- **هل هو متوافق مع .NET 6/7؟** نعم، تعمل الواجهة عبر جميع إصدارات .NET الحديثة.

## ما هو ضغط ملفات متعددة c#؟
يشير `zip multiple files c#` إلى إنشاء أرشيف ZIP واحد يحتوي على العديد من الملفات الفردية باستخدام كود C#. عندما تجمع ذلك مع **ضغط ZIP المتوازي**، تقوم المكتبة بمعالجة كل ملف في خيط منفصل، مما يقلل بشكل كبير الوقت اللازم لإنتاج الأرشيف النهائي.

## لماذا نستخدم Aspose.Zip للضغط المتوازي؟
- **السرعة:** يستفيد بالكامل من المعالجات متعددة النوى، غالبًا ما يقدم ضغطًا أسرع بمقدار 2‑3× مقارنةً بالطرق المتسلسلة.  
- **القابلية للتوسع:** يتعامل مع دفعات كبيرة من الملفات دون زيادة خطية في وقت المعالجة.  
- **البساطة:** تُجرد واجهة برمجة التطبيقات عالية المستوى عملية الخيوط، لتتمكن من التركيز على منطق عملك.  
- **المرونة:** يعمل مع أي نسخة من .NET (Framework, Core, .NET 5/6/7) ويتكامل بسهولة مع المشاريع الحالية.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- معرفة أساسية بـ C# وتطوير .NET.  
- تثبيت Aspose.Zip لـ .NET. يمكنك تنزيله **[من هنا](https://releases.aspose.com/zip/net/)**.  
- ترخيص مؤقت أو كامل (الترخيص المؤقت يكفي لهذا الدرس).  

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة في ملف C# حتى يعرف المترجم مكان العثور على الفئات التي ستستخدمها.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## الخطوة 1: إعداد دليل المستندات

عرّف المجلد الذي يحتوي على الملفات التي تريد ضغطها. يُخزن هذا المسار في المتغير `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: تهيئة عملية الضغط

افتح ملف ZIP جديد للكتابة. يضمن بيان `using` التخلص الصحيح من تدفق الملف بعد الانتهاء.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## الخطوة 3: قراءة وضغط الملفات بشكل متوازي

افتح كل ملف مصدر ترغب في إضافته إلى الأرشيف. في هذا المثال نتعامل مع نصين كلاسيكيين، لكن يمكنك **إضافة ملفات إلى zip** لأي عدد من المستندات.

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

أنشئ كائن `Archive` وأضف كل ملف كإدخال منفصل. هنا يحدث خطوة **إنشاء أرشيف zip c#**.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## الخطوة 5: تعريف معيار التوازي

قم بتكوين الضغط ليعمل بشكل متوازي عبر ضبط `ParallelOptions`. تُشير العلامة `ParallelCompressInMemory` إلى أن Aspose.Zip سيستخدم دائمًا المعالجة المتوازية.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## الخطوة 6: حفظ الأرشيف المضغوط

أخيرًا، اكتب الأرشيف إلى القرص مع الخيارات المطلوبة، بما في ذلك الترميز، التعليق، وإعدادات التوازي التي عُرِّفت مسبقًا.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **نصيحة احترافية:** إذا كنت تضغط ملفات كبيرة جدًا، فكر في ضبط `ParallelOptions.MaxDegreeOfParallelism` إلى قيمة أقل من عدد المعالجات المنطقية. يساعد ذلك في الحفاظ على استجابة الخادم تحت الحمل.

### حالات الاستخدام الشائعة

- **تقارير دفعة:** إنشاء حزمة ZIP من تقارير CSV اليومية للأنظمة المت downstream.  
- **أرشفة المستندات:** تخزين مجموعات كبيرة من ملفات PDF أو الصور أو السجلات في أرشيف واحد للنسخ الاحتياطي.  
- **واجهات تصدير البيانات:** إرجاع ملف ZIP يحتوي على ملفات بيانات متعددة للعميل في استجابة HTTP واحدة.

## المشكلات الشائعة والنصائح

- **ضغط الذاكرة على الملفات الضخمة:** بدلاً من تحميل الملف بالكامل في الذاكرة، قم ببث الملف على دفعات أو استخدم وضع `ParallelCompressInMemory` بشكل انتقائي.  
- **سلامة الخيوط:** واجهة Aspose.Zip آمنة للخيوط في الوضع المتوازي، لكن تجنّب تعديل نفس `FileStream` من خارج المكتبة أثناء عملية الضغط.  
- **تحسين الأداء:** جرّب تعديل `ParallelOptions.MaxDegreeOfParallelism` إذا احتجت إلى الحد من استهلاك المعالج على الخوادم المشتركة.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Zip لـ .NET مع مكتبات ضغط أخرى؟**  
ج: نعم، يمكن أن يتعايش Aspose.Zip مع مكتبات .NET أخرى؛ فقط احرص على تمييز مساحاتها الاسمية.

**س: هل يتوفر ترخيص مؤقت لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت للاختبار من **[هنا](https://purchase.aspose.com/temporary-license/)**.

**س: أين يمكنني طلب المساعدة إذا واجهت مشاكل؟**  
ج: زر **[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37)** للحصول على دعم المجتمع والنقاشات.

**س: أين يمكنني العثور على المزيد من أمثلة الشيفرة ووثائق API التفصيلية؟**  
ج: استكشف **[توثيق Aspose.Zip](https://reference.aspose.com/zip/net/)** للحصول على أمثلة شاملة.

**س: كيف أشتري ترخيصًا كاملًا لـ Aspose.Zip؟**  
ج: يمكنك شراء Aspose.Zip لـ .NET **[من هنا](https://purchase.aspose.com/buy)**.

---

**آخر تحديث:** 2026-02-15  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}