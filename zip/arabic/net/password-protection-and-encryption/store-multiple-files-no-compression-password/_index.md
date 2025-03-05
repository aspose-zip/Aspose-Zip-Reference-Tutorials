---
title: Aspose.Zip for .NET - برنامج تعليمي لتخزين الملفات الآمنة
linktitle: تخزين ملفات متعددة بدون ضغط باستخدام كلمة المرور
second_title: Aspose.Zip .NET API لضغط الملفات وأرشفتها
description: اكتشف كيفية استخدام Aspose.Zip لـ .NET لتخزين ملفات متعددة بشكل آمن دون ضغط. خطوات سهلة لحماية كلمة المرور. إطلاق العنان لقوة إدارة الملفات!
type: docs
weight: 13
url: /ar/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

في عالم تطوير .NET، تعد إدارة الملفات ومعالجتها مهمة شائعة. Aspose.Zip for .NET هي مكتبة قوية توفر للمطورين القدرة على ضغط أرشيفات Zip وفك ضغطها ومعالجتها بسلاسة. في هذا البرنامج التعليمي، سوف نتعمق في سيناريو محدد: تخزين ملفات متعددة دون ضغط وحمايتها بكلمة مرور. بحلول نهاية هذا الدليل، ستكون مجهزًا بالمعرفة اللازمة لتنفيذ هذه الوظيفة باستخدام Aspose.Zip for .NET.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Zip لمكتبة .NET: تأكد من تثبيت Aspose.Zip لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/zip/net/).

-  دليل المستندات: قم بإعداد دليل حيث توجد ملفات المصدر الخاصة بك. في المثال المقدم، المتغير`dataDir` يمثل دليل المستندات الخاص بك.

## استيراد مساحات الأسماء

للبدء، دعونا نستورد مساحات الأسماء الضرورية للتعليمات البرمجية الخاصة بنا:

```csharp
// المسار إلى دليل الموارد.
string dataDir = "Your Document Directory"

// استيراد مساحات الأسماء Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## الخطوة 1: افتح الملف المضغوط

```csharp
//ExStart: تخزين ملفات متعددة بدون ضغط باستخدام كلمة المرور
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 تتضمن هذه الخطوة إنشاء ملف مضغوط جديد باستخدام`FileStream`. سيتم تسمية الملف "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## الخطوة 2: افتح الملف المصدر

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

هنا، نفتح الملف المصدر الأول، "alice29.txt"، والذي سيتم تخزينه في الأرشيف المضغوط.

## الخطوة 3: إنشاء أرشيف

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 في هذه الخطوة، نقوم بإنشاء مثيل لـ`Archive` فئة، وتحديد إعدادات الضغط والتشفير. نحن نستخدم ال`StoreCompressionSettings` لتخزين الملفات دون ضغط و`AesEcryptionSettings` لتطبيق تشفير AES بكلمة مرور ("p@s$").

## الخطوة 4: إنشاء إدخال الأرشيف وحفظه

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

تتضمن هذه الخطوة الأخيرة إنشاء إدخال في الأرشيف لـ "alice29.txt" وحفظ الأرشيف، وإكمال عملية تخزين الملف بدون ضغط ومع حماية بكلمة مرور.

اختتم البرنامج التعليمي الخاص بك عن طريق تلخيص النقاط الرئيسية وتشجيع القراء على استكشاف المزيد من الإمكانيات باستخدام Aspose.Zip for .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية استخدام Aspose.Zip لـ .NET لتخزين ملفات متعددة دون ضغط وتأمينها بكلمة مرور. بينما تواصل رحلتك مع تطوير .NET، استفد من إمكانيات Aspose.Zip لتبسيط مهام إدارة الملفات وتعزيز أمان تطبيقاتك.

---

### الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Zip لـ .NET مع طرق تشفير أخرى؟
 نعم، يدعم Aspose.Zip طرق التشفير المختلفة. تحقق من الوثائق[هنا](https://reference.aspose.com/zip/net/) للتفاصيل.

### أين يمكنني الحصول على الدعم لـ Aspose.Zip لـ .NET؟
 قم بزيارة[منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) لدعم المجتمع والمناقشات.

### هل تتوفر نسخة تجريبية مجانية من Aspose.Zip لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip لـ .NET؟
 طلب ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء Aspose.Zip لـ .NET؟
 يمكنك شراء Aspose.Zip لـ .NET[هنا](https://purchase.aspose.com/buy).
