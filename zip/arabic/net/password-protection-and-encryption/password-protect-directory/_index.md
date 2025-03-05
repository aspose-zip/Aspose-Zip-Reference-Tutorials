---
title: حماية الدلائل بكلمة مرور في .NET باستخدام البرنامج التعليمي Aspose.Zip
linktitle: دليل حماية كلمة المرور
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعرف على كيفية حماية الدلائل بكلمة مرور في .NET باستخدام Aspose.Zip. قم بتأمين ملفاتك بسهولة من خلال هذا البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/password-protection-and-encryption/password-protect-directory/
---

## مقدمة

في عالم تطوير .NET، تعد إدارة الدلائل وتأمينها جانبًا مهمًا في معالجة الملفات. يوفر Aspose.Zip for .NET حلاً قويًا لحماية الدلائل بكلمات المرور، مما يضمن سرية وسلامة بياناتك الحساسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية حماية الدليل بكلمة مرور خطوة بخطوة، باستخدام Aspose.Zip لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- الفهم الأساسي للغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Zip لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/zip/net/).
- دليل يحتوي على الملفات التي تريد حمايتها بكلمة مرور.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. تعد مساحات الأسماء هذه ضرورية للاستفادة من الوظائف التي يوفرها Aspose.Zip لـ .NET.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## الخطوة 1: قم بتعيين المسار إلى دليل الموارد

أولاً، قم بتحديد المسار إلى الدليل الذي يحتوي على الملفات التي تريد حمايتها بكلمة مرور.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: حماية كلمة المرور للدليل

 الآن، دعونا نتعمق في الكود الذي يقوم بحماية الدليل بكلمة مرور. نحن نستخدم ال`TraditionalEncryptionSettings` class لتعيين كلمة مرور وتطبيقها على الدليل المحدد.

```csharp
//ExStart: دليل حماية كلمة المرور
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: دليل كلمة المرور
    }
}
```

## الخطوة 3: شرح الكود

دعنا نحلل الكود لفهم كل خطوة:

-  إعداد ملف الإخراج:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` يقوم بإنشاء ملف ZIP جديد للمخرجات المشفرة.

-  تعريف الدليل:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` يحدد الدليل ليكون محميًا بكلمة مرور.

-  إنشاء وحفظ الإدخالات:`archive.CreateEntries(corpus)` يقوم بإنشاء إدخالات للملفات الموجودة في الدليل المحدد، و`archive.Save(zipFile)`يحفظ الأرشيف المحمي بكلمة مرور.

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية حماية الدليل بكلمة مرور باستخدام Aspose.Zip لـ .NET. باتباع هذه الخطوات، يمكنك ضمان أمان ملفاتك الحساسة بطريقة سهلة الاستخدام وفعالة.

---

## أسئلة مكررة

### هل Aspose.Zip for .NET مناسب للأدلة الكبيرة؟
نعم، تم تصميم Aspose.Zip for .NET للتعامل مع المجلدات الكبيرة بكفاءة، وتوفير الأداء الأمثل.

### هل يمكنني تغيير كلمة المرور لدليل محمي بالفعل؟
 نعم، يمكنك تعديل كلمة المرور عن طريق ضبط`TraditionalEncryptionSettings` في الكود وفقا لذلك.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Zip لـ .NET؟
 نعم، يلزم وجود ترخيص صالح لاستخدام Aspose.Zip لـ .NET في بيئة الإنتاج. يمكنك الحصول على ترخيص[هنا](https://purchase.aspose.com/buy).

### هل تتوفر نسخة تجريبية مجانية من Aspose.Zip لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على دعم إضافي لـ Aspose.Zip لـ .NET؟
 يمكنك زيارة[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) لأي دعم أو استفسار.

