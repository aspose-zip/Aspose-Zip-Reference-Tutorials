---
date: 2026-06-19
description: تعلم كيفية ضغط ملفات tar، وإنشاء أرشيفات targz، واستخراج ملفات zip المحمية
  بكلمة مرور باستخدام Aspose.Zip for .NET – مما يعزز كفاءة التخزين والأمان.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: استخراج الأرشيفات والصيغ
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: كيفية ضغط ملفات Tar باستخدام Aspose.Zip for .NET
url: /ar/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ضغط ملفات Tar باستخدام Aspose.Zip لـ .NET

## مقدمة

في هذا الدليل ستكتشف **كيفية ضغط tar** باستخدام Aspose.Zip لـ .NET، وتتعلم إنشاء أرشيفات TarGz، وترى كيفية استخراج أرشيفات zip المحمية بكلمة مرور. التعامل الفعال مع الأرشيفات مهارة أساسية للمطورين الحديثين في .NET—سواءً كنت تبني خدمة نسخ احتياطي، أو عميل تخزين سحابي، أو خط أنابيب لمعالجة البيانات، فإن إتقان هذه الصيغ يقلل من تكاليف التخزين، ويسرّع النقل، ويحافظ على أمان البيانات الحساسة.

## إجابات سريعة
- **ما هو TarBz2؟** أرشيف مضغوط يجمع بين حزم TAR وضغط BZIP2 للحصول على نسب ضغط عالية.  
- **لماذا تختار Aspose.Zip لـ .NET؟** يقدم واجهة برمجة تطبيقات واحدة وسلسة لإنشاء واستخراج العديد من صيغ الأرشيف دون تبعيات خارجية.  
- **هل يمكنني إنشاء أرشيف TarGz؟** نعم – يدعم Aspose.Zip صيغ TarGz وTarLz وTarXz وTarZ وغيرها.  
- **كيف يمكن استخراج أرشيف zip محمي بكلمة مرور؟** استخدم خاصية `Password` في كائن `ArchiveEntry` عند الاستخراج.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب الترخيص التجاري للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية للتقييم.

## ما هو ضغط Tar؟
Tar (Tape Archive) هو تنسيق حاوية يجمع ملفات ودلائل متعددة في تدفق واحد دون ضغط. عندما تطبق خوارزمية ضغط مثل BZIP2 أو GZip أو LZMA أو XZ، تكون النتيجة **أرشيفًا قائمًا على tar** مثل `.tar.bz2`، `.tar.gz`، `.tar.lz`، إلخ. هذه الصيغ مدعومة على نطاق واسع عبر Linux وmacOS وWindows، مما يجعلها مثالية لتبادل البيانات عبر الأنظمة.

## لماذا تستخدم Aspose.Zip لـ .NET للتعامل مع هذه الصيغ؟
يوفر Aspose.Zip **واجهة برمجة تطبيقات موحدة وخالية من التبعيات** تدعم أكثر من 50 صيغة أرشيف وضغط، بما في ذلك TarBz2 وTarGz وTarLz وTarXz وTarZ. يعمل على Windows وLinux وmacOS، وتبقي هندسته القائمة على التدفق استهلاك الذاكرة تحت 10 ميغابايت حتى للأرشيفات التي تتجاوز مئات الميغابايت. الحماية بكلمة مرور مدمجة، مما يسمح بتشفير كل إدخال دون مكتبات إضافية.

## المتطلبات المسبقة
- .NET Framework 2.0–4.8.1، .NET Core 2.0–3.1، أو .NET 5–10.  
- حزمة NuGet الخاصة بـ Aspose.Zip لـ .NET مثبتة (`Install-Package Aspose.Zip`).  
- إلمام أساسي بـ I/O للملفات في C# ونظام مشاريع .NET.

## دليل خطوة بخطوة

