---
date: 2026-06-19
description: Aspose.Zip for .NET का उपयोग करके tar फ़ाइलों को संपीड़ित करना, targz
  अभिलेख बनाना, और पासवर्ड‑सुरक्षित zip फ़ाइलों को निकालना सीखें – जिससे संग्रहण दक्षता
  और सुरक्षा में वृद्धि होती है।
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: आर्काइव निष्कर्षण और स्वरूप
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
title: Aspose.Zip for .NET के साथ Tar फ़ाइलों को संपीड़ित करने का तरीका
url: /hi/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET के साथ Tar फ़ाइलों को संपीड़ित कैसे करें

## परिचय

इस गाइड में आप **Tar फ़ाइलों को संपीड़ित** करने के लिए Aspose.Zip for .NET का उपयोग करना सीखेंगे, TarGz अभिलेख बनाना सीखेंगे, और पासवर्ड‑सुरक्षित zip अभिलेखों को निकालना देखेंगे। कुशल अभिलेख प्रबंधन आधुनिक .NET डेवलपर्स के लिए एक मुख्य कौशल है—चाहे आप बैकअप सेवा, क्लाउड‑स्टोरेज क्लाइंट, या डेटा‑प्रोसेसिंग पाइपलाइन बना रहे हों, इन फ़ॉर्मैट्स में महारत हासिल करने से स्टोरेज लागत घटती है, ट्रांसफ़र गति बढ़ती है, और संवेदनशील डेटा सुरक्षित रहता है।

## त्वरित उत्तर
- **TarBz2 क्या है?** एक संपीड़ित अभिलेख जो TAR पैकेजिंग को BZIP2 संपीड़न के साथ मिलाता है, जिससे उच्च संपीड़न अनुपात मिलता है।  
- **Aspose.Zip for .NET क्यों चुनें?** यह बाहरी निर्भरताओं के बिना कई अभिलेख फ़ॉर्मैट बनाने और निकालने के लिए एकल, सहज API प्रदान करता है।  
- **क्या मैं TarGz अभिलेख बना सकता हूँ?** हाँ – Aspose.Zip TarGz, TarLz, TarXz, TarZ, और अधिक का समर्थन करता है।  
- **पासवर्ड‑सुरक्षित zip अभिलेख को कैसे निकालें?** निकासी के समय `ArchiveEntry` ऑब्जेक्ट पर `Password` प्रॉपर्टी का उपयोग करें।  
- **उत्पादन उपयोग के लिए लाइसेंस चाहिए?** उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल उपलब्ध है।

## Tar संपीड़न क्या है?
Tar (Tape Archive) एक कंटेनर फ़ॉर्मैट है जो कई फ़ाइलों और डायरेक्टरीज़ को बिना संपीड़न के एक ही स्ट्रीम में बंडल करता है। जब आप BZIP2, GZip, LZMA, या XZ जैसे संपीड़न एल्गोरिद्म लागू करते हैं, तो परिणाम **tar‑आधारित अभिलेख** जैसे `.tar.bz2`, `.tar.gz`, `.tar.lz` आदि होता है। ये फ़ॉर्मैट Linux, macOS, और Windows में व्यापक रूप से समर्थित हैं, जिससे वे क्रॉस‑प्लेटफ़ॉर्म डेटा एक्सचेंज के लिए आदर्श बनते हैं।

## इन फ़ॉर्मैट्स को संभालने के लिए Aspose.Zip for .NET क्यों उपयोग करें?
Aspose.Zip **एकीकृत, निर्भरतामुक्त API** प्रदान करता है जो 50+ अभिलेख और संपीड़न फ़ॉर्मैट का समर्थन करता है, जिसमें TarBz2, TarGz, TarLz, TarXz, और TarZ शामिल हैं। यह Windows, Linux, और macOS पर चलता है, और इसकी स्ट्रीम‑आधारित आर्किटेक्चर मल्टी‑हंड्रेड‑मेगाबाइट अभिलेखों के लिए भी मेमोरी उपयोग को 10 MB से कम रखती है। पासवर्ड सुरक्षा अंतर्निहित है, जिससे अतिरिक्त लाइब्रेरी के बिना प्रति‑एंट्री एन्क्रिप्शन संभव होता है।

## पूर्वापेक्षाएँ
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, या .NET 5–10।  
- Aspose.Zip for .NET NuGet पैकेज स्थापित (`Install-Package Aspose.Zip`)।  
- C# फ़ाइल I/O और .NET प्रोजेक्ट सिस्टम की बुनियादी समझ।

## चरण‑दर‑चरण गाइड

