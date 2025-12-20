---
date: 2025-12-20
description: تعلم كيفية إنشاء أرشيفات zip محمية بكلمة مرور في .NET باستخدام Aspose.Zip.
  يوضح هذا الدليل خطوة بخطوة كيفية ضغط الملفات باستخدام كلمات مرور، تعيين كلمة مرور
  لمدخل zip، واستخدام تشفير AES.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إنشاء ملفات ZIP محمية بكلمة مرور في .NET باستخدام Aspose.Zip
url: /ar/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ملفات ZIP محمية بكلمة مرور في .NET باستخدام Aspose.Zip

## المقدمة

إذا كنت بحاجة إلى **إنشاء أرشيف zip محمي بكلمة مرور** في تطبيق .NET، فإن Aspose.Zip يجعل العملية مباشرة. من خلال تعيين كلمة مرور فريدة لكل إدخال، يمكنك الحفاظ على سلامة المستندات الحساسة مع الاستمتاع بمرونة ضغط ZIP. في هذا البرنامج التعليمي ستتعلم كيفية ضغط الملفات بكلمات مرور فردية، اختيار طرق تشفير مختلفة، وتعيين كلمة مرور لإدخال zip — كل ذلك باستخدام شفرة واضحة جاهزة للإنتاج.

## إجابات سريعة
- **ما المكتبة التي يجب استخدامها؟** Aspose.Zip لـ .NET.  
- **هل يمكنني تعيين كلمة مرور مختلفة لكل ملف؟** نعم، كل إدخال يمكن أن يكون له كلمة مرور خاصة به.  
- **ما خوارزميات التشفير المدعومة؟** ZipCrypto التقليدي، AES‑128، و AES‑256.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل هذا متوافق مع .NET 6+؟** بالتأكيد – الـ API يستهدف .NET Standard 2.0 وما بعده.

## ما هو “إنشاء zip محمي بكلمة مرور”؟
إنشاء zip محمي بكلمة مرور يعني إضافة تشفير إلى إدخال أو أكثر داخل أرشيف ZIP بحيث لا يمكن فتح المحتوى دون كلمة المرور الصحيحة. هذا مثالي لنقل ملفات سرية، تخزين نسخ احتياطية، أو الالتزام بسياسات حماية البيانات.

## لماذا نستخدم Aspose.Zip للأرشيفات المحمية بكلمة مرور؟
- **تحكم دقيق** – تعيين كلمة مرور مميزة لكل ملف.  
- **خيارات تشفير متعددة** – من ZipCrypto القديم إلى AES‑128/256 القوي.  
- **بدون تبعيات خارجية** – مكتبة .NET صافية، سهلة التكامل.  
- **توثيق شامل** – يتضمن **دروس Aspose Zip** لسيناريوهات أعمق.

## المتطلبات المسبقة

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:

