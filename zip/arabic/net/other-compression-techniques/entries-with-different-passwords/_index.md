---
date: 2026-02-28
description: تعلم كيفية ضغط الملفات باستخدام كلمة مرور وتشفير أرشيفات ZIP باستخدام
  Aspose.Zip لـ .NET، مع تغطية حماية كلمة مرور 7z وكلمة مرور ZIP لكل ملف في C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط الملفات باستخدام كلمة مرور وتشفير ملفات ZIP بكلمات مرور مختلفة باستخدام
  Aspose.Zip لـ .NET
url: /ar/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط الملفات باستخدام كلمة مرور وتشفير إدخالات ZIP بكلمات مرور مختلفة باستخدام Aspose.Zip لـ .NET

## مقدمة

إذا كنت بحاجة إلى **ضغط الملفات باستخدام كلمة مرور** ومنح كل إدخال كلمة مرور خاصة به، فأنت في المكان الصحيح. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة لإنشاء أرشيف 7‑zip حيث يتم حماية كل ملف بكلمة مرور فريدة، باستخدام مكتبة Aspose.Zip لـ .NET. في النهاية ستفهم لماذا تشفير كل إدخال مهم، وكيفية إعداده، وكيفية التحقق من النتيجة في مشاريعك الخاصة.

## إجابات سريعة
- **ماذا يعني “تشفير zip”؟** يعني تطبيق حماية تعتمد على كلمة مرور (AES أو ZipCrypto) على محتويات أرشيف ZIP/7z.  
- **هل يمكن لكل إدخال أن يكون له كلمة مرور مختلفة؟** نعم—تتيح لك Aspose.Zip تعيين كلمات مرور مميزة لكل ملف.  
- **ما إصدارات .NET المدعومة؟** جميع إصدارات .NET Framework الحديثة، .NET Core، وإصدارات .NET 5/6.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج؛ تتوفر نسخة تجريبية مجانية.  
- **ما صيغة الضغط المستخدمة في المثال؟** العينة تنشئ أرشيف 7z مع تشفير AES‑256.

## كيفية ضغط الملفات باستخدام كلمة مرور باستخدام Aspose.Zip لـ .NET
في هذا القسم نجيب على السؤال الأساسي مباشرة ونهيئ الساحة للدليل خطوة بخطوة التالي.

## ما هو “كيفية تشفير zip” باستخدام Aspose.Zip؟
تشفير ملف ZIP (أو 7z) يعني تأمين إدخالاته بحيث لا يمكن فتحها دون كلمة المرور الصحيحة. تدعم Aspose.Zip لـ .NET كلًا من ZipCrypto الكلاسيكي وتشفير AES الأقوى، وتتيح لك تحديد إعدادات التشفير لكل إدخال، مما يمنحك تحكمًا دقيقًا في الأمان.

## لماذا نستخدم كلمات مرور مختلفة لكل إدخال؟
- **تقسيم الأمان:** إذا تم اختراق كلمة مرور واحدة، تظل الملفات الأخرى محمية.  
- **الامتثال التنظيمي:** تتطلب بعض الصناعات بيانات اعتماد منفصلة لفئات البيانات المختلفة.  
- **وصول مخصص للمستخدم:** يمكنك توزيع أرشيف واحد على عدة مستخدمين، كل منهم يفتح فقط الملفات التي يملك صلاحية الوصول إليها.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

