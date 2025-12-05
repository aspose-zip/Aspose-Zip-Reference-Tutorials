---
date: 2025-12-05
description: تعلم كيفية إنشاء أرشيف zip وإضافة ملفات إلى zip باستخدام Aspose.Zip لـ
  .NET. يوضح هذا الدليل خطوة بخطوة كيفية ضغط الملفات باستخدام FileInfo في مشاريع ASP.NET.
language: ar
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية إنشاء أرشيف Zip باستخدام Aspose.Zip لـ .NET – ضغط الملفات باستخدام FileInfo
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء أرشيف Zip باستخدام Aspose.Zip لـ .NET

## المقدمة

إذا كنت بحاجة إلى **إنشاء أرشيف zip** برمجيًا، فإن Aspose.Zip لـ .NET يوفّر لك واجهة برمجة تطبيقات نظيفة وعالية الأداء تعمل في أي تطبيق .NET (بما في ذلك ASP.NET). في هذا الدرس سنستعرض ضغط الملفات باستخدام الفئة `FileInfo`، ونوضح لك كيفية **إضافة ملفات إلى zip**، ونشرح لماذا يُعد هذا النهج مثاليًا لمشاريع .NET الحديثة. لنبدأ!

## إجابات سريعة
- **ما هي أسهل طريقة لإنشاء أرشيف zip؟** استخدم فئة `Archive` في Aspose.Zip مع كائنات `FileInfo`.  
- **هل يمكنني إضافة ملفات متعددة مرة واحدة؟** نعم – فقط أنشئ كائن `FileInfo` لكل ملف واستدعِ `CreateEntry`.  
- **هل أحتاج إلى ترخيص خاص لـ ASP.NET؟** يلزم وجود ترخيص تجاري لـ Aspose.Zip للاستخدام في الإنتاج؛ نسخة تجريبية مجانية تكفي للتقييم.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **هل الواجهة برمجة التطبيقات Thread‑Safe؟** نعم، طالما أن كل خيط يعمل على نسخة `Archive` خاصة به.

## ما هو أرشيف Zip ولماذا ننشئه؟
أرشيف zip يجمع ملفًا أو أكثر في حاوية مضغوطة واحدة. هذا يقلل من مساحة التخزين، يسرّع نقل البيانات عبر الشبكة، ويبسّط عملية التوزيع. سواءً كنت تُرسل سجلات، تُصدّر تقارير، أو تُعبئ أصولًا لعميل، فإن معرفة **كيفية إنشاء ملفات أرشيف zip** برمجيًا تُعد مهارة قيّمة لأي مطوّر .NET.

## لماذا نستخدم Aspose.Zip لإضافة ملفات إلى Zip؟
- **عدم وجود تبعيات خارجية** – تنفيذ نقي بــ .NET.  
- **تحكم كامل في مستوى الضغط والترميز** (ASCII، UTF‑8، إلخ).  
- **دعم الملفات الكبيرة** (> 4 GB) وحماية كلمة المرور.  
- **واجهة برمجة تطبيقات موحدة عبر .NET Framework، .NET Core، و .NET 5+**.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكّد من وجود ما يلي:

1. **Aspose.Zip لـ .NET** مثبت. حمّل أحدث حزمة من [صفحة تنزيل Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. مجلد على جهازك يحتوي على الملفات التي تريد ضغطها (مثل `alice29.txt` و `fields.c`).  

## استيراد المساحات الاسمية

في أي ملف C# ستعمل فيه مع أرشيفات zip، أضف عبارات `using` التالية:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

تمنحك هذه المساحات الاسمية الوصول إلى فئة `Archive`، خيارات الحفظ، وأدوات الإدخال/الإخراج القياسية.

## دليل خطوة بخطوة

### الخطوة 1 إعداد دليل المستندات الخاص بك

أولاً، حدّد المجلد الذي يحتوي على الملفات المصدرية. استبدل العنصر النائب بالمسار المطلق أو النسبي على نظامك:

```csharp
string dataDir = "Your Document Directory";
```

> **نصيحة احترافية:** استخدم `Path.Combine` لبناء المسارات بطريقة متعددة المنصات.

### الخطوة 2: فتح ملف Zip للكتابة

أنشئ `FileStream` يشير إلى ملف zip الناتج. يُفتح التيار في وضع **Create**، مما يستبدل أي ملف موجود بنفس الاسم:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### الخطوة 3 إعداد كائنات `FileInfo` لكل ملف مصدر

`FileInfo` يمنح Aspose.Zip وصولًا مباشرًا إلى الملفات الفعلية على القرص. أنشئ نسخة واحدة لكل ملف تريد ضغطه:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **لماذا نستخدم `FileInfo`؟** لأنه يتجنّب تحميل الملف بالكامل إلى الذاكرة، وهو ما يكون مفيدًا بشكل خاص للملفات الكبيرة.

### الخطوة 4: إنشاء الأرشيف وإضافة الإدخالات

أنشئ كائن `Archive`، ثم استدعِ `CreateEntry` لكل `FileInfo`. المعامل الأول هو الاسم الذي سيظهر داخل الـ zip، والمعامل الثاني هو كائن `FileInfo` المصدر:

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

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|---------|-------|------|
| **ملف zip فارغ** | `FileInfo` يشير إلى مسار غير موجود | تحقق من `dataDir` وأسماء الملفات؛ استخدم `File.Exists` للتحقق قبل إنشاء الإدخالات. |
| **ترميز اسم الملف غير صحيح** | استخدام الترميز الافتراضي مع أسماء غير ASCII | عيّن `Encoding = Encoding.UTF8` في `ArchiveSaveOptions`. |
| **OutOfMemoryException عند الملفات الكبيرة** | تحميل الملف بالكامل إلى الذاكرة | `FileInfo` يبث الملف؛ تأكّد من عدم قراءة الملف إلى مصفوفة بايت في مكان آخر. |
| **رفض الإذن** | التطبيق يفتقر إلى صلاحية الكتابة في المجلد الهدف | شغّل التطبيق بصلاحيات مناسبة أو اختر مجلدًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة حماية كلمة مرور إلى أرشيف zip؟**  
ج: نعم. بعد إنشاء الـ `Archive`، عيّن `archive.Password = "yourPassword"` قبل استدعاء `Save`.

**س: هل من الممكن تحديث ملف zip موجود؟**  
ج: يدعم Aspose.Zip فتح أرشيف موجود باستخدام `Archive.Open` ثم إضافة إدخالات جديدة.

**س: كيف أضغط ملفات في وحدة تحكم ASP.NET MVC؟**  
ج: نفس الشيفرة تعمل؛ فقط تأكّد من إرجاع التيار الناتج كـ `FileResult` للعميل.

**س: هل يدعم Aspose.Zip خوارزميات تشفير؟**  
ج: يدعم تشفير ZipCrypto القياسي وتشفير AES‑256.

**س: ماذا لو أردت ضغط مجلد بالكامل بشكل متكرر؟**  
ج: استخدم حلقة عبر `Directory.GetFiles` (وبما في ذلك المجلدات الفرعية) لإنشاء `FileInfo` لكل ملف، ثم أضفه إلى الأرشيف.

## قسم الأسئلة المتكررة الموجود (يبقى دون تغيير)

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

أنت الآن تعرف **كيفية إنشاء أرشيف zip** باستخدام Aspose.Zip لـ .NET، وكيفية **إضافة ملفات إلى zip**، ولماذا تُعد هذه الطريقة مثالية لتطبيقات ASP.NET وغيرها من تطبيقات .NET. جرّب مستويات ضغط مختلفة، وترميزات، وخيارات تشفير لتخصيص الأرشيف وفق احتياجاتك الدقيقة. ضغطًا سعيدًا!

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.Zip لـ .NET 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}