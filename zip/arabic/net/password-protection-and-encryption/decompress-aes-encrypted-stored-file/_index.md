---
title: Aspose.Zip for .NET - فك تشفير الملفات المشفرة AES
linktitle: قم بفك ضغط الملف المخزن المشفر AES
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعرف على كيفية فك ضغط الملفات المخزنة المشفرة بتقنية AES في Aspose.Zip لـ .NET باستخدام هذا الدليل الشامل خطوة بخطوة. عزز مهاراتك في تطوير .NET اليوم!
type: docs
weight: 19
url: /ar/net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

## مقدمة

مرحبًا بك في هذا الدليل المفصل خطوة بخطوة حول فك ضغط الملفات المخزنة المشفرة بتقنية AES باستخدام Aspose.Zip لـ .NET. Aspose.Zip هي مكتبة .NET قوية تمكن المطورين من العمل مع الملفات المضغوطة دون عناء. في هذا البرنامج التعليمي، سنركز على فك ضغط الملفات المشفرة بتقنية AES، مما يوفر لك فهمًا واضحًا للعملية.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Zip for .NET: تأكد من تثبيت مكتبة Aspose.Zip. يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/zip/net/).

-  نموذج ملف مشفر AES: قم بتنزيل نموذج ملف مشفر AES من[هذا الرابط](https://releases.aspose.com/zip/net/).

- دليل المستندات الخاص بك: قم بإعداد دليل حيث تريد تخزين الملف الذي تم فك ضغطه. استبدل "دليل المستندات الخاص بك" في مقتطف الشفرة بمسار الدليل الفعلي.

## استيراد مساحات الأسماء

في مقتطف الشفرة المقدم، ستلاحظ استخدام مساحات أسماء مختلفة. تأكد من تضمينها في مشروعك:

```csharp
using System.IO;
using Aspose.Zip;
```

## الخطوة 1: تحديد دليل الموارد

تأكد من تحديد المسار إلى دليل الموارد الخاص بك. في المثال، استبدل "دليل المستندات الخاص بك" بالمسار الفعلي.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: افتح الأرشيف المشفر

```csharp
using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
{
    using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
    {
        using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
        {
            // تابع إلى الخطوات التالية...
        }
    }
}
```

## الخطوة 3: فك ضغط الإدخال المشفر

```csharp
using (var decompressed = archive.Entries[0].Open())
{
    byte[] b = new byte[8192];
    int bytesRead;
    while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
    {
        extracted.Write(b, 0, bytesRead);
    }
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية فك ضغط الملفات المخزنة المشفرة بتقنية AES باستخدام Aspose.Zip لـ .NET. تسمح لك هذه العملية بالعمل بكفاءة مع الأرشيفات المشفرة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Zip لـ .NET مع خوارزميات تشفير أخرى؟
يدعم Aspose.Zip بشكل أساسي تشفير AES. تحقق من الوثائق للحصول على آخر التحديثات.

### هل هناك نسخة تجريبية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على دعم Aspose.Zip لـ .NET؟
 قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/zip/37) للحصول على المساعدة من المجتمع.

### ما هي تنسيقات الملفات المدعومة للضغط وإلغاء الضغط؟
يدعم Aspose.Zip العديد من التنسيقات، بما في ذلك ZIP و7z وTAR. الرجوع إلى الوثائق للحصول على قائمة شاملة.

### هل يمكنني استخدام Aspose.Zip لأغراض تجارية؟
 نعم، يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy) للاستخدام التجاري.

