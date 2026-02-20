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

## Introduction

Aspose.Zip for .NET kullanarak **tar sıkıştırma** ve bir tar arşivine dosya ekleme, ardından bir TarBz2 dosyası oluşturma konusundaki kapsamlı rehberimize hoş geldiniz. Yedekleme aracı oluşturuyor, dağıtım paketleri sunuyor ya da sadece dağıtım için kompakt bir arşiv ihtiyacınız varsa, bu öğretici her adımı net açıklamalar, gerçek dünya ipuçları ve pratik örneklerle size gösterir.

Başlamadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.

## Quick Answers
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET
- **Uygulama ne kadar sürer?** Yaklaşık 5‑10 dakika
- **Lisans gerekiyor mu?** Üretim için geçici bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur
- **Birden fazla dosyayı sıkıştırabilir miyim?** Evet – Tar arşivine istediğiniz kadar giriş ekleyebilirsiniz
- **.NET 6+ ile uyumlu mu?** Kesinlikle, Aspose.Zip .NET Framework ve .NET Core/5/6'yı destekler

## How to compress tar

Dosyaları bir **tar** (Tape Archive) arşivine eklemek, dizin yapısını ve dosya meta verilerini koruyan tek bir sıkıştırılmamış konteyner oluşturur. Ardından Bzip2 sıkıştırması uyguladığınızda sonuç **tar.bz2** (TarBz2) arşivi olur—verimli depolama ve aktarım için idealdir. Aspose.Zip bu süreci tek satırda gerçekleştirir, hem tar oluşturmayı hem de Bzip2 sıkıştırmasını arka planda halleder.

## Why compress files to TarBz2 with Aspose.Zip?

- **Hız ve Basitlik** – Tek satır API çağrıları hem tar oluşturmayı hem de Bzip2 sıkıştırmasını yönetir.  
- **Çapraz platform** – Windows, Linux ve macOS .NET çalışma zamanlarında çalışır.  
- **İnce ayarlı kontrol** – Hangi dosyaların dahil edileceğini seçin, özel giriş adları belirleyin ve doğrudan diske akıtın.  
- **Güçlü .NET desteği** – Konsol uygulamalarından web servislerine kadar **tar archive .net** senaryolarıyla tamamen uyumludur.

## Prerequisites

- **Aspose.Zip for .NET** – Resmi siteden en son paketi indirin: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – Arşivlemek istediğiniz dosyaları içeren bir klasör. Örneklerde bu klasöre `dataDir` değişkeniyle referans veriyoruz.

> **Pro ipucu:** İstenmeyen dosyaların yanlışlıkla dahil edilmesini önlemek için kaynak dosyalarınızı ayrı bir klasörde tutun.

## Import Namespaces

İlk olarak, Aspose.Zip’in Tar ve Bzip2 sınıflarına erişebilmek için gerekli ad alanlarını içe aktarın.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Step 1: Set the Document Directory

Arşivlemek istediğiniz dosyaları içeren klasöre işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

> `\"Your Document Directory\"` ifadesini kaynak klasörünüzün mutlak ya da göreli yolu ile değiştirin.

## Step 2: Add files to tar and create a TarBz2 archive

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

## Common Issues & Solutions

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** hatası | `dataDir` yolunun yanlış olması ya da dosya uzantısının eksik olması | Tam yolu doğrulayın ve dosyanın mevcut olduğundan emin olun. |
| **Boş arşiv** | `bz2.Save` öncesinde giriş eklenmemiş | En az bir `CreateEntry` çağrısı ekleyin. |
| **İzin reddedildi** | Uygulamanın çıktı klasörüne yazma izni yok | Uygulamayı gerekli izinlerle çalıştırın veya yazılabilir bir dizin seçin. |

## Frequently Asked Questions

**S: Aspose.Zip tüm .NET uygulamalarıyla uyumlu mu?**  
C: Evet. .NET Framework, .NET Core, .NET 5/6 ve daha yeni çalışma zamanlarıyla çalışır.

**S: Birden fazla dosyayı aynı anda sıkıştırabilir miyim?**  
C: Kesinlikle. Arşivi kaydetmeden önce her dosya için `CreateEntry` çağırın.

**S: Ek belgeleri nerede bulabilirim?**  
C: Ayrıntılı dokümantasyon [burada](https://reference.aspose.com/zip/net/) mevcuttur.

**S: Aspose.Zip için geçici bir lisans nasıl alabilirim?**  
C: Bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) talep edebilirsiniz.

**S: Ücretsiz deneme sürümü mevcut mu?**  
C: Evet, deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

## Conclusion

Artık **dosyaları tar’a eklemeyi**, Bzip2 akışıyla sarmayı ve Aspose.Zip for .NET kullanarak bir **TarBz2** arşivi üretmeyi öğrendiniz. Bu teknik hızlı, güvenilir ve tüm modern .NET platformlarında çalışır. Daha büyük dosya setleri, özel giriş adlarıyla denemeler yapabilir veya kodu kendi yedekleme ya da dağıtım hatlarınıza entegre edebilirsiniz.

Herhangi bir sorunla karşılaşırsanız, Aspose.Zip topluluğu yardımcı olmaya hazır—tek yapmanız gereken [Aspose.Zip destek forumuna](https://forum.aspose.com/c/zip/37) göz atmak.

**Son Güncelleme:** 2026-02-20  
**Test Edilen:** Aspose.Zip for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}