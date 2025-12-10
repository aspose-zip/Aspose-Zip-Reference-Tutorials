---
date: 2025-12-05
description: Aspose.Zip for .NET kullanarak zip arşivi oluşturmayı ve zip'e dosya
  eklemeyi öğrenin. Bu adım adım kılavuz, ASP.NET projelerinde FileInfo ile dosyaları
  nasıl sıkıştıracağınızı gösterir.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET Kullanarak Zip Arşivi Nasıl Oluşturulur – FileInfo ile
  Dosyaları Sıkıştırma
url: /tr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET Kullanarak Zip Arşivi Nasıl Oluşturulur

## Giriş

Programatik olarak **create a zip archive** oluşturmanız gerekiyorsa, Aspose.Zip for .NET, herhangi bir .NET (ASP.NET dahil) uygulamasında çalışan temiz, yüksek‑performanslı bir API sunar. Bu öğreticide `FileInfo` sınıfı ile dosyaları sıkıştırmayı adım adım gösterecek, **add files to zip** nasıl yapılır anlatacak ve bu yaklaşımın modern .NET projeleri için neden ideal olduğunu açıklayacağız. Hadi başlayalım!

## Hızlı Yanıtlar
- **Bir zip arşivi oluşturmanın en kolay yolu nedir?** Aspose.Zip’in `Archive` sınıfını `FileInfo` nesneleriyle birlikte kullanın.  
- **Birden fazla dosyayı aynı anda ekleyebilir miyim?** Evet – her dosya için bir `FileInfo` oluşturun ve `CreateEntry` metodunu çağırın.  
- **ASP.NET için özel bir lisansa ihtiyacım var mı?** Üretim ortamı için ticari bir Aspose.Zip lisansı gereklidir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API thread‑safe mi?** Evet, her iş parçacığı kendi `Archive` örneğiyle çalıştığı sürece güvenlidir.

## Zip Arşivi Nedir ve Neden Oluşturulur?
Bir zip arşivi, bir veya daha fazla dosyayı tek bir sıkıştırılmış konteynerde birleştirir. Bu, depolama alanını azaltır, ağ transferlerini hızlandırır ve dağıtımı basitleştirir. Günlükleri teslim ediyor, raporları dışa aktarıyor veya bir müşteriye varlıkları paketliyor olun, **how to create zip archive** dosyalarını programatik olarak oluşturabilmek her .NET geliştiricisi için değerli bir beceridir.

## Aspose.Zip'i Zip'e Dosya Eklemek İçin Neden Kullanmalısınız?
- **Sıfır dış bağımlılık** – saf .NET uygulaması.  
- **Sıkıştırma seviyesi ve kodlama üzerinde tam kontrol** (ASCII, UTF‑8 vb.).  
- **Büyük dosyaları destekler** (> 4 GB) ve parola koruması sağlar.  
- **.NET Framework, .NET Core ve .NET 5+ arasında tutarlı API**.

## Önkoşullar

Kodlamaya başlamadan önce şunların yüklü olduğundan emin olun:

1. **Aspose.Zip for .NET** yüklü. En son paketi [Aspose.Zip download page](https://releases.aspose.com/zip/net/) adresinden indirin.  
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

Bu ad alanları, `Archive` sınıfına, kaydetme seçeneklerine ve standart I/O yardımcılarına erişim sağlar.

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Ayarlayın

İlk olarak, kaynak dosyaların bulunduğu klasörü tanımlayın. Yer tutucuyu sisteminizdeki mutlak ya da göreli yol ile değiştirin:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Platformlar arası yol oluşturmak için `Path.Combine` kullanın.

### Adım 2: Yazma İçin Zip Dosyasını Açın

Çıktı zip dosyasına işaret eden bir `FileStream` oluşturun. Akış **Create** modunda açılır; aynı ada sahip mevcut bir dosya üzerine yazılır:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Adım 3: Her Kaynak Dosya İçin `FileInfo` Nesnelerini Hazırlayın

`FileInfo`, Aspose.Zip’e fiziksel dosyalara doğrudan erişim sağlar. Sıkıştırmak istediğiniz her dosya için bir örnek oluşturun:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Tüm dosyayı belleğe yüklemeyi önler; bu, özellikle büyük dosyalar için faydalıdır.

### Adım 4: Arşivi Oluşturun ve Girişleri Ekleyin

Bir `Archive` nesnesi oluşturun, ardından her `FileInfo` için `CreateEntry` metodunu çağırın. İlk argüman, dosyanın zip içinde alacağı isim; ikinci argüman ise kaynak `FileInfo`dır:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Adım 5: İstenilen Kodlamayla Zip Arşivini Kaydedin

Son olarak, daha önce açtığınız `FileStream`e arşivi kaydedin. Burada giriş isimleri için ASCII kodlaması kullanıyoruz, ancak dosya adlarınız ASCII dışı karakterler içeriyorsa UTF‑8’e geçebilirsiniz:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` blokları sona erdiğinde akışlar otomatik olarak kapanır ve zip dosyası kullanıma hazır olur.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|------|
| **Boş zip dosyası** | `FileInfo` mevcut olmayan bir yola işaret ediyor | `dataDir` ve dosya adlarını doğrulayın; giriş oluşturmadan önce `File.Exists` ile kontrol edin. |
| **Yanlış dosya adı kodlaması** | ASCII dışı adlarla varsayılan kodlama kullanılması | `ArchiveSaveOptions` içinde `Encoding = Encoding.UTF8` ayarlayın. |
| **Büyük dosyalarda OutOfMemoryException** | Tüm dosyanın belleğe yüklenmesi | `FileInfo` dosyayı akış olarak okur; başka bir yerde byte dizisine dönüştürmediğinizden emin olun. |
| **İzin reddedildi** | Uygulamanın çıktı klasörüne yazma izni yok | Uygulamayı gerekli yetkilerle çalıştırın veya yazılabilir bir dizin seçin. |

## Sık Sorulan Sorular

**S: Zip arşivine parola koruması ekleyebilir miyim?**  
C: Evet. `Archive` oluşturduktan sonra `archive.Password = "yourPassword"` ayarlayın ve ardından `Save` metodunu çağırın.

**S: Mevcut bir zip dosyasını güncelleyebilir miyim?**  
C: Aspose.Zip, `Archive.Open` ile mevcut bir arşivi açıp yeni girişler eklemenize olanak tanır.

**S: ASP.NET MVC denetleyicisinde dosyaları nasıl sıkıştırırım?**  
C: Aynı kod çalışır; yalnızca çıktıyı istemciye `FileResult` olarak geri gönderdiğinizden emin olun.

**S: Aspose.Zip şifreleme algoritmalarını destekliyor mu?**  
C: Standart ZipCrypto ve AES‑256 şifrelemelerini destekler.

**S: Bir klasörü rekürsif olarak sıkıştırmam gerekirse?**  
C: `Directory.GetFiles` (ve alt klasörler) üzerinden döngü kurarak her dosya için bir `FileInfo` oluşturun ve arşive ekleyin.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Sonuç

Artık Aspose.Zip for .NET kullanarak **how to create zip archive** dosyalarını nasıl oluşturacağınızı, **add files to zip** işlemini nasıl yapacağınızı ve bu yöntemin ASP.NET ve diğer .NET uygulamaları için neden ideal olduğunu biliyorsunuz. Farklı sıkıştırma seviyeleri, kodlamalar ve şifreleme seçenekleriyle deneyler yaparak arşivinizi tam ihtiyaçlarınıza göre özelleştirin. İyi sıkıştırmalar!

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}