---
date: 2026-02-15
description: Aspose.Zip for .NET kullanarak dosyaları tar arşivine eklemeyi ve TarZ
  formatına sıkıştırmayı öğrenin – verimli .NET dosya yönetimi için adım adım bir
  rehber.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dosyaları tar'a ekleyin ve Aspose.Zip for .NET ile TarZ olarak sıkıştırın
url: /tr/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar dosyalarına dosya ekleyin ve TarZ formatına sıkıştırın Aspose.Zip for .NET ile

## Giriş

Eğer **add files to tar** işlemini yapıp ardından arşivi TarZ formatına sıkıştırmanız gerekiyorsa, Aspose.Zip for .NET tüm süreci sorunsuz hâle getirir. Bu öğreticide, projenizi kurmaktan bir tar arşivi oluşturmaya, dosyaları eklemeye ve sonunda sıkıştırılmış .tar.z dosyasını kaydetmeye kadar her adımı adım adım göstereceğiz. Sonunda, herhangi bir .NET uygulamasına ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

## Hızlı Yanıtlar
- **Hangi kütüphane tar oluşturmayı yönetir?** Aspose.Zip for .NET  
- **Kaç satır kod?** Yaklaşık 15 satır (yorumlar hariç)  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim için lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Sadece dosyalar değil, klasörleri de sıkıştırabilir miyim?** Evet – bir döngü ile tüm dizinleri ekleyebilirsiniz.

## **add files to tar** nedir?

Dosyaları bir tar arşivine eklemek, onları tek bir sıkıştırılmamış konteynere toplar ve dizin yapısını ile dosya meta verilerini korur. Tar, klasik bir Unix formatıdır ve bu rehberde kullanılan TarZ formatı da dahil olmak üzere birçok sıkıştırma iş akışının temelini oluşturur.

## TarZ'ye sıkıştırmadan önce dosyaları tar'a eklemenin nedeni nedir?

- **Taşınabilirlik** – Bir tar arşivi, bireysel dosya işlemleriyle uğraşmadan platformlar arasında çalışır.  
- **Hız** – Tar konteyneri oluşturmak hızlıdır; ardından gelen Z‑sıkıştırma sadece boyutu küçültmeye odaklanır.  
- **Uyumluluk** – Birçok eski araç, gzip‑stilinde sıkıştırma uygulanmadan önce bir `.tar` dosyası bekler; bu da `.tar.z` dosyasının tam olarak sunduğu şeydir.  

### .NET geliştiricileri için bunun önemi
Bir tar konteyneri kullanmak, .NET kodunuzu basit ve belirli tutmanıza olanak sağlar. Arşivi bellek içinde oluşturabilir, doğrudan bir yanıt akışına gönderebilir veya geçici zip dosyalarıyla uğraşmadan diske kaydedebilirsiniz. Bu desen, özellikle derleme hatları, günlük toplama veya bir Linux‑tabanlı hizmete bir dizi yapılandırma dosyası gönderirken faydalıdır.

## Önkoşullar

Koda geçmeden önce şunların yüklü olduğundan emin olun:

- **Aspose.Zip for .NET** yüklü. Resmi siteden [buradan](https://releases.aspose.com/zip/net/) indirin.  
- Makinenizde arşivlemek istediğiniz dosyaları içeren bir klasör. Yer tutucu yolu gerçek dizininizle değiştirin.

## Ad Alanlarını İçe Aktarın

C# dosyanızın en üstüne gerekli `using` ifadelerini ekleyin:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro ipucu:** Yolları dinamik olarak oluşturmanız gerekiyorsa `Path.Combine` kullanın; farklı işletim sistemlerinde eksik yol ayırıcılarını önler.

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Tanımlayın

```csharp
string dataDir = "Your Document Directory";
```

> **Bu adımın önemi:** `dataDir`, ekleyeceğiniz her dosyanın temel konumu olarak görev yapar. Tek bir değişkende tutmak, kodun bakımını ve birden fazla arşivde yeniden kullanılmasını kolaylaştırır.

### Adım 2: Bir Tar Arşivi Oluşturun ve dosyaları ekleyin

#### 2.1: Tar arşivi örneğini oluşturun

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> `using` bloğu, `TarArchive` nesnesinin düzgün bir şekilde dispose edilmesini sağlar ve dosya tutamaçlarını ya da bellek tamponlarını serbest bırakır.

#### 2.2: Add files to the archive  

Inside the `using` block, add each file you want to include:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

İhtiyacınız kadar dosya eklemek için `CreateEntry`'yi tekrarlayabilir veya bir dizini döngüyle gezerek programlı olarak ekleyebilirsiniz. Örneğin, `foreach (var file in Directory.GetFiles(dataDir))` döngüsü, göreceli yollarını koruyarak rastgele sayıda dosyayı işlemenizi sağlar.

#### 2.3: Save the compressed TarZ file  

After adding all entries, compress the tar archive to the `.tar.z` format:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Oluşan `archive.tar.z` dosyası, `dataDir` içinde belirttiğiniz aynı klasörde yer alacaktır. Artık bu tek, sıkıştırılmış paketi TarZ'yi anlayan herhangi bir sisteme gönderebilirsiniz.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** | Yanlış yol veya eksik dosya uzantısı | `dataDir`'in bir yol ayırıcıyla bittiğini ve dosya adlarının doğru olduğunu doğrulayın. |
| **Erişim reddedildi** | Hedef klasörde yetersiz izinler | Uygulamayı uygun yetkilerle çalıştırın veya yazılabilir bir dizin seçin. |
| **Sıkıştırılmış dosya beklenenden büyük** | Orijinal dosyalar zaten sıkıştırılmış (ör. görseller, videolar) | TarZ, metin veya günlük dosyalarında en iyi çalışır; zaten sıkıştırılmış dosyaları olduğu gibi bırakmayı düşünün. |

### Dikkat edilmesi gereken yaygın tuzaklar
- **Eksik son eğik çizgi** – `dataDir` `\` veya `/` ile bitmezse, dize birleştirme geçersiz bir yol oluşturur.
- **Büyük dizinler** – Binlerce dosya eklemek bellek tüketebilir; girişleri akış olarak göndermeyi veya doğrudan bir dosya akışına yazan `TarArchive` aşırı yüklemesini kullanmayı düşünün.
- **Kodlama sorunları** – ASCII dışı dosya adları açık kodlama işleme gerektirebilir; Aspose.Zip varsayılan olarak UTF-8'i destekler, ancak hedef platformda doğrulayın.

## Sıkça Sorulan Sorular

**Q:** Aspose.Zip for .NET ile tüm klasörleri sıkıştırabilir miyim?  
**A:** Kesinlikle. Her dosya için `CreateEntry` çağırarak ve göreceli yolları koruyarak bir `Directory.GetFiles` döngüsü kullanın.

**Q:** Aspose.Zip for .NET için bir deneme sürümü mevcut mu?  
**A:** Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirerek Aspose.Zip for .NET'in yeteneklerini keşfedebilirsiniz.

**Q:** Aspose.Zip for .NET için kapsamlı belgeleri nerede bulabilirim?  
**A:** Belgeler [burada](https://reference.aspose.com/zip/net/) mevcuttur ve kütüphanenin özellikleri ve kullanımı hakkında ayrıntılı bilgiler sunar.

**Q:** Aspose.Zip for .NET için destek nasıl alabilirim?  
**A:** Yardım almak, deneyimlerinizi paylaşmak ve toplulukla iletişime geçmek için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

**Q:** Aspose.Zip for .NET için geçici bir lisans alabilir miyim?  
**A:** Evet, geçici bir lisansa ihtiyacınız varsa, birini [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç

Artık **add files to tar** işlemini nasıl yapacağınızı ve sonucu Aspose.Zip for .NET kullanarak bir TarZ arşivine nasıl sıkıştıracağınızı öğrendiniz. Bu yaklaşım, kolayca aktarılabilen, depolanabilen veya daha ileri işlenebilen temiz ve taşınabilir bir paket sunar. Kod parçacığını dizinleri toplu işleyerek, derleme hatlarına entegre ederek veya daha zengin belge iş akışları için diğer Aspose bileşenleriyle birleştirerek uyarlamaktan çekinmeyin.

---

**Son Güncelleme:** 2026-02-15  
**Test Edilen:** Aspose.Zip for .NET 24.11  
**Yazar:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}