### Tar फ़ाइलों को संपीड़ित करने का सीधा उत्तर
`Archive` एक अभिलेख फ़ाइल का प्रतिनिधित्व करता है और एंट्री जोड़ने तथा सहेजने के मेथड प्रदान करता है।  
एक `Archive` इंस्टेंस बनाएं, उन फ़ाइलों को जोड़ें जिन्हें आप बंडल करना चाहते हैं, `CompressionType.BZip2` सेट करें, और `ArchiveFormat.TarBz2` के साथ `Save` कॉल करें। लाइब्रेरी TAR कंटेनर लिखती है और एक ही स्ट्रीमिंग पास में इसे संपीड़ित करती है, इसलिए आप पूरे अभिलेख को मेमोरी में लोड नहीं करते।

### चरण 1: आवश्यक अभिलेख फ़ॉर्मैट चुनें
निर्णय लें कि कौन सा tar‑आधारित फ़ॉर्मैट आपके संपीड़न‑गति ट्रेड‑ऑफ़ से सबसे बेहतर मेल खाता है:

- **TarBz2** – सबसे उच्च संपीड़न अनुपात (TarGz से ≈30 % छोटा) लेकिन धीमा।  
- **TarGz** – गति और आकार का अच्छा संतुलन; अधिकांश क्लाउड‑स्टोरेज परिदृश्यों के लिए आदर्श।  
- **TarLz / TarXz** – बहुत उच्च संपीड़न, मध्यम गति; अभिलेखीय स्टोरेज के लिए उपयोगी।  
- **TarZ** – पुराने Unix टूल्स के साथ संगतता के लिए लेगेसी फ़ॉर्मैट।

### चरण 2: नया `Archive` इंस्टेंस बनाएं
`Archive` वह टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल अभिलेख फ़ाइल का प्रतिनिधित्व करता है।  

`Archive` क्लास पैकिंग और संपीड़न वर्कफ़्लो को प्रबंधित करती है, एंट्री जोड़ने और अंतिम फ़ाइल लिखने के मेथड प्रदान करती है।

### चरण 3: फ़ाइलें और फ़ोल्डर जोड़ें
आप `AddAll` के साथ पूरी डायरेक्टरी ट्री जोड़ सकते हैं या `AddFile` के साथ व्यक्तिगत फ़ाइलें जोड़ सकते हैं। मूल फ़ोल्डर पदानुक्रम को बनाए रखना बस बेस डायरेक्टरी पाथ पास करने जितना सरल है।

### चरण 4: वांछित संपीड़न प्रकार सेट करें
`CompressionType` समर्थित एल्गोरिद्म को सूचीबद्ध करता है।  

`CompressionType` वह एल्गोरिद्म (BZip2, GZip, LZMA, XZ, आदि) निर्धारित करता है जिसे सहेजते समय TAR स्ट्रीम पर लागू किया जाएगा।

### चरण 5: अभिलेख सहेजें
`ArchiveFormat` एक एनोम सेट है (जैसे `TarBz2`, `TarGz`) जो राइटर को बताता है कि कौन सा कंटेनर और संपीड़न उपयोग करना है।  

`Save` कॉल चयनित फ़ॉर्मैट के साथ अभिलेख को डिस्क पर लिखता है।

### चरण 6: पासवर्ड के साथ अभिलेख निकालना
`ArchiveEntry` अभिलेख के भीतर एकल फ़ाइल या डायरेक्टरी एंट्री का प्रतिनिधित्व करता है।  

पासवर्ड‑सुरक्षित zip को निकालने के लिए, अभिलेख खोलें, प्रत्येक `ArchiveEntry` खोजें, उसकी `Password` प्रॉपर्टी सेट करें, और `Extract` कॉल करें। यह प्रति‑एंट्री पासवर्ड मॉडल आपको एक ही zip में व्यक्तिगत फ़ाइलों को सुरक्षित करने की अनुमति देता है।

### चरण 7: परिणाम सत्यापित करें
निकासी के बाद, फ़ाइल आकार और SHA‑256 चेकसम की तुलना करें ताकि यह पुष्टि हो सके कि अभिलेख राउंड‑ट्रिप ने डेटा अखंडता बनाए रखी है।

## सामान्य उपयोग केस
- **बैकअप यूटिलिटीज़** – दैनिक बैकअप को `.tar.bz2` के रूप में संग्रहीत करें ताकि स्टोरेज लागत में 30 % तक कमी आए।  
- **क्रॉस‑प्लेटफ़ॉर्म डेटा एक्सचेंज** – Tar‑आधारित फ़ॉर्मैट Linux, macOS, और Windows टूल्स द्वारा मूल रूप से समझे जाते हैं।  
- **सुरक्षित वितरण** – संवेदनशील एंट्रीज़ को पासवर्ड असाइन करें, जिससे अतिरिक्त एन्क्रिप्शन टूल्स के बिना अनुपालन आवश्यकताओं को पूरा किया जा सके।

