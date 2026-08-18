---
date: 2026-06-24
description: تعلم كيفية ضغط LZMA في Aspose.Zip لـ .NET، مع تحسين التخزين وكفاءة نقل
  البيانات.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: ضغط إلى Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط LZMA في Aspose.Zip لـ .NET
url: /ar/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط LZMA باستخدام Aspose.Zip لـ .NET

## مقدمة

في هذا البرنامج التعليمي، ستتعلم **كيفية ضغط LZMA** في Aspose.Zip لـ .NET، وهي مهارة حاسمة لتحسين مساحة التخزين وتعزيز كفاءة نقل البيانات. يقدم LZMA (خوارزمية Lempel‑Ziv‑Markov chain) أرشيفات أصغر بنسبة تصل إلى 70 % مقارنةً بملفات ZIP التقليدية مع الحفاظ على سرعة فك الضغط، مما يجعلها مثالية للسيناريوهات ذات النطاق الترددي المحدود.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Zip لـ .NET  
- **ما الخوارزمية التي يغطيها هذا الدليل؟** ضغط LZMA  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10  
- **كم من الوقت تستغرق التنفيذ؟** عادةً أقل من 10 دقائق لملف أساسي.

## ما هو ضغط LZMA؟

LZMA هو خوارزمية ضغط غير فقدان عالية النسبة تستخدم ضغط القاموس وترميز النطاق. يمكنه تقليل حجم ملفات النص بنسبة 30‑70 % مع الحفاظ على سرعة فك الضغط مماثلة لZIP. بالنسبة لمجموعات البيانات الكبيرة، يقلل LZMA من تكاليف التخزين ويسرّع نقل الشبكة دون التضحية بسلامة البيانات.

## لماذا تستخدم Aspose.Zip لـ LZMA؟

يدعم Aspose.Zip **5 خوارزميات ضغط** (ZIP، Deflate، BZIP2، LZMA، و ZSTD) ويمكنه معالجة الأرشيفات حتى **4 جيجابايت** دون تحميل الملف بالكامل إلى الذاكرة. تعالج المكتبة مستندات مئات الصفحات في أقل من **2 ثانية** على خادم عادي، مما يوفر الأداء والقابلية للتوسع.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- Aspose.Zip لـ .NET: تأكد من تثبيت مكتبة Aspose.Zip. يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/zip/net/).
- دليل المستندات: اختر أو أنشئ مجلدًا يحتوي على الملفات التي تريد ضغطها.

## استيراد مساحات الأسماء

أضف مساحات الأسماء المطلوبة في أعلى ملف C# الخاص بك حتى تتمكن من الوصول إلى وظائف LZMA في Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## كيف أُحدد مجلد المصدر للضغط؟

حدد المجلد الذي يحتوي على الملفات التي تنوي أرشفتها. توفير دليل مصدر مخصص يضمن معالجة الملفات المقصودة فقط، يقلل من خطر تضمين بيانات غير مرغوب فيها، ويسهل إدارة المسارات عند العمل على مهام ضغط متعددة في نفس المشروع.

```csharp
string dataDir = "Your Document Directory";
```

## كيف أقوم بضغط ملف باستخدام LZMA؟

`LzmaArchive` هي فئة Aspose.Zip لإنشاء وإدارة أرشيفات LZMA.

أنشئ كائنًا من `LzmaArchive`، ووجهه إلى ملف المصدر، ثم استدعِ `Save` لإنشاء أرشيف `.lzma`. هذا النمط المكوّن من سطرين ينفّذ كامل سير عمل الضغط، يدير التدفقات داخليًا وينتج ملفًا مضغوطًا جاهزًا للتوزيع أو التخزين.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## كيف يمكنني التأكد من نجاح الضغط؟

`Console.WriteLine` يكتب سطرًا من النص إلى وحدة التحكم القياسية.

بعد حفظ الأرشيف، اطبع رسالة تأكيد قصيرة باستخدام `Console.WriteLine`. هذا الرد الفوري يساعد المطورين على التحقق من إكمال خطوة الضغط دون أخطاء، يبسط عملية تصحيح الأخطاء أثناء عمليات البناء الآلية، ويوفر معلومات حالة واضحة عندما يتم دمج الروتين في تطبيقات أو سكريبتات أكبر.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## المشكلات الشائعة والحلول

- **الملف غير موجود** – تحقق من أن سلسلة المسار تستخدم شرطتين مائلتين عكسيتين (`\\`) أو سلسلة حرفية (`@"C:\Path"`).  
- **الذاكرة غير كافية** – تقوم Aspose.Zip ببث البيانات، لكن الملفات الكبيرة جدًا قد تتطلب زيادة حد الذاكرة للعملية.  
- **الترخيص غير مفعّل** – تأكد من استدعاء `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` قبل أي عملية في Aspose.Zip.

## الأسئلة المتكررة

**س: هل يمكنني ضغط ملفات متعددة في أرشيف LZMA واحد؟**  
ج: نعم. استدعِ `archive.AddFile()` لكل ملف قبل استدعاء `archive.Save()`.

**س: هل هناك طريقة لتعيين مستوى الضغط لـ LZMA؟**  
ج: `LzmaArchive` يستخدم مستوى الضغط الافتراضي، الذي يوفر توازنًا جيدًا بين السرعة والحجم. الإعدادات المتقدمة متاحة عبر `LzmaEncoder` إذا كنت بحاجة إلى تحكم دقيق.

**س: هل سيعمل ملف .lzma الناتج على أنظمة غير Windows؟**  
ج: بالطبع. تنسيق LZMA مستقل عن المنصة، لذا يمكن فك ضغط الأرشيف على أي نظام تشغيل باستخدام أداة متوافقة مع LZMA.

**س: كيف أقوم بفك ضغط أرشيف LZMA باستخدام Aspose.Zip؟**  
ج: استخدم مُنشئ `LzmaArchive` مع مسار الأرشيف، ثم استدعِ `ExtractToDirectory()` لاستخراج محتوياته.

**س: هل يدعم Aspose.Zip ضغطًا متدفقًا لتجنب تحميل الملفات بالكامل إلى الذاكرة؟**  
ج: نعم. يمكنك العمل مع التدفقات بتمرير كائنات `Stream` إلى طُرُق `SetSource()` و `Save()`.

---

**آخر تحديث:** 2026-06-24  
**تم الاختبار مع:** Aspose.Zip لـ .NET (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [كيفية ضغط الملفات باستخدام Aspose.Zip لـ .NET](/zip/net/file-compression/compress-file/)
- [كيفية فتح أرشيف GZip وتقنيات الضغط الأخرى باستخدام Aspose.Zip لـ .NET](/zip/net/other-compression-techniques/)
- [ضغط الملفات c# – إنشاء أرشيف 7z باستخدام Aspose.Zip لـ .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}