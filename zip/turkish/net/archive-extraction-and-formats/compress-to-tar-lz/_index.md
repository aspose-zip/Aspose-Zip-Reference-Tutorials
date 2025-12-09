---
date: 2025-12-01
description: Aspose.Zip ile .NET’te tar.lz dosyalarını nasıl sıkıştıracağınızı öğrenin
  ve tar.lz arşivini kolayca oluşturun.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile tar.lz nasıl sıkıştırılır
url: /tr/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tar.lz dosyasını Aspose.Zip for .NET ile nasıl sıkıştırılır

Modern .NET geliştirmesinde, dosyaları verimli bir şekilde paketlemek dağıtım boyutunu ve ağ aktarım sürelerini büyük ölçüde iyileştirebilir. **tar.lz nasıl sıkıştırılır** hafif, LZ‑sıkıştırmalı bir TAR arşivi gerektiğinde yaygın bir gereksinimdir. Bu öğreticide, Aspose.Zip kütüphanesini kullanarak net, adım‑adım bir **tar.lz sıkıştırma örneği** üzerinden geçeceğiz, böylece kendi uygulamalarınızda hızlıca bir tar.lz arşivi oluşturabilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.  
- **Lisans gerekli mi?** Ücretsiz deneme testi için yeterlidir; üretim için ticari lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Birden fazla dosyayı aynı anda sıkıştırabilir miyim?** Evet – kaydetmeden önce daha fazla giriş ekleyin.

## tar.lz sıkıştırması nedir?
`tar.lz`, LZMA algoritması (genellikle sadece **LZ** olarak adlandırılır) kullanılarak sıkıştırılmış bir TAR arşividir. TAR'ın dosya gruplama basitliğini yüksek sıkıştırma oranı sağlayan LZ ile birleştirir, bu da yedekleme dosyaları, paket dağıtımı veya bant genişliğinin önemli olduğu herhangi bir senaryo için idealdir.

## Neden Aspose.Zip for .NET kullanmalı?
Aspose.Zip, arşiv oluşturmanın düşük seviyeli detaylarını soyutlayarak temiz, nesne‑yönelimli bir API sunar. Şunları elde edersiniz:

* **Sıfır dış bağımlılık** – saf .NET uygulaması.  
* **Çapraz platform desteği** – Windows, Linux ve macOS'ta çalışır.  
* **Yerleşik LZ sıkıştırması** – ek yerel araçlar kurmaya gerek yok.  
* **Güçlü hata yönetimi** – istisnalar açıklayıcıdır, hata ayıklamayı kolaylaştırır.

## Önkoşullar
Başlamadan önce şunların yüklü olduğundan emin olun:

- **Aspose.Zip for .NET** kütüphanesi – [buradan](https://releases.aspose.com/zip/net/) indirin.  
- Arşivlemek istediğiniz dosyaları içeren bir klasör. Bu klasörün yolu `dataDir` değişkeninde saklanacak (Adım 3'te ayarlayacaksınız).

## Ad Alanlarını İçe Aktarın
Kullanacağımız sınıfların nerede olduğunu derleyicinin bilmesi için gerekli ad alanlarını ekleyin.

```csharp
using System;
using Aspose.Zip.Tar;
```

## tar.lz arşivi nasıl oluşturulur – Adım‑Adım Kılavuz

### Adım 1: Tek bir dosyayı sıkıştır
İlk örnek, en temel senaryoyu gösterir – bir dosyayı bir TAR arşivine ekleyip ardından **tar.lz** dosyası olarak kaydetmek.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Açıklama**

- `new TarArchive()` boş bir TAR konteyneri oluşturur.  
- `CreateEntry` dosyanızı `dataDir` içindeki `alice29.txt` dosyasını ekler.  
- `SaveLzipped` arşivi diske yazar ve LZ sıkıştırması uygular, `archive.tar.lz` oluşturur.

### Adım 2: Tek bir arşivde birden fazla dosyayı sıkıştır
Genellikle birkaç dosyayı bir arada paketlemeniz gerekir. Kaydetmeden önce her dosya için `CreateEntry` çağırmanız yeterlidir.

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

- Kod, Adım 1 ile aynı deseni izler, ancak ikinci bir giriş (`lcet10.txt`) ekler.  
- `CreateEntry`'yi ihtiyacınız kadar tekrarlayabilirsiniz; kütüphane iç TAR yapısını otomatik olarak yönetir.

### Adım 3: Belge dizininizi belirtin
Yer tutucuyu, kaynak dosyalarınızın bulunduğu gerçek yol ile değiştirin. Bu yol, yukarıdaki örneklerde kullanılır.

```csharp
string dataDir = "Your Document Directory";
```

**Açıklama**

- `dataDir`'yi tam nitelikli bir klasör yolu olarak ayarlayın, ör. `@"C:\\MyFiles\\"`.  
- Dizini bir değişkende tutmak kodun yeniden kullanılabilir ve bakımını kolaylaştırır.

## Yaygın tuzaklar ve sorun giderme
| Belirti | Muhtemel neden | Çözüm |
|---------|----------------|-------|
| `FileNotFoundException` örnek çalıştırılırken | `dataDir` mevcut olmayan bir klasöre işaret ediyor ya da dosya adı hatalı yazılmış | Yolu ve dosya adlarını doğrulayın; güvenlik için `Path.Combine` kullanın. |
| Çıktı dosyası **0 KB** | `archive.SaveLzipped` herhangi bir giriş eklenmeden önce çağrıldı | En az bir `CreateEntry` çağrısının `SaveLzipped`'den önce yapıldığından emin olun. |
| Sıkıştırma yavaş görünüyor | Varsayılan tampon boyutuyla büyük dosyalar | Performans kritikse dosyaları parçalar halinde işleme veya asenkron I/O kullanmayı düşünün. |

## Sonuç
Artık **tar.lz dosyalarını nasıl sıkıştıracağınızı** Aspose.Zip for .NET kullanarak, tek bir belge ya da bir dosya koleksiyonu ile çalışıyor olun, biliyorsunuz. Bu **tar.lz sıkıştırma örneği**, kolayca aktarılabilen veya depolanabilen hafif arşivler oluşturmanın temiz, üretim‑hazır bir yolunu gösterir.

## Sıkça Sorulan Sorular

**S:** Aspose.Zip for .NET ile herhangi bir boyutta dosyayı sıkıştırabilir miyim?  
**C:** Evet, kütüphane hem küçük hem de çok büyük dosyaları yönetir; sadece geçici TAR yapısı için yeterli bellek ve disk alanına sahip olduğunuzdan emin olun.

**S:** Kod, en son Aspose.Zip sürümüyle uyumlu mu?  
**C:** Örnek mevcut sürümü hedef alır; hata düzeltmeleri ve yeni özellikler için NuGet paketini her zaman güncel tutun.

**S:** Lisans konuları var mı?  
**C:** Üretim kullanımı için ticari bir lisans gereklidir. Lisans detayları için [Aspose web sitesine](https://purchase.aspose.com/buy) bakın.

**S:** Bunu ticari bir projede kullanabilir miyim?  
**C:** Kesinlikle – geçerli bir lisansınız olduğunda, kütüphaneyi herhangi bir ticari uygulamaya entegre edebilirsiniz.

**S:** Sorun yaşarsam nereden yardım alabilirim?  
**C:** Topluluk desteği ve resmi yardım için [Aspose.Zip forumuna](https://forum.aspose.com/c/zip/37) göz atın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2025-12-01  
**Test Edilen:** Aspose.Zip for .NET (son sürüm)  
**Yazar:** Aspose