---
date: 2026-02-12
description: تعلم كيفية إضافة كلمة مرور للملف المضغوط وإنشاء أرشيفات zip بنظام LZMA
  باستخدام Aspose.Zip لـ .NET. يغطي هذا الدرس لتقنيات ضغط zip تنسيقات Bzip2 وLZMA
  (بما في ذلك حجم القاموس) وPPMd وEnhanced Deflate وStore compression، وضغط ملفات
  ASP.NET للملفات الكبيرة.
linktitle: Optimizing Compression Settings
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة كلمة مرور لملف ZIP بتقنية LZMA باستخدام Aspose.Zip لـ .NET
url: /ar/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة كلمة مرور zip إلى ملف zip بصيغة LZMA باستخدام Aspose.Zip لـ .NET

في تطبيقات .NET الحديثة، **إضافة كلمة مرور zip** أثناء إنشاء أرشيف zip بصيغة LZMA عالي النسبة يمكنه حماية البيانات الحساسة ولا يزال يمنحك أفضل ضغط ممكن. سواءً كنت تبني خدمة ضغط ملفات ASP.NET، أو أداة سطح مكتب تتعامل مع ملفات كبيرة، أو سير عمل سحابي، فإن هذا الدليل يوضح لك خطوة بخطوة كيفية تأمين وضغط ملفاتك باستخدام Aspose.Zip لـ .NET.

## إجابات سريعة
- **ما هو الفائدة الأساسية من ضغط LZMA؟** أعلى نسبة ضغط مع سرعة معقولة لمعظم أنواع الملفات.  
- **أي طريقة تخزن الملفات بدون ضغط؟** ضغط التخزين (المعروف أيضًا باسم “store compression zip”).  
- **هل يمكنني استخدام هذه الإعدادات في تطبيق ASP.NET؟** نعم — فقط قم بالإشارة إلى Aspose.Zip في مشروعك واستدعِ نفس الـ API.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب الترخيص التجاري للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ما هو “إضافة كلمة مرور zip” في Aspose.Zip؟
إضافة كلمة مرور zip تعني تشفير الإدخالات داخل أرشيف ZIP بحيث لا يمكن استخراج الملفات إلا من قبل المستخدمين الذين يعرفون كلمة المرور. توفر Aspose.Zip طريقة بسيطة `SetPassword` تعمل مع كل خوارزمية ضغط — Bzip2، LZMA، PPMd، Enhanced Deflate، و Store.

## لماذا تستخدم Aspose.Zip لضغط الملفات في .NET؟
- **واجهة برمجة تطبيقات موحدة** – واجهة متسقة واحدة لـ Bzip2 و LZMA و PPMd و Enhanced Deflate و Store.  
- **محسّن للأداء** – تنفيذ أصلي مُحسّن للمعالجة السريعة.  
- **متوافق مع ASP.NET** – يعمل بسلاسة في مشاريع الويب، الخدمات الخلفية، ووظائف Azure.  
- **تحكم دقيق** – ضبط حجم القاموس، مستوى الضغط، وإضافة كلمة مرور zip باستدعاء واحد.  
- **ضغط الملفات الكبيرة** بكفاءة عن طريق بث البيانات مباشرة إلى تدفق الإخراج.

