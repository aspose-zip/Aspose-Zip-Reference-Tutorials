---
date: 2026-02-28
description: Aspose.Zip for .NET kullanarak bir klasörü zip'e eklemeyi ve dosyaları
  zip'e eklemeyi öğrenin. Bu adım adım kılavuz, ASP.NET projelerinde FileInfo ile
  dosyaları nasıl sıkıştıracağınızı gösterir.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET Kullanarak Zip'e Klasör Nasıl Eklenir – FileInfo ile Dosyaları
  Sıkıştırma
url: /tr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET Kullanarak Klasörü Zip'e Ekleme

## Giriş

Programlı olarak **zip arşivi oluşturmanız** gerekiyorsa, Aspose.Zip for .NET, herhangi bir .NET (ASP.NET dahil) uygulamasında çalışan temiz, yüksek performanslı bir API sunar. Bu öğreticide `FileInfo` sınıfı ile dosyaları sıkıştırmayı adım adım gösterecek, **dosyaları zip'e ekleme** yöntemini gösterecek ve bu yaklaşımın modern .NET projeleri için neden ideal olduğunu açıklayacağız. Ayrıca **klasörü zip'e ekleme** konusunu da ele alacağız, böylece tek bir adımda tüm dizinleri paketleyebilirsiniz. Hadi başlayalım!

## Hızlı Yanıtlar
- **Zip arşivi oluşturmanın en kolay yolu nedir?** Aspose.Zip'in `Archive` sınıfını `FileInfo` nesneleriyle birlikte kullanın.  
- **Birden fazla dosyayı aynı anda ekleyebilir miyim?** Evet – her dosya için bir `FileInfo` oluşturup `CreateEntry` çağırın.  
- **ASP.NET için özel bir lisansa ihtiyacım var mı?** Üretim için ticari bir Aspose.Zip lisansı gereklidir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API çok iş parçacıklı (thread‑safe) mi?** Evet, her iş parçacığı kendi `Archive` örneğiyle çalıştığı sürece.

## Zip Arşivi Nedir ve Neden Oluşturulur?

Bir zip arşivi, bir veya daha fazla dosyayı tek bir sıkıştırılmış konteynere paketler. Bu, depolama alanını azaltır, ağ transferlerini hızlandırır ve dağıtımı basitleştirir. Günlükleri teslim ediyor, raporları dışa aktarıyor ya da bir müşteri için varlıkları paketliyor olsanız da, programlı olarak **zip arşivi oluşturmanın** nasıl yapılacağını bilmek her .NET geliştiricisi için değerli bir beceridir.

## Dosyaları Zip'e Eklemek İçin Aspose.Zip Neden Kullanılmalı?

- **Sıfır dış bağımlılık** – saf .NET uygulaması.  
- **Sıkıştırma seviyesi ve kodlama üzerinde tam kontrol** (ASCII, UTF‑8 vb.).  
- **Büyük dosyaları destekler** (> 4 GB) ve şifre koruması.  
- **.NET Framework, .NET Core ve .NET 5+ arasında tutarlı API**.

## Önkoşullar

Koda geçmeden önce şunların olduğundan emin olun:

1. **Aspose.Zip for .NET** yüklü. En son paketi [Aspose.Zip indirme sayfasından](https://releases.aspose.com/zip/net/) indirin.  
2. Sıkıştırmak istediğiniz dosyaları içeren bir klasör (ör. `alice29.txt` ve `fields.c`).  

## Ad Alanlarını İçe Aktarma

Zip arşivleriyle çalışacağınız herhangi bir C# dosyasında aşağıdaki `using` ifadelerini ekleyin:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Ayarlama

İlk olarak, kaynak dosyaları tutan klasörü tanımlayın. Yer tutucuyu sisteminizdeki mutlak ya da göreli yol ile değiştirin:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro ipucu:** `Path.Combine` kullanarak yolları çapraz platform bir şekilde oluşturun.

### Adım 2: Yazma İçin Zip Dosyasını Açma

Çıktı zip dosyasına işaret eden bir `FileStream` oluşturun. Akış **Create** modunda açılır ve aynı ada sahip mevcut dosyanın üzerine yazar:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Adım 3: Her Kaynak Dosya İçin `FileInfo` Nesnelerini Hazırlama

`FileInfo`, Aspose.Zip'e diskteki fiziksel dosyalara doğrudan erişim sağlar. Sıkıştırmak istediğiniz her dosya için bir örnek oluşturun:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Neden `FileInfo` kullanmalı?** Tüm dosyayı belleğe yüklemeyi önler, bu özellikle büyük dosyalar için faydalıdır.

### Adım 4: Arşivi Oluşturma ve Girişleri Ekleme

Bir `Archive` nesnesi oluşturun, ardından her `FileInfo` için `CreateEntry` çağırın. İlk argüman, dosyanın zip içinde alacağı isim, ikinci argüman ise kaynak `FileInfo`'dır:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Adım 5: İstenilen Kodlamayla Zip Arşivini Kaydetme

Son olarak, arşivi daha önce açtığınız `FileStream`'e kaydedin. Burada giriş isimleri için ASCII kodlaması kullanıyoruz, ancak dosya adlarınız ASCII dışı karakterler içeriyorsa UTF‑8'e geçebilirsiniz:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` blokları sona erdiğinde, akışlar otomatik olarak kapanır ve zip dosyası kullanıma hazır olur.

## Aspose.Zip Kullanarak Klasörü Zip'e Ekleme

Bireysel dosyalar yerine **klasörü zip'e eklemeniz** gerekiyorsa, süreç basittir:

1. **Klasörü enumerate edin** `DirectoryInfo.GetFiles` ile (ve isteğe bağlı olarak yineleme için `GetDirectories`).  
2. **Her bulunan dosya için bir `FileInfo` oluşturun**.  
3. **`CreateEntry` çağırın** ve klasör adını içeren göreli bir yol verin, ör. `"MyFolder/Report.pdf"`.

API `FileInfo` ile çalıştığı için, tüm dosyaları belleğe yüklemeniz gerekmez; bu, büyük dizinler için güvenlidir. Bu teknik, **zip multiple files asp.net** senaryolarında da çalışır; rapor setini anlık oluşturur ve tek bir arşiv olarak teslim etmeniz gerekir.

## Yaygın Sorunlar ve Çözümler

| Issue | Cause | Fix |
|-------|-------|-----|
| **Boş zip dosyası** | `FileInfo` var olmayan bir yola işaret ediyor | `dataDir` ve dosya adlarını doğrulayın; girişleri oluşturmadan önce `File.Exists` ile kontrol edin. |
| **Yanlış dosya adı kodlaması** | ASCII dışı adlarla varsayılan kodlamanın kullanılması | `ArchiveSaveOptions` içinde `Encoding = Encoding.UTF8` ayarlayın. |
| **Büyük dosyalarda OutOfMemoryException** | Tüm dosyanın belleğe yüklenmesi | `FileInfo` dosyayı akış olarak okur; başka bir yerde dosyayı byte dizisine okumadığınızdan emin olun. |
| **İzin reddedildi** | Uygulamanın çıktı klasörü için yazma izni yok | Uygulamayı uygun izinlerle çalıştırın veya yazılabilir bir dizin seçin. |

### Sıkça Sorulan Sorular

#### S1: Aspose.Zip tüm dosya türleriyle uyumlu mu?

C1: Aspose.Zip, sıkıştırmada çok yönlülük sağlayarak geniş bir dosya türü yelpazesini destekler.

#### S2: Aspose.Zip'i ticari projeler için kullanabilir miyim?

C2: Kesinlikle! Lisanslama seçeneklerini incelemek için [satın alma sayfamızı](https://purchase.aspose.com/buy) ziyaret edin.

#### S3: Aspose.Zip için nasıl destek alabilirim?

C3: Yardım ve tartışmalar için [Aspose.Zip forumunda](https://forum.aspose.com/c/zip/37) topluluğumuza katılın.

#### S4: Ücretsiz deneme sürümü mevcut mu?

C4: Evet, [ücretsiz deneme sürümünüzü buradan](https://releases.aspose.com/) edinebilirsiniz.

#### S5: Aspose.Zip için geçici lisansı nasıl edinebilirim?

C5: Geçici lisans edinme hakkında bilgi için [bu bağlantıyı](https://purchase.aspose.com/temporary-license/) ziyaret edin.

## Sonuç

Artık Aspose.Zip for .NET kullanarak **klasörü zip'e ekleme** ve **zip arşivi oluşturma** yöntemlerini, **dosyaları zip'e ekleme** yolunu biliyorsunuz ve bu yöntemin ASP.NET ve diğer .NET uygulamaları için neden ideal olduğunu anladınız. Farklı sıkıştırma seviyeleri, kodlamalar ve şifreleme seçenekleriyle deneyler yaparak arşivi tam ihtiyaçlarınıza göre özelleştirin. İyi sıkıştırmalar!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}