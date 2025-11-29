---
date: 2025-11-29
description: تعلم كيفية إضافة الملفات إلى تنسيق tar وضغط الملفات إلى تنسيق tarbz2
  في .NET باستخدام Aspose.Zip. يوضح هذا الدليل خطوة بخطوة كيفية إنشاء أرشيفات tarbz2
  بكفاءة.
language: ar
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة ملفات إلى tar وضغطها إلى TarBz2 باستخدام Aspose.Zip لـ .NET
url: /net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ملفات إلى tar وضغطها إلى TarBz2 باستخدام Aspose.Zip لـ .NET

## المقدمة

مرحبًا بك في دليلنا الشامل حول **كيفية إضافة ملفات إلى tar** وضغطها إلى صيغة TarBz2 باستخدام Aspose.Zip لـ .NET. سواءً كنت تبني أداة نسخ احتياطي، أو تُسلم حزم نشر، أو تحتاج فقط إلى أرشيف مضغوط للتوزيع، فإن هذا البرنامج التعليمي يمرّ بك عبر كل خطوة مع شروحات واضحة ونصائح عملية.

قبل أن نبدأ، دعنا نتأكد من أن لديك كل ما تحتاجه.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip لـ .NET
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 5‑10 دقائق
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت مطلوب للإنتاج؛ نسخة تجريبية مجانية متاحة
- **هل يمكنني ضغط ملفات متعددة؟** نعم – أضف عددًا لا نهائيًا من الإدخالات إلى أرشيف Tar
- **هل هو متوافق مع .NET 6+؟** بالتأكيد، Aspose.Zip يدعم .NET Framework و .NET Core/5/6

## ما هو “إضافة ملفات إلى tar”؟
إن إضافة ملفات إلى **tar** (Tape Archive) تُنشئ حاوية غير مضغوطة واحدة تحافظ على هيكل المجلدات وبيانات التعريف الخاصة بالملفات. عندما تقوم بعد ذلك بتطبيق ضغط Bzip2، يصبح الناتج **tar.bz2** (TarBz2) – وهو مثالي للتخزين الفعال والنقل.

## لماذا ضغط الملفات إلى TarBz2 باستخدام Aspose.Zip؟
- **السرعة والبساطة** – استدعاءات API سطرية واحدة تتعامل مع إنشاء tar وضغط Bzip2.
- **متعدد المنصات** – يعمل على بيئات .NET في Windows و Linux و macOS.
- **تحكم دقيق** – اختر الملفات التي تريد تضمينها، عيّن أسماء إدخالات مخصصة، وابدأ البث مباشرة إلى القرص.

## المتطلبات المسبقة

- **Aspose.Zip لـ .NET** – حمّل أحدث حزمة من الموقع الرسمي: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **دليل المستندات** – مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة نُشير إليه بالمتغيّر `dataDir`.

> **نصيحة محترف:** احفظ ملفات المصدر في مجلد مخصص لتجنب تضمين ملفات غير مرغوب فيها عن طريق الخطأ.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة حتى تتمكن من الوصول إلى فئات Tar و Bzip2 في Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## الخطوة 1: تعيين دليل المستندات

عرّف المسار الذي يشير إلى المجلد الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

> استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي إلى مجلد المصدر الخاص بك.

## الخطوة 2: إضافة ملفات إلى tar وإنشاء أرشيف TarBz2

جوهر العملية هو إنشاء `TarArchive`، إضافة الإدخالات، ثم تغليفه بـ `Bzip2Archive`. يوضح الكود أدناه **كيفية إنشاء tarbz2** بأسلوب نمط القابل للتصرف (disposable‑pattern) النظيف.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` يضيف كل ملف إلى حاوية **tar**.  
- `bz2.SetSource(archive)` يُخبر أرشيف Bzip2 بضغط تدفق tar بالكامل.  
- `bz2.Save(...)` يكتب ملف **tar.bz2** النهائي إلى القرص.

**نصيحة:** لضغط ملفات إلى tarbz2 دفعة واحدة، ما عليك سوى تكرار `archive.CreateEntry` لكل ملف تحتاجه.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|---------|--------|------|
| **خطأ “الملف غير موجود”** | مسار `dataDir` غير صحيح أو امتداد الملف مفقود | تحقق من المسار الكامل وتأكد من وجود الملف. |
| **أرشيف فارغ** | لم تُضف أي إدخالات قبل `bz2.Save` | أضف على الأقل استدعاء واحد لـ `CreateEntry`. |
| **رفض الإذن** | التطبيق لا يملك صلاحية كتابة إلى مجلد الإخراج | شغّل التطبيق بصلاحيات مناسبة أو اختر مجلدًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع تطبيقات .NET؟**  
ج: نعم. يعمل مع .NET Framework و .NET Core و .NET 5/6 والإصدارات الأحدث.

**س: هل يمكنني ضغط ملفات متعددة في آنٍ واحد؟**  
ج: بالتأكيد. استدعِ `CreateEntry` لكل ملف قبل حفظ الأرشيف.

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/zip/net/).

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب واحد [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم، حمّل نسخة تجريبية [هنا](https://releases.aspose.com/).

## الخاتمة

لقد تعلمت الآن **كيفية إضافة ملفات إلى tar**، تغليفها في تدفق Bzip2، وإنتاج أرشيف **TarBz2** باستخدام Aspose.Zip لـ .NET. هذه التقنية سريعة، موثوقة، وتعمل عبر جميع منصات .NET الحديثة. لا تتردد في تجربة مجموعات ملفات أكبر، أو أسماء إدخالات مخصصة، أو دمج الكود في خطوط أنابيب النسخ الاحتياطي أو النشر الخاصة بك.

إذا واجهت أي تحديات، فإن مجتمع Aspose.Zip جاهز للمساعدة—فقط توجه إلى [منتدى دعم Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**آخر تحديث:** 2025-11-29  
**تم الاختبار مع:** Aspose.Zip لـ .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}