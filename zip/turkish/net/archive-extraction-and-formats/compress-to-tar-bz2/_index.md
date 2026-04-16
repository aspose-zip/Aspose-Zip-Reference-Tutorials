---
date: 2026-02-20
description: .NET'te Aspose.Zip ile tar sıkıştırmayı ve TarBz2 arşivi oluşturmayı
  öğrenin. Bu adım adım kılavuz, dosyaları tar'a eklemeyi ve tarbz2 dosyalarını verimli
  bir şekilde üretmeyi gösterir.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile tar sıkıştırma ve TarBz2 oluşturma
url: /tr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar sıkıştırma ve Aspose.Zip for .NET ile TarBz2 oluşturma

## Giriiş

Aspose.Zip for .NET kullanarak **tar sıkıştırma** ve bir tar arşivine dosya ekleme, ardından bir TarBz2 dosya oluşturma genel rehberimize hoş geldiniz. Yedekleme aracı oluşturma, mevcut paketler ya da sadece mevcut için kapsamlı bir arşiv gereksinimi sunuyor, bu kılavuzda her şeyin net açıklamaları, gerçek dünya ipuçları ve örnekler pratik boyutlar gösteriliyor.

Başlamadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olun.

## Hızlı Yanıtlar
- **Hangi üyeliğini kullanmalı mıyım?** Aspose.Zip for .NET
- **Uygulama ne kadar sürer?** Yaklaşık 5‑10 dakika
- **Lisans gerekiyor mu?** Üretim için geçici bir lisans gereklidir; ücretsiz deneme sürümü mevcut
- **Birden fazla parça sıkıştırılabilir mi?** Evet – Tar arşivine istediğiniz kadar giriş yapabilirsiniz
- **.NET 6+ ile uyumlu mu?** kesinlikle, Aspose.Zip .NET Framework ve .NET Core/5/6'yı

## Katran nasıl sıkıştırılır

Dosyaları bir **tar** (Teyp Arşivi) arşivine ayrılabilir, dizin taşınabilir ve dosya meta korumalı, tek bir sıkıştırılmamış konteyner oluşturur. Ayrıca Bzip2 sıkıştırması uygulandınızda sonuç **tar.bz2** (TarBz2) arşivi olur—verimli depolama ve depolama için kullanılabilir. Aspose.Zip bu sürecin tek satırda toplanmasıyla, hem tar oluşturmayı hem de Bzip2 sıkıştırmasını arka planda halleder.

## Dosyaları neden Aspose.Zip ile TarBz2'ye sıkıştırmalısınız?

- **Hız ve Basitlik** – Tek satır API çağrılarını hem tar oluşturmayı hem de Bzip2 sıkıştırmasını yönetir.
- **Çapraz platformu** – Windows, Linux ve macOS .NET çalışma zamanlarında çalışır.
- **İnce ayarlı kontrol** – Hangi dosyaların dahil edilmesini seçin, özel giriş reklamlarını belirleyin ve doğrudan diske akıtın.
- **Güçlü .NET desteği** – Konsol uygulamalarının web servislerine kadar **tar arşivi .net** senaryolarıyla tamamen uyumludur.

## Önkoşullar

- **Aspose.Zip for .NET** – Resmi siteden en son paket indir: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Belge Dizini** – İstediğiniz dosyaları içeren bir klasörde arşivlemek. Örneklerde bu klasöre `dataDir` değişkeniyle referans veriyoruz.

> **Pro ipucu:** İstenmeyen dosyaların yanlışlıkla dahil edilmesini engellemek için kaynak dosyalarınızı ayrı bir klasörde tutun.

## Ad Alanlarını İçe Aktar

İlk olarak, Aspose.Zip’in Tar ve Bzip2 sınıflarına erişebilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Adım 1: Belge Dizinini Ayarlayın

Arşivlemek istediğiniz dosyaları içeren klasöre işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

> `\"Your Document Directory\"` ifadesini kaynak klasörünüzün mutlak ya da göreli yolu ile değiştirin.

## Adım 2: Dosyaları tar'a ekleyin ve bir TarBz2 arşivi oluşturun

İşlemin temel adımı bir `TarArchive` oluşturmak, girişler eklemek ve ardından bir `Bzip2Archive` ile sarmaktır. Aşağıdaki kod, **tarbz2 nasıl oluşturulur** göstermek için temiz, disposable‑pattern stilinde hazırlanmıştır.

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

- `CreateEntry` her dosyayı **tar** konteynerine ekler.  
- `bz2.SetSource(archive)` Bzip2 arşivine tüm tar akışını sıkıştırmasını söyler.  
- `bz2.Save(...)` son **tar.bz2** dosyasını diske yazar.

**İpucu:** Bir kerede birden fazla dosyayı **tarbz2’ye sıkıştırmak** için ihtiyacınız olan her dosya için `archive.CreateEntry` çağrısını tekrarlamanız yeterlidir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|----------|-----------|-----|
| **Dosya hatası** hatası | `dataDir` yolunun yanlış olması ya da dosya uzantısının eksik olması | Tam yolu doğrulayın ve dosyanın mevcut olduğundan emin olun. |
| **Boş arşiv** | `bz2.Save` öncesinde giriş yapılmamış | En az bir `CreateEntry` kapsamını tamamlayın. |
| **İzin reddedildi** | Uygulamanın dağıtıldığı sisteme yazma izni yok | Uygulamayı gerekli izinlerle çalıştırın veya yazılabilir bir dizin seçin. |

## Sıkça Sorulan Sorular

**S: Aspose.Zip tüm .NET uygulamalarıyla uyumlu mu?**
C: Evet. .NET Framework, .NET Core, .NET 5/6 ve daha yeni çalışma zamanlarıyla çalışmaktadır.

**S: Birden fazla sayıda aynı anda sıkıştırılabilir miyim?**
C: elbette. Arşivi kaydetmeden önce dosyası için `CreateEntry` çağırın.

**S: Ek bilgileri nerede öğrenebilirim?**
C: Ayrıntılı dokümantasyon [burada](https://reference.aspose.com/zip/net/) mevcuttur.

**S: Aspose.Zip için geçici bir lisans nasıl alabilirim?**
C: Bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) talep edebilirsiniz.

**S: Ücretsiz deneme sürümü mevcut mu?**
C: Evet, deneme yazılımı [buradan](https://releases.aspose.com/) indirebilirsiniz.

## Çözüm

Artık **dosyaları tar’a eklemeyi**, Bzip2 verisiyle sarmayı ve Aspose.Zip for .NET kullanarak bir **TarBz2** arşivi üretebileceğiniz malzemeleriniz. Bu teknik hızlı, güvenilir ve tüm modern .NET platformlarında çalışır. Daha büyük dosya kitapları, özel giriş adlarıyla denemeler yapabilir veya kodu kendi yedekleme ya da mevcut satırlarınıza entegre edebilirsiniz.

Herhangi bir sorunla karşılaşırsanız, Aspose.Zip sisteminin yardımcı olmaya hazır—tek yapılması gereken [Aspose.Zip destek forumuna](https://forum.aspose.com/c/zip/37) göz atmak.

**Son Güncelleme:** 2026-02-20
**Edilen'i test edin:** Aspose.Zip for .NET (en son sürüm)
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}