- Aspose.Zip لـ .NET: تأكد من تثبيت مكتبة Aspose.Zip في مشروع .NET الخاص بك. يمكنك العثور على الوثائق اللازمة [هنا](https://reference.aspose.com/zip/net/).

- التحميل: إذا لم تقم بذلك بعد، حمّل مكتبة Aspose.Zip لـ .NET من [هذا الرابط](https://releases.aspose.com/zip/net/).

- دليل المستندات: جهّز دليلًا يحتوي على الملفات التي تريد ضغطها.

## استيراد المساحات الاسمية

في مشروع .NET الخاص بك، تأكد من استيراد المساحات الاسمية اللازمة:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## الخطوة 1: تعيين مسار دليل الموارد

عرّف المسار إلى دليل الموارد حيث توجد ملفات المصدر الخاصة بك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: ضغط الملفات بكلمات مرور فردية

الآن، لنضغط الملفات بكلمات مرور فردية. سنستخدم ثلاثة ملفات تجريبية (`alice29.txt`، `asyoulik.txt`، و `fields.c`) مع كلمات مرور مميزة لكل منها. يوضح هذا كيفية **ضغط الملفات بكلمات مرور** وكذلك كيفية **تعيين كلمة مرور لإدخال zip** باستخدام أنظمة تشفير مختلفة، بما في ذلك **أرشيف zip مع aes**.

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

### كيف يعمل ذلك
- **TraditionalEncryptionSettings** يستخدم خوارزمية ZipCrypto القديمة (متوافقة مع معظم أدوات ZIP).  
- **AesEcryptionSettings** يتيح لك اختيار AES‑128 أو AES‑256 لأمان أقوى.  
- كل استدعاء `CreateEntry` يتلقى كائن `ArchiveEntrySettings` حيث نحدد طريقة الضغط وإعدادات التشفير، مما يؤدي إلى **حماية كلمة مرور لأرشيف zip**.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| “كلمة مرور غير صالحة” عند فتح الـ ZIP | عدم تطابق كلمة المرور المستخدمة في الشفرة مع ما يُدخل في أداة الاستخراج | تحقق من السلسلة الدقيقة التي تم تمريرها إلى `TraditionalEncryptionSettings` أو `AesEcryptionSettings`. |
| أدوات استخراج قديمة لا تستطيع فتح الإدخالات المشفرة بـ AES | ليست كل أدوات ZIP تدعم تشفير AES | استخدم طريقة ZipCrypto التقليدية لأقصى توافق، أو نصح المستخدمين باستخدام أداة حديثة (مثل 7‑Zip). |
| الملفات الكبيرة تتسبب في `OutOfMemoryException` | تحميل ملفات ضخمة إلى الذاكرة قبل الضغط | قم ببث الملف مباشرة باستخدام `FileStream` دون تحميل الملف بالكامل إلى كائن `FileInfo`. |

## الأسئلة المتكررة (FAQs)

### هل يمكنني استخدام طرق تشفير مختلفة لكل ملف؟
نعم، Aspose.Zip لـ .NET يسمح لك باستخدام طرق تشفير مختلفة لكل ملف أثناء الضغط.

### هل هناك نسخة تجريبية متاحة؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Zip لـ .NET [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
زر منتدى [Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على مساعدة من المجتمع ودعم Aspose.

### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Zip لـ .NET؟
الوثائق متاحة [هنا](https://reference.aspose.com/zip/net/).

### هل يمكنني شراء ترخيص مؤقت لأغراض الاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

## أسئلة سريعة إضافية

**س: هل تدعم المكتبة .NET Core و .NET 5/6؟**  
ج: نعم، Aspose.Zip يستهدف .NET Standard، مما يجعله متوافقًا مع .NET Framework، .NET Core، و .NET 5/6.

**س: هل يمكنني إضافة تعليق إلى كل إدخال ZIP؟**  
ج: بينما يركز Aspose.Zip على الضغط والتشفير، يمكنك تخزين بيانات تعريفية في ملف بيان منفصل داخل الأرشيف.

**س: هل يمكن تشفير الأرشيف بالكامل بكلمة مرور واحدة؟**  
ج: يمكنك تعيين كلمة مرور على كل إدخال بشكل فردي (كما هو موضح) أو تطبيق نفس كلمة المرور على جميع الإدخالات لنهج أبسط “أرشيف zip مع aes”.

## الخلاصة

لقد أصبحت الآن قادرًا على **إنشاء ملفات zip محمية بكلمة مرور** في .NET باستخدام Aspose.Zip. من خلال تعيين كلمات مرور فردية واختيار طريقة التشفير المناسبة، يمكنك الحفاظ على أمان بياناتك دون التضحية بمرونة ضغط ZIP. استكشف ميزات Aspose.Zip الأخرى مثل بث الملفات الكبيرة، إضافة بيانات تعريفية مخصصة، والتكامل مع التخزين السحابي لمزيد من السيناريوهات القوية.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Zip لـ .NET 23.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}