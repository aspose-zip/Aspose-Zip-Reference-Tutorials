---
date: 2026-04-24
description: .NET'te Aspose.Zip ile tar sıkıştırmayı ve TarBz2 arşivi oluşturmayı
  öğrenin. Bu adım adım rehber, dosyaları tar'a eklemeyi ve tarbz2 dosyalarını verimli
  bir şekilde üretmeyi gösterir.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: TarBz2'ye Sıkıştırma
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile tar sıkıştırma ve TarBz2 oluşturma
url: /tr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tar sıkıştırma ve Aspose.Zip for .NET ile TarBz2 oluşturma

## Giriş

Bu öğreticide **tar sıkıştırma** arşivlerini nasıl sıkıştıracağınızı ve **Aspose.Zip** .NET kütüphanesini kullanarak kompakt bir **TarBz2** dosyasına nasıl dönüştüreceğinizi keşfedeceksiniz. Yedekleme aracı oluşturuyor, dağıtım paketleri yayımlıyor ya da sadece dağıtım için hafif bir paket ihtiyacınız olsun, aşağıdaki adımlar tar'a dosya eklemeyi, Bzip2 sıkıştırmasını uygulamayı ve paylaşmaya hazır bir arşiv üretmeyi size gösterecek.

İlerlemeye başlamadan önce, bu kılavuzda daha sonra listelenen önkoşullara sahip olduğunuzdan emin olun, böylece sorunsuz bir şekilde takip edebilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET  
- **Uygulama ne kadar sürer?** Yaklaşık 5‑10 dakika  
- **Lisans gerekli mi?** Üretim için geçici bir lisans gerekir; ücretsiz deneme mevcuttur  
- **Birden fazla dosyayı sıkıştırabilir miyim?** Evet – tar arşivine istediğiniz kadar giriş ekleyebilirsiniz  
- **.NET 6+ ile uyumlu mu?** Kesinlikle, Aspose.Zip .NET Framework ve .NET Core/5/6'yı destekler  

## TarBz2 arşivi nedir?

**TarBz2** dosyası, geleneksel **tar** konteynerini (dizin yapısını ve dosya meta verilerini korur) **Bzip2** sıkıştırmasıyla birleştirir ve yüksek sıkıştırmalı bir `.tar.bz2` paketi oluşturur. Bu format, sıkıştırma oranı ile açma hızı arasında iyi bir denge sunduğu için Unix benzeri sistemlerde popülerdir.

## Neden dosyaları TarBz2 ile Aspose.Zip kullanarak sıkıştırmalısınız?

- **Hız ve Basitlik** – Tek satır API çağrıları hem tar oluşturmayı hem de Bzip2 sıkıştırmasını yönetir.  
- **Çapraz platform** – Windows, Linux ve macOS .NET çalışma zamanlarında çalışır.  
- **İnce ayarlı kontrol** – Hangi dosyaların dahil edileceğini seçin, özel giriş adları belirleyin ve doğrudan diske akıtın.  
- **Güçlü .NET desteği** – Konsol uygulamalarından web servislerine kadar **tar archive .net** senaryoları için mükemmeldir.  

## Önkoşullar

- **Aspose.Zip for .NET** – Resmi siteden en son paketi indirin: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – Arşivlemek istediğiniz dosyaları içeren bir klasör. Örneklerde bu klasöre `dataDir` değişkeniyle atıfta bulunuyoruz.

> **Pro ipucu:** İstenmeyen dosyaların yanlışlıkla dahil edilmesini önlemek için kaynak dosyalarınızı ayrı bir klasörde tutun.

## Ad Alanlarını İçe Aktarın

İlk olarak, Aspose.Zip’in Tar ve Bzip2 sınıflarına erişebilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Adım 1: Document Directory'yi Ayarla

Arşivlemek istediğiniz dosyaları içeren klasöre işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` ifadesini kaynak klasörünüzün mutlak ya da göreli yolu ile değiştirin.

## Adım 2: Dosyaları tar'a ekleyin ve bir TarBz2 arşivi oluşturun

İşlemin temel kısmı bir `TarArchive` oluşturmak, girişler eklemek ve ardından bir `Bzip2Archive` ile sarmaktır. Aşağıdaki kod, **tar nasıl oluşturulur** ve **TarBz2**'ye nasıl sıkıştırılır gösteren temiz, disposable‑pattern stilinde bir örnek sunar.

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

- `CreateEntry` **tar'a dosya ekler** – arşivde ihtiyaç duyduğunuz her dosya için bu yöntemi çağırabilirsiniz.  
- `bz2.SetSource(archive)` Bzip2 arşivine tüm tar akışını sıkıştırmasını söyler.  
- `bz2.Save(...)` son **TarBz2** dosyasını diske yazar.

**İpucu:** Toplu olarak **tar'a dosya eklemek** için, `bz2.Save` çağırmadan önce her dosya için `archive.CreateEntry` komutunu tekrarlamanız yeterlidir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** hatası | `dataDir` yolu yanlış veya dosya uzantısı eksik | Tam yolu doğrulayın ve dosyanın mevcut olduğundan emin olun. |
| **Boş arşiv** | `bz2.Save` öncesinde giriş eklenmemiş | En az bir `CreateEntry` çağrısı ekleyin. |
| **İzin reddedildi** | Uygulamanın çıktı klasörüne yazma izni yok | Uygulamayı uygun yetkilerle çalıştırın veya yazılabilir bir dizin seçin. |

## Sıkça Sorulan Sorular

**S: Aspose.Zip tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5/6 ve daha yeni çalışma zamanlarıyla çalışır.

**S: Birden fazla dosyayı aynı anda sıkıştırabilir miyim?**  
C: Kesinlikle. Arşivi kaydetmeden önce her dosya için `CreateEntry` çağırın.

**S: Ek belgeleri nerede bulabilirim?**  
C: Ayrıntılı belgeler [burada](https://reference.aspose.com/zip/net/) mevcuttur.

**S: Aspose.Zip için geçici bir lisans nasıl alabilirim?**  
C: Bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) talep edebilirsiniz.

**S: Ücretsiz deneme mevcut mu?**  
C: Evet, deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

## Sonuç

Artık **tar sıkıştırma** yöntemini, dosyaları eklemeyi ve sonucu bir Bzip2 akışıyla sarmalayarak **TarBz2** arşivi üretmeyi Aspose.Zip for .NET kullanarak öğrendiniz. Bu yaklaşım hızlı, güvenilir ve tüm modern .NET platformlarında çalışır. Daha büyük dosya setleri, özel giriş adlarıyla denemeler yapabilir veya kodu kendi yedekleme ya da dağıtım hatlarınıza entegre edebilirsiniz.

Herhangi bir sorunla karşılaşırsanız, Aspose.Zip topluluğu yardımcı olmaya hazır—sadece [Aspose.Zip destek forumuna](https://forum.aspose.com/c/zip/37) gidin.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}