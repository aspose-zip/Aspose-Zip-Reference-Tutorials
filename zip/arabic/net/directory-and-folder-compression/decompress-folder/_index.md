---
date: 2025-12-01
description: تعلم كيفية ضغط دليل إلى ملف zip واستخراج ملف zip إلى دليل باستخدام Aspose.Zip
  لـ .NET – دليل كامل لضغط zip في .NET وإنشاء أرشيف zip في .NET.
language: ar
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: ضغط المجلد إلى ملف Zip وفك الضغط – Aspose.Zip لـ .NET
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضغط دليل إلى Zip وفك الضغط – Aspose.Zip لـ .NET

إذا كنت بحاجة إلى **compress directory to zip** ثم استخراج ذلك الأرشيف في تطبيق .NET، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض سير العمل بالكامل—بدءًا بإنشاء أرشيف zip، ثم نعرض لك عملية فك الضغط خطوة بخطوة باستخدام Aspose.Zip لـ .NET. في النهاية ستحصل على نمط قابل لإعادة الاستخدام لضغط zip في مشاريع .NET وفهم قوي لكيفية فك الضغط بأسلوب .NET.

## إجابات سريعة
- **What does “compress directory to zip” mean?** يعني تحويل محتويات مجلد إلى ملف .zip واحد.  
- **How do I extract zip to directory?** استخدم الطريقة `Archive.ExtractToDirectory` كما هو موضح في الدليل.  
- **Which .NET versions are supported?** جميع إصدارات .NET Framework الحديثة، .NET Core، وإصدارات .NET 5/6+.  
- **Is a license required for production?** نعم، يلزم الحصول على ترخيص تجاري لـ Aspose.Zip للاستخدام غير التجريبي.  
- **Can I automate this in CI/CD pipelines?** بالتأكيد—فقط أضف نفس الشيفرة إلى سكريبتات البناء الخاصة بك.

## ما هو “compress directory to zip”؟
ضغط دليل إلى zip يجمع كل ملف ومجلد فرعي في أرشيف مضغوط واحد. هذا يقلل من حجم التخزين، يبسط عملية النقل، وهو طريقة قياسية لتجميع الموارد للنشر.

## لماذا تستخدم Aspose.Zip لـ .NET؟
Aspose.Zip يقدم واجهة برمجة تطبيقات **pure‑managed** تعمل دون تبعيات أصلية، يدعم الملفات الكبيرة، ويوفر قدرات ضغط zip عالية الأداء لـ .NET. كما يتعامل مع الحالات الخاصة مثل الأرشيفات المحمية بكلمة مرور وأسماء الملفات Unicode مباشرةً.

## المتطلبات المسبقة
- مكتبة **Aspose.Zip for .NET** مثبتة (حمّلها [هنا](https://releases.aspose.com/zip/net/)).  
- مجلد على القرص تريد أرشفته – حدّد مساره في المتغيّر `dataDir`.  
- بيئة تطوير .NET (Visual Studio، VS Code، أو أي IDE تفضله).

## استيراد مساحات الأسماء
First, bring the required namespaces into scope:

```csharp
using Aspose.Zip;
using System.IO;
```

## الخطوة 1: ضغط دليل إلى Zip
سنقوم بإنشاء ملف zip من الدليل الذي تخطط لفك ضغطه لاحقًا. المساعد `CompressDirectory.Run()` يقوم بالعمل الشاق.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** عينة `CompressDirectory` تُعبئ كل ملف في `dataDir` إلى `CompressDirectory_out.zip`. لا تتردد في إعادة تسمية ملف الإخراج ليتوافق مع تسمياتك.

## الخطوة 2: فك ضغط المجلد (كيفية فك ضغط .NET)

### الخطوة 2.1: فتح ملف Zip
افتح الأرشيف المُنشأ باستخدام `FileStream`. هذا يُجهّز الملف للقراءة.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### الخطوة 2.2: إنشاء كائن Archive
أنشئ كائن `Archive`، الذي يمثل حاوية zip.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### الخطوة 2.3: استخراج إلى دليل
أخيرًا، استخرج المحتويات إلى مجلد جديد. هذه هي خطوة **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

تهانينا! لقد نجحت في **compressed a directory to zip** ثم **extracted the zip to a directory** باستخدام Aspose.Zip لـ .NET. يضمن هذا النهج سلامة البيانات مع الحفاظ على شفرة مختصرة وسهلة القراءة.

## المشكلات الشائعة والحلول
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` عند الاستخراج | المجلد الهدف للقراءة فقط أو قيد الاستخدام | تأكد من أن مسار الوجهة قابل للكتابة وغير مقفل |
| مجلد الإخراج فارغ بعد الاستخراج | مسار zip المصدر غير صحيح | تحقق مرة أخرى من أن `dataDir + "CompressDirectory_out.zip"` يشير إلى الملف الصحيح |
| الملفات الكبيرة تسبب OutOfMemoryException | استخدام حجم المخزن المؤقت الافتراضي على أرشيفات ضخمة جدًا | استخدم `ArchiveOptions` لزيادة حجم المخزن المؤقت أو قم ببث الملفات على دفعات |

## الأسئلة المتكررة

**Q: هل يمكنني استخدام Aspose.Zip لـ .NET مع أي نوع من الملفات؟**  
A: نعم، Aspose.Zip يدعم جميع أنواع الملفات—النصية، الثنائية، الصور، PDFs، وما إلى ذلك.

**Q: هل Aspose.Zip مناسب للتطبيقات على نطاق واسع؟**  
A: بالتأكيد. تم تصميمه لسيناريوهات ضغط zip عالية الأداء لـ .NET، ويتعامل مع أرشيفات متعددة الجيجابايت بذاكرة منخفضة.

**Q: أين يمكنني العثور على وثائق شاملة لـ Aspose.Zip لـ .NET؟**  
A: استكشف الوثائق التفصيلية [هنا](https://reference.aspose.com/zip/net/).

**Q: هل يمكنني تجربة Aspose.Zip قبل الشراء؟**  
A: نعم، تتوفر نسخة تجريبية مجانية في صفحة تحميل [Aspose.Zip](https://releases.aspose.com/).

**Q: كيف يمكنني الحصول على دعم لـ Aspose.Zip لـ .NET؟**  
A: زر [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37) للحصول على مساعدة المجتمع والدعم الرسمي.

---

**آخر تحديث:** 2025-12-01  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}