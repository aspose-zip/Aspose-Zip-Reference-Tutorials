---
title: فك ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET
linktitle: فك ضغط ملفات متعددة
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعرف على كيفية فك ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET. اتبع دليلنا خطوة بخطوة لإدارة الملفات بكفاءة.
type: docs
weight: 11
url: /ar/net/file-decompression/decompress-multiple-files/
---
## مقدمة

مرحبًا بك في برنامجنا التعليمي الشامل حول فك ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET! إذا كنت تتطلع إلى التعامل بكفاءة مع الملفات المضغوطة التي تحتوي على إدخالات متعددة، فأنت في المكان الصحيح. في هذا الدليل، سنرشدك خلال العملية خطوة بخطوة، باستخدام Aspose.Zip لـ .NET.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Zip لـ .NET: تأكد من تثبيت مكتبة Aspose.Zip لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/zip/net/).

- دليل المستندات: قم بإعداد دليل حيث يتم تخزين المستندات الخاصة بك. ستستخدم هذا كدليل أساسي في الكود.

الآن، دعونا نبدأ مع الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية لـ Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: ضغط ملفات متعددة

لفك ضغط ملفات متعددة، تحتاج أولاً إلى ملف مضغوط يحتوي على إدخالات متعددة. لنقم بإنشاء واحد:

```csharp
string dataDir = "Your Document Directory";

// قم بتشغيل طريقة الضغط
CompressMultipleFiles.Run();
```

## الخطوة الثانية: فك ضغط الملفات

والآن دعونا نقوم بفك ضغط الملفات خطوة بخطوة:

### الخطوة 2.1: فتح الملف المضغوط

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### الخطوة 2.2: إدخالات القائمة وتتبع التقدم

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### الخطوة 2.3: استخراج الإدخال الأول

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // قراءة وكتابة البيانات من الدفق المضغوط إلى ملف الاستخراج.
    }
}
```

### الخطوة 2.4: استخراج الإدخال الثاني

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

وهناك لديك! لقد نجحت في فك ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية الخطوات الأساسية لفك ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET. باتباع هذا الدليل، يمكنك إدارة الملفات المضغوطة بكفاءة وبسهولة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Zip for .NET في كل من المشاريع التجارية والشخصية؟

 A1: نعم، يمكن استخدام Aspose.Zip for .NET في المشاريع التجارية والشخصية. للحصول على تفاصيل الترخيص، راجع[معلومات ترخيص Aspose](https://purchase.aspose.com/buy).

### س2: هل تتوفر نسخة تجريبية مجانية من Aspose.Zip لـ .NET؟

 ج2: نعم، يمكنك استكشاف النسخة التجريبية المجانية من Aspose.Zip لـ .NET[هنا](https://releases.aspose.com/zip/net).

### س3: أين يمكنني العثور على دعم إضافي لـ Aspose.Zip لـ .NET؟

 ج3: قم بزيارة[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) لدعم المجتمع والمناقشات.

### س4: كيف يمكنني شراء ترخيص مؤقت لـ Aspose.Zip لـ .NET؟

 ج٤: احصل على ترخيص مؤقت لـ Aspose.Zip لـ .NET[هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل هناك أي متطلبات نظام محددة لاستخدام Aspose.Zip لـ .NET؟

 ج5: راجع[توثيق](https://reference.aspose.com/zip/net/) لمتطلبات النظام التفصيلية.