## समस्या निवारण एवं टिप्स
- **बड़े अभिलेख** – मेमोरी उपयोग कम रखने के लिए स्ट्रीमिंग API (`Archive.CreateEntryFromFile`) को प्राथमिकता दें।  
- **पासवर्ड असंगतता** – प्रत्येक `ArchiveEntry` पर सेट किया गया पासवर्ड बिल्कुल मेल खाना चाहिए; अन्यथा `InvalidPasswordException` फेंका जाता है।  
- **संपीड़न स्तर** – BZIP2 कस्टम स्तर प्रदान नहीं करता; यदि आपको अधिक नियंत्रण चाहिए तो LZMA (`CompressionType.LZMA`) या XZ (`CompressionType.XZ`) पर स्विच करें।  

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: मैं TarGz अभिलेख कैसे बनाऊँ?**  
उत्तर: `CompressionType.GZip` सेट करें और `Save` कॉल करते समय `ArchiveFormat.TarGz` उपयोग करें। इससे एक ही चरण में `.tar.gz` फ़ाइल बनती है।

**प्रश्न: क्या मैं पासवर्ड‑सुरक्षित अभिलेख को बिना पासवर्ड के निकाल सकता हूँ?**  
उत्तर: नहीं। प्रत्येक एंट्री को सही पासवर्ड प्रदान करना आवश्यक है; अन्यथा निकासी `InvalidPasswordException` के साथ विफल होगी।

**प्रश्न: क्या Aspose.Zip विभिन्न एंट्रीज़ के लिए अलग‑अलग पासवर्ड के साथ अभिलेख निकालने का समर्थन करता है?**  
उत्तर: हाँ। `Extract` कॉल करने से पहले प्रत्येक `ArchiveEntry` को व्यक्तिगत रूप से पासवर्ड असाइन करें।

**प्रश्न: कौन सा फ़ॉर्मैट सबसे अच्छा संपीड़न देता है?**  
उत्तर: सामान्यतः TarBz2 सबसे छोटा आकार देता है, उसके बाद TarLz और TarXz आते हैं। TarGz तेज़ लेकिन अभी भी प्रभावी विकल्प है।

**प्रश्न: क्या TAR अभिलेख में जोड़ने योग्य फ़ाइलों की संख्या पर कोई सीमा है?**  
उत्तर: व्यावहारिक रूप से कोई सीमा नहीं है, लेकिन अत्यधिक बड़े अभिलेख (>10 GB) को संभालने में आसान बनाने के लिए कई भागों में विभाजित करना लाभदायक हो सकता है।

## अभिलेख निकासी और फ़ॉर्मैट ट्यूटोरियल
### [Aspose.Zip for .NET के साथ TarBz2 फ़ाइल संपीड़न](./compress-to-tar-bz2/)
.NET में Aspose.Zip का उपयोग करके फ़ाइलों को TarBz2 फ़ॉर्मैट में संपीड़ित करना सीखें। कुशल फ़ाइल संपीड़न के लिए हमारा चरण‑दर‑चरण गाइड देखें।  
### [Aspose.Zip for .NET के साथ TarGz में संपीड़न](./compress-to-tar-gz/)
.NET में Aspose.Zip के साथ कुशल फ़ाइल संपीड़न का अन्वेषण करें। TarGz में आसानी से संपीड़ित करें।  
### [Aspose.Zip for .NET के साथ TarLz में संपीड़न](./compress-to-tar-lz/)
.NET में Aspose.Zip के साथ फ़ाइलों को आसानी से संपीड़ित करें। चरण‑दर‑चरण TarLz अभिलेख बनाना सीखें।  
### [Aspose.Zip for .NET के साथ TarXz में संपीड़न](./compress-to-tar-xz/)
Aspose.Zip का उपयोग करके .NET में फ़ाइलों को TarXz फ़ॉर्मैट में संपीड़ित करना सीखें। कुशल स्टोरेज और ट्रांसमिशन के लिए हमारा गाइड देखें।  
### [Aspose.Zip for .NET के साथ TarZ में संपीड़न](./compress-to-tar-z/)
Aspose.Zip for .NET का उपयोग करके TarZ में चरण‑दर‑चरण संपीड़न का अन्वेषण करें। आपके .NET प्रोजेक्ट्स के लिए कुशल फ़ाइल हैंडलिंग।  
### [Aspose.Zip for .NET में विभिन्न पासवर्ड वाले अभिलेख एंट्रीज़ को निकालना](./extract-archive-different-passwords/)
Aspose.Zip for .NET में विभिन्न पासवर्ड वाले अभिलेख एंट्रीज़ को निकालना सीखें। अपने अनुप्रयोगों में सुरक्षा और लचीलापन बढ़ाएँ।

---

**अंतिम अपडेट:** 2026-06-19  
**परीक्षित संस्करण:** Aspose.Zip for .NET 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Zip for .NET के साथ tar अभिलेख बनाना और फ़ाइलें जोड़ना](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip for .NET के साथ tar संपीड़ित करना और TarBz2 बनाना](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aspose.Zip के साथ फ़ाइलें जोड़ना और tarxz अभिलेख बनाना](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}