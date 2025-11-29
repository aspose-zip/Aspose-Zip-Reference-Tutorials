---
date: 2025-11-29
description: Aspose.Zip for .NET kullanarak dosyaları tar arşivine eklemeyi ve TarZ
  olarak sıkıştırmayı öğrenin – verimli .NET dosya işleme için adım adım bir rehber.
language: tr
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dosyaları tar'a ekleyin ve Aspose.Zip for .NET ile TarZ olarak sıkıştırın
url: /net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar dosyalarına dosya ekleme ve TarZ olarak sıkıştırma Aspose.Zip for .NET ile

## Giriş

**Tar dosyalarına dosya ekleme** ve ardından arşivi TarZ formatına sıkıştırma ihtiyacınız varsa, Aspose.Zip for .NET tüm süreci sorunsuz hâle getirir. Bu öğreticide, projenizi kurmaktan bir tar arşivi oluşturmaya, dosyaları eklemeye ve son olarak sıkıştırılmış .tar.z dosyasını kaydetmeye kadar her adımı adım adım inceleyeceğiz. Sonunda, herhangi bir .NET uygulamasına ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Tar oluşturmayı hangi kütüphane yönetir?** Aspose.Zip for .NET  
- **Kaç satır kod?** Yaklaşık 15 satır (yorumlar hariç)  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim için lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Sadece dosyalar değil, klasörler de sıkıştırabilir miyim?** Evet – bir döngü ile tüm dizinleri ekleyebilirsiniz.

## **add files to tar** nedir?
Dosyaları bir tar arşivine eklemek, onları tek bir sıkıştırılmamış konteynerde birleştirir; bu konteyner dizin yapısını ve dosya meta verilerini korur. Tar, klasik bir Unix formatıdır ve bu kılavuzda kullanılan TarZ formatı dahil birçok sıkıştırma iş akışının temelini oluşturur.

## TarZ olarak sıkıştırmadan önce dosyaları tar’a eklemek neden gerekir?
- **Taşınabilirlik** – Bir tar arşivi, bireysel dosya işlemleriyle uğraşmadan platformlar arasında sorunsuz çalışır.  
- **Hız** – Tar konteynerinin oluşturulması hızlıdır; ardından gelen Z‑sıkıştırma sadece boyutu küçültmeye odaklanır.  
- **Uyumluluk** – Birçok eski araç, gzip‑stil sıkıştırma uygulanmadan önce bir `.tar` bekler; işte `.tar.z` tam da bunu sağlar.

## Ön Koşullar

Koda geçmeden önce şunların kurulu olduğundan emin olun:

- **Aspose.Zip for .NET** yüklü. Resmi siteden [buradan](https://releases.aspose.com/zip/net/) indirebilirsiniz.  
- Makinenizde arşivlemek istediğiniz dosyaları içeren bir klasör bulun. Yer tutucu yolu, gerçek dizininizle değiştirin.

## Ad Alanlarını İçe Aktarın

C# dosyanızın en üstüne gerekli `using` ifadelerini ekleyin:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Tanımlayın

```csharp
string dataDir = "Your Document Directory";
```

> **İpucu:** Dinamik olarak yol oluşturmanız gerekiyorsa `Path.Combine` kullanın; bu, farklı işletim sistemlerinde eksik yol ayırıcılarından kaçınmanızı sağlar.

### Adım 2: Bir Tar Arşivi Oluşturun ve dosyaları ekleyin

#### 2.1: Tar arşivi örneğini oluşturun

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Arşive dosyaları ekleyin  

`using` bloğu içinde, eklemek istediğiniz her dosyayı şu şekilde ekleyin:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

İhtiyacınız olan kadar `CreateEntry` çağrısı yapabilir ya da bir dizini döngüyle gezerek programatik olarak ekleyebilirsiniz.

#### 2.3: Sıkıştırılmış TarZ dosyasını kaydedin  

Tüm girişleri ekledikten sonra tar arşivini `.tar.z` formatına sıkıştırın:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Ortaya çıkan `archive.tar.z` dosyası, `dataDir` içinde belirttiğiniz aynı klasörde bulunacaktır.

## Yaygın Sorunlar ve Çözümleri

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** | Yanlış yol veya eksik dosya uzantısı | `dataDir` sonunun bir yol ayırıcı içerdiğini ve dosya adlarının doğru olduğunu doğrulayın. |
| **Erişim reddedildi** | Hedef klasörde yetersiz izinler | Uygulamayı gerekli yetkilerle çalıştırın veya yazılabilir bir dizin seçin. |
| **Sıkıştırılmış dosya beklenenden büyük** | Orijinal dosyalar zaten sıkıştırılmış (ör. görüntüler, videolar) | TarZ, metin veya günlük dosyalarında en iyi sonucu verir; zaten sıkıştırılmış dosyaları olduğu gibi bırakmayı düşünün. |

## Sıkça Sorulan Sorular

**S: Aspose.Zip for .NET ile tüm klasörleri sıkıştırabilir miyim?**  
C: Kesinlikle. `Directory.GetFiles` döngüsü kullanarak her dosya için `CreateEntry` çağırabilir ve göreli yolları koruyabilirsiniz.

**S: Aspose.Zip for .NET için deneme sürümü mevcut mu?**  
C: Evet, Aspose.Zip for .NET’in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Zip for .NET için kapsamlı belgeleri nerede bulabilirim?**  
C: Kütüphanenin özellikleri ve kullanımı hakkında detaylı bilgiler [burada](https://reference.aspose.com/zip/net/) mevcuttur.

**S: Aspose.Zip for .NET için destek nasıl alınır?**  
C: Yardım almak, deneyimlerinizi paylaşmak ve toplulukla iletişime geçmek için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

**S: Aspose.Zip for .NET için geçici bir lisans alabilir miyim?**  
C: Evet, geçici lisans ihtiyacınız varsa [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

## Sonuç

Artık **tar dosyalarına dosya ekleme** ve sonucu Aspose.Zip for .NET kullanarak TarZ arşivi olarak sıkıştırma konusunda bilgi sahibisiniz. Bu yöntem, kolayca aktarılabilir, depolanabilir veya daha ileri işlem yapılabilir temiz ve taşınabilir bir paket sunar. Kod parçacığını dizinleri toplu işleyerek, derleme hatlarına entegre ederek veya diğer Aspose bileşenleriyle birleştirerek daha zengin belge iş akışları oluşturmak için özgürce uyarlayabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-11-29  
**Test Edilen Versiyon:** Aspose.Zip for .NET 24.11  
**Yazar:** Aspose  

---