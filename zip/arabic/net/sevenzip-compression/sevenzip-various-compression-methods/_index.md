---
title: إنشاء سبعة ملفات مضغوطة - البرنامج التعليمي Aspose.Zip لـ .NET
linktitle: SevenZip مع طرق ضغط مختلفة
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعلم كيفية إنشاء ملفات Seven Zip باستخدام Aspose.Zip لـ .NET باستخدام طرق ضغط مختلفة. خطوات سهلة لـ LZMA2 وBZip2 وStore (بدون ضغط).
type: docs
weight: 12
url: /ar/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## مقدمة

في مجال تطوير .NET، تعد إدارة الملفات وضغطها مهمة شائعة. يوفر Aspose.Zip for .NET حلاً قويًا للعمل مع الأرشيفات المضغوطة، حيث يقدم مجموعة متنوعة من طرق الضغط. في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام Aspose.Zip لـ .NET لإنشاء ملفات Seven Zip بطرق ضغط مختلفة.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:

- فهم أساسي للبرمجة C#.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Zip لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/zip/net/).

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. استخدم مقتطف الكود التالي للبدء:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## ضغط LZMA2

```csharp
//ExStart: SevenZip مع طرق ضغط مختلفة

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## ضغط BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## تخزين، لا ضغط

```csharp
//تخزين، لا ضغط
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا تعدد استخدامات Aspose.Zip for .NET في إنشاء ملفات Seven Zip باستخدام طرق ضغط مختلفة. سواء كنت بحاجة إلى نسب ضغط عالية أو تفضل عدم الضغط على الإطلاق، فإن Aspose.Zip يوفر المرونة اللازمة لتلبية متطلباتك.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Zip لـ .NET مع أي نوع من الملفات؟
نعم، يدعم Aspose.Zip for .NET نطاقًا واسعًا من أنواع الملفات، مما يسمح لك بضغط التنسيقات المختلفة وفك ضغطها.

### هل تتوفر نسخة تجريبية مجانية من Aspose.Zip لـ .NET؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق Aspose.Zip لـ .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/zip/net/).

### كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Zip لـ .NET؟
 يمكن الحصول على تراخيص مؤقتة[هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على الدعم لـ Aspose.Zip لـ .NET؟
 يمكنك طلب الدعم على[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37).
