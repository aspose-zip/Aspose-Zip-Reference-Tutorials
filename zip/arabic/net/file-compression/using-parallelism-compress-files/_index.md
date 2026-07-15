---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضغط ملفات متعددة c# باستخدام ضغط متوازي Aspose.Zip

## مقدمة

إذا كنت بحاجة إلى **zip multiple files c#** بسرعة وكفاءة، فإن الاستفادة من المعالجة المتوازية هي الطريقة المثلى. في تطبيقات .NET الحديثة، يمكن أن يصبح إنشاء أرشيفات zip الكبيرة عنق زجاجة—خاصةً عند التعامل مع العشرات أو المئات من الملفات. يزيل Aspose.Zip لـ .NET هذه المشكلة من خلال تقديم **parallel zip compression** المدمج الذي يوزع العمل على جميع أنوية المعالج المتاحة. في هذا البرنامج التعليمي سنستعرض العملية بالكامل: من إعداد البيئة إلى حفظ أرشيف zip مع تمكين التوازي، وسنظهر لك أيضًا كيفية **create zip archive c#** التي تعمل بسلاسة على .NET Core.

## إجابات سريعة
- **What is parallel zip compression?** إنه يضغط عدة ملفات في نفس الوقت، باستخدام خيوط متعددة لتقليل الوقت الكلي للمعالجة.  
- **Which .NET library supports it?** توفر Aspose.Zip لـ .NET واجهة برمجة تطبيقات بسيطة للضغط المتوازي.  
- **Do I need a license for production?** نعم—يتطلب ترخيص كامل؛ يتوفر ترخيص مؤقت للاختبار.  
- **Can I add files to zip on the fly?** بالطبع—استخدم `Archive.CreateEntry` لكل ملف تريد تضمينه.  
- **Is it compatible with .NET 6/7?** نعم، تعمل الواجهة عبر جميع بيئات .NET الحديثة.

## ما هو zip multiple files c#؟
`zip multiple files c#` يشير إلى ممارسة إنشاء أرشيف ZIP واحد يحتوي على العديد من الملفات الفردية، باستخدام كود C#. عندما تجمع ذلك مع **parallel zip compression**، تقوم المكتبة بمعالجة كل ملف في خيط منفصل، مما يقلل بشكل كبير الوقت اللازم لإنتاج الأرشيف النهائي.

## لماذا تستخدم Aspose.Zip للضغط المتوازي؟
يتيح لك الضغط المتوازي الاستفادة من كل نواة في جهاز متعدد المعالجات، غالبًا ما يوفر معدل نقل أسرع **2‑3×** مقارنةً بالنهج أحادي الخيط. كما أنه يتوسع بسلاسة: إضافة المزيد من الملفات لا يزيد الوقت الزمني بشكل خطي، وتتعامل الواجهة مع إدارة الخيوط نيابةً عنك، بحيث يمكنك التركيز على منطق الأعمال.

- **Speed:** يستخدم جميع المعالجات المنطقية، مما يقلل وقت إنشاء zip بنسبة تصل إلى 70 % في الأحمال النموذجية.  
- **Scalability:** يتعامل مع دفعات من أكثر من 500 ملف دون زيادة متناسبة في وقت المعالج.  
- **Simplicity:** تُخفي الأساليب عالية المستوى تعقيد `System.Threading.Tasks`.  
- **Flexibility:** يدعم .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10، بما في ذلك .NET 6/7 للخدمات السحابية الأصلية.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