- **Aspose.Zip لـ .NET** مثبت – راجع الوثائق الرسمية [documentation](https://reference.aspose.com/zip/net/) للحصول على تعليمات التحميل والتثبيت.  
- مجلد على جهازك حيث ستحفظ الملفات المصدرية ("Document Directory").  
- إلمام أساسي بـ C# و Visual Studio (أو بيئة التطوير .NET المفضلة لديك).

## استيراد مساحات الأسماء

نبدأ باستدعاء مساحات الأسماء التي تحتوي على الفئات التي سنحتاجها.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: تعيين دليل المستندات الخاص بك

حدد المسار الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء إدخالات بكلمات مرور مختلفة

هذا هو جوهر البرنامج التعليمي. نفتح ملف 7z جديد، ننشئ ثلاثة كائنات `FileInfo`، ونضيف كل منها كإدخال مع كلمة مرور AES الخاصة به.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### كيف يعمل هذا

- `SevenZipArchive` هو الحاوية لأرشيف 7‑z.  
- `CreateEntry` يأخذ اسم الإدخال، الملف المصدر، علامة للكتابة فوق، وكائن `SevenZipEntrySettings`.  
- داخل `SevenZipEntrySettings` نوفر كائنين للإعدادات: أحدهما للضغط (`SevenZipStoreCompressionSettings`) والآخر للتشفير (`SevenZipAESEncryptionSettings`).  
- كل استدعاء يزود **كلمة مرور مختلفة** (`"test1"`, `"test2"`, `"test3"`)، محققًا حماية لكل إدخال.

## الخطوة 3: التحقق

بعد حفظ الأرشيف، يمكنك طباعة رسالة تأكيد بسيطة.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

شغّل البرنامج، ثم حاول فتح `archive.7z` بأداة مثل 7‑Zip. سيطلب منك كلمة مرور لكل إدخال، مؤكدًا أن كلمات المرور مختلفة بالفعل.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **خطأ كلمة المرور غير صحيحة** | سلسلة كلمة المرور تحتوي على مسافات زائدة أو أحرف غير مرئية. | قم بقطع مسافات سلاسل كلمة المرور (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **الأرشيف لا يفتح في الأدوات القديمة** | بعض أدوات ZIP القديمة لا تدعم تشفير AES‑256 المستخدم في 7z. | استخدم أداة استخراج حديثة (7‑Zip 19.00+). |
| **الملف لم يُضاف إلى الأرشيف** | مسار الملف المصدر غير صحيح أو الملف غير موجود. | تحقق من `dataDir` وأسماء الملفات، أو استخدم `Path.Combine(dataDir, "data1.bin")`. |

## الأسئلة المتكررة

### س1: هل Aspose.Zip لـ .NET متوافق مع جميع إصدارات .NET؟

A1: نعم، تم تصميم Aspose.Zip لـ .NET ليتكامل بسلاسة مع جميع إصدارات إطار عمل .NET.

### س2: هل يمكنني استخدام Aspose.Zip لـ .NET في مشاريعي التجارية؟

A2: بالتأكيد! تقدم Aspose.Zip لـ .NET تراخيص تجارية، ويمكنك العثور على مزيد من المعلومات حول كيفية الشراء [here](https://purchase.aspose.com/buy).

### س3: هل هناك نسخة تجريبية مجانية متاحة؟

A3: نعم، يمكنك استكشاف ميزات Aspose.Zip لـ .NET من خلال نسخة تجريبية مجانية. ابدأ [here](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على دعم Aspose.Zip لـ .NET؟

A4: لأي استفسارات أو مساعدة، زر [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### س5: هل يمكنني استخدام Aspose.Zip لـ .NET بدون ترخيص دائم؟

A5: نعم، يمكنك الحصول على ترخيص مؤقت لاحتياجاتك القصيرة الأمد. تجد المزيد من التفاصيل [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة

لقد تعلمت الآن **كيفية ضغط الملفات باستخدام كلمة مرور** وتشفير أرشيفات ZIP بكلمات مرور لكل إدخال باستخدام Aspose.Zip لـ .NET. تمنحك هذه التقنية المرونة لحماية كل ملف على حدة، مما يلبي متطلبات أمان أكثر صرامة ويسهل توزيع الملفات حسب المستخدم. لا تتردد في تجربة إعدادات ضغط أخرى، مجموعات ملفات أكبر، أو دمج هذه المنطق في خدمة ويب تُنشئ أرشيفات آمنة في الوقت الفعلي.

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}