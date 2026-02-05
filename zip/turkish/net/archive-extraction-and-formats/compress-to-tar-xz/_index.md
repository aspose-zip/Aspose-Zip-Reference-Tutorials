---
date: 2026-02-05
description: Aspose.Zip kullanarak .NET’te dosyaları tar arşivine eklemeyi ve tarxz
  arşivleri oluşturmayı öğrenin. Bu rehber, dosyaları yüksek verimlilikle tarxz formatına
  sıkıştırmayı gösterir.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dosyaları tar'a ekle, Aspose.Zip ile .NET'te tarxz arşivi oluştur
url: /tr/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

 formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar dosyasına dosya ekleme ve .NET ile Aspise.Zip kullanarak tarxz arşivi oluşturma

## Giriş

Eğer **dosyaları tar'a ekleyip** ardından .NET kullanarak bir tarxz arşivine sıkıştırmanız gerekiyorsa, Aspose.Zip for .NET bu süreci basit ve güvenilir hâle getirir. Günlük dosyaları, yapılandırma dosyalarını veya depolama ya da aktarım için paketlemek istediğiniz diğer varlıkları paketlerken, TarXz formatına sıkıştırmak yüksek sıkıştırma oranı sağlar ve tanıdık tar yapısını korur. Bu öğreticide, kod parçacıklarıyla birlikte tam adımları göstereceğiz; böylece .NET uygulamalarınıza tarxz oluşturmayı güvenle entegre edebilirsiniz.

## Hızlı Yanıtlar
- **Birincil sınıf nedir?** `TarArchive` from `Aspose.Zip.Tar`
- **Tarxz nasıl sıkıştırılır?** `SaveXzCompressed` kullanarak girişleri ekledikten sonra
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Lisans gerekli mi?** Evet, üretim için geçerli bir Aspose.Zip lisansı gerekir
- **Tipik uygulama süresi?** ~5‑10 dakika

## TarXz arşivi nedir?

Bir **TarXz arşivi**, geleneksel Unix `tar` konteynerini XZ sıkıştırmasıyla birleştirir. Tar bölümü birden çok dosyayı tek bir akışta toplar, XZ ise güçlü, kayıpsız sıkıştırma sağlar. Bu format, dizin yapısını koruduğu ve düz tar ya da zip'ten daha küçük dosya boyutları elde ettiği için kaynak kod, yedekler ve büyük veri setleri dağıtımında popülerdir.

## Neden dosyaları tar'a ekleyip tarxz'ye sıkıştırmalısınız Aspose.Zip ile?

- **Yüksek sıkıştırma oranı** – XZ, gzip'ten %30‑%50 daha küçük sıkıştırma yapar.  
- **Çapraz platform uyumluluğu** – TarXz dosyaları Linux, macOS ve Windows'ta açılabilir.  
- **Basit API** – Aspose.Zip düşük seviyeli detayları soyutlayarak iş mantığınıza odaklanmanızı sağlar.  
- **Harici araç gerektirmez** – Her şey .NET süreciniz içinde çalışır, bulut ya da CI boru hatları için mükemmeldir.  

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

- **Aspose.Zip for .NET** yüklü (resmi [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) adresinden indirin).  
- Arşivlemek istediğiniz dosyaları içeren bir klasör. Aşağıdaki örneklerde bu klasör `dataDir` değişkeniyle referans verilir.  
- Geçerli bir Aspose.Zip lisansı (değerlendirme için isteğe bağlı, üretim için zorunlu).

## Namespace'leri İçe Aktarma

```csharp
using System;
using Aspose.Zip.Tar;
```

## Aspose.Zip kullanarak tar'a dosya ekleme

### Adım 1: Bir `TarArchive` Başlatma

Sıkıştırmak istediğiniz dosyaları tutacak yeni bir `TarArchive` örneği oluşturun.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tip:** `using` ifadesi arşivin doğru şekilde disposed edilmesini sağlar ve yönetilmeyen kaynakları serbest bırakır.

### Adım 2: Arşive Dosyalar Ekleme

Eklemek istediğiniz her dosyayı ekleyin. Bu örnekte iki metin dosyası ekliyoruz, ancak ihtiyacınız kadar giriş ekleyebilirsiniz.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Neden bu önemli:** Sıkıştırmadan önce girişleri eklemek, Aspose.Zip'in önce tar konteynerini oluşturup ardından tek bir adımda XZ sıkıştırması uygulamasını sağlar.

### Adım 3: XZ Sıkıştırmasıyla Arşivi Kaydetme

Son olarak, XZ sıkıştırmasıyla tar arşivini diske yazın. Oluşan dosyanın uzantısı `.tar.xz` olacaktır.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Sonuç:** Artık herhangi bir platformda TarXz destekleyen sistemlerde aktarılabilir, depolanabilir veya açılabilir tam sıkıştırılmış bir `archive.tar.xz` dosyanız var.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **“File not found” exception** | Yanlış `dataDir` yolu | Dizin yolunun ters eğik çizgi (`\`) ile bittiğini doğrulayın veya `Path.Combine` kullanın. |
| **Büyük bellek kullanımı** | Bellekte çok büyük dosyalar sıkıştırılıyor | `TarArchive`'ı akış modunda kullanın (`SaveXzCompressed` overload'ı bir `Stream` kabul eder). |
| **Lisans uygulanmadı** | Lisans dosyası eksik | Uygulama başlangıcında lisansı yükleyin: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Sıkça Sorulan Sorular

**S: Aspose.Zip tüm .NET ortamlarıyla uyumlu mu?**  
C: Evet, Aspose.Zip .NET Framework 4.5+, .NET Core 3.1+, ve .NET 5/6+ ile çalışır. Detaylar için [documentation](https://reference.aspose.com/zip/net/) sayfasına bakın.

**S: Aspose.Zip için geçici bir lisans nasıl alınır?**  
C: [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) üzerinden geçici bir lisans talep edebilirsiniz.

**S: Diğer arşiv formatları için ek örnekler var mı?**  
C: Kesinlikle—tam örnek setini [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) adresinde keşfedebilirsiniz.

**S: Yardım almak ya da sorunları tartışmak için nereden ulaşabilirim?**  
C: Topluluk desteği ve resmi yanıtlar için [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) sayfasına katılabilirsiniz.

**S: Satın almadan önce Aspose.Zip'i ücretsiz denemek mümkün mü?**  
C: Evet, ücretsiz deneme sürümünü [Aspose.Zip download page](https://releases.aspose.com/zip/net) adresinden edinebilirsiniz.

## Sonuç

Yukarıdaki adımları izleyerek **dosyaları tar'a eklemeyi** ve **Aspose.Zip kullanarak tarxz arşivleri oluşturmayı** öğrendiniz. Bu yaklaşım, masaüstü yardımcı programı, web servisi veya otomatik CI/CD boru hattı olsun, herhangi bir .NET iş akışına sorunsuz bir şekilde entegre edilebilen kompakt ve taşınabilir bir paket sunar.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}