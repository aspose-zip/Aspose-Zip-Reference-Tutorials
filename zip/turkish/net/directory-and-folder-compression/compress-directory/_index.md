---
date: 2026-02-12
description: Aspose.Zip for .NET ile klasörleri nasıl zipleyeceğinizi öğrenin, .NET’te
  zip arşivi verimli bir şekilde oluşturun ve .NET uygulamalarınızda depolama alanını
  azaltın.
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET Kullanarak Klasörü Zipleme
url: /tr/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET Kullanarak Klasör Nasıl Sıkıştırılır

Bu öğreticide, Aspose.Zip for .NET ile **klasör nasıl sıkıştırılır** hızlı ve güvenilir bir şekilde öğreneceksiniz. İster bir masaüstü yardımcı programı, ister bulut tabanlı bir hizmet, ister otomatik bir yedekleme betiği oluşturuyor olun, bir klasörü ZIP arşivine sıkıştırmak depolama gereksinimlerini büyük ölçüde azaltabilir ve ağ transferlerini hızlandırabilir. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve yaygın tuzakları vurgulayacağız, böylece tekniği güvenle uygulayabilirsiniz.

## Hızlı Yanıtlar
- **Aspose.Zip ne yapar?** Harici bağımlılıklar olmadan ZIP arşivleri oluşturmak ve çıkarmak için basit bir .NET API'si sağlar.  
- **Uygulama ne kadar sürer?** Temel bir klasör sıkıştırması için genellikle 10 dakikadan az sürer.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+ ve .NET 5/6+.  
- **Üretim için lisans gerekir mi?** Evet, üretim kullanımında ticari bir lisans gereklidir.  
- **Birden fazla klasörü aynı anda sıkıştırabilir miyim?** Kesinlikle—herhangi bir `DirectoryInfo` koleksiyonunda `CreateEntries` metodunu kullanarak tek bir çalıştırmada **birden fazla klasörü sıkıştırabilirsiniz**.

## “klasör nasıl sıkıştırılır” nedir?

Bir klasörü sıkıştırmak, belirli bir dizindeki tüm dosya ve alt‑klasörleri alıp tek bir ZIP arşivine paketlemek anlamına gelir. Bu, toplam boyutu azaltır, orijinal hiyerarşiyi korur ve veriyi aktarımı veya depolamayı kolaylaştırır.

## Neden Aspose.Zip'i bu görev için kullanmalısınız?

- **Hız ve Verimlilik:** Optimize edilmiş algoritmalar büyük klasörleri hızlı bir şekilde işler.  
- **Saf .NET:** Yerel ikili dosyalar veya üçüncü‑taraf araçlar gerekmez.  
- **Zengin Özellik Seti:** Şifre korumasını (`add password zip`), akış işlemlerini ve özel bir sıkıştırma seviyesi ayarlamayı (`set compression level`) destekler.  
- **Tutarlı API:** .NET Framework, .NET Core ve .NET 5/6 arasında aynı şekilde çalışır, bu da **create zip archive .net** senaryoları için idealdir.  

## Önkoşullar

- **Aspose.Zip for .NET** – bunu [buradan](https://releases.aspose.com/zip/net/) indirin.  
- **Geliştirme Ortamı** – Visual Studio, Rider veya C# destekleyen herhangi bir IDE.  
- **Belge Dizini** – kodda `"Your Document Directory"` ifadesini sıkıştırmak istediğiniz klasörün yolu ile değiştirin.  
- **Referans Dokümantasyonu** – resmi belgeleri [buradan](https://reference.aspose.com/zip/net/) inceleyin.

## Ad Alanlarını İçe Aktarın

Gerekli ad alanlarını içe aktararak başlayın. Bunlar, temel sıkıştırma sınıflarına erişmenizi sağlar.

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip ile Klasör Nasıl Sıkıştırılır

Aşağıda, **klasör nasıl sıkıştırılır** içeriğini gösteren basit bir örnek bulunmaktadır. Aynı desen **zip multiple files .net** için genişletilebilir veya özel arşiv yapıları oluşturmak için kullanılabilir.

### Adım 1: Belge Dizinini Başlatın

`dataDir` değişkenini sıkıştırmak istediğiniz dizinin yolu olarak ayarlayın.

```csharp
string dataDir = "Your Document Directory";
```

### Adım 2: Çıktı ZIP Dosyalarını Oluşturun

Çıktı ZIP dosyaları için iki `FileStream` nesnesi açın. Bu, aynı kaynaktan birden fazla arşiv oluşturabileceğinizi gösterir—sürümleme yedeklemeleri için faydalıdır.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Adım 3: Dizini Sıkıştırın

Hedef klasörden her bir girdiyi eklemek için `Archive` sınıfını kullanın. Örnek, **CanterburyCorpus** adlı bir örnek klasör kullanıyor, ancak istediğiniz herhangi bir dizine yönlendirebilirsiniz.

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

> **Pro ipucu:** Belirli bir sıkıştırma seviyesiyle **create zip archive .net** oluşturmanız gerekiyorsa, `Save` metodunu çağırmadan önce `archive.CompressionLevel` değerini ayarlayın.

## Yaygın Sorunlar ve Çözümleri

| Semptom | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| Boş ZIP dosyası | `dataDir` yanlış klasöre işaret ediyor veya son slash eksik | Yolu doğrulayın ve klasörün dosya içerdiğinden emin olun |
| `UnauthorizedAccessException` | Uygulamanın dosya sistemi izinleri yok | Visual Studio'yu yönetici olarak çalıştırın veya okuma/yazma izinleri verin |
| Büyük dizinler için yüksek bellek kullanımı | Tüm girdileri bir anda belleğe yüklemek | `Archive.CreateEntryFromFile` metodunu bir döngü içinde kullanarak dosyaları tek tek akışa alın |

## Sıkça Sorulan Sorular (Ek)

**S: ZIP arşivine şifre ekleyebilir miyim?**  
C: Evet. `Save` metodunu çağırmadan önce `archive.Password = "yourPassword";` olarak ayarlayın.

**S: Yalnızca belirli dosya türlerini nasıl dahil ederim?**  
C: `CreateEntries` metodunu çağırmadan önce `DirectoryInfo` koleksiyonunu `GetFiles("*.txt")` gibi bir filtreyle daraltın.

**S: Mevcut bir ZIP'i yeniden oluşturmadan güncellemenin bir yolu var mı?**  
C: Aspose.Zip, `Archive.UpdateEntry` aracılığıyla artımlı güncellemeleri destekler.

## SSS

### S1: Aspose.Zip for .NET'i hem ticari hem de kişisel projelerde kullanabilir miyim?

A1: Evet, Aspose.Zip for .NET hem ticari hem de kişisel kullanım için lisanslanmıştır.

### S2: Ücretsiz deneme mevcut mu?

A2: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/zip/net) keşfedebilirsiniz.

### S3: Aspose.Zip for .NET için destek nasıl alınır?

A3: Topluluk desteği için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin veya özel yardım için bir [geçici lisans](https://purchase.aspose.com/temporary-license/) satın almayı düşünün.

### S4: Başka örnekler ve öğreticiler mevcut mu?

A4: Evet, [dokümantasyon](https://reference.aspose.com/zip/net/) kapsamlı örnekler ve öğreticiler içerir.

### S5: Aspose.Zip for .NET'i satın alabilir miyim?

A5: Elbette, satın alımınızı [buradan](https://purchase.aspose.com/buy) gerçekleştirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-02-12  
**Test Edilen Versiyon:** Aspose.Zip 24.11 for .NET  
**Yazar:** Aspose