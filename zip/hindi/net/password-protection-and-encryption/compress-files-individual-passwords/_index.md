---
title: Aspose.Zip के साथ .NET में सुरक्षित फ़ाइल संपीड़न
linktitle: व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करें
second_title: फ़ाइलें संपीड़न और संग्रहण के लिए Aspose.Zip .NET API
description: जानें कि .NET अनुप्रयोगों में फ़ाइल सुरक्षा कैसे बढ़ाएं! .NET के लिए Aspose.Zip का उपयोग करके व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करने पर हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 16
url: /hi/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## परिचय

.NET विकास की दुनिया में, फ़ाइलों को कुशलतापूर्वक प्रबंधित करना और संपीड़ित करना एक महत्वपूर्ण कार्य है। .NET के लिए Aspose.Zip फ़ाइल संपीड़न के लिए एक शक्तिशाली समाधान प्रदान करता है, जो आपके अनुप्रयोगों को बढ़ाने के लिए विभिन्न सुविधाएँ प्रदान करता है। एक उल्लेखनीय विशेषता व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करने की क्षमता है, जो सुरक्षा की एक अतिरिक्त परत प्रदान करती है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Zip का उपयोग करके व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करने की प्रक्रिया के बारे में मार्गदर्शन करेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

-  .NET के लिए Aspose.Zip: सुनिश्चित करें कि आपके .NET प्रोजेक्ट में Aspose.Zip लाइब्रेरी स्थापित है। आप आवश्यक दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/zip/net/).

-  डाउनलोड: यदि आपने पहले से नहीं किया है, तो .NET लाइब्रेरी के लिए Aspose.Zip डाउनलोड करें[इस लिंक](https://releases.aspose.com/zip/net/).

- दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जिसमें वे फ़ाइलें हों जिन्हें आप संपीड़ित करना चाहते हैं।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## चरण 1: संसाधन निर्देशिका पथ सेट करें

उस संसाधन निर्देशिका का पथ परिभाषित करें जहाँ आपकी फ़ाइलें स्थित हैं।

```csharp
string dataDir = "Your Document Directory";
```

## चरण 2: व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करें

अब, आइए अलग-अलग पासवर्ड के साथ फ़ाइलों को संपीड़ित करें। हम तीन नमूना फ़ाइलों का उपयोग करेंगे (`alice29.txt`, `asyoulik.txt` , और`fields.c`) प्रत्येक के लिए अलग-अलग पासवर्ड के साथ।

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // प्रत्येक फ़ाइल को एक व्यक्तिगत पासवर्ड से संपीड़ित करें
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // संपीड़ित फ़ाइलें सहेजें
        archive.Save(zipFile);
    }
}
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Zip का उपयोग करके व्यक्तिगत पासवर्ड के साथ फ़ाइलों को संपीड़ित करना सफलतापूर्वक सीख लिया है। यह सुविधा गोपनीयता सुनिश्चित करते हुए आपकी संपीड़ित फ़ाइलों में सुरक्षा की एक अतिरिक्त परत जोड़ती है।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### क्या मैं प्रत्येक फ़ाइल के लिए भिन्न एन्क्रिप्शन विधियों का उपयोग कर सकता हूँ?
हाँ, .NET के लिए Aspose.Zip आपको संपीड़न के दौरान प्रत्येक फ़ाइल के लिए विभिन्न एन्क्रिप्शन विधियों का उपयोग करने की अनुमति देता है।

### क्या कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप .NET के लिए Aspose.Zip के निःशुल्क परीक्षण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).

### यदि मुझे कोई समस्या आती है तो मुझे सहायता कैसे मिल सकती है?
 दौरा करना[Aspose.ज़िप फोरम](https://forum.aspose.com/c/zip/37) समुदाय से सहायता और Aspose समर्थन के लिए।

### मुझे .NET के लिए Aspose.Zip के लिए विस्तृत दस्तावेज़ कहाँ मिल सकते हैं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/zip/net/).

### क्या मैं परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
