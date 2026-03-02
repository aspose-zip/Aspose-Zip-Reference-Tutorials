---
date: 2026-03-02
description: تعلم كيفية إنشاء أرشيف ZIP محمي بكلمة مرور وضغط الملفات باستخدام كلمات
  مرور في .NET باستخدام Aspose.Zip. اتبع دليلنا خطوة بخطوة.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إنشاء أرشيف ZIP محمي بكلمة مرور في .NET باستخدام Aspose.Zip
url: /ar/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء أرشيف ZIP محمي بكلمة مرور في .NET باستخدام Aspose.Zip

## مقدمة

عندما تحتاج إلى مشاركة بيانات حساسة، يُعد **أرشيف ZIP محمي بكلمة مرور** أحد أبسط وأكثر الطرق فعالية للحفاظ على أمان المعلومات. في تطبيقات .NET، تجعل Aspose.Zip من السهل **ضغط الملفات باستخدام كلمات مرور**، مما يمنح كل ملف مفتاح تشفير خاص به. في هذا الدرس ستتعلم بالضبط كيفية إنشاء مثل هذا الأرشيف، ولماذا هو مهم، وأين يمكنك تطبيقه في مشاريع العالم الحقيقي.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** توفر Aspose.Zip لـ .NET دعمًا مدمجًا لكلمات مرور لكل ملف وطرق تشفير متعددة.  
- **كم عدد أسطر الكود؟** حوالي 30 سطرًا، بما في ذلك الإعداد وحفظ الأرشيف.  
- **هل يمكن لكل ملف أن يكون له كلمة مرور مختلفة؟** نعم – يمكنك تعيين كلمة مرور فريدة لكل إدخال.  
- **ما هي طرق التشفير المتاحة؟** ZipCrypto التقليدي، AES‑128، و AES‑256.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية.

## ما هو أرشيف ZIP محمي بكلمة مرور؟
أرشيف ZIP محمي بكلمة مرور هو ملف مضغوط (ZIP) يتطلب كلمة مرور لاستخراج محتوياته. يمكن لكلمة المرور حماية الأرشيف بالكامل أو الإدخالات الفردية، وتوفر الخوارزميات الحديثة مثل AES‑128/256 تشفيرًا قويًا.

## لماذا ضغط الملفات باستخدام كلمات مرور باستخدام Aspose.Zip؟
- **أمان دقيق** – تعيين كلمة مرور مميزة لكل ملف، وهو مثالي لسيناريوهات متعددة المستأجرين.  
- **معايير تشفير متعددة** – اختر بين ZipCrypto القديم وAES القوي.  
- **بدون أدوات خارجية** – يتم التعامل مع كل شيء برمجيًا داخل قاعدة كود .NET الخاصة بك.  
- **الأداء** – ضغط سريع باستخدام Deflate مع الحفاظ على حجم الأرشيف صغيرًا.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك:

- **Aspose.Zip لـ .NET** – قم بتثبيت المكتبة في مشروعك. الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/zip/net/).  
- **حمّل أحدث حزمة** إذا لم تقم بذلك بعد، من [هذا الرابط](https://releases.aspose.com/zip/net/).  
- مجلد يحتوي على الملفات التي تريد ضغطها.

## استيراد مساحات الأسماء

أضف مساحات الأسماء المطلوبة في أعلى ملف C# الخاص بك:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## الخطوة 1: تعيين مسار دليل الموارد

وجه الكود إلى المجلد الذي يحتوي على الملفات المصدرية:

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: ضغط الملفات باستخدام كلمات مرور فردية

الآن سننشئ **أرشيف ZIP محمي بكلمة مرور** حيث يستخدم كل ملف كلمة مرور وطريقة تشفير خاصة به. يستخدم المثال ثلاثة ملفات عينة (`alice29.txt`، `asyoulik.txt`، و `fields.c`) بكلمات مرور مختلفة.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### كيف يعمل
- **CreateEntry** يضيف ملفًا إلى الأرشيف.  
- الوسيط الرابع (`ArchiveEntrySettings`) يتيح لك تحديد كل من الضغط (`DeflateCompressionSettings`) والتشفير (`TraditionalEncryptionSettings` أو `AesEcryptionSettings`).  
- بتمرير سلسلة كلمة مرور مختلفة لكل إدخال، ستحصل على **أرشيف ZIP محمي بكلمة مرور** حيث يتم فتح كل ملف فقط باستخدام مفتاحه الخاص.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| الفشل في الاستخراج مع “كلمة مرور خاطئة” | عدم تطابق كلمة المرور أو طريقة تشفير خاطئة | تحقق من سلسلة كلمة المرور الدقيقة وتأكد من أنك استخدمت نفس `EncryptionMethod` عند الاستخراج. |
| حجم الأرشيف أكبر من المتوقع | استخدام AES‑256 على ملفات نصية صغيرة قد يضيف عبئًا | بالنسبة للملفات الصغيرة، قد يكون AES‑128 كافيًا ويؤدي إلى أرشيف أصغر. |
| استثناء وقت التشغيل على `archive.Save` | عدم وجود إذن كتابة على المجلد المستهدف | تأكد من أن التطبيق لديه صلاحية كتابة إلى `dataDir` أو استخدم مسار إخراج مختلف. |

## الأسئلة المتكررة (FAQs)

### هل يمكنني استخدام طرق تشفير مختلفة لكل ملف؟
نعم، يتيح لك Aspose.Zip لـ .NET خلط طرق التشفير—ZipCrypto التقليدي، AES‑128، و AES‑256—على أساس كل ملف.

### هل تتوفر نسخة تجريبية؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Zip لـ .NET [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
قم بزيارة [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على المساعدة من المجتمع ودعم Aspose.

### أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Zip لـ .NET؟
الوثائق متاحة [هنا](https://reference.aspose.com/zip/net/).

### هل يمكنني شراء ترخيص مؤقت لأغراض الاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose