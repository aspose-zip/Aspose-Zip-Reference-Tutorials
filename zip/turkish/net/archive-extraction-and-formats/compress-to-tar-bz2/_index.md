---
date: 2026-10-31
description: Aspose.Zip kullanarak .NET'te tar arşivi oluşturmayı ve bir TarBz2 dosyasına
  sıkıştırmayı öğrenin. Adım adım rehber, tar oluşturma, Bzip2 sıkıştırma ve en iyi
  uygulama ipuçlarını gösterir.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: TarBz2'ye Sıkıştırma
og_description: Aspose.Zip for .NET kullanarak tar arşivi oluşturmayı ve bir TarBz2
  dosyasına sıkıştırmayı öğrenin. Adım adım rehber, tar oluşturma, Bzip2 sıkıştırma
  ve en iyi uygulama ipuçlarını kapsar.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: .NET ile tar arşivi oluşturma ve TarBz2'ye sıkıştırma
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: .NET ile tar arşivi oluşturma ve TarBz2'ye sıkıştırma
url: /tr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET ile tar arşivi oluşturma ve TarBz2'ye sıkıştırma

Bu öğreticide **tar arşivi** dosyalarını nasıl oluşturacağınızı ve ardından **Aspose.Zip** .NET kütüphanesini kullanarak bunları kompakt bir **TarBz2** paketine nasıl sıkıştıracağınızı öğreneceksiniz. Yedekleme aracı oluşturuyor, dağıtım paketleri hazırlıyor ya da hafif bir dağıtım formatına ihtiyacınız varsa, aşağıdaki adımlar dosyaları bir tar konteynerine eklemenizi, Bzip2 sıkıştırması uygulamanızı ve son `.tar.bz2` dosyasını yazmanızı sağlayacak.

## Hızlı cevaplar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET  
- **Uygulama ne kadar sürer?** Yaklaşık 5‑10 dakika  
- **Lisans gerekli mi?** Üretim için geçici bir lisans gerekir; ücretsiz deneme sürümü mevcuttur  
- **Birden fazla dosyayı sıkıştırabilir miyim?** Evet – tar arşivine istediğiniz kadar giriş ekleyebilirsiniz  
- **.NET 6+ ile uyumlu mu?** Kesinlikle, Aspose.Zip .NET Framework ve .NET Core/5/6'yı destekler  

## TarBz2 arşivi nedir?

TarBz2 dosyası, geleneksel **tar** konteynerini (dizin yapısını ve dosya meta verilerini korur) **Bzip2** sıkıştırmasıyla birleştirerek yüksek sıkıştırmalı bir `.tar.bz2` paketi oluşturur. Bu format, sıkıştırma oranı ile açma hızı arasında iyi bir denge sunduğu için Unix benzeri sistemlerde popülerdir.

## Dosyaları TarBz2'ye Aspose.Zip ile neden sıkıştırmalıyız?

Aspose.Zip, akışları verimli bir şekilde yönetirken **iki API çağrısı**yla bir TarBz2 arşivi oluşturabilir. **50+ arşiv ve sıkıştırma formatını** destekler, **2 GB**'a kadar dosyaları tüm arşivi belleğe yüklemeden işler ve Windows, Linux ve macOS .NET çalışma zamanlarında çalışır. Kütüphane ayrıca giriş adları, zaman damgaları ve sıkıştırma seviyeleri üzerinde ince ayar yapmanıza olanak tanır; bu da hem konsol araçları hem de web servisleri için idealdir.

## Önkoşullar

- **Aspose.Zip for .NET** – resmi siteden en son paketi indirin: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – arşivlemek istediğiniz dosyaları içeren bir klasör. Örneklerde bu klasöre `dataDir` değişkeniyle referans veriyoruz.

> **Pro ipucu:** İstenmeyen dosyaların yanlışlıkla dahil edilmesini önlemek için kaynak dosyalarınızı ayrı bir klasörde tutun.

## Ad alanlarını içe aktar

İlk olarak, Aspose.Zip’in Tar ve Bzip2 sınıflarına erişebilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Adım 1: belge dizinini ayarla

