---
date: 2025-12-17
description: تعلم كيفية ضغط LZMA في Aspose.Zip لـ .NET، مع تحسين كفاءة التخزين ونقل
  البيانات.
linktitle: Compress to Lzma
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط LZMA في Aspose.Zip لـ .NET
url: /ar/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط LZMA في Aspose.Zip لـ .NET

## مقدمة

في هذا البرنامج التعليمي، ستتعلم **كيفية ضغط LZMA** في Aspose.Zip لـ .NET، وهي مهارة حاسمة لتحسين مساحة التخزين وتعزيز كفاءة نقل البيانات. يوفر Aspose.Zip لـ .NET حلاً قويًا لضغط الملفات، ويقدم عدة خوارزميات—بما في ذلك LZMA—حتى تتمكن من اختيار الأنسب لسيناريوك.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Zip for .NET  
- **أي خوارزمية يغطيها هذا الدليل؟** ضغط LZMA  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للاختبار؛ ترخيص كامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **كم من الوقت يستغرق التنفيذ؟** عادةً أقل من 10 دقائق لملف أساسي.

## كيفية ضغط LZMA

## المتطلبات المسبقة

قبل الغوص في التفاصيل، تأكد من أن لديك ما يلي:

- Aspose.Zip for .NET: تأكد من تثبيت مكتبة Aspose.Zip. يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/zip/net/).
- Document Directory: اختر أو أنشئ مجلدًا يحتوي على الملفات التي تريد ضغطها.

## استيراد مساحات الأسماء

أضف مساحات الأسماء المطلوبة في أعلى ملف C# الخاص بك حتى تتمكن من الوصول إلى وظائف LZMA في Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## الخطوة 1: تعيين دليل المستندات

```csharp
string dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار الفعلي للمجلد الذي يحتوي على الملفات التي تنوي ضغطها.

## الخطوة 2: ضغط ملف باستخدام LZMA

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

هنا نقوم بإنشاء مثال من `LzmaArchive`، ونشير إليه إلى ملف المصدر (`alice29.txt`)، ثم نحفظ الناتج المضغوط كـ `archive.lzma`.

## الخطوة 3: عرض رسالة النجاح

```csharp
Console.WriteLine("Successfully Compressed a File");
```

بعد انتهاء الضغط، يُظهر هذا السطر للمستخدم أن العملية نجحت.

## الخاتمة

تهانينا! لقد تعلمت بنجاح **كيفية ضغط LZMA** باستخدام Aspose.Zip لـ .NET. تساعدك هذه التقنية الفعّالة في تقليل مساحة التخزين وتسريع نقل البيانات، مما يجعل تطبيقاتك أكثر استجابة وفعالية من حيث التكلفة.

## الأسئلة المتكررة

### س1: هل Aspose.Zip متوافق مع خوارزميات ضغط أخرى؟

ج1: نعم، يدعم Aspose.Zip لـ .NET عدة خوارزميات ضغط، بما في ذلك Lzma و Deflate و BZip2.

### س2: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Zip لـ .NET؟

ج2: الوثائق متاحة [هنا](https://reference.aspose.com/zip/net/).

### س3: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟

ج3: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س4: هل هناك عينات شفرة متاحة لخوارزميات ضغط مختلفة؟

ج4: نعم، يمكنك العثور على عينات شفرة في الوثائق لخوارزميات الضغط المختلفة.

### س5: أين يمكنني طلب الدعم أو طرح أسئلة حول Aspose.Zip لـ .NET؟

ج5: زر [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على الدعم والمناقشات.

## الأسئلة المتكررة الشائعة

**س: هل يمكنني ضغط ملفات متعددة في أرشيف LZMA واحد؟**  
ج: نعم. استدعِ `archive.AddFile()` لكل ملف قبل استدعاء `archive.Save()`.

**س: هل هناك طريقة لتحديد مستوى الضغط لـ LZMA؟**  
ج: تستخدم فئة `LzmaArchive` مستوى الضغط الافتراضي، والذي يوفر توازنًا جيدًا بين السرعة والحجم. تتوفر إعدادات متقدمة عبر `LzmaEncoder` إذا كنت بحاجة إلى تحكم دقيق.

**س: هل سيعمل ملف .lzma الناتج على أنظمة غير Windows؟**  
ج: بالتأكيد. تنسيق LZMA مستقل عن المنصة، لذا يمكن فك ضغط الأرشيف على أي نظام تشغيل باستخدام أداة متوافقة مع LZMA.

**س: كيف يمكنني فك ضغط أرشيف LZMA باستخدام Aspose.Zip؟**  
ج: استخدم مُنشئ `LzmaArchive` مع مسار الأرشيف، ثم استدعِ `ExtractToDirectory()` لاستخراج محتوياته.

**س: هل يدعم Aspose.Zip ضغطًا متدفقًا لتجنب تحميل الملفات بالكامل في الذاكرة؟**  
ج: نعم. يمكنك العمل مع التدفقات بتمرير كائنات `Stream` إلى طريقتي `SetSource()` و `Save()`.

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Zip لـ .NET (أحدث إصدار في وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}