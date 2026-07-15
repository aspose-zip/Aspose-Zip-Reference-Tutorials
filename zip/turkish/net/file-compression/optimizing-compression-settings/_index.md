---
date: 2026-06-09
description: Aspose.Zip for .NET kullanarak zip dosyasına şifre eklemeyi ve LZMA zip
  arşivleri oluşturmayı öğrenin. Bu öğreticide Bzip2, LZMA (sözlük boyutu), PPMd,
  Gelişmiş Deflate, Store sıkıştırma ve büyük dosyaların ASP.NET dosya sıkıştırması
  ele alınmaktadır.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Sıkıştırma Ayarlarını Optimize Etme
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile zip dosyasına şifre ekleyin ve LZMA arşivi oluşturun
url: /tr/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zip'e şifre ekleyin ve Aspose.Zip for .NET ile LZMA arşivi oluşturun

Modern .NET uygulamalarında, yüksek oranlı LZMA zip arşivi oluştururken **add password to zip** şifresi eklemek hassas verileri koruyabilir ve yine de mümkün olan en iyi sıkıştırmayı sağlayabilir. ASP.NET dosya sıkıştırma hizmeti, çok gigabayt dosyaları işleyen bir masaüstü yardımcı programı ya da bulut tabanlı bir iş akışı oluşturuyor olun, bu öğretici Aspose.Zip for .NET ile dosyalarınızı güvenli bir şekilde sıkıştırmak için gereken adımları size gösterir.

## Hızlı Yanıtlar
- **LZMA sıkıştırmasının temel faydası nedir?** En yüksek sıkıştırma oranı, çoğu dosya türü için makul bir hızla.  
- **Hangi yöntem sıkıştırma olmadan dosyaları depolar?** Store compression (also called “store compression zip”).  
- **Bu ayarları bir ASP.NET uygulamasında kullanabilir miyim?** Evet—projenizde Aspose.Zip'i referans gösterin ve aynı API'yi çağırın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Üretim için ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ve .NET 5–10.

## Aspose.Zip'te “add password to zip” nedir?

**Bir zip şifresi eklemek, ZIP arşivindeki her girişi şifreler, böylece sadece şifreyi bilen kullanıcılar dosyaları çıkarabilir.** Aspose.Zip, geleneksel ZipCrypto şifrelemesinin yanı sıra AES şifrelemesini (128, 192 veya 256‑bit) destekler. Şifreleme ayarları, bir `Archive` oluşturulurken `ArchiveEntrySettings`'e ikinci argüman olarak sağlanır; ayrı bir `SetPassword` yöntemi yoktur.

## Neden .NET dosya sıkıştırması için Aspose.Zip kullanmalı?

Aspose.Zip, birçok algoritmayı kapsayan tek ve tutarlı bir API sağlar ve yüksek performans ile düşük bellek kullanımı sunar. Geliştiricilerin her senaryo için en iyi sıkıştırma yöntemini seçmesine ve şifrelemeyi tek adımda uygulamasına olanak tanır, kodu basitleştirir ve bakım yükünü azaltır.

- **Unified API** – Bzip2, LZMA, PPMd, Enhanced Deflate ve Store için tek tutarlı arayüz.
- **Performance‑tuned** – Optimize edilmiş yerel uygulama, **10 GB'a kadar dosyaları** tüm dosyayı belleğe yüklemeden işler.
- **ASP.NET friendly** – Web projelerinde, arka plan hizmetlerinde ve Azure Functions'da sorunsuz çalışır.
- **Fine‑grained control** – Sözlük boyutunu, sıkıştırma seviyesini ve şifrelemeyi tek bir yapıcı çağrısıyla ayarlayın.
- **Supports 10+ compression algorithms** – kurumsal veri hatlarındaki en yaygın kullanım senaryolarını kapsar.

