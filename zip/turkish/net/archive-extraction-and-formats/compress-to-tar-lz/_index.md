---
date: 2026-07-04
description: Aspose.Zip for .NET kullanarak birden fazla dosyayı tar olarak nasıl
  sıkıştıracağınızı öğrenin ve tar.lz arşivlerini verimli bir şekilde oluşturun.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: TarLz'ye Sıkıştırma
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile birden fazla dosyayı tar olarak sıkıştırma
url: /tr/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET ile birden fazla dosyayı tar olarak sıkıştırma

Modern .NET geliştirmede, dosyaları verimli bir şekilde paketlemek dağıtım boyutunu ve ağ aktarım sürelerini büyük ölçüde iyileştirebilir. **Birden fazla dosyayı tar olarak sıkıştırma** hafif, LZ‑sıkıştırmalı bir TAR arşivi yedeklemeler, dağıtım veya bulut yüklemeleri için sıkça ihtiyaç duyulan bir gereksinimdir. Bu öğreticide, Aspose.Zip kütüphanesini kullanarak net, adım‑adım bir **tar.lz sıkıştırma örneği** üzerinden geçeceğiz, böylece kendi uygulamalarınızda hızlıca bir **tar.lz arşivi** oluşturabilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.  
- **Lisans gereklimi?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Birden fazla dosyayı aynı anda sıkıştırabilir miyim?** Evet – kaydetmeden önce daha fazla giriş ekleyin.

## Aspose.Zip for .NET ile birden fazla dosyayı tar olarak nasıl sıkıştırırım?
Kaynak dosyalarınızı yükleyin, bir `TarArchive` örneği oluşturun, her dosyayı `CreateEntry` ile ekleyin ve `SaveLzipped` çağrısı yaparak işlemi tamamlayın. Kütüphane TAR yapısını ve LZ sıkıştırmasını dahili olarak yönetir, böylece sadece birkaç satır kodla tek bir `*.tar.lz` dosyasına sahip olursunuz. Bu yaklaşım, Windows, Linux ve macOS'ta herhangi bir yerel bağımlılık olmadan çalışır.

## tar.lz sıkıştırması nedir?
`tar.lz`, LZMA algoritması (genellikle sadece **LZ** olarak anılır) kullanılarak sıkıştırılmış bir TAR arşividir. TAR'ın dosya gruplama basitliğini yüksek sıkıştırma oranı sağlayan LZ ile birleştirir, bu da yedekleme dosyaları, paket dağıtımı veya bant genişliğinin önemli olduğu herhangi bir senaryo için idealdir.

## Neden Aspose.Zip for .NET kullanmalısınız?
Aspose.Zip, harici araçlar gerektirmeden TAR, ZIP ve LZ‑tabanlı arşivler oluşturan saf‑yönetilen, çapraz‑platform bir çözüm sunar, 30’dan fazla arşiv formatını destekler ve büyük dosyalarda %30’a kadar daha iyi sıkıştırma sağlar; ayrıca sağlam hata yönetimi için ayrıntılı istisnalar sunar. .NET kayıt çerçeveleriyle sorunsuz entegrasyon sağlar ve ayrıntılı ilerleme olayları sunar.

## Önkoşullar
- **Aspose.Zip for .NET** kütüphanesi – bunu [buradan](https://releases.aspose.com/zip/net/) indirin.  
- Arşivlemek istediğiniz dosyaları içeren bir klasör. Bu klasörün yolu `dataDir` değişkeninde saklanacaktır (Adım 3'te ayarlayacaksınız).

## Ad Alanlarını İçe Aktarın
Kullanacağımız sınıfların nerede bulunduğunu derleyicinin bilmesi için gerekli ad alanlarını ekleyin.

```csharp
using System;
using Aspose.Zip.Tar;
```

## tar.lz arşivi oluşturma – Adım‑Adım Kılavuz

### Adım 1: Tek bir dosyayı sıkıştırma
İlk örnek, en temel senaryoyu gösterir – bir dosyayı TAR arşivine ekleyip ardından **tar.lz** dosyası olarak kaydetmek.

`TarArchive` sınıfı, tek bir arşivde birden fazla dosyayı tutabilen bir TAR konteynerini temsil eder.  

**Açıklama**

- `new TarArchive()` boş bir TAR konteyneri oluşturur.  
- `CreateEntry` `dataDir` içindeki `alice29.txt` dosyasını ekler.  
- `SaveLzipped` arşivi diske yazar ve LZ sıkıştırması uygular, `archive.tar.lz` oluşturur.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Adım 2: Tek bir arşivde birden fazla dosyayı sıkıştırma
Genellikle birkaç dosyayı bir araya getirmeniz gerekir. Kaydetmeden önce her dosya için `CreateEntry` çağırın. Bu, **tar lz'ye dosya ekleme** ve etkili bir şekilde **birden fazla dosyayı tar olarak sıkıştırma** gösterir.

**Açıklama**

- Kod, Adım 1 ile aynı deseni izler, ancak ikinci bir giriş (`lcet10.txt`) ekler.  
- İhtiyacınız kadar `CreateEntry` tekrar edebilirsiniz; kütüphane iç TAR yapısını otomatik olarak yönetir.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Adım 3: Belge dizininizi belirtin
Yer tutucuyu, kaynak dosyalarınızın bulunduğu gerçek yol ile değiştirin. Bu yol, yukarıdaki örnekler tarafından kullanılır.

**Açıklama**

- `dataDir`'i tam nitelikli bir klasör yolu olarak ayarlayın, ör. `@"C:\\MyFiles\\"`.  
- Dizini bir değişkende tutmak kodun yeniden kullanılabilir ve bakımını kolaylaştırır.

```csharp
string dataDir = "Your Document Directory";
```

## Yaygın tuzaklar ve sorun giderme
| Semptom | Muhtemel neden | Çözüm |
|---------|----------------|-------|
| Örnek çalıştırılırken `FileNotFoundException` | `dataDir` mevcut olmayan bir klasöre işaret ediyor veya dosya adı yanlış yazılmış | Yolu ve dosya adlarını doğrulayın; güvenlik için `Path.Combine` kullanın. |
| Çıktı dosyası **0 KB** | `archive.SaveLzipped` hiçbir giriş eklenmeden önce çağrıldı | `SaveLzipped`'den önce en az bir `CreateEntry` çağrısı yapıldığından emin olun. |
| Sıkıştırma yavaş görünüyor | Varsayılan tampon boyutuyla büyük dosyalar | Performans kritikse dosyaları parçalar halinde işleme veya asenkron I/O kullanmayı düşünün. |

## Sonuç
Artık Aspose.Zip for .NET kullanarak **tar.lz** dosyalarını nasıl sıkıştıracağınızı biliyorsunuz; tek bir belge ya da bir dosya koleksiyonu ile çalışıyor olun. Bu **tar.lz sıkıştırma örneği**, kolayca aktarılabilir veya depolanabilir **tar lz arşivi oluşturma** için temiz, üretim‑hazır bir yol gösterir. Tüm istenen girişleri ekledikten sonra `SaveLzipped` çağırarak aynı API ile dosyaları tar.lz'ye sıkıştırabilirsiniz.

## Sıkça Sorulan Sorular

**S:** Aspose.Zip for .NET ile herhangi bir boyutta dosyayı sıkıştırabilir miyim?  
**C:** Evet, kütüphane hem küçük hem de çok büyük dosyaları yönetir; sadece geçici TAR yapısı için yeterli bellek ve disk alanına sahip olduğunuzdan emin olun.

**S:** Kod, en son Aspose.Zip sürümüyle uyumlu mu?  
**C:** Örnek mevcut sürümü hedeflemektedir; hata düzeltmeleri ve yeni özellikler için NuGet paketini her zaman güncel tutun.

**S:** Lisanslama ile ilgili hususlar var mı?  
**C:** Üretim kullanımı için ticari lisans gereklidir. Lisans detayları için [Aspose web sitesine](https://purchase.aspose.com/buy) bakın.

**S:** Bunu ticari bir projede kullanabilir miyim?  
**C:** Kesinlikle – geçerli bir lisansınız olduğunda, kütüphaneyi herhangi bir ticari uygulamaya entegre edebilirsiniz.

**S:** Sorun yaşarsam nereden yardım alabilirim?  
**C:** Topluluk desteği ve resmi yardım için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

---

**Son Güncelleme:** 2026-07-04  
**Test Edildi:** Aspose.Zip for .NET (latest release)  
**Yazar:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Zip for .NET ile tar arşivi oluşturma ve dosyaları tar'a ekleme](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip for .NET ile tar sıkıştırma ve TarBz2 oluşturma](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aspose.Zip ile dosyaları tar'a ekleme ve tarxz arşivi oluşturma](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}