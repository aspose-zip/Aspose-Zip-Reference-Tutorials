---
date: 2025-12-09
description: Aspose.Zip for .NET kullanarak dizini nasıl sıkıştıracağınızı ve .NET’te
  zip arşivi verimli bir şekilde nasıl oluşturacağınızı öğrenin. .NET uygulamalarınızda
  depolama alanını optimize edin.
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET Kullanarak Dizin Nasıl Sıkıştırılır
url: /tr/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zorluksuz Dizin Sıkıştırma Aspose.Zip for .NET ile

Bu öğreticide, Aspose.Zip for .NET kullanarak **dizini nasıl sıkıştıracağınızı** göstereceğiz, büyük veri setlerini yönetmenin ve depolama alanı tasarrufu sağlamanın güçlü bir yolu. İster bir masaüstü yardımcı programı ister bulut tabanlı bir hizmet geliştiriyor olun, klasörleri verimli bir şekilde sıkıştırmak performansı büyük ölçüde artırabilir ve maliyetleri azaltabilir. Her adımı ayrıntılı olarak inceleyecek, kodun arkasındaki mantığı açıklayacak ve yaygın tuzakları göstereceğiz, böylece tekniği güvenle uygulayabilirsiniz.

## Quick Answers
- **Aspose.Zip ne yapar?** Harici bağımlılıklar olmadan ZIP arşivleri oluşturmak ve çıkarmak için basit bir .NET API'si sağlar.  
- **Uygulama ne kadar sürer?** Temel bir dizin sıkıştırması için genellikle 10 dakikadan az sürer.  
- **Hangi .NET sürümleri desteklenir?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Üretim için lisansa ihtiyacım var mı?** Evet, üretim kullanımında ticari bir lisans gereklidir.  
- **Birden fazla klasörü aynı anda sıkıştırabilir miyim?** Kesinlikle—herhangi bir `DirectoryInfo` koleksiyonunda `CreateEntries` metodunu kullanın.

## Introduction

Aspose.Zip for .NET, .NET geliştiricilerinin sıkıştırılmış dosyalar ve dizinlerle sorunsuz çalışmasını sağlayan güçlü bir kütüphanedir. Büyük veri setleriyle uğraşıyor olun ya da **generate zip file c#**‑stil arşivler oluşturmanız gerekse, Aspose.Zip sıkıştırma ve açma görevleri için sağlam bir özellik seti sunar.

## What is “how to compress directory”?

Bir dizini sıkıştırmak, belirli bir klasör içindeki tüm dosya ve alt‑klasörleri alıp tek bir ZIP arşivine paketlemek anlamına gelir. Bu, toplam boyutu azaltır, aktarımı basitleştirir ve orijinal klasör hiyerarşisini korur.

## Why use Aspose.Zip for this task?

- **Hız ve Verimlilik:** Optimize edilmiş algoritmalar büyük klasörleri hızlı bir şekilde işler.  
- **Saf .NET:** Yerel ikili dosyalar veya üçüncü‑taraf araçları gerekmez.  
- **Zengin Özellik Seti:** Şifre koruması, akış ve anlık giriş eklemeyi destekler—**zip multiple files .net** senaryoları için mükemmeldir.  
- **Tutarlı API:** .NET Framework, .NET Core ve .NET 5/6 arasında aynı şekilde çalışır.

## Prerequisites

- **Aspose.Zip for .NET** – indirmek için [buraya](https://releases.aspose.com/zip/net/) tıklayın.  
- **Geliştirme Ortamı** – Visual Studio, Rider veya C# destekleyen herhangi bir IDE.  
- **Belge Dizini** – kodda `"Your Document Directory"` ifadesini sıkıştırmak istediğiniz klasörün yolu ile değiştirin.  
- **Referans Dokümantasyonu** – resmi dokümantasyona [buradan](https://reference.aspose.com/zip/net/) bakın.

## Import Namespaces

Gerekli ad alanlarını içe aktararak başlayın. Bunlar, temel sıkıştırma sınıflarına erişim sağlar.

```csharp
using Aspose.Zip;
using System.IO;
```

## How to Zip Folder with Aspose.Zip

Aşağıda, **how to zip folder** içeriğini gösteren basit bir örnek bulunmaktadır. Aynı desen **zip multiple files .net** için genişletilebilir veya özel arşiv yapıları oluşturmak için kullanılabilir.

### Step 1: Initialize Your Document Directory

`dataDir` değişkenini sıkıştırmak istediğiniz dizinin yolu olarak ayarlayın.

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create Output Zip Files

Çıktı ZIP dosyaları için iki `FileStream` nesnesi açın. Bu, aynı kaynaktan birden fazla arşiv oluşturabileceğinizi gösterir—sürüm yedeklemeleri için kullanışlıdır.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Step 3: Compress the Directory

Hedef klasörden her bir girişi eklemek için `Archive` sınıfını kullanın. Örnek, **CanterburyCorpus** adlı bir örnek klasör kullanıyor, ancak istediğiniz herhangi bir dizine yönlendirebilirsiniz.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Pro ipucu:** Belirli bir sıkıştırma seviyesine sahip **create zip archive .net** oluşturmanız gerekiyorsa, `Save` metodunu çağırmadan önce `archive.CompressionLevel` değerini ayarlayın.

## Common Issues and Solutions

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| Boş ZIP dosyası | `dataDir` yanlış klasöre işaret ediyor veya son slash eksik | Yolu doğrulayın ve klasörün dosya içerdiğinden emin olun |
| `UnauthorizedAccessException` | Uygulamanın dosya sistemi izinleri yok | Visual Studio'yu yönetici olarak çalıştırın veya okuma/yazma izinleri verin |
| Büyük dizinlerde yüksek bellek kullanımı | Tüm girişleri bir anda belleğe yüklemek | Dosyaları tek tek akıtmak için bir döngüde `Archive.CreateEntryFromFile` kullanın |

## Frequently Asked Questions (Additional)

**S: ZIP arşivine şifre ekleyebilir miyim?**  
C: Evet. `Save` metodunu çağırmadan önce `archive.Password = "yourPassword";` ayarlayın.

**S: Yalnızca belirli dosya türlerini nasıl dahil ederim?**  
C: `CreateEntries` metodunu çağırmadan önce `DirectoryInfo` koleksiyonunu `GetFiles("*.txt")` gibi bir filtreyle daraltın.

**S: Mevcut bir ZIP'i yeniden oluşturmadan güncellemenin bir yolu var mı?**  
C: Aspose.Zip, `Archive.UpdateEntry` aracılığıyla artımlı güncellemeleri destekler.

## FAQ's

### S1: Aspose.Zip for .NET'i hem ticari hem de kişisel projelerde kullanabilir miyim?

C1: Evet, Aspose.Zip for .NET hem ticari hem de kişisel kullanım için lisanslanmıştır.

### S2: Ücretsiz deneme mevcut mu?

C2: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/zip/net) keşfedebilirsiniz.

### S3: Aspose.Zip for .NET için destek nasıl alabilirim?

C3: Topluluk desteği için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin veya özel yardım için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) satın almayı düşünün.

### S4: Başka örnekler ve öğreticiler mevcut mu?

C4: Evet, [dokümantasyon](https://reference.aspose.com/zip/net/) kapsamlı örnekler ve öğreticiler içerir.

### S5: Aspose.Zip for .NET'i satın alabilir miyim?

C5: Elbette, satın alımınızı [buradan](https://purchase.aspose.com/buy) gerçekleştirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose