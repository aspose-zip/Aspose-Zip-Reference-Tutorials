---
date: 2026-02-28
description: تعلم كيفية إضافة مجلد إلى ملف zip وإضافة ملفات إلى zip باستخدام Aspose.Zip
  لـ .NET. يوضح هذا الدليل خطوة بخطوة كيفية ضغط الملفات باستخدام FileInfo في مشاريع
  ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية إضافة مجلد إلى ملف ZIP باستخدام Aspose.Zip لـ .NET – ضغط الملفات باستخدام
  FileInfo
url: /ar/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مجلد إلى ملف Zip باستخدام Aspose.Zip لـ .NET

## المقدمة

إذا كنت بحاجة إلى **إنشاء أرشيف zip** برمجيًا، فإن Aspose.Zip لـ .NET يوفّر لك واجهة برمجة تطبيقات نظيفة وعالية الأداء تعمل في أي تطبيق .NET (بما في ذلك ASP.NET). في هذا الدرس سنستعرض ضغط الملفات باستخدام فئة `FileInfo`، ونوضح لك كيفية **إضافة ملفات إلى zip**، ونشرح لماذا يُعَدّ هذا النهج مثالياً لمشروعات .NET الحديثة. سنغطي أيضًا كيفية **إضافة مجلد إلى zip** حتى تتمكن من تجميع أدلة كاملة في خطوة واحدة. لنبدأ!

## إجابات سريعة
- **ما هي أسهل طريقة لإنشاء أرشيف zip؟** استخدم فئة `Archive` من Aspose.Zip مع كائنات `FileInfo`.  
- **هل يمكنني إضافة ملفات متعددة مرة واحدة؟** نعم – فقط أنشئ كائن `FileInfo` لكل ملف واستدعِ `CreateEntry`.  
- **هل أحتاج إلى ترخيص خاص لـ ASP.NET؟** يلزم وجود ترخيص تجاري لـ Aspose.Zip للإنتاج؛ نسخة تجريبية مجانية تكفي للتقييم.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **هل الواجهة برمجة التطبيقات آمنة للاستخدام المتعدد الخيوط؟** نعم، طالما أن كل خيط يعمل على نسخة `Archive` خاصة به.

## ما هو أرشيف Zip ولماذا ننشئه؟
أرشيف zip يجمع ملفًا أو أكثر في حاوية مضغوطة واحدة. هذا يقلل من مساحة التخزين، يسرّع نقل البيانات عبر الشبكة، ويبسّط عملية التوزيع. سواءً كنت تُرسل سجلات، تُصدّر تقارير، أو تُحزم موارد لعميل، فإن معرفة **كيفية إنشاء أرشيف zip** برمجيًا تُعدّ مهارة قيّمة لأي مطوّر .NET.

## لماذا نستخدم Aspose.Zip لإضافة ملفات إلى zip؟
- **لا توجد تبعيات خارجية** – تنفيذ نقي بلغة .NET.  
- **تحكم كامل في مستوى الضغط والترميز** (ASCII، UTF‑8، إلخ).  
- **يدعم الملفات الكبيرة** (> 4 GB) وحماية كلمة المرور.  
- **واجهة برمجة تطبيقات موحدة عبر .NET Framework و .NET Core و .NET 5+**.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

