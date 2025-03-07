---
title: अपनी फ़ाइलें सुरक्षित करें - Aspose.Zip के साथ AES एन्क्रिप्शन
linktitle: एईएस के साथ पासवर्ड सुरक्षित रखें
second_title: फ़ाइलें संपीड़न और संग्रहण के लिए Aspose.Zip .NET API
description: AES एन्क्रिप्शन के साथ .NET के लिए Aspose.Zip का उपयोग करके अपनी फ़ाइल सुरक्षा को बढ़ाने का तरीका जानें। सर्वोत्तम सुरक्षा के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# अपनी फ़ाइलें सुरक्षित करें - Aspose.Zip के साथ AES एन्क्रिप्शन


## परिचय

आज के डिजिटल युग में आपकी संवेदनशील फ़ाइलों को सुरक्षित रखना महत्वपूर्ण है, और .NET के लिए Aspose.Zip उन्नत एन्क्रिप्शन स्टैंडर्ड (एईएस) का उपयोग करके आपके अभिलेखागार को पासवर्ड से सुरक्षित रखने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि आपकी संपीड़ित फ़ाइलों के लिए उच्चतम स्तर की सुरक्षा सुनिश्चित करते हुए तीन प्रमुख लंबाई - 128-बिट, 192-बिट और 256-बिट के साथ एईएस एन्क्रिप्शन कैसे लागू किया जाए।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Zip: सुनिश्चित करें कि आपके पास Aspose.Zip लाइब्रेरी आपके .NET प्रोजेक्ट में एकीकृत है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/zip/net/).

- दस्तावेज़ निर्देशिका: एक निर्देशिका रखें जहाँ आपकी स्रोत फ़ाइलें स्थित हैं।

## नामस्थान आयात करें

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## चरण 1: एईएस-128 के साथ पासवर्ड सुरक्षित रखें

```csharp
//एक्सस्टार्ट: पासवर्डप्रोटेक्टविथएईएस128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: पासवर्डप्रोटेक्टविथएईएस128
```

इस चरण में, हम एक ज़िप फ़ाइल बनाते हैं और इसे AES-128 एन्क्रिप्शन के साथ सुरक्षित करते हैं। पासवर्ड "p@s$" आपके संग्रह की सुरक्षा सुनिश्चित करता है।

## चरण 2: AES-192 के साथ पासवर्ड सुरक्षित रखें

```csharp
//एक्सस्टार्ट: पासवर्डप्रोटेक्टविथएईएस192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: पासवर्डप्रोटेक्टविथएईएस192
```

यह चरण दर्शाता है कि उन्नत सुरक्षा के लिए AES-192 एन्क्रिप्शन को कैसे लागू किया जाए। एकरूपता के लिए समान पासवर्ड "p@s$" का उपयोग किया जाता है।

## चरण 3: AES-256 के साथ पासवर्ड सुरक्षित रखें

```csharp
//एक्सस्टार्ट: पासवर्डप्रोटेक्टविथएईएस256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: पासवर्डप्रोटेक्टविथएईएस256
```

इस अंतिम चरण में, हम उच्चतम स्तर के एन्क्रिप्शन, AES-256 को लागू करते हैं, जो आपकी संपीड़ित फ़ाइलों के लिए सुरक्षा की एक अतिरिक्त परत प्रदान करता है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Zip में AES एन्क्रिप्शन का उपयोग करके आपके अभिलेखागार को पासवर्ड से सुरक्षित करने के लिए आवश्यक चरणों को शामिल किया है। चाहे आप 128-बिट, 192-बिट, या 256-बिट एन्क्रिप्शन चुनें, आपकी फ़ाइलें अनधिकृत पहुंच से सुरक्षित रहेंगी।

## अक्सर पूछे जाने वाले प्रश्नों

### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Zip का उपयोग कर सकता हूँ?
Aspose.Zip मुख्य रूप से .NET अनुप्रयोगों के लिए डिज़ाइन किया गया है, जो निर्बाध एकीकरण और इष्टतम प्रदर्शन सुनिश्चित करता है।

### क्या एईएस एन्क्रिप्शन विधि संवेदनशील डेटा के लिए सुरक्षित है?
हां, संवेदनशील जानकारी की सुरक्षा के लिए एईएस एन्क्रिप्शन को एक सुरक्षित और मजबूत विधि के रूप में व्यापक रूप से मान्यता प्राप्त है।

### क्या मैं पहले से एन्क्रिप्टेड संग्रह के लिए पासवर्ड बदल सकता हूँ?
नहीं, एन्क्रिप्टेड संग्रह का पासवर्ड एक बार सेट हो जाने के बाद बदला नहीं जा सकता। आपको एक अलग पासवर्ड के साथ एक नया एन्क्रिप्टेड संग्रह बनाना होगा।

### क्या फ़ाइल प्रकारों पर कोई सीमाएँ हैं जिन्हें Aspose.Zip का उपयोग करके एन्क्रिप्ट किया जा सकता है?
Aspose.Zip विभिन्न प्रकार के डेटा को सुरक्षित करने में लचीलापन सुनिश्चित करते हुए, विभिन्न फ़ाइल प्रकारों के एन्क्रिप्शन का समर्थन करता है।

### यदि मैं एन्क्रिप्टेड संग्रह का पासवर्ड भूल जाऊं तो क्या होगा?
दुर्भाग्य से, एन्क्रिप्टेड संग्रह के पासवर्ड को पुनर्प्राप्त करने का कोई तरीका नहीं है। पासवर्ड को सुरक्षित स्थान पर रखना महत्वपूर्ण है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
