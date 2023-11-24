---
title: ضغط الملفات باستخدام FileInfo في Aspose.Zip لـ .NET
linktitle: ضغط الملفات باستخدام FileInfo
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعلم كيفية ضغط الملفات باستخدام fileinfo مع Aspose.Zip لـ .NET. اتبع دليلنا خطوة بخطوة لإدارة الملفات بكفاءة.
type: docs
weight: 11
url: /ar/net/file-compression/compress-files-fileinfo/
---
## مقدمة

مرحبًا بك في دليلنا الشامل حول ضغط الملفات باستخدام Aspose.Zip لـ .NET! إذا كنت تتطلع إلى تحسين تخزين الملفات أو نقلها، فإن Aspose.Zip هو الحل الأمثل لك. في هذا البرنامج التعليمي، سنرشدك خلال عملية ضغط الملفات باستخدام فئة FileInfo، مع توفير دليل تفصيلي خطوة بخطوة. دعونا الغوص في!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Zip لـ .NET: تأكد من تثبيت مكتبة Aspose.Zip. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/zip/net/).

2. دليل المستندات: قم بإعداد دليل على نظامك لتخزين الملفات التي تريد ضغطها.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

أول الأشياء أولاً، تحديد الدليل الذي تم تخزين مستنداتك فيه. يمكنك استخدام الكود التالي:

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: ضغط الملفات باستخدام FileInfo

 الآن، دعونا ندخل في جوهر العملية. سوف نستخدم`FileInfo` فئة مع Aspose.Zip لضغط الملفات. اتبع الخطوات التالية:

### الخطوة 2.1: افتح ملفًا مضغوطًا

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### الخطوة 2.2: إنشاء كائنات FileInfo

 يخلق`FileInfo` كائنات للملفات التي تريد ضغطها:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### الخطوة 2.3: إنشاء الأرشيف وإضافة الإدخالات

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### الخطوة 2.4: احفظ الملف المضغوط

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

تهانينا! لقد نجحت في ضغط الملفات باستخدام فئة FileInfo في Aspose.Zip لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية ضغط الملفات بكفاءة باستخدام Aspose.Zip لـ .NET. باتباع هذه الخطوات، يمكنك تحسين قدرات إدارة الملفات لديك وتحسين استخدام المساحة. قم بتجربة أنواع وأحجام ملفات مختلفة لتجربة الإمكانات الكاملة لـ Aspose.Zip.

## الأسئلة الشائعة

### س1: هل Aspose.Zip متوافق مع كافة أنواع الملفات؟

A1: يدعم Aspose.Zip نطاقًا واسعًا من أنواع الملفات، مما يضمن تعدد استخدامات الضغط.

### س2: هل يمكنني استخدام Aspose.Zip للمشاريع التجارية؟

 ج2: بالتأكيد! زرنا[صفحة الشراء](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.

### س3: كيف يمكنني الحصول على الدعم لـ Aspose.Zip؟

 A3: انضم إلى مجتمعنا على[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للمساعدة والمناقشات.

### س4: هل هناك نسخة تجريبية مجانية متاحة؟

 ج4: نعم، يمكنك الاستيلاء على الخاص بك[تجربة مجانية هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟

 ج5: زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على معلومات حول الحصول على ترخيص مؤقت.