### كيفية ضغط ملفات Tar – إجابة مباشرة
`Archive` يمثل ملف أرشيف ويوفر طرقًا لإضافة الإدخالات وحفظه.  
أنشئ مثيلًا من `Archive`، أضف الملفات التي تريد تجميعها، اضبط `CompressionType.BZip2`، واستدعِ `Save` مع `ArchiveFormat.TarBz2`. تقوم المكتبة بكتابة حاوية TAR وضغطها في تمريرة تدفق واحدة، لذا لا تقوم بتحميل الأرشيف بالكامل في الذاكرة.

### الخطوة 1: اختر صيغة الأرشيف التي تحتاجها
قرر أي صيغة تعتمد على tar تتناسب مع موازنة السرعة مقابل الضغط:

- **TarBz2** – أعلى نسبة ضغط (≈30 % أصغر من TarGz) لكنه أبطأ.  
- **TarGz** – توازن جيد بين السرعة والحجم؛ مثالي لمعظم سيناريوهات التخزين السحابي.  
- **TarLz / TarXz** – ضغط عالي جدًا مع سرعة معتدلة، مفيد للتخزين الأرشيفي.  
- **TarZ** – صيغة قديمة للتوافق مع أدوات Unix القديمة.

### الخطوة 2: إنشاء مثيل جديد من `Archive`
`Archive` هو الكائن الأعلى مستوى الذي يمثل ملف أرشيف واحد في الذاكرة.  

تدير فئة `Archive` سير عمل التعبئة والضغط، وتوفر طرقًا لإضافة الإدخالات وكتابة الملف النهائي.

### الخطوة 3: إضافة ملفات ومجلدات
يمكنك إضافة شجرة دليل كاملة باستخدام `AddAll` أو إضافة ملفات فردية باستخدام `AddFile`. الحفاظ على هيكل المجلد الأصلي بسيط كتمرير مسار الدليل الأساسي.

### الخطوة 4: ضبط نوع الضغط المطلوب
`CompressionType` يعدد الخوارزميات المدعومة.  

`CompressionType` يحدد الخوارزمية (BZip2، GZip، LZMA، XZ، إلخ) التي سيتم تطبيقها على تدفق TAR أثناء الحفظ.

### الخطوة 5: حفظ الأرشيف
`ArchiveFormat` هو مجموعة تعداد (مثل `TarBz2`، `TarGz`) تخبر الكاتب أي حاوية وضغط يستخدم.  

استدعاء `Save` يكتب الأرشيف إلى القرص باستخدام الصيغة المحددة.

### الخطوة 6: استخراج الأرشيفات باستخدام كلمات مرور
`ArchiveEntry` يمثل ملفًا أو دليلًا واحدًا داخل الأرشيف.  

لاستخراج zip محمي بكلمة مرور، افتح الأرشيف، حدد كل `ArchiveEntry`، عيّن خاصية `Password` الخاصة به، واستدعِ `Extract`. يتيح لك نموذج كلمة المرور لكل إدخال حماية ملفات فردية داخل zip واحد.

### الخطوة 7: التحقق من النتيجة
بعد الاستخراج، قارن أحجام الملفات وتحقق من مجموعات SHA‑256 للتأكد من أن عملية المرور عبر الأرشيف حافظت على سلامة البيانات.

## حالات الاستخدام الشائعة
- **Backup utilities** – احفظ النسخ الاحتياطية اليومية كـ `.tar.bz2` لتقليل تكاليف التخزين حتى 30 %.  
- **Cross‑platform data exchange** – صيغ Tar مفهومة أصلاً من قبل أدوات Linux وmacOS وWindows.  
- **Secure distribution** – عيّن كلمات مرور للمدخلات الحساسة، لتلبية متطلبات الامتثال دون أدوات تشفير إضافية.

