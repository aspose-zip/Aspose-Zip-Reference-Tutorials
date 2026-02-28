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

 preserved.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}
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

## Sıkça Sorulan Sorular

**S: Zip arşivine şifre koruması ekleyebilir miyim?**  
C: Evet. `Archive` oluşturduktan sonra `Save` çağırmadan önce `archive.Password = "yourPassword"` ayarlayın.

**S: Mevcut bir zip dosyasını güncelleyebilir miyim?**  
C: Aspose.Zip, `Archive.Open` ile mevcut bir arşivi açmayı ve ardından yeni girişler eklemeyi destekler.

**S: ASP.NET MVC denetleyicisinde dosyaları nasıl sıkıştırırım?**  
C: Aynı kod çalışır; sadece çıktı akışını istemciye `FileResult` olarak döndürdüğünüzden emin olun.

**S: Aspose.Zip şifreleme algoritmalarını destekliyor mu?**  
C: Standart ZipCrypto ve AES‑256 şifrelemeyi destekler.

**S: Klasörü yinelemeli (recursive) olarak sıkıştırmam gerekirse?**  
C: `Directory.GetFiles` (ve alt klasörler) üzerinden döngü kurup her dosya için bir `FileInfo` oluşturun, ardından arşive ekleyin.

## Ek SSS

**S: Büyük veri setleri için .net zip arşivi nasıl oluştururum?**  
C: Veri akışı için `FileInfo` nesnelerini kullanın ve optimal performans için `ArchiveSaveOptions` içinde `CompressionLevel` ayarlayın.

**S: .NET Core web API'de (zip files asp.net core) Aspose.Zip kullanabilir miyim?**  
C: Kesinlikle – kütüphane .NET Core 3.1 ve sonrası ile tam uyumludur.

**S: Özel bir döngü yazmadan klasörü zip'e eklemenin bir yolu var mı?**  
C: Aspose.Zip tek bir “add folder” yöntemi sunmaz, ancak `DirectoryInfo` ile yineleme hafiftir ve giriş adları üzerinde tam kontrol sağlar.

**S: Zip arşivi şifre koruması sıkıştırma hızını etkiler mi?**  
C: Şifreleme etkinleştirildiğinde küçük bir ek yük eklenir, ancak çoğu kullanım senaryosunda etkisi çok azdır.

**S: Ticari dağıtım için hangi lisans gerekir?**  
C: Üretim için ücretli bir Aspose.Zip lisansı gerekir; geliştirme ve test için ücretsiz deneme kullanılabilir.

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

Artık Aspose.Zip for .NET kullanarak **klasörü zip'e ekleme** ve **zip arşivi oluşturma** yöntemlerini, **dosyaları zip'e ekleme** yolunu biliyorsunuz ve bu yöntemin ASP.NET ve diğer .NET uygulamaları için neden ideal olduğunu anladınız. Farklı sıkıştırma seviyeleri, kodlamalar ve şifreleme seçenekleriyle deneyler yaparak arşivi tam ihtiyaçlarınıza göre özelleştirin. İyi sıkıştırmalar!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}