- معرفة أساسية بـ C# وتطوير .NET.  
- تثبيت Aspose.Zip لـ .NET. يمكنك تنزيله **[here](https://releases.aspose.com/zip/net/)**.  
- ترخيص مؤقت أو كامل (الترخيص المؤقت يكفي لهذا البرنامج التعليمي).  

## استيراد المساحات الاسمية

مساحة الأسماء `Aspose.Zip` تحتوي على جميع الأنواع التي تحتاجها للعمل مع أرشيفات ZIP.

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

أولاً، استورد مساحات الأسماء المطلوبة في ملف C# الخاص بك حتى يعرف المترجم أين يجد الفئات التي ستستخدمها.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## الخطوة 1: إعداد دليل المستندات الخاص بك

حدد المجلد الذي يحتوي على الملفات التي تريد ضغطها. يتم تخزين هذا المسار في المتغير `dataDir`، والذي يمكنك توجيهه إلى أي موقع على القرص.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: تهيئة عملية الضغط

افتح ملف ZIP جديد للكتابة. يضمن بيان `using` التخلص الصحيح من تدفق الملف بعد العملية، مما يمنع تسرب مقبض الملف.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## الخطوة 3: قراءة وضغط الملفات بشكل متوازي

`Parallel.ForEach` ينفّذ حلقة foreach حيث قد تُنفّذ التكرارات بشكل متزامن على خيوط متعددة.

افتح كل ملف مصدر تنوي إضافته إلى الأرشيف. في هذا المثال نعمل مع نصين كلاسيكيين، ولكن يمكنك **add files to zip** لأي عدد من المستندات. توزع حلقة `Parallel.ForEach` العمل عبر الخيوط تلقائيًا.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

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

الفئة `Archive` هي الكائن الأعلى مستوى في Aspose.Zip الذي يمثل حاوية ZIP التي تقوم بإنشائها.

`CreateEntry` ينشئ إدخالًا جديدًا في أرشيف ZIP لملف محدد. كل استدعاء لـ `CreateEntry` يضيف إدخال ملف جديد إلى الأرشيف.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## الخطوة 5: تعريف معيار التوازي

`ParallelOptions` هو نوع في .NET يتحكم في كيفية تنفيذ الحلقات المتوازية.

قم بتكوين الضغط للعمل بشكل متوازي عن طريق ضبط `ParallelOptions`. علم `ParallelCompressInMemory` يخبر Aspose.Zip باستخدام المعالجة المتوازية دائمًا، بينما يتيح لك `MaxDegreeOfParallelism` تحديد الحد الأقصى لعدد الخيوط المتزامنة.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## الخطوة 6: حفظ الأرشيف المضغوط

أخيرًا، اكتب الأرشيف إلى القرص باستخدام الخيارات المطلوبة، بما في ذلك الترميز، التعليق، وإعدادات التوازي المحددة سابقًا. طريقة `Save` تُنهي ملف ZIP.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **نصيحة احترافية:** إذا كنت تضغط ملفات كبيرة جدًا، فكر في ضبط `ParallelOptions.MaxDegreeOfParallelism` إلى قيمة أقل من عدد المعالجات المنطقية. هذا يساعد على إبقاء الخادم مستجيبًا تحت الحمل.

### حالات الاستخدام الشائعة
- **Batch reporting:** إنشاء حزمة zip من تقارير CSV اليومية للأنظمة المتلقية.  
- **Document archiving:** تخزين مجموعات كبيرة من ملفات PDF أو الصور أو السجلات في أرشيف واحد للنسخ الاحتياطي.  
- **Data export APIs:** إرجاع ملف zip يحتوي على ملفات بيانات متعددة إلى العميل في استجابة HTTP واحدة.  

## المشكلات الشائعة والنصائح
- **Memory pressure on huge files:** بدلاً من تحميل الملف بالكامل في الذاكرة، قم ببث الملف على أجزاء أو استخدم وضع `ParallelCompressInMemory` بشكل انتقائي.  
- **Thread safety:** واجهة Aspose.Zip آمنة للخيوط في الوضع المتوازي، لكن تجنب تعديل نفس `FileStream` من خارج المكتبة أثناء تشغيل الضغط.  
- **Performance tuning:** جرب ضبط `ParallelOptions.MaxDegreeOfParallelism` إذا كنت بحاجة لتقليل استخدام المعالج على الخوادم المشتركة.  

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.Zip لـ .NET مع مكتبات ضغط أخرى؟**  
**ج:** نعم، يمكن أن يتعايش Aspose.Zip مع مكتبات .NET الأخرى؛ فقط احرص على تمييز مساحات الأسماء الخاصة بها.

**س: هل يتوفر ترخيص مؤقت لأغراض الاختبار؟**  
**ج:** نعم، يمكنك الحصول على ترخيص مؤقت للاختبار من **[here](https://purchase.aspose.com/temporary-license/)**.

**س: أين يمكنني طلب المساعدة إذا واجهت مشاكل؟**  
**ج:** زر **[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37)** للحصول على دعم المجتمع والنقاشات.

**س: أين يمكنني العثور على المزيد من أمثلة الشيفرة ووثائق API التفصيلية؟**  
**ج:** استكشف **[توثيق Aspose.Zip](https://reference.aspose.com/zip/net/)** للحصول على أمثلة شاملة.

**س: كيف يمكنني شراء ترخيص كامل لـ Aspose.Zip؟**  
**ج:** يمكنك شراء Aspose.Zip لـ .NET **[here](https://purchase.aspose.com/buy)**.

---
**Last Updated:** 2026-06-09  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [ضغط ملفات متعددة c# – ضغط سهل مع Aspose.Zip لـ .NET](/zip/net/file-compression/compress-multiple-files/)
- [كيفية إنشاء أرشيف Zip وإضافة ملف إلى Zip باستخدام Aspose.Zip لـ .NET](/zip/net/file-compression/compress-single-file/)
- [ضغط ملفات متعددة مع التشفير في Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}