## استكشاف الأخطاء والنصائح
- **Large archives** – يفضَّل استخدام واجهة برمجة التطبيقات المتدفقة (`Archive.CreateEntryFromFile`) للحفاظ على انخفاض استهلاك الذاكرة.  
- **Password mismatches** – يجب أن تتطابق كلمة المرور المحددة لكل `ArchiveEntry` تمامًا؛ وإلا سيتم رمي `InvalidPasswordException`.  
- **Compression level** – لا يتيح BZIP2 مستويات مخصصة؛ إذا كنت تحتاج إلى تحكم أدق، انتقل إلى LZMA (`CompressionType.LZMA`) أو XZ (`CompressionType.XZ`).  

## الأسئلة المتكررة

**س: كيف يمكنني إنشاء أرشيف TarGz؟**  
A: قم بتعيين `CompressionType.GZip` واستخدم `ArchiveFormat.TarGz` عند استدعاء `Save`. ينتج ذلك ملف `.tar.gz` في خطوة واحدة.

**س: هل يمكن استخراج أرشيف محمي بكلمة مرور دون معرفة كلمة المرور؟**  
A: لا. يجب تزويد كل إدخال بكلمة المرور الصحيحة؛ وإلا سيفشل الاستخراج مع `InvalidPasswordException`.

**س: هل يدعم Aspose.Zip استخراج الأرشيفات بكلمات مرور مختلفة لكل إدخال؟**  
A: نعم. عيّن كلمة مرور لكل `ArchiveEntry` على حدة قبل استدعاء `Extract`.

**س: أي صيغة توفر أفضل ضغط؟**  
A: عادةً ما ينتج TarBz2 أصغر حجم، يليه TarLz وTarXz. يوفر TarGz بديلًا أسرع ولا يزال فعالًا.

**س: هل هناك حد لعدد الملفات التي يمكنني إضافتها إلى أرشيف TAR؟**  
A: عمليًا لا يوجد حد، لكن الأرشيفات الضخمة جدًا (>10 GB) قد تستفيد من تقسيمها إلى أجزاء متعددة لتسهيل التعامل.

## دروس استخراج الأرشيفات والصيغ

### [ضغط الملفات إلى TarBz2 باستخدام Aspose.Zip لـ .NET](./compress-to-tar-bz2/)
تعلم كيفية ضغط الملفات إلى صيغة TarBz2 في .NET باستخدام Aspose.Zip. اتبع دليلنا خطوة بخطوة لضغط ملفات فعال.

### [الضغط إلى TarGz باستخدام Aspose.Zip لـ .NET](./compress-to-tar-gz/)
استكشف ضغط ملفات فعال في .NET باستخدام Aspose.Zip. اضغط إلى TarGz بسهولة.

### [الضغط إلى TarLz باستخدام Aspose.Zip لـ .NET](./compress-to-tar-lz/)
ضغط الملفات بسهولة في .NET باستخدام Aspose.Zip. تعلم إنشاء أرشيفات TarLz خطوة بخطوة.

### [الضغط إلى TarXz باستخدام Aspose.Zip لـ .NET](./compress-to-tar-xz/)
تعلم ضغط الملفات إلى صيغة TarXz في .NET باستخدام Aspose.Zip. اتبع دليلنا لتخزين ونقل فعال.

### [الضغط إلى TarZ باستخدام Aspose.Zip لـ .NET](./compress-to-tar-z/)
استكشف ضغط TarZ خطوة بخطوة باستخدام Aspose.Zip لـ .NET. معالجة ملفات فعالة لمشاريع .NET الخاصة بك.

### [استخراج مدخلات الأرشيف بكلمات مرور مختلفة في Aspose.Zip لـ .NET](./extract-archive-different-passwords/)
تعلم كيفية استخراج مدخلات الأرشيف بكلمات مرور مختلفة في Aspose.Zip لـ .NET. عزز الأمان والمرونة في تطبيقاتك.

---

**آخر تحديث:** 2026-06-19  
**تم الاختبار مع:** Aspose.Zip for .NET 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء أرشيف tar وإضافة ملفات إلى tar باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [كيفية ضغط tar وإنشاء TarBz2 باستخدام Aspose.Zip لـ .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [إضافة ملفات إلى tar وإنشاء أرشيف tarxz باستخدام Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}