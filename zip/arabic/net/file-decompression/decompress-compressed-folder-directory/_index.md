---
title: قم بفك ضغط المجلد المضغوط إلى الدليل في Aspose.Zip لـ .NET
linktitle: قم بفك ضغط المجلد المضغوط إلى الدليل
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: أطلق العنان لإمكانات Aspose.Zip لـ .NET! تعرف على كيفية فك ضغط المجلدات بسهولة باستخدام هذا الدليل التفصيلي خطوة بخطوة. انغمس في عالم الضغط والاستخراج السلس.
weight: 14
url: /ar/net/file-decompression/decompress-compressed-folder-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بفك ضغط المجلد المضغوط إلى الدليل في Aspose.Zip لـ .NET

## مقدمة

مرحبًا بك في عالم Aspose.Zip for .NET، وهي مكتبة قوية تمكّن المطورين من التعامل مع المجلدات المضغوطة دون عناء. في هذا البرنامج التعليمي، سوف نتعمق في عملية فك ضغط مجلد مضغوط إلى دليل باستخدام Aspose.Zip for .NET. اربط حزام الأمان بينما نأخذك خلال كل خطوة بالتفصيل، ونزيل الغموض عن تعقيدات هذه الأداة القوية.

## المتطلبات الأساسية

قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Zip for .NET Library: قم بتنزيل المكتبة وتثبيتها من ملف[Aspose.Zip لوثائق .NET](https://reference.aspose.com/zip/net/).

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة لفهم شامل.

## الخطوة 1: فتح المجلد المضغوط

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

 ابدأ بفتح المجلد المضغوط باستخدام ملف`FileStream`اضبط مسار الملف وفقًا لبنية مشروعك.

## الخطوة 2: إنشاء مثيل الأرشيف

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

 إنشاء مثيل ل`Archive` كائن، ويمر`zipFile` البث وتوفير خيارات التحميل الاختيارية، مثل كلمة مرور فك التشفير في هذه الحالة.

## الخطوة 3: الاستخراج إلى الدليل

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

 وأخيرا، استخدم`ExtractToDirectory` طريقة فك الضغط واستخراج محتويات المجلد المضغوط إلى الدليل المحدد.

كرر هذه الخطوات مع المجلدات المضغوطة الأخرى، مما يضمن التكامل السلس مع Aspose.Zip for .NET.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية فك ضغط مجلد مضغوط إلى دليل باستخدام Aspose.Zip لـ .NET. أثبتت هذه المكتبة أنها مصدر لا يقدر بثمن للمطورين الذين يتعاملون مع البيانات المضغوطة في مشاريعهم.

## الأسئلة الشائعة

### س1: هل يتوافق Aspose.Zip for .NET مع تنسيقات الضغط المختلفة؟

ج1: نعم، يدعم Aspose.Zip for .NET تنسيقات الضغط الشائعة مثل ZIP وGZIP والمزيد.

### س2: هل يمكنني استخدام Aspose.Zip لـ .NET في كل من المشاريع التجارية وغير التجارية؟

ج2: بالتأكيد، يمكنك استخدام Aspose.Zip for .NET في كل من التطبيقات التجارية وغير التجارية.

### س3: هل تتوفر نسخة تجريبية مجانية من Aspose.Zip لـ .NET؟

 ج3: نعم، يمكنك استكشاف الميزات من خلال النسخة التجريبية المجانية من خلال زيارة الموقع[هنا](https://releases.aspose.com/).

### س٤: كيف يمكنني الحصول على دعم Aspose.Zip لـ .NET؟

 ج4: اطلب المساعدة من مجتمع Aspose.Zip على[منتدى الدعم](https://forum.aspose.com/c/zip/37).

### س5: هل أحتاج إلى ترخيص مؤقت لاختبار Aspose.Zip لـ .NET؟

 ج5: نعم، يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