1. **Aspose.Zip لـ .NET** مُثبّت. حمّل أحدث حزمة من [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. مجلد على جهازك يحتوي على الملفات التي تريد ضغطها (مثال: `alice29.txt` و `fields.c`).  

## استيراد المساحات الاسمية

في أي ملف C# ستتعامل فيه مع أرشيفات zip، أضف بيانات `using` التالية:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

هذه المساحات الاسمية تمنحك الوصول إلى فئة `Archive`، خيارات الحفظ، وأدوات الإدخال/الإخراج القياسية.

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل المستندات

أولاً، عرّف المجلد الذي يحتوي على ملفات المصدر. استبدل العنصر النائب بالمسار المطلق أو النسبي على نظامك:

```csharp
string dataDir = "Your Document Directory";
```

> **نصيحة احترافية:** استخدم `Path.Combine` لبناء المسارات بطريقة متوافقة مع جميع الأنظمة.

### الخطوة 2: فتح ملف Zip للكتابة

أنشئ `FileStream` يشير إلى ملف zip الناتج. يُفتح التيار في وضع **Create**، مما يستبدل أي ملف موجود بالاسم نفسه:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### الخطوة 3: تحضير كائنات `FileInfo` لكل ملف مصدر

توفر `FileInfo` وصولًا مباشرًا إلى الملفات الفعلية على القرص. أنشئ نسخة واحدة لكل ملف تريد ضغطه:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **لماذا نستخدم `FileInfo`؟** لأنها تتجنّب تحميل الملف بالكامل إلى الذاكرة، وهو ما يكون مفيدًا خاصةً للملفات الكبيرة.

### الخطوة 4: إنشاء الأرشيف وإضافة الإدخالات

قم بإنشاء كائن `Archive`، ثم استدعِ `CreateEntry` لكل `FileInfo`. المعامل الأول هو الاسم الذي سيظهر داخل zip، والمعامل الثاني هو كائن `FileInfo` المصدر:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### الخطوة 5: حفظ أرشيف Zip بالترميز المطلوب

أخيرًا، احفظ الأرشيف إلى `FileStream` الذي فتحته مسبقًا. هنا نستخدم ترميز ASCII لأسماء الإدخالات، لكن يمكنك التحويل إلى UTF‑8 إذا احتوت أسماء الملفات على أحرف غير ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

عند خروج كتل `using`، تُغلق التيارات تلقائيًا ويصبح ملف zip جاهزًا للاستخدام.

## كيفية إضافة مجلد إلى Zip باستخدام Aspose.Zip

إذا كنت بحاجة إلى **إضافة مجلد إلى zip** بدلاً من ملفات فردية، فإن العملية بسيطة:

1. **استعرض المجلد** باستخدام `DirectoryInfo.GetFiles` (ويمكنك أيضًا استدعاء `GetDirectories` للتكرار).  
2. **أنشئ كائن `FileInfo`** لكل ملف يتم اكتشافه.  
3. **استدعِ `CreateEntry`** مع مسار نسبي يتضمن اسم المجلد، مثل `"MyFolder/Report.pdf"`.

نظرًا لأن الواجهة تعمل مع `FileInfo`، لن تحتاج أبدًا إلى تحميل الملفات بالكامل إلى الذاكرة، مما يجعلها آمنة للأدلة الكبيرة. تعمل هذه التقنية أيضًا في سيناريوهات **zip multiple files asp.net** حيث تُولّد مجموعة تقارير في الوقت الفعلي وتحتاج إلى تقديمها كأرشيف واحد.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **ملف zip فارغ** | مسار `FileInfo` غير موجود | تحقق من `dataDir` وأسماء الملفات؛ استخدم `File.Exists` للتحقق قبل إنشاء الإدخالات. |
| **ترميز اسم الملف غير صحيح** | استخدام الترميز الافتراضي مع أسماء غير ASCII | عيّن `Encoding = Encoding.UTF8` في `ArchiveSaveOptions`. |
| **OutOfMemoryException عند الملفات الكبيرة** | تحميل الملف بالكامل إلى الذاكرة | `FileInfo` يبث الملف؛ تأكد من عدم قراءته إلى مصفوفة بايت في مكان آخر. |
| **رفض الإذن** | التطبيق لا يملك صلاحية كتابة للمجلد الهدف | شغّل التطبيق بصلاحيات مناسبة أو اختر دليلًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة حماية بكلمة مرور إلى أرشيف zip؟**  
ج: نعم. بعد إنشاء كائن `Archive`، عيّن `archive.Password = "yourPassword"` قبل استدعاء `Save`.

**س: هل يمكن تحديث ملف zip موجود؟**  
ج: يدعم Aspose.Zip فتح أرشيف موجود باستخدام `Archive.Open` ثم إضافة إدخالات جديدة.

**س: كيف أضغط ملفات في وحدة تحكم ASP.NET MVC؟**  
ج: الكود نفسه يعمل؛ فقط تأكّد من إرجاع التيار كـ `FileResult` للعميل.

**س: هل يدعم Aspose.Zip خوارزميات تشفير؟**  
ج: يدعم تشفير ZipCrypto القياسي وتشفير AES‑256.

**س: ماذا لو أردت ضغط مجلد بشكل متكرر؟**  
ج: قم بالتكرار عبر `Directory.GetFiles` (والأدلة الفرعية) وأنشئ `FileInfo` لكل ملف، ثم أضفه إلى الأرشيف.

## أسئلة إضافية

**س: كيف أنشئ أرشيف zip .net لمجموعات بيانات كبيرة؟**  
ج: استخدم كائنات `FileInfo` لبث البيانات واضبط `CompressionLevel` في `ArchiveSaveOptions` للحصول على أفضل أداء.

**س: هل يمكنني استخدام Aspose.Zip في واجهة برمجة تطبيقات ويب .NET Core (zip files asp.net core)؟**  
ج: بالتأكيد – المكتبة متوافقة تمامًا مع .NET Core 3.1 وما بعده.

**س: هل هناك طريقة لإضافة مجلد إلى zip دون كتابة حلقة مخصصة؟**  
ج: لا توجد طريقة “إضافة مجلد” واحدة في Aspose.Zip، لكن التكرار باستخدام `DirectoryInfo` خفيف الوزن ويمنحك تحكمًا كاملًا في أسماء الإدخالات.

**س: هل تؤثر حماية كلمة المرور على سرعة الضغط؟**  
ج: إضافة التشفير يضيف قليلًا من الحمل، لكن الأثر ضئيل في معظم الحالات.

**س: ما الترخيص المطلوب للنشر التجاري؟**  
ج: يلزم الحصول على ترخيص مدفوع لـ Aspose.Zip للإنتاج؛ يمكن استخدام النسخة التجريبية للتطوير والاختبار.

## قسم الأسئلة المتكررة (مُحافظ عليه دون تعديل)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## الخلاصة

أنت الآن تعرف **كيفية إضافة مجلد إلى zip** و**كيفية إنشاء أرشيف zip** باستخدام Aspose.Zip لـ .NET، وكيفية **إضافة ملفات إلى zip**، ولماذا تُعد هذه الطريقة مثالية لتطبيقات ASP.NET وغيرها من تطبيقات .NET. جرّب مستويات ضغط مختلفة، وترميزات، وخيارات تشفير لتخصيص الأرشيف وفق احتياجاتك الدقيقة. ضغطًا سعيدًا!

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Zip لـ .NET 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}