## Önkoşullar
- **Aspose.Zip for .NET Library** – [Aspose documentation](https://reference.aspose.com/zip/net/) adresinden indirin ve kurun.  
- **Sample Text File** – Sıkıştıracağınız örnek bir dosya (ör. `sample.txt`) hazırlayın.  
- **.NET development environment** – Visual Studio 2022 veya uyumlu herhangi bir IDE.

## Ad Alanlarını İçe Aktarın

`Archive`, `ArchiveEntrySettings` ve şifreleme sınıfları `Aspose.Zip` ad alanında bulunur. Dosyanızın en üstüne bunları içe aktarın:

- `Archive` bir ZIP arşiv kapsayıcısını temsil eder.  
- `ArchiveEntrySettings` her giriş için sıkıştırma ve şifreleme seçeneklerini tutar.  
- Şifreleme sınıfları (ör. `AesEncryptionSettings`) verinin nasıl şifreleneceğini tanımlar.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Şimdi her sıkıştırma ayarını inceleyelim ve uygun olduğunda **add password to zip** nasıl yapılacağını görelim.

## Bzip2 Sıkıştırma Ayarlarını Kullanma

### Adım 1: Bzip2 Sıkıştırmasını Geleneksel Şifreleme ile Başlatın

`Bzip2CompressionSettings` Bzip2 algoritmasını (blok boyutu vb.) yapılandırır.  
`TraditionalEncryptionSettings` bir girişe eski ZipCrypto şifrelemesini uygular.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*Şifre koruması, doğrudan `ArchiveEntrySettings`'e geçirilen `TraditionalEncryptionSettings` aracılığıyla uygulanır.*

## Aspose.Zip for .NET kullanarak zip'e şifre ekleme

Kaynak dosyanızı yükleyin, giriş ayarlarıyla bir `Archive` oluşturun ve dosyayı arşive ekleyin. Şifreleme, `ArchiveEntrySettings` örneği oluşturulurken sağlandığı için otomatik olarak uygulanır.

**Direct answer (40‑70 words):**  
"İstenen sıkıştırma ayarlarını ve `TraditionalEncryptionSettings` ya da `AesEncryptionSettings`'i içeren bir `ArchiveEntrySettings` nesnesi oluşturun. Bu nesneyi `Archive` yapıcısına geçirin ve dosyaları `AddEntry` ile ekleyin. Arşiv, şifre zaten gömülü olarak yazılır, bu yüzden oluşturulduktan sonra ekstra bir adım gerekmez."

`ArchiveEntrySettings`, Aspose.Zip'e her girişin nasıl sıkıştırılacağını ve şifreleneceğini belirten yapılandırma tutucusudur.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Aspose.Zip kullanarak LZMA zip arşivi oluşturma

### Adım 1: LZMA Sıkıştırmasını AES256 Şifreleme ile Başlatın

`LzmaCompressionSettings` sözlük boyutu ve fast bytes gibi LZMA‑özel parametreleri kontrol eder.  
`AesEncryptionSettings` arşiv girişleri için AES‑256 şifreleme sağlar.

**Direct answer (40‑70 words):**  
"Seçilen bir `DictionarySize` ile `LzmaCompressionSettings` örneği oluşturun, şifreniz ve `EncryptionMethod.AES256` ile bir `AesEncryptionSettings` nesnesi yaratın, ardından ikisinden bir `ArchiveEntrySettings` oluşturun. Bunu `Archive` yapıcısına geçirin ve dosyalarınızı ekleyin; ortaya çıkan zip tek bir işlemde LZMA‑sıkıştırılmış ve AES‑korumalı olacaktır."

`LzmaCompressionSettings`, sözlük boyutu ve fast bytes gibi LZMA‑özel parametreleri kontrol eden sınıftır.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **İpucu:** LZMA, sıkıştırma oranı ve bellek kullanımını etkileyen yapılandırılabilir bir **LZMA sözlük boyutu** sunar. Çok büyük dosyalar için ince ayar yapmanız gerekiyorsa, bunu `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` şeklinde ayarlayabilirsiniz.

## PPMd Sıkıştırma Ayarlarını Kullanma

### Adım 1: PPMd Sıkıştırmasını AES256 Şifreleme ile Başlatın

`PpmdCompressionSettings` PPMd algoritması için sıra ve bellek kullanımını tanımlar.  
`AesEncryptionSettings` arşiv girişleri için AES‑256 şifreleme sağlar.

**Direct answer (40‑70 words):**  
"`PpmdCompressionSettings` örneği oluşturun, şifrenizi içeren bir `AesEncryptionSettings` nesnesiyle birleştirin ve ikisini `ArchiveEntrySettings` içine besleyin. `Archive` oluştururken bu ayar nesnesini kullanın; ortaya çıkan zip PPMd‑sıkıştırılmış ve şifre korumalı olur, ekstra çağrı gerekmez."

`PpmdCompressionSettings`, PPMd algoritması için sıra ve bellek kullanımını tanımlar.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Enhanced Deflate Sıkıştırma Ayarlarını Kullanma

### Adım 1: Enhanced Deflate Sıkıştırmasını AES256 Şifreleme ile Başlatın

`EnhancedDeflateCompressionSettings` hız ve boyutu dengeleyen bir sıkıştırma seviyesi belirlemenizi sağlar.  
`AesEncryptionSettings` arşiv girişleri için AES‑256 şifreleme sağlar.

**Direct answer (40‑70 words):**  
"İstediğiniz seviyede (0‑9) `EnhancedDeflateCompressionSettings` oluşturun, `AesEncryptionSettings` ile eşleştirin ve `ArchiveEntrySettings` içinde paketleyin. Bunu `Archive` yapıcısına geçirin ve dosyaları ekleyin; arşiv tek bir geçişte Enhanced Deflate sıkıştırması ve AES‑256 şifre koruması ile oluşturulur."

`EnhancedDeflateCompressionSettings`, hız ve boyutu dengeleyen bir sıkıştırma seviyesi belirlemenizi sağlar.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Store Sıkıştırma Ayarlarını Kullanma (store compression zip)

### Adım 1: Store Sıkıştırmasını Geleneksel Şifreleme ile Başlatın

`StoreCompressionSettings` Aspose.Zip'e sıkıştırmayı tamamen atlamasını, kaynak dosyayı bayt‑bayt korumasını söyler.  
`TraditionalEncryptionSettings` eski ZipCrypto şifrelemesini uygular.

**Direct answer (40‑70 words):**  
"`StoreCompressionSettings` (sıkıştırma yapmayan) bir örnek oluşturun, şifrenizi içeren `TraditionalEncryptionSettings` ile birleştirin ve ikisini `ArchiveEntrySettings` içinde paketleyin. Bunu `Archive` yapıcısına geçirin; ortaya çıkan zip orijinal dosyayı sıkıştırılmadan ama şifre korumalı olarak içerir."

`StoreCompressionSettings`, Aspose.Zip'e sıkıştırmayı tamamen atlamasını ve kaynak dosyayı bayt‑bayt korumasını söyler.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro ipucu:** `dataDir` değişkenini gerçek çalışma dizininize işaret edecek şekilde ayarlayın ve tek bir arşive birden fazla dosya eklemeniz gerekiyorsa aynı `Archive` örneğini yeniden kullanın.

## Yaygın Sorunlar ve Çözümler
- **"File not found" hataları** – `dataDir`'in bir yol ayırıcı (`\` veya `/`) ile bittiğini ve `sample.txt` dosyasının mevcut olduğunu doğrulayın.  
- **Büyük dosyalarda bellek tüketimi** – Veriyi doğrudan çıktı akışına yazan akış modunu etkinleştirmek için `ArchiveEntrySettings` kullanın.  
- **Uyumsuz sıkıştırma seviyesi** – Bazı algoritmalar (ör. LZMA) `DictionarySize` gibi ek özellikler sunar. Daha ince kontrol gerekiyorsa API belgelerine bakın.  
- **Şifre uygulanmadı** – Şifreleme ayarları nesnesinin, arşiv oluşturulurken `ArchiveEntrySettings`'e ikinci argüman olarak geçirildiğinden, arşiv oluşturulduktan sonra değil, emin olun.

## Sıkça Sorulan Sorular

**Q: Aspose.Zip for .NET'i diğer sıkıştırma kütüphaneleriyle kullanabilir miyim?**  
**A:** Aspose.Zip, kendi yerleşik algoritmalarıyla çalışacak şekilde tasarlanmıştır. Üçüncü‑taraf kütüphaneleri entegre etmek mümkündür ancak Aspose API'sinin dışındaki özel bir işlem gerektirir.

**Q: Aspose.Zip ile oluşturulan bir zip'e şifre koruması nasıl ekleyebilirim?**  
**A:** `Archive` oluşturulurken `ArchiveEntrySettings`'e ikinci argüman olarak `TraditionalEncryptionSettings` ya da `AesEncryptionSettings` geçirin. Tam örnekler için [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) adresine bakın.

**Q: Test edebileceğim bir deneme sürümü var mı?**  
**A:** Evet, deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**Q: Topluluk desteği alabileceğim veya soru sorabileceğim yer neresi?**  
**A:** Destek ve topluluk tartışmaları için [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) adresini ziyaret edin.

**Q: Değerlendirme için geçici bir lisans alabilir miyim?**  
**A:** Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

**Q: Bu, ASP.NET dosya sıkıştırmasıyla nasıl yardımcı olur?**  
**A:** Aynı API'yi bir ASP.NET denetleyicisi veya ara katmandan çağırarak, dosyaları istemciye göndermeden önce anında sıkıştırabilir, bant genişliğini azaltır ve algılanan performansı artırır.

**Q: Büyük dosyaları verimli bir şekilde sıkıştırmanın en iyi yolu nedir?**  
**A:** Akış modunu LZMA sıkıştırması ve uygun bir `DictionarySize` ile birleştirin. Bu, büyük veri setleri için bellek kullanımını ve sıkıştırma oranını dengeler.

**Son Güncelleme:** 2026-06-09  
**Test Edilen:** Aspose.Zip 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Zip for .NET - Zip Arşivini Şifreyle Koruma ve Sıkıştırma Olmadan Çoklu Dosya Depolama](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [.NET dizinleri için şifre korumalı zip oluşturma – Aspose.Zip Öğreticisi](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [c# ile birden fazla dosyayı zipleme – Aspose.Zip for .NET ile Sorunsuz Sıkıştırma](/zip/net/file-compression/compress-multiple-files/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}