## المتطلبات المسبقة
- **مكتبة Aspose.Zip لـ .NET** – قم بتنزيلها وتثبيتها من [توثيق Aspose](https://reference.aspose.com/zip/net/).  
- **ملف نصي تجريبي** – حضّر ملفًا تجريبيًا (مثال: `sample.txt`) لتضغطه.  
- **بيئة تطوير .NET** – Visual Studio 2022 أو أي بيئة تطوير متوافقة.

## استيراد المساحات الاسمية

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

الآن دعنا نستكشف كل إعداد ضغط ونرى كيف نضيف **كلمة مرور zip** حيث يلزم.

## استخدام إعدادات ضغط Bzip2

### الخطوة 1: تهيئة ضغط Bzip2

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new Bzip2CompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Optional: protect the archive with a password
        archive.SetPassword("MySecret123");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

*استدعاء `SetPassword` يوضح كيفية **إضافة كلمة مرور zip** إلى أرشيف مضغوط بـ Bzip2.*

## كيفية إضافة كلمة مرور zip باستخدام Aspose.Zip لـ .NET

يمكنك تطبيق كلمة مرور على أي كائن أرشيف قبل استدعاء `Save`. تعمل نفس الطريقة مع ضغط LZMA، PPMd، Enhanced Deflate، و Store. ما عليك سوى استبدال كائن إعدادات الضغط مع الحفاظ على استدعاء `SetPassword`.

## كيفية إنشاء أرشيف zip بصيغة LZMA باستخدام Aspose.Zip

### الخطوة 1: تهيئة ضغط LZMA

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new LzmaCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Add password protection (LZMA supports it)
        archive.SetPassword("StrongPwd!2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **نصيحة:** يقدم LZMA حجم قاموس **LZMA dictionary size** قابلًا للتكوين يؤثر على كل من نسبة الضغط واستهلاك الذاكرة. يمكنك ضبطه عبر `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` إذا كنت بحاجة إلى ضبط دقيق للملفات الكبيرة جدًا.

## استخدام إعدادات ضغط PPMd

### الخطوة 1: تهيئة ضغط PPMd

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new PPMdCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Secure the archive
        archive.SetPassword("PPMdPwd#2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## استخدام إعدادات ضغط Enhanced Deflate

### الخطوة 1: تهيئة ضغط Enhanced Deflate

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new EnhancedDeflateCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Password protection works here as well
        archive.SetPassword("DeflatePwd2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## استخدام إعدادات ضغط Store (store compression zip)

### الخطوة 1: تهيئة ضغط Store

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Even for store compression you can add a password
        archive.SetPassword("StorePwd2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **نصيحة احترافية:** عدل المتغير `dataDir` ليشير إلى دليل العمل الفعلي الخاص بك، وأعد استخدام نفس كائن `Archive` إذا كنت بحاجة لإضافة ملفات متعددة إلى أرشيف واحد.

## المشكلات الشائعة والحلول
- **أخطاء “الملف غير موجود”** – تحقق من أن `dataDir` ينتهي بفاصل مسار (`\` أو `/`) وأن `sample.txt` موجود.  
- **استهلاك الذاكرة مع الملفات الكبيرة** – استخدم `ArchiveEntrySettings` لتمكين وضع البث، الذي يكتب البيانات مباشرة إلى تدفق الإخراج.  
- **مستوى ضغط غير متوافق** – بعض الخوارزميات (مثل LZMA) تكشف عن خصائص إضافية مثل `DictionarySize`. راجع وثائق الـ API إذا كنت بحاجة إلى تحكم أدق.  
- **لم يتم تطبيق كلمة المرور** – تأكد من استدعاء `SetPassword` *قبل* `archive.Save(zipFile);`.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Zip لـ .NET مع مكتبات ضغط أخرى؟**  
ج: تم تصميم Aspose.Zip للعمل مع الخوارزميات المدمجة فيه. يمكن دمج مكتبات الطرف الثالث ولكن يتطلب معالجة مخصصة خارج API الخاص بـ Aspose.

**س: كيف يمكنني إضافة حماية كلمة مرور إلى zip تم إنشاؤه باستخدام Aspose.Zip؟**  
ج: استخدم طريقة `SetPassword(string password)` على كائن `Archive` قبل الحفظ. راجع [التوثيق](https://reference.aspose.com/zip/net/) لمزيد من التفاصيل.

**س: هل هناك نسخة تجريبية يمكنني اختبارها؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على مساعدة المجتمع أو طرح أسئلة؟**  
ج: للدعم ومناقشات المجتمع، زر [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37).

**س: هل يمكنني الحصول على ترخيص مؤقت للتقييم؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: كيف يساعد هذا في ضغط ملفات asp.net؟**  
ج: من خلال استدعاء نفس الـ API من متحكم ASP.NET أو Middleware، يمكنك ضغط الملفات أثناء النقل قبل إرسالها إلى العميل، مما يقلل من استهلاك النطاق الترددي ويحسن الأداء الظاهري.

**س: ما هي أفضل طريقة لضغط ملفات كبيرة بكفاءة؟**  
ج: اجمع بين وضع البث وضغط LZMA وحجم قاموس مناسب `DictionarySize`. هذا يوازن بين استهلاك الذاكرة ونسبة الضغط للبيانات الضخمة.

---

**آخر تحديث:** 2026-02-12  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}