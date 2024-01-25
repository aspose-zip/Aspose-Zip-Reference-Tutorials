---
title: .NET के लिए Aspose.Zip - सुरक्षित फ़ाइल संग्रहण ट्यूटोरियल
linktitle: पासवर्ड के साथ संपीड़न के बिना एकाधिक फ़ाइलें संग्रहीत करें
second_title: फ़ाइलें संपीड़न और संग्रहण के लिए Aspose.Zip .NET API
description: बिना संपीड़न के एकाधिक फ़ाइलों को सुरक्षित रूप से संग्रहीत करने के लिए .NET के लिए Aspose.Zip का उपयोग करने का तरीका जानें। पासवर्ड सुरक्षा के लिए आसान कदम. फ़ाइल प्रबंधन की शक्ति अनलॉक करें!
type: docs
weight: 13
url: /hi/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

.NET विकास की दुनिया में, फ़ाइलों का प्रबंधन और हेरफेर करना एक सामान्य कार्य है। .NET के लिए Aspose.Zip एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को ज़िप अभिलेखागार को निर्बाध रूप से संपीड़ित, डीकंप्रेस और हेरफेर करने की क्षमता प्रदान करती है। इस ट्यूटोरियल में, हम एक विशिष्ट परिदृश्य में गहराई से उतरेंगे: कई फ़ाइलों को बिना संपीड़न के संग्रहीत करना और उन्हें पासवर्ड से सुरक्षित करना। इस गाइड के अंत तक, आप .NET के लिए Aspose.Zip का उपयोग करके इस कार्यक्षमता को लागू करने के ज्ञान से लैस होंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Zip: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Zip स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/zip/net/).

-  दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जहाँ आपकी स्रोत फ़ाइलें स्थित हैं। दिए गए उदाहरण में, वेरिएबल`dataDir` आपकी दस्तावेज़ निर्देशिका का प्रतिनिधित्व करता है।

## नामस्थान आयात करें

आरंभ करने के लिए, आइए अपने कोड के लिए आवश्यक नामस्थान आयात करें:

```csharp
// संसाधन निर्देशिका का पथ.
string dataDir = "Your Document Directory"

// Aspose.Zip नामस्थान आयात करें
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## चरण 1: ज़िप फ़ाइल खोलें

```csharp
//एक्सस्टार्ट: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 इस चरण में एक नई ज़िप फ़ाइल का उपयोग करना शामिल है`FileStream`. फ़ाइल का नाम "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip" होगा।

## चरण 2: स्रोत फ़ाइल खोलें

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

यहां, हम पहली स्रोत फ़ाइल, "alice29.txt" खोलते हैं, जो ज़िप संग्रह में संग्रहीत की जाएगी।

## चरण 3: एक पुरालेख बनाएँ

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 इस चरण में, हम इसका एक उदाहरण बनाते हैं`Archive` वर्ग, संपीड़न और एन्क्रिप्शन सेटिंग्स निर्दिष्ट करता है। हम उपयोग करते हैं`StoreCompressionSettings` फ़ाइलों को संपीड़न के बिना संग्रहीत करने के लिए और`AesEcryptionSettings` पासवर्ड ("p@s$") के साथ AES एन्क्रिप्शन लागू करने के लिए।

## चरण 4: पुरालेख प्रविष्टि बनाएँ और सहेजें

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

इस अंतिम चरण में "alice29.txt" के लिए संग्रह में एक प्रविष्टि बनाना और संग्रह को सहेजना, फ़ाइल को संपीड़न के बिना और पासवर्ड सुरक्षा के साथ संग्रहीत करने की प्रक्रिया को पूरा करना शामिल है।

मुख्य बिंदुओं को सारांशित करके और पाठकों को .NET के लिए Aspose.Zip के साथ आगे की संभावनाएं तलाशने के लिए प्रोत्साहित करके अपने ट्यूटोरियल का समापन करें।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.Zip का उपयोग कैसे करें ताकि कई फ़ाइलों को बिना संपीड़न के संग्रहीत किया जा सके और उन्हें पासवर्ड से सुरक्षित किया जा सके। जैसे ही आप .NET विकास के साथ अपनी यात्रा जारी रखते हैं, फ़ाइल प्रबंधन कार्यों को सुव्यवस्थित करने और अपने अनुप्रयोगों की सुरक्षा बढ़ाने के लिए Aspose.Zip की क्षमताओं का लाभ उठाएं।

---

### पूछे जाने वाले प्रश्न

### क्या मैं अन्य एन्क्रिप्शन विधियों के साथ .NET के लिए Aspose.Zip का उपयोग कर सकता हूँ?
 हाँ, Aspose.Zip विभिन्न एन्क्रिप्शन विधियों का समर्थन करता है। दस्तावेज़ीकरण की जाँच करें[यहाँ](https://reference.aspose.com/zip/net/) जानकारी के लिए।

### मुझे .NET के लिए Aspose.Zip के लिए समर्थन कहाँ से मिल सकता है?
 दौरा करना[Aspose.ज़िप फोरम](https://forum.aspose.com/c/zip/37) सामुदायिक समर्थन और चर्चा के लिए।

### क्या .NET के लिए Aspose.Zip का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### मैं .NET के लिए Aspose.Zip के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 अस्थायी लाइसेंस का अनुरोध करें[यहाँ](https://purchase.aspose.com/temporary-license/).

### मैं .NET के लिए Aspose.Zip कहां से खरीद सकता हूं?
 आप .NET के लिए Aspose.Zip खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
