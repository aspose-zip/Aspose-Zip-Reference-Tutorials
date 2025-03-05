---
title: تأمين ضغط الملفات في .NET باستخدام Aspose.Zip
linktitle: ضغط الملفات بكلمات مرور فردية
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: تعرف على كيفية تحسين أمان الملفات في تطبيقات .NET! اتبع دليلنا خطوة بخطوة حول ضغط الملفات بكلمات مرور فردية باستخدام Aspose.Zip لـ .NET.
type: docs
weight: 16
url: /ar/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## مقدمة

في عالم تطوير .NET، تعد إدارة الملفات وضغطها بكفاءة مهمة بالغة الأهمية. يوفر Aspose.Zip for .NET حلاً قويًا لضغط الملفات، ويقدم ميزات متنوعة لتحسين تطبيقاتك. إحدى الميزات البارزة هي القدرة على ضغط الملفات بكلمات مرور فردية، مما يوفر طبقة إضافية من الأمان. في هذا البرنامج التعليمي، سنرشدك خلال عملية ضغط الملفات بكلمات مرور فردية باستخدام Aspose.Zip for .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

-  Aspose.Zip لـ .NET: تأكد من تثبيت مكتبة Aspose.Zip في مشروع .NET الخاص بك. يمكنك العثور على الوثائق اللازمة[هنا](https://reference.aspose.com/zip/net/).

-  التنزيل: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Aspose.Zip for .NET Library من[هذا الرابط](https://releases.aspose.com/zip/net/).

- دليل المستندات: قم بإعداد دليل يحتوي على الملفات التي تريد ضغطها.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## الخطوة 1: قم بتعيين مسار دليل الموارد

حدد المسار إلى دليل الموارد حيث توجد ملفاتك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: ضغط الملفات بكلمات مرور فردية

الآن، دعونا ضغط الملفات بكلمات مرور فردية. سنستخدم ثلاثة ملفات نموذجية (`alice29.txt`, `asyoulik.txt` ، و`fields.c`) مع كلمات مرور مميزة لكل منها.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // ضغط كل ملف بكلمة مرور فردية
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // احفظ الملفات المضغوطة
        archive.Save(zipFile);
    }
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية ضغط الملفات بكلمات مرور فردية باستخدام Aspose.Zip لـ .NET. تضيف هذه الميزة طبقة إضافية من الأمان إلى ملفاتك المضغوطة، مما يضمن السرية.

## الأسئلة المتداولة (الأسئلة الشائعة)

### هل يمكنني استخدام طرق تشفير مختلفة لكل ملف؟
نعم، يتيح لك Aspose.Zip for .NET استخدام طرق تشفير مختلفة لكل ملف أثناء الضغط.

### هل هناك نسخة تجريبية متاحة؟
 نعم، يمكنك الوصول إلى الإصدار التجريبي المجاني من Aspose.Zip لـ .NET[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 قم بزيارة[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على المساعدة من المجتمع ودعم Aspose.

### أين يمكنني العثور على وثائق مفصلة عن Aspose.Zip for .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/zip/net/).

### هل يمكنني شراء ترخيص مؤقت لأغراض الاختبار؟
 نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
