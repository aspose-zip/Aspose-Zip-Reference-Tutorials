---
date: 2026-01-28
description: تعلم كيفية إنشاء أرشيف tar.gz، وإضافة ملفات إلى tar وضغطها باستخدام Aspose.Zip
  لـ .NET – طريقة سريعة وموثوقة لأرشفة الملفات.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إنشاء أرشيف tar.gz وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات إلى tar وإنشاء TarGz باستخدام Aspose.Zip لـ .NET

## Introduction

في تطبيقات .NET الحديثة، **إضافة ملفات إلى tar** بسرعة وموثوقية هي متطلب شائع — سواء كنت تقوم بضغط السجلات، أو إعداد البيانات للتخزين السحابي، أو بناء حزم النشر. Aspose.Zip لـ .NET يوفّر لك واجهة برمجة تطبيقات نظيفة وعالية الأداء **لإضافة ملفات إلى tar**، ثم ضغط الأرشيف إلى تنسيق **tar.gz** الشائع. في هذا البرنامج التعليمي ستتعلم بالضبط كيف **إنشاء أرشيف tar.gz** من الصفر، خطوة بخطوة، باستخدام مكتبة Aspose.Zip .NET.

## Quick Answers
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip for .NET  
- **كيف أضيف ملفات إلى tar؟** استخدم `TarArchive.CreateEntry` لكل ملف.  
- **هل يمكنني الضغط مباشرة إلى tar.gz؟** نعم — استدعِ `SaveGzipped`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص Aspose صالح للاستخدام غير التجريبي.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## What is “add files to tar”?

إضافة ملفات إلى أرشيف tar تعني تجميع ملفات متعددة في حاوية واحدة غير مضغوطة. يحافظ تنسيق tar على هياكل الدليل وبيانات التعريف الخاصة بالملفات، مما يجعله مثالياً للأرشفة قبل الضغط الاختياري (مثل gzip) **لإنشاء أرشيف tar.gz**.

## Why use Aspose.Zip to compress files to tar.gz?
- **لا أدوات خارجية** – كل شيء يُنفّذ داخل كود .NET الخاص بك.  
- **أداء عالي** – واجهة برمجة تطبيقات تعتمد على التدفق تتعامل بفعالية مع الملفات الكبيرة.  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.  
- **مجموعة ميزات غنية** – يدعم التشفير، حماية كلمة المرور، وسمات الإدخالات المخصصة.  

## Prerequisites

قبل البدء، تأكد من توفر ما يلي:

- خبرة أساسية في تطوير .NET.  
- Visual Studio (أو أي بيئة تطوير مفضلة).  
- Aspose.Zip for .NET مثبت – راجع الوثائق الرسمية [هنا](https://reference.aspose.com/zip/net/).  
- مكتبة Aspose.Zip تم تحميلها من [هذا الرابط](https://releases.aspose.com/zip/net/).

## Import Namespaces

في مشروع .NET الخاص بك، استورد المساحات الاسمية التي تُظهر الفئات المتعلقة بـ tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to create tar.gz archive with Aspose.Zip for .NET

### Step 1: Set Your Document Directory

أولاً، حدّد مسار المجلد الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** استخدم `Path.Combine` عند بناء المسارات لتجنب مشاكل الفواصل الخاصة بالمنصات.

### Step 2: Initialize the TarArchive

أنشئ كائن `TarArchive` سيحمل الإدخالات.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### Step 3: Add Files – the core of “add files to tar”

داخل كتلة `using`، أضف كل ملف تريد تضمينه في الأرشيف.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

كل استدعاء لـ `CreateEntry` يأخذ **اسم الإدخال** (كيف سيظهر الملف داخل tar) و**مسار الملف المصدر** على القرص.

### Step 4: Save as a Gzipped Tar (how to compress files to tar.gz)

أخيراً، اكتب محتويات tar إلى تدفق gzip لإنتاج ملف `archive.tar.gz` مضغوط.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` يتعامل مع كل من تعبئة tar وضغط gzip في استدعاء واحد سلس.

## Common Use Cases

| السيناريو | لماذا تساعد “إضافة ملفات إلى tar” |
|----------|-----------------------------------|
| **تجميع السجلات** | تجميع سجلات اليوم في أرشيف واحد قبل رفعه إلى التخزين السحابي. |
| **حزم النشر** | إنشاء حزم tar.gz محمولة لخوادم Linux من خط أنابيب بناء على Windows. |
| **نسخ احتياطي للبيانات** | الحفاظ على هيكل المجلدات وبيانات التعريف مع الحفاظ على حجم النسخة الاحتياطية منخفضاً. |

## Common Issues and Solutions

- **خطأ عدم العثور على الملف** – تأكد من أن `dataDir` ينتهي بالفاصل المناسب أو استخدم `Path.Combine`.  
- **الملفات الكبيرة تسبب ضغطًا على الذاكرة** – استخدم الإصدارات المعتمدة على التدفق (`CreateEntry` مع `Stream`) لتجنب تحميل الملفات بالكامل في الذاكرة.  
- **مخرجات Gzip تالفة** – تحقق من إغلاق الأرشيف (`using` block) قبل استدعاء `SaveGzipped`.

## Frequently Asked Questions

**س: هل Aspose.Zip لـ .NET متوافق مع جميع تطبيقات .NET؟**  
ج: نعم، يعمل مع مشاريع .NET Framework و .NET Core و .NET 5/6/7.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip لـ .NET؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لطلب ترخيص تجريبي.

**س: هل هناك أي قيود على حجم الملفات؟**  
ج: المكتبة مُحسّنة للملفات الكبيرة؛ لا يوجد حد ثابت للحجم سوى الذاكرة المتاحة في النظام.

**س: أين يمكنني الحصول على الدعم؟**  
ج: استخدم منتدى الدعم المجتمعي [هنا](https://forum.aspose.com/c/zip/37) للحصول على مساعدة من مهندسي Aspose ومطوريين آخرين.

**س: هل يمكن تجربة Aspose.Zip لـ .NET مجانًا؟**  
ج: بالتأكيد — حمّل النسخة التجريبية المجانية من [صفحة إصدارات Aspose Zip](https://releases.aspose.com/zip/net).

## Conclusion

لقد تعلمت الآن **كيفية إضافة ملفات إلى tar**، إنشاء أرشيف tar، وضغطه إلى **tar.gz** باستخدام Aspose.Zip لـ .NET. يزيل هذا النهج الاعتماد على أدوات خارجية، يمنحك تحكمًا دقيقًا في محتويات الأرشيف، ويتعامل مع مجموعات بيانات كبيرة. لا تتردد في استكشاف ميزات إضافية في Aspose.Zip مثل التشفير، سمات الإدخالات المخصصة، وواجهات برمجة التطبيقات المتدفقة لتعزيز سير عمل الأرشفة الخاص بك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose