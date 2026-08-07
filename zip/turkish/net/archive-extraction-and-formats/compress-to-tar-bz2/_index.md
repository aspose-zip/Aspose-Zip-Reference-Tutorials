---
date: 2026-08-07
description: Aspose.Zip kullanarak .NET'te dosyaları tar'a eklemeyi ve bir TarBz2
  arşivi oluşturmayı öğrenin. Adım adım kılavuz, tar oluşturmayı, Bzip2 sıkıştırmasını
  ve en iyi uygulama ipuçlarını gösterir.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: TarBz2'ye sıkıştırma
og_description: Aspose.Zip kullanarak .NET'te dosyaları tar'a ekleyin ve bir TarBz2
  arşivi oluşturun. Bu kılavuz, tar oluşturmayı, Bzip2 sıkıştırmasını ve sorun giderme
  ipuçlarını kapsar.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Dosyaları tar'a ekleyin ve Aspose.Zip ile bir TarBz2 arşivi oluşturun
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
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
title: Dosyaları tar'a ekleyin ve Aspose.Zip ile bir TarBz2 arşivi oluşturun
url: /tr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar'a dosya ekleme ve Aspose.Zip ile TarBz2 arşivi oluşturma

Bu öğreticide, .NET için **Aspose.Zip** kütüphanesini kullanarak **tar** arşivlerine dosya eklemenin ve bunları kompakt bir **TarBz2** dosyasına dönüştürmenin nasıl yapılacağını keşfedeceksiniz. Yedekleme aracı oluşturuyor, dağıtım paketleri yayınlıyor ya da dağıtım için hafif bir paket ihtiyacınız varsa, aşağıdaki adımlar size tar konteynerine dosya ekleme, Bzip2 sıkıştırması uygulama ve paylaşmaya hazır bir arşiv üretme sürecini gösterir.

## Hızlı cevaplar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET  
- **Uygulama ne kadar sürer?** About 5‑10 minutes  
- **Lisans gerekir mi?** A temporary license is required for production; a free trial is available  
- **Birden fazla dosyayı sıkıştırabilir miyim?** Yes – add as many entries as you like to the tar archive  
- **.NET 6+ ile uyumlu mu?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## TarBz2 arşivi nedir?

Bir TarBz2 dosyası, geleneksel **tar** konteynerini (dizin yapısını ve dosya meta verilerini korur) **Bzip2** sıkıştırmasıyla birleştirir ve yüksek sıkıştırmalı bir `.tar.bz2` paketi oluşturur. Bu format, sıkıştırma oranı ile açma hızı arasında iyi bir denge sunduğu için Unix benzeri sistemlerde popülerdir.

## Neden dosyaları TarBz2 ile Aspose.Zip kullanarak sıkıştırmalıyız?

Aspose.Zip, akışları verimli bir şekilde yönetirken **iki API çağrısı** ile bir TarBz2 arşivi oluşturabilir. **50+ arşiv ve sıkıştırma formatını** destekler, tüm arşivi belleğe yüklemeden **2 GB**'a kadar dosyayı işler ve Windows, Linux ve macOS .NET çalışma zamanlarında çalışır. Kütüphane ayrıca giriş adları, zaman damgaları ve sıkıştırma seviyeleri üzerinde ayrıntılı kontrol sağlar; bu da onu hem konsol yardımcı programları hem de web hizmetleri için ideal kılar.

## Önkoşullar

- **Aspose.Zip for .NET** – resmi siteden en son paketi indirin: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – arşivlemek istediğiniz dosyaları içeren bir klasör. Örneklerde bu klasöre `dataDir` değişkeniyle referans verilir.

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

Arşivlemek istediğiniz dosyaları içeren klasöre işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` ifadesini kaynak klasörünüzün mutlak ya da göreli yolu ile değiştirin.

## Adım 2: dosyaları tar'a ekle ve bir TarBz2 arşivi oluştur

`TarArchive` birden çok dosya girdisi tutabilen bellek içi bir tar konteynerini temsil eder.  
`Bzip2Archive` bir akışı Bzip2 algoritmasıyla sıkıştırır.  
`CreateEntry` yöntemi, bir dosyayı yeni bir giriş olarak tar arşivine ekler.

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

**İpucu:** **Dosyaları tar'a toplu olarak eklemek** için, `bz2.Save` çağırmadan önce her dosya için `archive.CreateEntry` ifadesini tekrarlamanız yeterlidir.

## Dosyaları tar'a nasıl eklenir?

Kaynak dizini yükleyin, bir `TarArchive` örneği oluşturun, her dosyayı `CreateEntry` ile ekleyin, ardından tar akışını bir `Bzip2Archive` içine sarın ve `Save` metodunu çağırın. Bu iki adımlı desen, istediğiniz sayıda dosyayı ekleyerek tek bir akıcı işlemde bir `.tar.bz2` dosyası üretir; geçici dosyalara veya harici araçlara ihtiyaç duymaz.

## Yaygın sorunlar ve çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** hatası | `dataDir` yolunun yanlış olması veya dosya uzantısının eksik olması | Tam yolu doğrulayın ve dosyanın mevcut olduğundan emin olun. |
| **Boş arşiv** | `bz2.Save`'den önce hiçbir giriş eklenmemiş | En az bir `CreateEntry` çağrısı ekleyin. |
| **İzin reddedildi** | Uygulamanın çıktı klasörüne yazma izni yok | Uygulamayı gerekli yetkilerle çalıştırın veya yazılabilir bir klasör seçin. |

## Sıkça sorulan sorular

**S: Aspose.Zip tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5/6 ve daha yeni çalışma zamanlarıyla çalışır.

**S: Birden fazla dosyayı aynı anda sıkıştırabilir miyim?**  
C: Kesinlikle. Arşivi kaydetmeden önce her dosya için `CreateEntry` çağırın.

**S: Ek belgeleri nerede bulabilirim?**  
C: Ayrıntılı belgeler **Aspose.Zip .NET API referansında** mevcuttur: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**S: Aspose.Zip için geçici bir lisans nasıl alabilirim?**  
C: Buradan **geçici bir lisans talep edebilirsiniz**: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**S: Ücretsiz bir deneme sürümü mevcut mu?**  
C: Evet, **Aspose sürümlerinden bir deneme sürümü indirebilirsiniz**: [download a trial version](https://releases.aspose.com/).

## Sonuç

Artık **dosyaları tar'a nasıl ekleyeceğinizi**, tar akışını Bzip2 ile sıkıştırıp Aspose.Zip for .NET kullanarak bir **TarBz2** arşivi oluşturmayı biliyorsunuz. Bu yöntem hızlı, bellek‑verimli ve tüm modern .NET platformlarında çalışır. Daha büyük dosya setleri, özel giriş adlarıyla denemeler yapabilir veya kodu kendi yedekleme ya da dağıtım hatlarınıza entegre edebilirsiniz.

Herhangi bir sorunla karşılaşırsanız, Aspose.Zip topluluğu yardımcı olmaya hazır—sadece **Aspose.Zip destek forumuna** gidin: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Son Güncelleme:** 2026-08-07  
**Test Edilen:** Aspose.Zip for .NET (latest release)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Zip for .NET ile tar arşivi oluşturma ve dosyaları tar'a ekleme](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip ile dosyaları tar'a ekleme ve tarxz arşivi oluşturma](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Aspose.Zip for .NET ile dosyaları tar'a ekleme ve TarZ ile sıkıştırma](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}