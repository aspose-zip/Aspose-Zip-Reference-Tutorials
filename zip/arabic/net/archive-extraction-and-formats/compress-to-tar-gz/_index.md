---
date: 2026-02-20
description: تعلم كيفية إنشاء أرشيف tar، وإضافة ملفات إلى tar، وضغطه إلى tar.gz باستخدام
  Aspose.Zip لـ .NET – طريقة سريعة وعبر‑المنصات لإنشاء أرشيفات TarGz.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET

## Introduction

في تطبيقات .NET الحديثة، **إنشاء أرشيف tar** و**إضافة ملفات إلى tar** بسرعة وموثوقية هو مطلب شائع — سواء كنت تقوم بتجميع السجلات، أو إعداد البيانات للتخزين السحابي، أو بناء حزم النشر. يوفر Aspose.Zip لـ .NET واجهة برمجة تطبيقات نظيفة وعالية الأداء **لإضافة ملفات إلى tar**، ثم ضغط الأرشيف إلى تنسيق **tar.gz** واسع الاستخدام. في هذا الدليل سنستعرض العملية بالكامل، من إعداد مشروعك إلى إنتاج ملف `archive.tar.gz` جاهز للإرسال.

## Quick Answers
- **ما المكتبة التي يجب استخدامها؟** Aspose.Zip for .NET  
- **كيف يمكنني إضافة ملفات إلى tar؟** استخدم `TarArchive.CreateEntry` لكل ملف.  
- **هل يمكنني الضغط مباشرة إلى tar.gz؟** نعم—استدعِ `SaveGzipped`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص Aspose صالح للاستخدام غير التجريبي.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “add files to tar”?

إضافة ملفات إلى أرشيف tar يعني تجميع ملفات متعددة في حاوية واحدة غير مضغوطة. يحافظ تنسيق tar على بنية الدليل وبيانات التعريف الخاصة بالملفات، مما يجعله مثاليًا للأرشفة قبل الضغط الاختياري (مثل gzip) لإنشاء أرشيف **tar.gz**.

## Why use Aspose.Zip to compress files to tar.gz?
- **لا أدوات خارجية** – كل شيء يعمل داخل كود .NET الخاص بك.  
- **أداء عالي** – واجهة برمجة تطبيقات تعتمد على التدفقات تتعامل مع الملفات الكبيرة بكفاءة.  
- **tar متعدد المنصات** – يعمل على Windows وLinux وmacOS دون تعديل.  
- **مجموعة ميزات غنية** – يدعم التشفير، حماية كلمة المرور، وسمات الإدخالات المخصصة.

## Prerequisites

قبل أن تبدأ، تأكد من وجود:

- خبرة أساسية في تطوير .NET.  
- Visual Studio (أو أي بيئة تطوير مفضلة).  
- تم تثبيت Aspose.Zip for .NET – راجع الوثائق الرسمية [هنا](https://reference.aspose.com/zip/net/).  
- مكتبة Aspose.Zip تم تحميلها من [هذا الرابط](https://releases.aspose.com/zip/net/).

## Import Namespaces

في مشروع .NET الخاص بك، استورد المساحات الاسم التي تعرض الفئات المتعلقة بـ tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to add files to tar using Aspose.Zip for .NET

### Step 1: Set Your Document Directory

أولاً، وجه الكود إلى المجلد الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

> **نصيحة احترافية:** استخدم `Path.Combine` عند بناء المسارات لتجنب مشاكل الفواصل الخاصة بالمنصة.

### Step 2: Create a TarGz Archive

الآن سننشئ أرشيف tar، نضيف الإدخالات، ونضغطه في تدفق واحد سلس.

#### 2.1 Initialize the TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Add Files – the core of “add files to tar”

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

كل استدعاء `CreateEntry` يأخذ **اسم الإدخال** (كيف سيظهر الملف داخل tar) و**مسار الملف المصدر** على القرص. يمكنك استدعاء `CreateEntry` بشكل متكرر لإضافة ملفات متعددة إلى tar في أرشيف واحد.

#### 2.3 Save as a Gzipped Tar (how to compress tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` يكتب محتويات tar إلى تدفق gzip، مما يمنحك ملف `archive.tar.gz` مضغوط جاهز للتوزيع.

## Common Use Cases

| السيناريو | لماذا تساعد إضافة ملفات إلى tar |
|----------|--------------------------------|
| **تجميع السجلات** | تجميع السجلات اليومية في أرشيف واحد قبل رفعه إلى التخزين السحابي. |
| **حزم النشر** | إنشاء حزم tar.gz قابلة للنقل لخوادم Linux من خط تجميع Windows. |
| **نسخ احتياطي للبيانات** | الحفاظ على هيكل المجلدات وبيانات التعريف مع الحفاظ على حجم النسخة الاحتياطية منخفضًا. |

## Common Issues and Solutions

- **خطأ عدم العثور على الملف** – تأكد من أن `dataDir` ينتهي بالفاصل المناسب للمسار أو استخدم `Path.Combine`.  
- **الملفات الكبيرة تسبب ضغطًا على الذاكرة** – استخدم الإصدارات المعتمدة على التدفق (`CreateEntry` مع `Stream`) لتجنب تحميل الملفات بالكامل في الذاكرة.  
- **مخرجات gzip تالفة** – تحقق من إغلاق الأرشيف (`using` block) قبل استدعاء `SaveGzipped`.  

## Frequently Asked Questions

**س: هل Aspose.Zip لـ .NET متوافق مع جميع تطبيقات .NET؟**  
ج: نعم، يعمل مع مشاريع .NET Framework و .NET Core و .NET 5/6/7.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip لـ .NET؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لطلب ترخيص تجريبي.

**س: هل هناك أي حدود لحجم الملفات؟**  
ج: المكتبة مُحسّنة للملفات الكبيرة؛ لا يوجد حد ثابت للحجم سوى الذاكرة المتاحة في النظام.

**س: أين يمكنني الحصول على الدعم؟**  
ج: استخدم منتدى الدعم المجتمعي [هنا](https://forum.aspose.com/c/zip/37) للحصول على مساعدة من مهندسي Aspose ومطوريين آخرين.

**س: هل يمكنني تجربة Aspose.Zip لـ .NET مجانًا؟**  
ج: بالتأكيد — حمّل النسخة التجريبية المجانية من [صفحة إصدارات Aspose Zip](https://releases.aspose.com/zip/net).

## Conclusion

لقد تعلمت الآن **كيفية إنشاء أرشيف tar**، إضافة ملفات إليه، وضغطه إلى **tar.gz** باستخدام Aspose.Zip لـ .NET. يزيل هذا النهج الاعتماد على أدوات خارجية، يمنحك تحكمًا دقيقًا في محتويات الأرشيف، ويتعامل مع مجموعات بيانات كبيرة. لا تتردد في استكشاف ميزات إضافية في Aspose.Zip مثل التشفير، سمات الإدخالات المخصصة، وواجهات برمجة التطبيقات المتدفقة لتعزيز سير عمل الأرشفة الخاص بك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose