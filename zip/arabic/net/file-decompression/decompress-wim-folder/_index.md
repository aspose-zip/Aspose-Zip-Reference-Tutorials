---
date: 2025-12-17
description: تعرّف على كيفية استخراج ملفات WIM إلى مجلد باستخدام Aspose.Zip لـ .NET.
  اتبع هذا الدليل خطوةً بخطوة لفك ضغط أرشيفات WIM بفعالية في تطبيقات .NET الخاصة بك.
linktitle: Decompress Wim to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية استخراج WIM إلى مجلد باستخدام Aspose.Zip لـ .NET
url: /ar/net/file-decompression/decompress-wim-folder/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخراج ملفات WIM إلى مجلد باستخدام Aspose.Zip لـ .NET

## المقدمة

مرحبًا بكم في هذا الدرس الشامل حول **كيفية استخراج ملفات WIM** إلى مجلد باستخدام Aspose.Zip لـ .NET. Aspose.Zip هي مكتبة قوية توفر قدرات سلسة للعمل مع تنسيقات الأرشيف المختلفة في تطبيقات .NET. في هذا الدرس، سنرشدكم خلال عملية فك ضغط أرشيف Wim إلى مجلد محدد خطوة بخطوة.

## إجابات سريعة
- **ما المكتبة الموصى بها؟** Aspose.Zip for .NET  
- **هل يمكنني استخراج ملفات WIM على .NET Core؟** نعم، تعمل الواجهة البرمجية مع .NET Core، .NET 5+، و .NET 6+.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **ما هو الحد الأدنى لإصدار .NET؟** .NET Framework 4.5+ أو .NET Core 3.1+.  
- **كم يستغرق الاستخراج من الوقت؟** عادةً بضع ثوانٍ للصور القياسية لـ WIM؛ قد تستغرق الصور الأكبر وقتًا أطول.

## المتطلبات المسبقة

قبل الغوص في الدرس، تأكد من توفر المتطلبات المسبقة التالية:

- مكتبة Aspose.Zip: تأكد من تثبيت مكتبة Aspose.Zip لـ .NET. يمكنك تنزيلها من [الموقع الإلكتروني](https://releases.aspose.com/zip/net/).
- دليل المستندات: قم بإعداد دليل المستندات حيث توجد ملف أرشيف Wim الذي تريد فك ضغطه.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك. هذه الخطوة تضمن حصولك على إمكانية الوصول إلى وظائف Aspose.Zip.

```csharp
using System.IO;
using Aspose.Zip.Wim;
```

## كيفية استخراج WIM إلى مجلد

فيما يلي الخطوات الدقيقة التي توضح **كيفية استخراج أرشيفات WIM** باستخدام Aspose.Zip. اتبع كل خطوة بعناية.

### الخطوة 1: تعيين دليل المستندات الخاص بك

حدد مسار الدليل حيث يقع ملف أرشيف Wim الخاص بك. استبدل `"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "Your Document Directory";
```

### الخطوة 2: فك ضغط أرشيف Wim

افتح ملف أرشيف Wim باستخدام `FileStream` ثم استخرج المحتويات إلى دليل محدد باستخدام Aspose.Zip.

```csharp
using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
{
    using (WimArchive archive = new WimArchive(fs))
    {
        archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
    }
}
```

تقوم هذه الشفرة بقراءة ملف أرشيف Wim، والوصول إلى صورته الأولى، واستخراج محتوياته إلى دليل الإخراج المحدد.

## الخاتمة

تهانينا! لقد تعلمت بنجاح **كيفية استخراج أرشيفات WIM** إلى مجلد باستخدام Aspose.Zip لـ .NET. هذه العملية البسيطة والقوية تتيح لك إدارة واستخراج البيانات من أرشيفات Wim بفعالية في تطبيقات .NET الخاصة بك.

## الأسئلة المتكررة

### Q1: هل يمكنني استخدام Aspose.Zip لـ .NET مع تنسيقات أرشيف أخرى؟
A1: نعم، يدعم Aspose.Zip تنسيقات أرشيف مختلفة، بما في ذلك ZIP و TAR و GZIP وغيرها.

### Q2: أين يمكنني العثور على مزيد من الأمثلة والوثائق لـ Aspose.Zip؟
A2: استكشف [وثائق Aspose.Zip](https://reference.aspose.com/zip/net/) للحصول على أمثلة مفصلة ووثائق شاملة.

### Q3: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Zip لـ .NET؟
A3: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### Q4: كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Zip لـ .NET؟
A4: احصل على تراخيص مؤقتة من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### Q5: أين يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.Zip لـ .NET؟
A5: زر [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على الدعم والنقاشات.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}