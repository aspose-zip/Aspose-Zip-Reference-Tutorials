---
title: .NET के लिए Aspose.Zip में FileInfo का उपयोग करके फ़ाइलों को संपीड़ित करें
linktitle: FileInfo का उपयोग करके फ़ाइलों को संपीड़ित करें
second_title: फ़ाइलें संपीड़न और संग्रहण के लिए Aspose.Zip .NET API
description: .NET के लिए Aspose.Zip के साथ फ़ाइलइन्फो का उपयोग करके फ़ाइलों को संपीड़ित करना सीखें। कुशल फ़ाइल प्रबंधन के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/file-compression/compress-files-fileinfo/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Zip में FileInfo का उपयोग करके फ़ाइलों को संपीड़ित करें

## परिचय

.NET के लिए Aspose.Zip का उपयोग करके फ़ाइलों को संपीड़ित करने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है! यदि आप अपने फ़ाइल भंडारण या ट्रांसमिशन को अनुकूलित करना चाह रहे हैं, तो Aspose.Zip आपके लिए उपयुक्त समाधान है। इस ट्यूटोरियल में, हम आपको विस्तृत चरण-दर-चरण मार्गदर्शिका प्रदान करते हुए, FileInfo क्लास का उपयोग करके फ़ाइलों को संपीड़ित करने की प्रक्रिया के बारे में बताएंगे। आइए गोता लगाएँ!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET के लिए Aspose.Zip: सुनिश्चित करें कि आपके पास Aspose.Zip लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/zip/net/).

2. दस्तावेज़ निर्देशिका: जिन फ़ाइलों को आप संपीड़ित करना चाहते हैं उन्हें संग्रहीत करने के लिए अपने सिस्टम पर एक निर्देशिका सेट करें।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, आवश्यक नामस्थान शामिल करें:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें

सबसे पहली बात, उस निर्देशिका को परिभाषित करें जहां आपके दस्तावेज़ संग्रहीत हैं। आप निम्न कोड का उपयोग कर सकते हैं:

```csharp
string dataDir = "Your Document Directory";
```

## चरण 2: FileInfo का उपयोग करके फ़ाइलों को संपीड़ित करें

 अब, आइए प्रक्रिया के मूल में आते हैं। हम उपयोग करेंगे`FileInfo` फ़ाइलों को संपीड़ित करने के लिए Aspose.Zip के साथ क्लास। इन चरणों का पालन करें:

### चरण 2.1: एक ज़िप फ़ाइल खोलें

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### चरण 2.2: फाइलइन्फो ऑब्जेक्ट बनाएं

 बनाएं`FileInfo` उन फ़ाइलों के लिए ऑब्जेक्ट जिन्हें आप संपीड़ित करना चाहते हैं:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### चरण 2.3: पुरालेख बनाएं और प्रविष्टियाँ जोड़ें

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### चरण 2.4: ज़िप फ़ाइल सहेजें

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

बधाई हो! आपने .NET के लिए Aspose.Zip में FileInfo क्लास का उपयोग करके फ़ाइलों को सफलतापूर्वक संपीड़ित कर लिया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि .NET के लिए Aspose.Zip का उपयोग करके फ़ाइलों को कुशलतापूर्वक कैसे संपीड़ित किया जाए। इन चरणों का पालन करके, आप अपनी फ़ाइल प्रबंधन क्षमताओं को बढ़ा सकते हैं और स्थान उपयोग को अनुकूलित कर सकते हैं। Aspose.Zip की पूरी क्षमता का अनुभव करने के लिए विभिन्न फ़ाइल प्रकारों और आकारों के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Zip सभी फ़ाइल प्रकारों के साथ संगत है?

A1: Aspose.Zip संपीड़न में बहुमुखी प्रतिभा सुनिश्चित करते हुए, फ़ाइल प्रकारों की एक विस्तृत श्रृंखला का समर्थन करता है।

### Q2: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Zip का उपयोग कर सकता हूँ?

 ए2: बिल्कुल! हमारी यात्रा[खरीद पृष्ठ](https://purchase.aspose.com/buy) लाइसेंसिंग विकल्पों का पता लगाने के लिए।

### Q3: मैं Aspose.Zip के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A3: हमारे समुदाय में शामिल हों[Aspose.ज़िप फोरम](https://forum.aspose.com/c/zip/37) सहायता और चर्चा के लिए.

### Q4: क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 A4: हाँ, आप अपना ले सकते हैं[यहां नि:शुल्क परीक्षण](https://releases.aspose.com/).

### Q5: मैं Aspose.Zip के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए5: विजिट करें[इस लिंक](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने की जानकारी के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
