---
date: 2026-10-31
description: تعلم كيفية إنشاء أرشيف tar وضغطه إلى ملف TarBz2 في .NET باستخدام Aspose.Zip.
  دليل خطوة بخطوة يوضح إنشاء tar، ضغط Bzip2، ونصائح أفضل الممارسات.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: الضغط إلى TarBz2
og_description: تعلم كيفية إنشاء أرشيف tar وضغطه إلى ملف TarBz2 باستخدام Aspose.Zip
  لـ .NET. دليل خطوة بخطوة يغطي إنشاء tar، ضغط Bzip2، ونصائح أفضل الممارسات.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: إنشاء أرشيف tar وضغطه إلى TarBz2 باستخدام .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: كيفية إنشاء أرشيف tar وضغطه إلى TarBz2 باستخدام .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء أرشيف tar وضغطه إلى TarBz2 باستخدام .NET

في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء ملفات أرشيف tar** ثم ضغطها إلى حزمة **TarBz2** مدمجة باستخدام مكتبة **Aspose.Zip** لـ .NET. سواءً كنت تبني أداة نسخ احتياطي، أو تُعد حزم نشر، أو تحتاج إلى تنسيق توزيع خفيف الوزن، فإن الخطوات أدناه ستُرشدك إلى إضافة الملفات إلى حاوية tar، وتطبيق ضغط Bzip2، وكتابة الملف النهائي `.tar.bz2`.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip for .NET  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 5‑10 دقائق  
- **هل أحتاج إلى ترخيص؟** يتطلب ترخيص مؤقت للإنتاج؛ يتوفر نسخة تجريبية مجانية  
- **هل يمكنني ضغط ملفات متعددة؟** نعم – أضف عددًا غير محدود من الإدخالات كما تشاء إلى أرشيف tar  
- **هل هو متوافق مع .NET 6+؟** بالتأكيد، Aspose.Zip يدعم .NET Framework و .NET Core/5/6  

## ما هو أرشيف TarBz2؟

ملف TarBz2 يجمع بين حاوية **tar** التقليدية (التي تحافظ على بنية الدليل وبيانات تعريف الملفات) وضغط **Bzip2**، مما ينتج حزمة `.tar.bz2` مضغوطة بشكل كبير. هذا التنسيق شائع على الأنظمة الشبيهة بـ Unix لأنه يوفر توازنًا جيدًا بين نسبة الضغط وسرعة فك الضغط.

## لماذا ضغط الملفات إلى TarBz2 باستخدام Aspose.Zip؟

يمكن لـ Aspose.Zip إنشاء أرشيف TarBz2 في **استدعائين للـ API** مع معالجة التدفقات بكفاءة. يدعم **أكثر من 50 تنسيق أرشيف وضغط**، يعالج ملفات تصل إلى **2 GB** دون تحميل الأرشيف بالكامل في الذاكرة، ويعمل على بيئات .NET على Windows و Linux و macOS. كما يمنحك المكتبة تحكمًا دقيقًا في أسماء الإدخالات، والطوابع الزمنية، ومستويات الضغط، مما يجعلها مثالية لكل من أدوات سطر الأوامر والخدمات الويب.

## المتطلبات المسبقة

- **Aspose.Zip for .NET** – قم بتنزيل أحدث حزمة من الموقع الرسمي: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة نشير إليه بالمتغير `dataDir`.

> **نصيحة احترافية:** احتفظ بملفات المصدر في مجلد مخصص لتجنب تضمين ملفات غير مرغوب فيها عن طريق الخطأ.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء المطلوبة حتى تتمكن من الوصول إلى فئات Tar و Bzip2 في Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## الخطوة 1: تعيين دليل المستند

حدد المسار الذي يشير إلى المجلد الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

> استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي إلى مجلد المصدر الخاص بك.

## الخطوة 2: إضافة ملفات إلى tar وإنشاء أرشيف TarBz2

تمثل الفئة `TarArchive` حاوية tar في الذاكرة، بينما تقوم `Bzip2Archive` بضغط التدفقات باستخدام خوارزمية Bzip2.  
طريقة `CreateEntry` تضيف إدخال ملف جديد إلى أرشيف tar.

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

- `CreateEntry` **يضيف ملفات إلى tar** – يمكنك استدعاء هذه الطريقة لكل ملف تحتاجه في الأرشيف.  
- `bz2.SetSource(archive)` يُخبر أرشيف Bzip2 بضغط تدفق tar بالكامل.  
- `bz2.Save(...)` يكتب ملف **TarBz2** النهائي إلى القرص.

**نصيحة:** لإضافة ملفات إلى tar **بشكل جماعي**، ببساطة كرّر `archive.CreateEntry` لكل ملف قبل استدعاء `bz2.Save`.

## كيف تضيف ملفات إلى tar؟

حمّل دليل المصدر، أنشئ مثيلًا من `TarArchive`، أضف كل ملف باستخدام `CreateEntry`، ثم غلف تدفق tar في `Bzip2Archive` واستدعِ `Save`. يضيف هذا النمط ذو الخطوتين أي عدد من الملفات وينتج ملف `.tar.bz2` في تدفق واحد سلس، مما يلغي الحاجة إلى ملفات مؤقتة أو أدوات خارجية.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **خطأ الملف غير موجود** | مسار `dataDir` غير صحيح أو امتداد الملف مفقود | تحقق من المسار الكامل وتأكد من وجود الملف. |
| **أرشيف فارغ** | لم تُضاف أي إدخالات قبل `bz2.Save` | أضف على الأقل استدعاء واحد لـ `CreateEntry`. |
| **تم رفض الإذن** | التطبيق يفتقر إلى صلاحية الكتابة إلى مجلد الإخراج | شغّل التطبيق بصلاحيات مناسبة أو اختر مجلدًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع تطبيقات .NET؟**  
ج: نعم. يعمل مع .NET Framework و .NET Core و .NET 5/6 وأحدث بيئات التشغيل.

**س: هل يمكنني ضغط ملفات متعددة في آن واحد؟**  
ج: بالتأكيد. استدعِ `CreateEntry` لكل ملف قبل حفظ الأرشيف.

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: الوثائق التفصيلية متاحة في **مرجع Aspose.Zip .NET API**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك **طلب ترخيص مؤقت** هنا: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، **قم بتنزيل نسخة تجريبية من إصدارات Aspose**: [download a trial version](https://releases.aspose.com/).

يمكنك أيضًا [تنزيل نسخة تجريبية](https://releases.aspose.com/).

## الخلاصة

أنت الآن تعرف **كيفية إنشاء أرشيف tar**، وضغط تدفق tar باستخدام Bzip2، وإنشاء أرشيف **TarBz2** باستخدام Aspose.Zip لـ .NET. النهج سريع، فعال في الذاكرة، ويعمل عبر جميع منصات .NET الحديثة. لا تتردد في تجربة مجموعات ملفات أكبر، أو أسماء إدخالات مخصصة، أو دمج الشيفرة في خطوط النسخ الاحتياطي أو النشر الخاصة بك.

إذا واجهت أي تحديات، فإن مجتمع Aspose.Zip جاهز للمساعدة—فقط توجه إلى **منتدى دعم Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**آخر تحديث:** 2026-10-31  
**تم الاختبار مع:** Aspose.Zip for .NET (latest release)  
**المؤلف:** Aspose  

## دروس ذات صلة

- [إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [إضافة ملفات إلى tar وضغطها إلى TarZ باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}