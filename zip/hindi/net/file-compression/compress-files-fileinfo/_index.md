---
date: 2026-07-18
description: Aspose.Zip for .NET का उपयोग करके फ़ोल्डर को ज़िप में जोड़ना और फ़ाइलों
  को ज़िप में जोड़ना सीखें। यह चरण‑दर‑चरण गाइड दिखाता है कि ASP.NET प्रोजेक्ट्स में
  FileInfo के साथ फ़ाइलों को कैसे संपीड़ित किया जाए।
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: FileInfo का उपयोग करके फ़ाइलें संपीड़ित करें
og_description: Aspose.Zip for .NET का उपयोग करके फ़ोल्डर को ज़िप में जोड़ें। जानें
  कि ज़िप आर्काइव कैसे बनाएं, फ़ाइलों को ज़िप में जोड़ें, और ASP.NET में फ़ोल्डरों
  को प्रभावी रूप से कैसे संपीड़ित करें।
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: फ़ोल्डर को ज़िप में जोड़ें – Aspose.Zip for .NET के साथ फ़ाइलें संपीड़ित
  करें
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Aspose.Zip for .NET का उपयोग करके फ़ोल्डर को ज़िप में जोड़ें – FileInfo के
  साथ फ़ाइलें संपीड़ित करें
url: /hi/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# फ़ोल्डर को ज़िप में जोड़ें Aspose.Zip for .NET का उपयोग करके

## परिचय

यदि आपको प्रोग्रामेटिक रूप से **add folder to zip** करने की आवश्यकता है, तो Aspose.Zip for .NET एक साफ़, उच्च‑प्रदर्शन API प्रदान करता है जो किसी भी .NET (ASP.NET सहित) एप्लिकेशन में काम करता है। इस ट्यूटोरियल में हम `FileInfo` क्लास का उपयोग करके फ़ाइलों को संकुचित करने की प्रक्रिया दिखाएंगे, आपको **add files to zip** करने का तरीका बताएंगे, और समझाएंगे कि यह तरीका आधुनिक .NET प्रोजेक्ट्स के लिए क्यों आदर्श है। हम **add folder to zip** करने के सटीक चरणों को भी कवर करेंगे ताकि आप एक ही ऑपरेशन में पूरी डायरेक्टरी को बंडल कर सकें। चलिए शुरू करते हैं!

## त्वरित उत्तर
- **ज़िप आर्काइव बनाने का सबसे आसान तरीका क्या है?** Use Aspose.Zip’s `Archive` class together with `FileInfo` objects.  
- **क्या मैं एक साथ कई फ़ाइलें जोड़ सकता हूँ?** Yes – just create a `FileInfo` for each file and call `CreateEntry`.  
- **क्या मुझे ASP.NET के लिए विशेष लाइसेंस चाहिए?** A commercial Aspose.Zip license is required for production; a free trial works for evaluation.  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **क्या API थ्रेड‑सेफ़ है?** Yes, as long as each thread works with its own `Archive` instance.

## ज़िप आर्काइव क्या है और इसे क्यों बनाएं?

एक ज़िप आर्काइव एक या अधिक फ़ाइलों को एकल, संकुचित कंटेनर में बंडल करता है। यह स्टोरेज स्पेस कम करता है, नेटवर्क ट्रांसफ़र को तेज़ बनाता है, और वितरण को सरल बनाता है। चाहे आप लॉग्स डिलीवर कर रहे हों, रिपोर्ट्स एक्सपोर्ट कर रहे हों, या क्लाइंट के लिए एसेट्स पैकेज कर रहे हों, प्रोग्रामेटिक रूप से **how to create zip archive** फ़ाइलें बनाना किसी भी .NET डेवलपर के लिए एक मूल्यवान कौशल है।

## ज़िप में फ़ाइलें जोड़ने के लिए Aspose.Zip का उपयोग क्यों करें?

Aspose.Zip एक शुद्ध‑.NET समाधान प्रदान करता है जो बाहरी निर्भरताओं को समाप्त करता है और डेवलपर्स को संपीड़न, एन्कोडिंग, और सुरक्षा पर सूक्ष्म नियंत्रण देता है। यह बड़े फ़ाइलों, पासवर्ड सुरक्षा को सपोर्ट करता है, और सभी समर्थित .NET संस्करणों में लगातार काम करता है, जिससे यह लेगेसी और आधुनिक दोनों एप्लिकेशन के लिए एक विश्वसनीय विकल्प बनता है।  

- **बाहरी निर्भरताएँ नहीं** – शुद्ध .NET इम्प्लीमेंटेशन।  
- **संकुचन स्तर और एन्कोडिंग पर पूर्ण नियंत्रण** (ASCII, UTF‑8, आदि)।  
- **4 GB से बड़ी फ़ाइलों और पासवर्ड सुरक्षा को सपोर्ट करता है**।  
- **50+ .NET संस्करणों में सुसंगत API** – .NET Framework 2.0 से लेकर .NET 10 तक।  

## पूर्वापेक्षाएँ

