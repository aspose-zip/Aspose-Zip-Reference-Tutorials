---
date: 2026-06-09
description: تعلم كيفية إضافة كلمة مرور إلى ملف zip وإنشاء أرشيفات zip بتقنية LZMA
  باستخدام Aspose.Zip for .NET. يغطي هذا الدليل Bzip2، LZMA (dictionary size)، PPMd،
  Enhanced Deflate، Store compression، وضغط ملفات ASP.NET للملفات الكبيرة.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: تحسين إعدادات الضغط
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: إضافة كلمة مرور إلى ملف zip وإنشاء أرشيف LZMA باستخدام Aspose.Zip for .NET
url: /ar/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة كلمة مرور إلى ملف zip وإنشاء أرشيف LZMA باستخدام Aspose.Zip لـ .NET

## إجابات سريعة
- **ما هو الفائدة الرئيسية لضغط LZMA؟** أعلى نسبة ضغط مع سرعة معقولة لمعظم أنواع الملفات.  
- **أي طريقة تخزن الملفات بدون ضغط؟** ضغط التخزين (المعروف أيضًا باسم “store compression zip”).  
- **هل يمكنني استخدام هذه الإعدادات في تطبيق ASP.NET؟** نعم — ما عليك سوى الإشارة إلى Aspose.Zip في مشروعك واستدعاء نفس API.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم ترخيص تجاري للإنتاج؛ تتوفر نسخة تجريبية مجانية.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، و .NET 5–10.

## ما هو “إضافة كلمة مرور إلى zip” في Aspose.Zip؟
**إضافة كلمة مرور إلى ملف zip تشفر كل إدخال داخل أرشيف ZIP بحيث لا يستطيع استخراج الملفات إلا المستخدمون الذين يعرفون كلمة المرور.** يدعم Aspose.Zip كلًا من تشفير ZipCrypto التقليدي وتشفير AES (128 أو 192 أو 256‑بت). يتم توفير إعدادات التشفير كوسيط ثانٍ إلى `ArchiveEntrySettings` عند إنشاء `Archive`؛ لا توجد طريقة منفصلة `SetPassword`.

## لماذا نستخدم Aspose.Zip لضغط الملفات في .NET؟
يوفر Aspose.Zip واجهة برمجة تطبيقات واحدة ومتسقة تغطي العديد من الخوارزميات مع تقديم أداء عالي واستهلاك منخفض للذاكرة. يتيح للمطورين اختيار أفضل طريقة ضغط لكل سيناريو وتطبيق التشفير في خطوة واحدة، مما يبسط الكود ويقلل من عبء الصيانة.

- **واجهة برمجة تطبيقات موحدة** – واجهة متسقة واحدة لـ Bzip2، LZMA، PPMd، Enhanced Deflate، و Store.  
- **محسّن للأداء** – المعالجة الأصلية المحسّنة تتعامل مع **ملفات تصل إلى 10 GB** دون تحميل الملف بالكامل إلى الذاكرة.  
- **متوافق مع ASP.NET** – يعمل بسلاسة في مشاريع الويب، الخدمات الخلفية، و Azure Functions.  
- **تحكم دقيق** – ضبط حجم القاموس، مستوى الضغط، والتشفير باستدعاء مُنشئ واحد.  
- **يدعم أكثر من 10 خوارزميات ضغط** – يغطي أكثر حالات الاستخدام شيوعًا في خطوط بيانات المؤسسات.

## المتطلبات المسبقة
- **مكتبة Aspose.Zip لـ .NET** – قم بتحميلها وتثبيتها من [توثيق Aspose](https://reference.aspose.com/zip/net/).  
- **ملف نصي تجريبي** – حضّر ملفًا تجريبيًا (مثال: `sample.txt`) لتضغطه.  
- **بيئة تطوير .NET** – Visual Studio 2022 أو أي بيئة تطوير متوافقة.  

## استيراد مساحات الأسماء

فئات `Archive` و `ArchiveEntrySettings` وفئات التشفير موجودة في مساحة الأسماء `Aspose.Zip`. استوردها في أعلى ملفك:

- `Archive` تمثل حاوية أرشيف ZIP.  
- `ArchiveEntrySettings` تحتفظ بخيارات الضغط والتشفير لكل إدخال.  
- فئات التشفير (مثل `AesEncryptionSettings`) تحدد كيفية تشفير البيانات.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

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

الآن دعنا نستكشف كل إعداد ضغط ونرى كيف نضيف **كلمة مرور إلى zip** حيث يلزم.

## استخدام إعدادات ضغط Bzip2

### الخطوة 1: تهيئة ضغط Bzip2 مع تشفير تقليدي

`Bzip2CompressionSettings` يضبط خوارزمية Bzip2 (حجم الكتلة، إلخ).  
`TraditionalEncryptionSettings` يطبق تشفير ZipCrypto التقليدي على إدخال.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*يتم تطبيق حماية كلمة المرور عبر `TraditionalEncryptionSettings` الممررة مباشرة إلى `ArchiveEntrySettings`.*

## كيفية إضافة كلمة مرور إلى zip باستخدام Aspose.Zip لـ .NET

حمّل ملف المصدر الخاص بك، أنشئ `Archive` باستخدام إعدادات الإدخال، وأضف الملف إلى الأرشيف. يتم تطبيق التشفير تلقائيًا لأنه تم توفيره عند إنشاء كائن `ArchiveEntrySettings`.

**الإجابة المباشرة (40‑70 كلمة):**  
أنشئ كائن `ArchiveEntrySettings` يتضمن كلًا من إعدادات الضغط المطلوبة إما `TraditionalEncryptionSettings` أو `AesEncryptionSettings`. ثم مرّر هذا الكائن إلى مُنشئ `Archive` وأضف الملفات باستخدام `AddEntry`. يُكتب الأرشيف مع كلمة المرور مدمجة مسبقًا، لذا لا حاجة لأي خطوة إضافية بعد الإنشاء.

`ArchiveEntrySettings` هو الحامل الذي يخبر Aspose.Zip كيف يجب ضغط كل إدخال وتشفيره.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## كيفية إنشاء أرشيف zip بتقنية LZMA باستخدام Aspose.Zip

### الخطوة 1: تهيئة ضغط LZMA مع تشفير AES256

`LzmaCompressionSettings` يتحكم في معلمات LZMA الخاصة مثل حجم القاموس والبايتات السريعة.  
`AesEncryptionSettings` يوفر تشفير AES‑256 لإدخالات الأرشيف.

**الإجابة المباشرة (40‑70 كلمة):**  
أنشئ `LzmaCompressionSettings` مع `DictionarySize` المختار، ثم أنشئ كائن `AesEncryptionSettings` باستخدام كلمة مرورك و`EncryptionMethod.AES256`. بعد ذلك، كوّن `ArchiveEntrySettings` من كلا الإعدادين. مرّر هذا إلى مُنشئ `Archive` وأضف ملفاتك؛ سيصبح الـ zip مضغوطًا بتقنية LZMA ومحمياً بـ AES‑256 في عملية واحدة.

`LzmaCompressionSettings` هو الفئة التي تتحكم في معلمات LZMA الخاصة مثل حجم القاموس والبايتات السريعة.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **نصيحة:** يقدم LMA حجم قاموس LZMA قابل للتكوين يؤثر على كل من نسبة الضغط واستهلاك الذاكرة. يمكنك ضبطه عبر `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` إذا كنت بحاجة إلى ضبط دقيق للملفات الكبيرة جدًا.

## استخدام إعدادات ضغط PPMd

### الخطوة 1: تهيئة ضغط PPMd مع تشفير AES256

`PpmdCompressionSettings` يحدد الترتيب واستهلاك الذاكرة لخوارزمية PPMd.  
`AesEncryptionSettings` يوفر تشفير AES‑256 لإدخالات الأرشيف.

**الإجابة المباشرة (40‑70 كلمة):**  
أنشئ كائن `PpmdCompressionSettings`، اجمعه مع كائن `AesEncryptionSettings` الذي يحتوي على كلمة مرورك، ومرّر كلاهما إلى `ArchiveEntrySettings`. استخدم هذا الكائن عند إنشاء `Archive`؛ سيصبح الـ zip مضغوطًا بـ PPMd ومحمياً بكلمة مرور دون استدعاءات إضافية.

`PpmdCompressionSettings` يحدد الترتيب واستهلاك الذاكرة لخوارزمية PPMd.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## استخدام إعدادات ضغط Enhanced Deflate

### الخطوة 1: تهيئة ضغط Enhanced Deflate مع تشفير AES256

`EnhancedDeflateCompressionSettings` يتيح لك تحديد مستوى الضغط الذي يوازن بين السرعة والحجم.  
`AesEncryptionSettings` يوفر تشفير AES‑256 لإدخالات الأرشيف.

**الإجابة المباشرة (40‑70 كلمة):**  
أنشئ `EnhancedDeflateCompressionSettings` بالمستوى المطلوب (0‑9)، اجمعه مع `AesEncryptionSettings`، ولفهما داخل `ArchiveEntrySettings`. مرّر هذا إلى مُنشئ `Archive` وأضف الملفات؛ سيُنشأ الأرشيف بضغط Enhanced Deflate وحماية كلمة مرور AES‑256 في خطوة واحدة.

`EnhancedDeflateCompressionSettings` يتيح لك تحديد مستوى الضغط الذي يوازن بين السرعة والحجم.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## استخدام إعدادات ضغط Store (store compression zip)

### الخطوة 1: تهيئة ضغط Store مع تشفير تقليدي

`StoreCompressionSettings` يخبر Aspose.Zip بتخطي الضغط تمامًا، مع الحفاظ على الملف الأصلي بايتًا بايتًا.  
`TraditionalEncryptionSettings` يطبق تشفير ZipCrypto التقليدي.

**الإجابة المباشرة (40‑70 كلمة):**  
أنشئ كائن `StoreCompressionSettings` (الذي لا يطبق ضغطًا)، اجمعه مع `TraditionalEncryptionSettings` الذي يحتوي على كلمة مرورك، ولفهما داخل `ArchiveEntrySettings`. مرّر هذا إلى مُنشئ `Archive`؛ سيحتوي الـ zip الناتج على الملف الأصلي غير مضغوط ولكنه محمي بكلمة مرور.

`StoreCompressionSettings` يخبر Aspose.Zip بتخطي الضغط تمامًا، مع الحفاظ على الملف الأصلي بايتًا بايتًا.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **نصيحة احترافية:** اضبط المتغير `dataDir` ليشير إلى دليل العمل الفعلي الخاص بك، وأعد استخدام نفس كائن `Archive` إذا كنت بحاجة لإضافة ملفات متعددة إلى أرشيف واحد.

## المشكلات الشائعة والحلول
- **خطأ "الملف غير موجود"** – تحقق من أن `dataDir` ينتهي بفاصل مسار (`\` أو `/`) وأن `sample.txt` موجود.  
- **استهلاك الذاكرة مع الملفات الكبيرة** – استخدم `ArchiveEntrySettings` لتمكين وضع البث، الذي يكتب البيانات مباشرة إلى تدفق الإخراج.  
- **مستوى ضغط غير متوافق** – بعض الخوارزميات (مثل LZMA) تكشف عن خصائص إضافية مثل `DictionarySize`. راجع وثائق API إذا كنت بحاجة إلى تحكم أدق.  
- **كلمة المرور غير مطبقة** – تأكد من تمرير كائن إعدادات التشفير كوسيط ثانٍ إلى `ArchiveEntrySettings` عند الإنشاء، وليس بعد إنشاء الأرشيف.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Zip لـ .NET مع مكتبات ضغط أخرى؟**  
ج: تم تصميم Aspose.Zip للعمل مع الخوارزميات المدمجة فيه. يمكن دمج مكتبات الطرف الثالث ولكن يتطلب معالجة مخصصة خارج API الخاص بـ Aspose.

**س: كيف يمكنني إضافة حماية كلمة مرور إلى zip تم إنشاؤه باستخدام Aspose.Zip؟**  
ج: مرّر إما `TraditionalEncryptionSettings` أو `AesEncryptionSettings` كوسيط ثانٍ إلى `ArchiveEntrySettings` عند إنشاء `Archive`. راجع [التوثيق](https://docs.aspose.com/zip/net/password-protecting-archives/) للحصول على أمثلة كاملة.

**س: هل هناك نسخة تجريبية يمكنني اختبارها؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على مساعدة المجتمع أو طرح الأسئلة؟**  
ج: للحصول على الدعم ومناقشات المجتمع، زر [منتدى Aspose.Zip](https://forum.aspose.com/c/zip/37).

**س: هل يمكنني الحصول على ترخيص مؤقت للتقييم؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: كيف يساعد هذا في ضغط ملفات ASP.NET؟**  
ج: من خلال استدعاء نفس API من وحدة تحكم ASP.NET أو middleware، يمكنك ضغط الملفات أثناء النقل قبل إرسالها إلى العميل، مما يقلل من استهلاك النطاق الترددي ويحسن الأداء الظاهري.

**س: ما هي أفضل طريقة لضغط الملفات الكبيرة بكفاءة؟**  
ج: اجمع بين وضع البث وضغط LZMA وحجم `DictionarySize` المناسب. يوازن ذلك بين استهلاك الذاكرة ونسبة الضغط للبيانات الضخمة.

---

**آخر تحديث:** 2026-06-09  
**تم الاختبار مع:** Aspose.Zip 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [Aspose.Zip لـ .NET - حماية كلمة مرور لأرشيف Zip وتخزين ملفات متعددة بدون ضغط](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [إنشاء zip محمي بكلمة مرور لأدلة .NET – درس Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [ضغط ملفات متعددة c# – ضغط سهل مع Aspose.Zip لـ .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}