Arşivlemek istediğiniz dosyaları tutan klasöre işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` ifadesini kaynak klasörünüzün mutlak ya da göreli yolu ile değiştirin.

## Adım 2: dosyaları tar'a ekle ve bir TarBz2 arşivi oluştur

`TarArchive` sınıfı bellek içi bir tar konteynerini temsil ederken, `Bzip2Archive` akışları Bzip2 algoritmasıyla sıkıştırır.  
`CreateEntry` yöntemi, tar arşivine yeni bir dosya girişi ekler.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **dosyaları tar'a ekler** – arşivde ihtiyacınız olan her dosya için bu yöntemi çağırabilirsiniz.  
- `bz2.SetSource(archive)` Bzip2 arşivine tüm tar akışını sıkıştırmasını söyler.  
- `bz2.Save(...)` son **TarBz2** dosyasını diske yazar.

**İpucu:** Toplu olarak **dosyaları tar'a eklemek** için, `bz2.Save` çağırmadan önce her dosya için `archive.CreateEntry` ifadesini tekrarlamanız yeterlidir.

## Dosyaları tar'a nasıl eklerim?

Kaynak dizini yükleyin, bir `TarArchive` örneği oluşturun, her dosyayı `CreateEntry` ile ekleyin, ardından tar akışını bir `Bzip2Archive` içine sarın ve `Save` çağırın. Bu iki adımlı desen, istediğiniz sayıda dosyayı ekler ve geçici dosyalara ya da harici araçlara ihtiyaç duymadan tek bir akışta `.tar.bz2` dosyası üretir.

## Yaygın sorunlar ve çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** hatası | `dataDir` yolunun yanlış olması ya da dosya uzantısının eksik olması | Tam yolu doğrulayın ve dosyanın mevcut olduğundan emin olun. |
| **Boş arşiv** | `bz2.Save`'den önce hiçbir giriş eklenmemiş | En az bir `CreateEntry` çağrısı ekleyin. |
| **İzin reddedildi** | Uygulamanın çıktı klasörüne yazma izni yok | Uygulamayı gerekli izinlerle çalıştırın veya yazılabilir bir klasör seçin. |

## Sıkça sorulan sorular

**S: Aspose.Zip tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5/6 ve daha yeni çalışma zamanlarıyla çalışır.

**S: Birden fazla dosyayı aynı anda sıkıştırabilir miyim?**  
C: Kesinlikle. Arşivi kaydetmeden önce her dosya için `CreateEntry` çağırın.

**S: Ek dokümantasyonu nerede bulabilirim?**  
C: Ayrıntılı belgeler **Aspose.Zip .NET API reference** içinde mevcuttur: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**S: Aspose.Zip için geçici bir lisans nasıl alabilirim?**  
C: Buradan **geçici bir lisans isteyebilirsiniz**: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**S: Ücretsiz bir deneme sürümü var mı?**  
C: Evet, **Aspose sürümlerinden bir deneme sürümü indirebilirsiniz**: [download a trial version](https://releases.aspose.com/).

Ayrıca [deneme sürümünü indirebilirsiniz](https://releases.aspose.com/).

## Sonuç

Artık **tar arşivi** nasıl oluşturulur, tar akışı Bzip2 ile nasıl sıkıştırılır ve Aspose.Zip for .NET kullanarak bir **TarBz2** arşivi nasıl üretilir biliyorsunuz. Yaklaşım hızlı, bellek‑verimli ve tüm modern .NET platformlarında çalışır. Daha büyük dosya setleri, özel giriş adlarıyle denemeler yapabilir veya kodu kendi yedekleme ya da dağıtım hatlarınıza entegre edebilirsiniz.

Herhangi bir zorlukla karşılaşırsanız, Aspose.Zip topluluğu yardımcı olmaya hazır—tek yapmanız gereken **Aspose.Zip destek forumuna** gitmek: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Son Güncelleme:** 2026-10-31  
**Test Edilen:** Aspose.Zip for .NET (latest release)  
**Yazar:** Aspose  

## İlgili öğreticiler

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Add files to tar and compress to TarZ with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}