---
date: 2026-02-02
description: Aspose.Zip ile .NET’te tar.lz dosyalarını nasıl sıkıştıracağınızı öğrenin
  – tar.lz arşivlerini kolayca sıkıştırmak için adım adım bir rehber.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile tar.lz nasıl sıkıştırılır
url: /tr/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET ile tar.lz nasıl sıkıştırılır

Modern .NET geliştirmesinde, dosyaları verimli bir şekilde paketlemek dağıtım boyştirebilir. **tar.lz sıkıştırması** hafif, LZ‑sıkıştırmalı bir TAR arşivi ihtiyacınız olduğunda yaygın bir gereksinimdir. Bu öğreticide, Aspose.Zip kütüphanesğiz; böylece kendi uygulamalarınızda hızlıca bir tar.lz arşivi oluşturabilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılmalı?** Aspose.Zip for .NET.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.  
- **Lisans gerekli mi?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, fazla dosyayı aynı anda sıkıştırabilir miyim?** Evet – kaydetmeden önce daha fazla giriş ekleyin.

## tar.lz sıkıştırması nedir?
`tar.lz` LZMA algoritması (genellikle sadece **LZ** olarak anılır) kullanılarak sıkıştırılmış bir TAR arşividir. TAR birleştirir; bu da yedekleme dosyaları, paket dağıtımı veya bant genişliğinin kritik olduğu senaryolar için idealdir.

## Aspose.Zip for .NET neden kullanılmalı?
Aspose.Zip, arşiv oluşturmanın düşük seviyeli ayrıntılarını soyutlayarak temiz, nesne‑yönelimli bir API sunar. Şunları elde edersiniz:

* **Sıfır dış bağımlılık** – saf .NET uygulaması.  
* **Çapraz platform desteği** – Windows, Linuxik LZ sıkıştırması** – ek yerel araçlar kurmaya gerek yok.  
* **Güçlü hata yönetimi** – istisnalar açıklayıcıdır, hata ayıklamayı kolaylaştırır.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

- **Aspose.Zip for .NET** kütüphanesi – [buradan](https://releases.aspose bir klasör. Bu klasörün saklanacaktır (3. adımda ayarlayacaksınız).

abilmesi için gerekli namespace’leri ekleyin.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Aspose.Zip ile tar.lz sıkıştırma – Adım Adım Kılavuz

### Adım 1: tar.lz arşivi TAR arşivine ekleyip ardından **tar.lz** dosyası olarak kaydetmek.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Açıklama**

- `new TarArchive()` boş bir TAR konteynerialice29.txt` dosyasını ekler.  
- `SaveLzipped` arşivi diske yazar ve LZ sıkıştırması uygular, `archive.tar.lz` oluşturur.

### Adım 2: Birden çok dosyayı tar.lz ile sıkıştır – birkaç giriş ekle
Genellikle birden fazla dosyayı bir arada paketlemeniz gerekir. Kaydetmeden önce her dosya için `CreateEntry` çağırın.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Açıklama**

- Kod, Adım 1 ile aynı desenı izler, ancak ikinci bir giriş (`lcet10.txt`) ekler.  
- `CreateEntry`’yi ihtiyacınız kadar tekrarlayabilirsiniz; kütüphane iç TAR yapısını otomatik olarak yönetir.

### Adım 3: Belge dizininizi belirtin – tar.lz arşivi oluşturma yolu
Yer tutucuyu, kaynak dosyalarınızın bulunduğu gerçek yol ile değiştirin. Bu yol, yukarıdaki örneklerde kullanılır.

```csharp
string dataDir = "Your Document Directory";
```

**Açıklama**

- `dataDir` değişkenine tam nitelikli klasör yolu atayın, ör. `@"C:\MyFiles\"`.  
- Dizini bir değişkende tutmak kodun yeniden kullanılabilirliğini ve bakımını kolaylaştırır.

## Yaygın tuzaklar ve sorun giderme
| Belirti | Muhtemel neden | Çözüm |
|---------|----------------|------|
| `FileNotFoundException` örnek çalıştırılırken | `dataDir` var olmayan bir klasöre işaret ediyor veya dosya adı hatalı | Yol ve dosya adlarını doğrulayın; güvenlik için `Path.Combine` kullanın. |
| Çıktı dosyası **0 KB** | `archive.SaveLzipped` hiçbir giriş eklenmeden çağrıldı | `SaveLzipped`’den önce en az bir `CreateEntry` çağrısı olduğundan emin olun. |
| Sıkıştırma yavaş görünü veya asenkron I/O kullanın. |

## Sıkça Sorulan Sorular

**S:** Aspose.Zip for .NET ile herhangi bir boyutta dosya sıkıştırabilir miyim?  
**C:** Evet, kütüphane hem küçük hem de çok büyük dosyaları yönetir; sadece geçici TAR yapısı için yeterli bellek ve disk alanınızın olduğundan emin olun düzeltmeleri ve yeni özellikler için NuGet paketini her zaman güncel tutun.

**S:** Lisans konuları nasıl?  
**C:** Üretim kullanımı için ticari lisans gerekir. Detaylar için [Aspose web sitesindeki lisans sayfasına](https://purchase.aspose.com/buy) bakın.

**S:** Bu kodu ticari bir projede kullanabilir miyim?  
**C:** Kesinlikle – geçerli bir lisansınız olduğunda kütüphaneyi herhangi bir ticari uygulamaya entegre edebilirsiniz.

**S:** Sorun yaşarsam nereden destek alabilirim?  
**C:** Topluluk desteği ve resmi yardım için [Aspose.Zip forumuna](https://forum.aspose.com/c/zip/37) göz atın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-02-02  
**Test Edilen Versiyon:** Aspose.Zip for .NET (en son sürüm)  
**Yazar:** Aspose  

---