कोड में जाने से पहले, सुनिश्चित करें कि आपके पास:

1. **Aspose.Zip for .NET** स्थापित है। नवीनतम पैकेज [Aspose.Zip download page](https://releases.aspose.com/zip/net/) से डाउनलोड करें।  
2. आपके मशीन पर एक फ़ोल्डर जिसमें आप संकुचित करना चाहते हैं फ़ाइलें हों (उदा., `alice29.txt` और `fields.c`).  

## नेमस्पेस आयात करें

किसी भी C# फ़ाइल में जहाँ आप ज़िप आर्काइव के साथ काम करेंगे, निम्नलिखित `using` स्टेटमेंट्स जोड़ें:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

ये नेमस्पेस आपको `Archive` क्लास, सहेजने के विकल्प, और मानक I/O यूटिलिटीज़ तक पहुँच प्रदान करते हैं।

## स्टेप‑बाय‑स्टेप गाइड

### चरण 1: अपना डॉक्यूमेंट डायरेक्टरी सेट करें

सबसे पहले, उस फ़ोल्डर को परिभाषित करें जिसमें स्रोत फ़ाइलें हैं। प्लेसहोल्डर को आपके सिस्टम पर पूर्ण या सापेक्ष पथ से बदलें:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** `Path.Combine` का उपयोग करके पाथ को क्रॉस‑प्लेटफ़ॉर्म तरीके से बनाएं।

### चरण 2: लिखने के लिए ज़िप फ़ाइल खोलें

`FileStream` बनाएं जो आउटपुट ज़िप फ़ाइल की ओर इशारा करता हो। स्ट्रीम **Create** मोड में खुलती है, जो समान नाम वाली मौजूदा फ़ाइल को ओवरराइट कर देती है:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### चरण 3: प्रत्येक स्रोत फ़ाइल के लिए `FileInfo` ऑब्जेक्ट तैयार करें

`FileInfo` Aspose.Zip को डिस्क पर फिजिकल फ़ाइलों तक सीधा एक्सेस देता है। आप जिस प्रत्येक फ़ाइल को संकुचित करना चाहते हैं, उसके लिए एक इंस्टेंस बनाएं:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **`FileInfo` क्यों उपयोग करें?** यह पूरी फ़ाइल को मेमोरी में लोड करने से बचाता है, जो बड़े फ़ाइलों के लिए विशेष रूप से उपयोगी है।

### चरण 4: आर्काइव बनाएं और एंट्रीज़ जोड़ें

`Archive` क्लास Aspose.Zip का मुख्य ऑब्जेक्ट है जो मेमोरी में ज़िप कंटेनर को दर्शाता है। एक `Archive` ऑब्जेक्ट बनाएं, फिर प्रत्येक `FileInfo` के लिए `CreateEntry` कॉल करें। पहला आर्ग्यूमेंट वह नाम है जो फ़ाइल ज़िप के अंदर रखेगी, दूसरा आर्ग्यूमेंट स्रोत `FileInfo` है:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` मेथड एक नई फ़ाइल एंट्री को आर्काइव में जोड़ता है, एंट्री नाम को स्रोत `FileInfo` से लिंक करता है ताकि आर्काइव सहेजते समय डेटा सीधे डिस्क से स्ट्रीम हो।

### चरण 5: इच्छित एन्कोडिंग के साथ ज़िप आर्काइव सहेजें

अंत में, आर्काइव को पहले खुले `FileStream` में सहेजें। यहाँ एंट्री नामों के लिए ASCII एन्कोडिंग का उपयोग किया गया है, लेकिन यदि आपके फ़ाइलनाम में गैर‑ASCII अक्षर हैं तो आप UTF‑8 में स्विच कर सकते हैं:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` ब्लॉक्स के समाप्त होने पर, स्ट्रीम्स स्वतः बंद हो जाते हैं और ज़िप फ़ाइल उपयोग के लिए तैयार हो जाती है।

## Aspose.Zip का उपयोग करके फ़ोल्डर को ज़िप में कैसे जोड़ें?

लक्ष्य डायरेक्टरी लोड करें, प्रत्येक फ़ाइल को सूचीबद्ध करें, और प्रत्येक को फ़ोल्डर नाम सहित रिलेटिव पाथ के साथ जोड़ें। यह तरीका आपको **add folder to zip** करने देता है बिना प्रत्येक फ़ाइल को मैन्युअल रूप से सूचीबद्ध किए। एंट्री नामों में फ़ोल्डर पदानुक्रम को संरक्षित करके, परिणामी आर्काइव को मूल डायरेक्टरी संरचना के साथ निकाला जा सकता है, जो कई डिप्लॉयमेंट परिदृश्यों के लिए आवश्यक है।

1. `DirectoryInfo` का उपयोग करके उस फ़ोल्डर की ओर इशारा करें जिसे आप संकुचित करना चाहते हैं।  
2. `GetFiles("*", SearchOption.AllDirectories)` कॉल करके सभी फ़ाइलों को पुनरावर्ती रूप से प्राप्त करें।  
3. प्रत्येक फ़ाइल के लिए, एक `FileInfo` बनाएं और `"MyFolder/Report.pdf"` जैसे पाथ के साथ `CreateEntry` कॉल करें।

क्योंकि API `FileInfo` के साथ काम करता है, यह प्रत्येक फ़ाइल को सीधे डिस्क से स्ट्रीम करता है, जिससे मेमोरी उपयोग कम रहता है, भले ही फ़ोल्डर में सैकड़ों मेगाबाइट की फ़ाइलें हों।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **खाली ज़िप फ़ाइल** | `FileInfo` एक गैर‑मौजूद पथ की ओर इशारा करता है | `dataDir` और फ़ाइल नामों की जाँच करें; एंट्री बनाने से पहले `File.Exists` का उपयोग करके सत्यापित करें। |
| **गलत फ़ाइलनाम एन्कोडिंग** | डिफ़ॉल्ट एन्कोडिंग का उपयोग करना जब फ़ाइलनाम में गैर‑ASCII अक्षर हों | `ArchiveSaveOptions` में `Encoding = Encoding.UTF8` सेट करें। |
| **बड़ी फ़ाइलों पर OutOfMemoryException** | पूरी फ़ाइल को मेमोरी में लोड करना | `FileInfo` फ़ाइल को स्ट्रीम करता है; सुनिश्चित करें कि आप कहीं और फ़ाइल को बाइट एरे में नहीं पढ़ रहे हैं। |
| **अनुमति अस्वीकृत** | एप्लिकेशन के पास आउटपुट फ़ोल्डर के लिए लिखने की अनुमति नहीं है | एप्लिकेशन को उचित अधिकारों के साथ चलाएँ या लिखने योग्य डायरेक्टरी चुनें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही कॉल में पूरी फ़ोल्डर को ज़िप आर्काइव में जोड़ सकता हूँ?**  
A: कोई एकल‑कॉल मेथड नहीं है, लेकिन `DirectoryInfo` से फ़ाइलों को सूचीबद्ध करके और प्रत्येक को `CreateEntry` से जोड़ने से समान परिणाम कुशलता से प्राप्त होता है।

**Q: क्या Aspose.Zip पासवर्ड सुरक्षा को सपोर्ट करता है?**  
A: हाँ, आप सहेजने से पहले `Archive` ऑब्जेक्ट पर पासवर्ड सेट करके पूरे आर्काइव को एन्क्रिप्ट कर सकते हैं।

**Q: Aspose.Zip कितनी बड़ी ज़िप फ़ाइल को संभाल सकता है?**  
A: लाइब्रेरी 4 GB से बड़ी फ़ाइलों को प्रोसेस करती है और 10 GB से अधिक के आर्काइव बना सकती है बिना पूरे आर्काइव को मेमोरी में लोड किए।

**Q: क्या API .NET 6 और .NET 8 के साथ संगत है?**  
A: बिल्कुल। Aspose.Zip .NET 5 से .NET 10 तक सपोर्ट करता है, जो सभी वर्तमान LTS रिलीज़ को कवर करता है।

**Q: कौन से संपीड़न स्तर उपलब्ध हैं?**  
A: आप `CompressionLevel.NoCompression`, `Fast`, `Normal`, या `Maximum` चुन सकते हैं ताकि गति और आकार का संतुलन बना रहे।

## अतिरिक्त संसाधन

- नवीनतम Aspose.Zip पैकेज डाउनलोड करें: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- प्रोडक्शन उपयोग के लिए लाइसेंस खरीदें: [purchase page](https://purchase.aspose.com/buy)  
- समुदाय से मदद प्राप्त करें: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Aspose.Zip को मुफ्त में आज़माएँ: [free trial here](https://releases.aspose.com/)  
- मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त करें: [this link](https://purchase.aspose.com/temporary-license/)

## निष्कर्ष

अब आप जानते हैं **how to add folder to zip** और **how to create zip archive** फ़ाइलें Aspose.Zip for .NET का उपयोग करके, **add files to zip** कैसे करें, और क्यों यह तरीका ASP.NET और अन्य .NET एप्लिकेशन के लिए आदर्श है। विभिन्न संपीड़न स्तरों, एन्कोडिंग और एन्क्रिप्शन विकल्पों के साथ प्रयोग करें ताकि आर्काइव को अपनी सटीक जरूरतों के अनुसार अनुकूलित कर सकें। संकुचन का आनंद लें!

---

**अंतिम अपडेट:** 2026-07-18  
**परीक्षण किया गया:** Aspose.Zip for .NET 24.12 (latest)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Zip for .NET का उपयोग करके फ़ोल्डर को ज़िप कैसे करें](/zip/net/directory-and-folder-compression/compress-directory/)
- [c# में कई फ़ाइलें ज़िप करें – Aspose.Zip for .NET के साथ आसान संपीड़न](/zip/net/file-compression/compress-multiple-files/)
- [ज़िप आर्काइव बनाएं .NET – Aspose.Zip के साथ फ़ाइल संपीड़न](/zip/net/file-compression/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}