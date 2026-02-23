---
date: 2026-02-23
description: Aspose.Zip kullanarak .NET’te dosyaları tar arşivine eklemeyi ve dosyaları
  tarxz arşivine sıkıştırmayı öğrenin. Verimli depolama ve aktarım için bu adım adım
  rehberi izleyin.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dosyaları tar'a ekleyin ve Aspose.Zip ile tarxz arşivi oluşturun
url: /tr/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

. So table headers also translate. Keep pipe separators.

But need to keep content inside code snippets (like `TarArchive`) unchanged.

Also translate bullet points.

Let's translate.

I'll write Turkish.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip ile tar dosyasına dosya ekleme ve tarxz arşivi oluşturma

## Giriş

**tar dosyasına dosya eklemeniz** ve ardından **.net için tarxz arşivi oluşturmanız** gerektiğinde, Aspose.Zip for .NET bu süreci basit ve güvenilir hâle getirir. Günlük dosyaları, yapılandırma dosyalarını veya depolama ya da aktarım için paketlemek istediğiniz diğer varlıkları sıkıştırırken, TarXz formatı yüksek sıkıştırma oranı sunar ve tanıdık tar yapısını korur. Bu öğreticide, kod parçacıklarıyla birlikte tam adımları gösterecek ve .NET uygulamalarınıza tarxz oluşturmayı güvenle entegre edebileceksiniz.

## Hızlı Yanıtlar
- **Ana sınıf hangisi?** `TarArchive` (`Aspose.Zip.Tar` içinde)
- **tarxz nasıl sıkıştırılır?** Girişleri ekledikten sonra `SaveXzCompressed` kullanın
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Lisans gerekli mi?** Evet, üretim için geçerli bir Aspose.Zip lisansı
- **Tipik uygulama süresi?** ~5‑10 dakika

## TarXz arşivi nedir?

**TarXz arşivi**, geleneksel Unix `tar` kapsayıcısını XZ sıkıştırmasıyla birleştirir. tar bölümü birden çok dosyayı tek bir akışta toplar, XZ ise güçlü, kayıpsız sıkıştırma sağlar. Bu format, dizin yapısını koruması ve düz tar ya da zip’e göre daha küçük dosya boyutları elde etmesi nedeniyle kaynak kodu, yedeklemeler ve büyük veri setleri dağıtımında popülerdir.

## Aspose.Zip ile .net için tarxz arşivi oluşturmanın avantajları

- **Yüksek sıkıştırma oranı** – XZ, gzip’e göre %30‑50 daha küçük dosyalar üretebilir.  
- **Çapraz platform uyumluluğu** – TarXz dosyaları Linux, macOS ve Windows’ta açılabilir.  
- **Basit API** – Aspose.Zip düşük‑seviye detayları soyutlayarak iş mantığınıza odaklanmanızı sağlar.  
- **Harici araç gerektirmez** – Her şey .NET süreciniz içinde çalışır, bulut ya da CI boru hatları için idealdir.

## Önkoşullar

Başlamadan önce şunların kurulu olduğundan emin olun:

- **Aspose.Zip for .NET** yüklü (resmi [Aspose.Zip belgeleri](https://reference.aspose.com/zip/net/) üzerinden indirilebilir).  
- Arşivlemek istediğiniz dosyaları içeren bir klasör. Aşağıdaki örneklerde bu klasör `dataDir` değişkeniyle gösterilmiştir.  
- Geçerli bir Aspose.Zip lisansı (değerlendirme için isteğe bağlı, üretim için zorunlu).

## Ad Alanlarını İçe Aktarma

TarXz işlevselliğini ortaya çıkaran ad alanlarını içe aktarın.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Aspose.Zip ile tar dosyasına dosya ekleme

Aşağıda **tar dosyasına dosya ekleme** adımlarını tam olarak gösteren bir rehber bulacaksınız.

### Adım 1: `TarArchive` nesnesini başlatma

Sıkıştırmak istediğiniz dosyaları tutacak yeni bir `TarArchive` örneği oluşturun.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **İpucu:** `using` ifadesi arşivin doğru şekilde disposed edilmesini sağlar, böylece yönetilmeyen kaynaklar serbest bırakılır.

### Adım 2: Dosyaları Arşive Ekleme

Eklemek istediğiniz her dosyayı ekleyin. Bu örnekte iki metin dosyası ekleniyor, ancak ihtiyacınız kadar giriş ekleyebilirsiniz.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Neden Önemli:** Sıkıştırmadan önce girişleri eklemek, Aspose.Zip’in önce tar kapsayıcısını oluşturup ardından XZ sıkıştırmasını tek adımda uygulamasını sağlar.

### Adım 3: XZ Sıkıştırmasıyla Arşivi Kaydetme

Son olarak, XZ sıkıştırmasıyla tar arşivini diske yazın. Oluşan dosyanın uzantısı `.tar.xz` olacaktır.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Sonuç:** Artık herhangi bir platformda TarXz destekleyen sistemlerde aktarılabilir, depolanabilir veya açılabilir bir `archive.tar.xz` dosyanız var.

## Aspose.Zip ile tarxz dosyalarını sıkıştırma

Yukarıdaki süreç, **tarxz dosyalarını sıkıştırma** yönteminin temelidir: önce dosyaları bir tar konteynerine (`add files to tar`) ekler, ardından `SaveXzCompressed` çağrısını yaparsınız. Bu tek‑çağrı yaklaşımı harici komut satırı araçlarına ihtiyaç duymadan her şeyi .NET kod tabanınız içinde tutar.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-------|
| **“File not found” istisnası** | Yanlış `dataDir` yolu | Dizin yolunun ters eğik çizgi (`\`) ile bittiğini doğrulayın veya `Path.Combine` kullanın. |
| **Büyük bellek kullanımı** | Çok büyük dosyaların bellekte sıkıştırılması | `TarArchive`’i akış modunda kullanın (`SaveXzCompressed`’in `Stream` kabul eden aşırı yüklemesi). |
| **Lisans uygulanmadı** | Lisans dosyasının eksik olması | Uygulama başlangıcında lisansı yükleyin: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Sık Sorulan Sorular

**S: Aspose.Zip tüm .NET ortamlarıyla uyumlu mu?**  
C: Evet, Aspose.Zip .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6+ ile çalışır. Ayrıntılar için [belgelere](https://reference.aspose.com/zip/net/) bakın.

**S: Aspose.Zip için geçici bir lisans nasıl alınır?**  
C: [Aspose geçici‑lisans sayfasından](https://purchase.aspose.com/temporary-license/) geçici lisans talep edebilirsiniz.

**S: Diğer arşiv formatları için ek örnekler var mı?**  
C: Kesinlikle—tam örnek setine [Aspose.Zip API referansından](https://reference.aspose.com/zip/net/) ulaşabilirsiniz.

**S: Yardım almak ya da sorunları tartışmak için nereden ulaşabilirim?**  
C: Topluluk desteği ve resmi yanıtlar için [Aspose.Zip forumuna](https://forum.aspose.com/c/zip/37) katılabilirsiniz.

**S: Aspose.Zip’i satın almadan ücretsiz denemek mümkün mü?**  
C: Evet, ücretsiz deneme sürümü [Aspose.Zip indirme sayfasında](https://releases.aspose.com/zip/net) mevcuttur.

## Sonuç

Yukarıdaki adımları izleyerek **tar dosyasına dosya ekleme**, **tarxz sıkıştırma** ve daha da önemlisi **Aspose.Zip kullanarak .net için tarxz arşivi oluşturma** konularında bilgi sahibi oldunuz. Bu yöntem, masaüstü yardımcı programları, web servisleri veya otomatik CI/CD boru hatları gibi herhangi bir .NET iş akışına sorunsuz bir şekilde entegre edilebilen kompakt ve taşınabilir bir paket sunar.

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen Sürüm:** Aspose.Zip for .NET 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}