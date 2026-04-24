---
date: 2026-04-24
description: تعلم كيفية ضغط tar وإنشاء أرشيف TarBz2 في .NET باستخدام Aspose.Zip. يوضح
  هذا الدليل خطوة بخطوة كيفية إضافة الملفات إلى tar وإنشاء ملفات tarbz2 بكفاءة.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: ضغط إلى TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط ملف tar وإنشاء TarBz2 باستخدام Aspose.Zip لـ .NET
url: /ar/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط tar وإنشاء TarBz2 باستخدام Aspose.Zip لـ .NET

## مقدمة

في هذا الدرس ستكتشف **كيفية ضغط tar** للأرشيفات وتحويلها إلى ملف **TarBz2** مضغوط باستخدام مكتبة **Aspose.Zip** لـ .NET. سواءً كنت تبني أداة نسخ احتياطي، أو تنشر حزم نشر، أو تحتاج ببساطة إلى حزمة خفيفة الوزن للتوزيع، فإن الخطوات أدناه ستوجهك عبر إضافة الملفات إلى tar، وتطبيق ضغط Bzip2، وإنتاج أرشيف جاهز للمشاركة.

قبل أن نبدأ، تأكد من أن لديك المتطلبات المسبقة المذكورة لاحقًا في هذا الدليل حتى تتمكن من المتابعة دون أي مشاكل.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Zip for .NET  
- **كم من الوقت تستغرق العملية؟** حوالي 5‑10 دقائق  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت للإنتاج؛ نسخة تجريبية مجانية متاحة  
- **هل يمكنني ضغط ملفات متعددة؟** نعم – أضف عددًا غير محدود من الإدخالات إلى أرشيف tar  
- **هل هو متوافق مع .NET 6+؟** بالتأكيد، Aspose.Zip يدعم .NET Framework و .NET Core/5/6  

## ما هو أرشيف TarBz2؟

ملف **TarBz2** يجمع بين حاوية **tar** التقليدية (التي تحافظ على هيكل الدليل وبيانات تعريف الملفات) وضغط **Bzip2**، مما ينتج حزمة `.tar.bz2` مضغوطة بشكل كبير. هذا التنسيق شائع على الأنظمة الشبيهة بـ Unix لأنه يوفر توازنًا جيدًا بين نسبة الضغط وسرعة فك الضغط.

## لماذا ضغط الملفات إلى TarBz2 باستخدام Aspose.Zip؟

- **السرعة والبساطة** – استدعاءات API ذات سطر واحد تتعامل مع إنشاء tar وضغط Bzip2.  
- **متعدد المنصات** – يعمل على بيئات .NET في Windows و Linux و macOS.  
- **تحكم دقيق** – اختر الملفات التي تريد تضمينها، عيّن أسماء إدخالات مخصصة، وابدأ البث مباشرة إلى القرص.  
- **دعم .NET قوي** – مثالي لسيناريوهات **tar archive .net**، من تطبيقات سطر الأوامر إلى خدمات الويب.  

## المتطلبات المسبقة

- **Aspose.Zip for .NET** – قم بتنزيل أحدث حزمة من الموقع الرسمي: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – مجلد يحتوي على الملفات التي تريد أرشفتها. في الأمثلة نشير إليه بالمتغير `dataDir`.

> **نصيحة احترافية:** احتفظ بملفات المصدر في مجلد مخصص لتجنب تضمين ملفات غير مرغوب فيها عن طريق الخطأ.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة حتى تتمكن من الوصول إلى فئات Tar و Bzip2 في Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## الخطوة 1: تعيين دليل المستندات

حدد المسار الذي يشير إلى المجلد الذي يحتوي على الملفات التي تريد أرشفتها.

```csharp
string dataDir = "Your Document Directory";
```

> استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي إلى مجلد المصدر الخاص بك.

## الخطوة 2: إضافة ملفات إلى tar وإنشاء أرشيف TarBz2

جوهر العملية هو إنشاء `TarArchive`، إضافة الإدخالات، ثم تغليفه بـ `Bzip2Archive`. يوضح الكود أدناه **كيفية إنشاء tar** وضغطه إلى **TarBz2** بأسلوب نمط النفايات النظيف.

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
- `bz2.SetSource(archive)` يحدد لأرشيف Bzip2 ضغط تدفق tar بالكامل.  
- `bz2.Save(...)` يكتب ملف **TarBz2** النهائي إلى القرص.

**نصيحة:** لإ **إضافة ملفات إلى tar** دفعة واحدة، ببساطة كرّر `archive.CreateEntry` لكل ملف قبل استدعاء `bz2.Save`.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **File not found** error | مسار `dataDir` خاطئ أو امتداد ملف مفقود | تحقق من المسار الكامل وتأكد من وجود الملف. |
| **Empty archive** | لا توجد إدخالات مضافة قبل `bz2.Save` | أضف على الأقل استدعاء واحد لـ `CreateEntry`. |
| **Permission denied** | التطبيق يفتقر إلى صلاحية الكتابة إلى مجلد الإخراج | شغّل التطبيق بصلاحيات مناسبة أو اختر مجلدًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Zip متوافق مع جميع تطبيقات .NET؟**  
ج: نعم. يعمل مع .NET Framework و .NET Core و .NET 5/6، والبيئات الأحدث.

**س: هل يمكنني ضغط ملفات متعددة في آن واحد؟**  
ج: بالتأكيد. استدعِ `CreateEntry` لكل ملف قبل حفظ الأرشيف.

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/zip/net/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Zip؟**  
ج: يمكنك طلب واحد [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، قم بتحميل نسخة تجريبية [هنا](https://releases.aspose.com/).

## الخاتمة

لقد تعلمت الآن **كيفية ضغط tar**، إضافة ملفات إليه، وتغليف النتيجة في تدفق Bzip2 لإنتاج أرشيف **TarBz2** باستخدام Aspose.Zip لـ .NET. هذا النهج سريع، موثوق، ويعمل عبر جميع منصات .NET الحديثة. لا تتردد في تجربة مجموعات ملفات أكبر، أو أسماء إدخالات مخصصة، أو دمج الكود في عمليات النسخ الاحتياطي أو نشر التطبيقات الخاصة بك.

إذا واجهت أي تحديات، فإن مجتمع Aspose.Zip جاهز للمساعدة—فقط انتقل إلى [منتدى دعم Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**آخر تحديث:** 2026-04-24  
**تم الاختبار مع:** Aspose.Zip for .NET (latest release)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}