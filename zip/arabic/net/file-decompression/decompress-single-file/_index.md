---
title: فك ضغط ملف واحد باستخدام Aspose.Zip لـ .NET
linktitle: فك الضغط عن ملف واحد
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: استكشف العالم السلس لفك ضغط الملفات باستخدام Aspose.Zip for .NET. تعامل بسهولة مع الملفات المضغوطة في مشاريع C# الخاصة بك.
weight: 12
url: /ar/net/file-decompression/decompress-single-file/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# فك ضغط ملف واحد باستخدام Aspose.Zip لـ .NET

## مقدمة

في مجال تطوير .NET، يمثل Aspose.Zip حلاً قويًا للتعامل مع الملفات المضغوطة ببراعة. سيرشدك هذا البرنامج التعليمي خلال عملية فك ضغط ملف واحد باستخدام Aspose.Zip لـ .NET. استعد بينما نكشف عن قدرات هذه المكتبة القوية خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Zip for .NET Library: قم بتنزيل المكتبة وتثبيتها من ملف[Aspose.Zip لتوثيق .NET](https://reference.aspose.com/zip/net/).

- بيئة التطوير: جهز بيئة تطوير .NET وظيفية، بما في ذلك Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة.

- الفهم الأساسي لـ C#: تعرف على أساسيات برمجة C#.

الآن، دعونا نتسخ أيدينا ببعض التعليمات البرمجية!

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية لبدء رحلة Aspose.Zip الخاصة بك:

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## فك ضغط ملف واحد باستخدام Aspose.Zip لـ .NET

### الخطوة 1: قم بتعيين دليل المستندات الخاص بك

 ابدأ بتحديد الدليل الذي تم تخزين مستنداتك فيه. يستبدل`"Your Document Directory"` مع المسار الفعلي

```csharp
string dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء ملف مضغوط

استخدم مقتطف التعليمات البرمجية التالي لإنشاء ملف مضغوط سنقوم بفك ضغطه لاحقًا.

```csharp
CompressSingleFile.Run();
```

### الخطوة 3: فك ضغط الملف

الآن، دعونا نتعمق في جوهر الأمر – فك ضغط الملف الفردي. استخدم الكود التالي:

```csharp
// ExStart: إلغاء ضغط الملف المنفرد
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

يتعامل هذا الرمز بكفاءة مع عملية إلغاء الضغط، مما يوفر تحديثات التقدم في الوقت الفعلي.

## خاتمة

تهانينا! لقد نجحت في اجتياز تعقيدات فك ضغط ملف واحد باستخدام Aspose.Zip لـ .NET. احتضن قوة هذه المكتبة لتبسيط مهام معالجة الملفات الخاصة بك دون عناء.

## الأسئلة الشائعة

### س1: هل يمكنني ضغط ملفات متعددة باستخدام Aspose.Zip لـ .NET؟

A1: نعم، يدعم Aspose.Zip for .NET ضغط ملفات متعددة. الرجوع إلى الوثائق للحصول على تعليمات مفصلة.

### س2: هل Aspose.Zip متوافق مع .NET Core؟

ج2: بالتأكيد! يتكامل Aspose.Zip بسلاسة مع كل من .NET Framework و.NET Core.

### س3: كيف يمكنني التعامل مع الملفات المضغوطة المحمية بكلمة مرور؟

A3: يوفر Aspose.Zip طرقًا للعمل مع الأرشيفات المحمية بكلمة مرور. راجع الوثائق للحصول على التوجيه.

### س 4: هل هناك أي اعتبارات ترخيص لاستخدام Aspose.Zip؟

 ج4: قم بمراجعة معلومات الترخيص الموجودة على[موقع أسبوز](https://purchase.aspose.com/buy).

### س5: أين يمكنني طلب المساعدة إذا واجهت مشكلات؟

 ج5: قم بزيارة[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) لدعم المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
