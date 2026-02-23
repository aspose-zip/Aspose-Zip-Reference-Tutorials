---
date: 2026-02-23
description: Aspose.Zip for .NET kullanarak birden fazla dosyayı tar ile sıkıştırmayı
  ve tar.lz arşivlerini verimli bir şekilde oluşturmayı öğrenin.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile birden fazla dosyayı tar olarak sıkıştırma
url: /tr/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET ile birden fazla dosyayı tar sıkıştırma

Modern .NET geliştirmede, dosyaları verimli bir şekilde paketlemek dağıtım boyutunu ve ağ aktarım sürelerini büyük ölçüde iyileştirebilir. **Birden fazla dosyayı tar sıkıştırma** hafif, LZ‑sıkıştırmalı bir TAR arşivi yedeklemeler, dağıtım veya bulut yüklemeleri için sıkça ihtiyaç duyulan bir durumdur. Bu öğreticide, Aspose.Zip kütüphanesini kullanarak net, adım‑adım bir **tar.lz sıkıştırma örneği** üzerinden geçeceğiz, böylece kendi uygulamalarınızda hızlıca bir **tar.lz arşivi** oluşturabilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 5‑10 dakika.  
- **Lisans gerekli mi?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gerekir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Birden fazla dosyayı aynı anda sıkıştırabilir miyim?** Evet – kaydetmeden önce daha fazla giriş ekleyin.

## Birden fazla dosyayı tar sıkıştırma
Bu bölüm, birincil anahtar kelimeyi doğrudan ele alır ve Aspose.Zip kullanarak **birden fazla dosyayı tar sıkıştırma** işleminin tam adımlarını gösterir. Yaklaşım, herhangi bir dosya sayısı için çalışır ve kendi klasör yapınıza kolayca uyarlayabilirsiniz.

## tar.lz sıkıştırması nedir?
`tar.lz` LZMA algoritması (genellikle sadece **LZ** olarak anılır) kullanılarak sıkıştırılmış bir TAR arşividir. TAR'ın dosya gruplama basitliğini yüksek sıkıştırma oranı sağlayan LZ ile birleştirir, bu da yedek dosyaları, paket dağıtımı veya bant genişliğinin önemli olduğu herhangi bir senaryo için idealdir.

## Neden Aspose.Zip for .NET kullanmalı?
* **Sıfır dış bağımlılık** – saf .NET uygulaması.  
* **Çapraz platform desteği** – Windows, Linux ve macOS'ta çalışır.  
* **Yerleşik LZ sıkıştırması** – ek yerel araçlar kurmaya gerek yok.  
* **Güçlü hata yönetimi** – istisnalar açıklayıcıdır, hata ayıklamayı kolaylaştırır.

## Önkoşullar
Başlamadan önce, şunların olduğundan emin olun:

- **Aspose.Zip for .NET** kütüphanesi – [buradan](https://releases.aspose.com/zip/net/) indirin.  
- Arşivlemek istediğiniz dosyaları içeren bir klasör. Bu klasörün yolu `dataDir` değişkeninde saklanacak (Adım 3'te ayarlayacaksınız).

## Ad Alanlarını İçe Aktarma
Kompilatörün kullanacağımız sınıfları nerede bulacağını bilmesi için gerekli ad alanlarını ekleyin.

```csharp
using System;
using Aspose.Zip.Tar;
```

## tar.lz arşivi oluşturma – Adım‑Adım Kılavuz

### Adım 1: Tek bir dosyayı sıkıştırma
İlk örnek en temel senaryoyu gösterir – bir dosyayı TAR arşivine ekleyip ardından **tar.lz** dosyası olarak kaydetmek.

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
- `CreateEntry` `dataDir` içindeki `alice29.txt` dosyasını ekler.  
- `SaveLzipped` arşivi diske yazar ve LZ sıkıştırması uygular, `archive.tar.lz` oluşturur.

### Adım 2: Tek bir arşivde birden fazla dosyayı sıkıştırma
Genellikle birkaç dosyayı bir araya getirmeniz gerekir. Kaydetmeden önce her dosya için `CreateEntry` çağırın. Bu, **tar lz'ye dosya ekleme** ve etkili bir şekilde **birden fazla dosyayı tar sıkıştırma** gösterir.

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
- İhtiyacınız kadar `CreateEntry` tekrarlayabilirsiniz; kütüphane iç TAR yapısını otomatik olarak yönetir.

### Adım 3: Belge dizininizi belirtin
Yer tutucuyu, kaynak dosyalarınızın bulunduğu gerçek yol ile değiştirin. Bu yol, yukarıdaki örnekler tarafından kullanılır.

```csharp
string dataDir = "Your Document Directory";
```

**Açıklama**

- `dataDir` değişkenini tam nitelikli bir klasör yolu olarak ayarlayın, ör. `@"C:\\MyFiles\\"`.  
- Dizini bir değişkende tutmak kodun yeniden kullanılabilir ve bakımını kolaylaştırır.

## Yaygın tuzaklar ve sorun giderme
| Semptom | Muhtemel neden | Çözüm |
|---------|----------------|-------|
| Örneği çalıştırırken `FileNotFoundException` | `dataDir` var olmayan bir klasöre işaret ediyor veya dosya adı yanlış yazılmış | Yolu ve dosya adlarını doğrulayın; güvenlik için `Path.Combine` kullanın. |
| Çıktı dosyası **0 KB** | `archive.SaveLzipped` herhangi bir giriş eklenmeden önce çağrıldı | En az bir `CreateEntry` çağrısının `SaveLzipped`'den önce yapıldığından emin olun. |
| Sıkıştırma yavaş görünüyor | Varsayılan tampon boyutuyla büyük dosyalar | Performans kritikse dosyaları parçalar halinde işleme veya asenkron I/O kullanmayı düşünün. |

## Sonuç
Artık Aspose.Zip for .NET kullanarak **tar.lz nasıl sıkıştırılır** dosyalarını nasıl sıkıştıracağınızı biliyorsunuz, tek bir belge ya da bir dosya koleksiyonu ile çalışıyor olun. Bu **tar.lz sıkıştırma örneği** temiz, üretim‑hazır bir şekilde **tar lz arşivi oluşturma** dosyaları oluşturmayı gösterir; bu dosyalar kolayca aktarılabilir veya depolanabilir.

## Sıkça Sorulan Sorular

**Q:** Aspose.Zip for .NET kullanarak herhangi bir boyutta dosyayı sıkıştırabilir miyim?  
**A:** Evet, kütüphane hem küçük hem de çok büyük dosyaları yönetir; sadece geçici TAR yapısı için yeterli bellek ve disk alanına sahip olduğunuzdan emin olun.

**Q:** Kod, en son Aspose.Zip sürümüyle uyumlu mu?  
**A:** Örnek mevcut sürümü hedef alır; hata düzeltmeleri ve yeni özellikler için NuGet paketini her zaman güncel tutun.

**Q:** Lisans konuları var mı?  
**A:** Üretim kullanımı için ticari bir lisans gereklidir. Lisans detayları için [Aspose web sitesindeki](https://purchase.aspose.com/buy) lisanslama bölümüne bakın.

**Q:** Bunu ticari bir projede kullanabilir miyim?  
**A:** Kesinlikle – geçerli bir lisansınız olduğunda, kütüphaneyi herhangi bir ticari uygulamaya entegre edebilirsiniz.

**Q:** Sorun yaşarsam nereden yardım alabilirim?  
**A:** Topluluk desteği ve resmi yardım için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen:** Aspose.Zip for .NET (son sürüm)  
**Yazar:** Aspose