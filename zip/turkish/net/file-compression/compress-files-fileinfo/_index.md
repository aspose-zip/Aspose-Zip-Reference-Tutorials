---
date: 2026-07-18
description: Aspose.Zip for .NET kullanarak klasörü zip'e eklemeyi ve dosyaları zip'e
  eklemeyi öğrenin. Bu adım adım kılavuz, ASP.NET projelerinde FileInfo ile dosyaları
  nasıl sıkıştıracağınızı gösterir.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: FileInfo ile Dosyaları Sıkıştır
og_description: Aspose.Zip for .NET kullanarak klasörü zip'e ekleyin. Zip arşivi oluşturmayı,
  dosyaları zip'e eklemeyi ve ASP.NET'te klasörleri verimli bir şekilde sıkıştırmayı
  öğrenin.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Klasörü Zip'e Ekle – Aspose.Zip for .NET ile Dosyaları Sıkıştır
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Aspose.Zip for .NET kullanarak Klasörü Zip'e Ekle – FileInfo ile Dosyaları
  Sıkıştır
url: /tr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Klasörü Zip'e Eklemek için Aspose.Zip for .NET

## Giriş

Programlı olarak **klasörü zip'e eklemeniz** gerektiğinde, Aspose.Zip for .NET, herhangi bir .NET (ASP.NET dahil) uygulamasında çalışan temiz ve yüksek performanslı bir API sunar. Bu öğreticide `FileInfo` sınıfı ile dosyaları sıkıştırmayı adım adım gösterecek, **dosyaları zip'e ekleme** yöntemini gösterecek ve bu yaklaşımın modern .NET projeleri için neden ideal olduğunu açıklayacağız. Ayrıca **klasörü zip'e ekleme** için tam adımları ele alacağız, böylece tek bir işlemle tüm dizinleri paketleyebilirsiniz. Hadi başlayalım!

## Hızlı Yanıtlar
- **Zip arşivi oluşturmanın en kolay yolu nedir?** Aspose.Zip'in `Archive` sınıfını `FileInfo` nesneleriyle birlikte kullanın.  
- **Birden fazla dosyayı aynı anda ekleyebilir miyim?** Evet – her dosya için bir `FileInfo` oluşturup `CreateEntry` çağırmanız yeterlidir.  
- **ASP.NET için özel bir lisansa ihtiyacım var mı?** Üretim için ticari bir Aspose.Zip lisansı gereklidir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ve .NET 5–10.  
- **API çok iş parçacıklı (thread‑safe) mi?** Evet, her iş parçacığı kendi `Archive` örneğiyle çalıştığı sürece.

## Zip Arşivi Nedir ve Neden Oluşturulur?
Bir zip arşivi, bir veya daha fazla dosyayı tek bir sıkıştırılmış konteynerde birleştirir. Bu, depolama alanını azaltır, ağ transferlerini hızlandırır ve dağıtımı basitleştirir. Günlükleri teslim ediyor, raporları dışa aktarıyor veya bir müşteri için varlıkları paketliyor olun, **zip arşivi dosyalarını programlı olarak oluşturmayı** bilmek her .NET geliştiricisi için değerli bir beceridir.

## Dosyaları Zip'e Eklemek İçin Aspose.Zip Neden Kullanılmalı?
Aspose.Zip, dış bağımlılıkları ortadan kaldıran saf .NET bir çözüm sunar ve geliştiricilere sıkıştırma, kodlama ve güvenlik üzerinde ince ayar kontrolü sağlar. Büyük dosyaları, şifre korumasını destekler ve tüm desteklenen .NET sürümlerinde tutarlı bir şekilde çalışır, bu da hem eski hem de modern uygulamalar için güvenilir bir seçim yapar.  

- **Sıfır dış bağımlılık** – saf .NET uygulaması.  
- **Sıkıştırma seviyesi ve kodlama üzerinde tam kontrol** (ASCII, UTF‑8 vb.).  
- **4 GB'den büyük dosyaları** ve şifre korumasını destekler.  
- **50+ .NET sürümünde tutarlı API** – .NET Framework 2.0'dan .NET 10'a kadar.  

## Önkoşullar

Before we dive into the code, make sure you have:

1. **Aspose.Zip for .NET** yüklü. En son paketi [Aspose.Zip indirme sayfasından](https://releases.aspose.com/zip/net/) indirin.  
2. Sıkıştırmak istediğiniz dosyaları içeren bir klasör (ör. `alice29.txt` ve `fields.c`).  

## Ad Alanlarını İçe Aktarma

In any C# file where you’ll work with zip archives, add the following `using` statements:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Bu ad alanları `Archive` sınıfına, kaydetme seçeneklerine ve standart I/O yardımcı programlarına erişim sağlar.

## Adım‑Adım Kılavuz

### Adım 1: Belge Dizinini Ayarlama

İlk olarak, kaynak dosyaları tutan klasörü tanımlayın. Yer tutucuyu sisteminizdeki mutlak ya da göreli yol ile değiştirin:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro ipucu:** `Path.Combine` kullanarak yolları çapraz platform bir şekilde oluşturun.

### Adım 2: Yazma İçin Zip Dosyası Açma

Çıktı zip dosyasını gösteren bir `FileStream` oluşturun. Akış **Create** modunda açılır ve aynı isimdeki mevcut dosyanın üzerine yazar:

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

> **Neden `FileInfo` kullanmalı?** Tüm dosyayı belleğe yüklemeyi önler, bu da özellikle büyük dosyalar için faydalıdır.

### Adım 4: Arşivi Oluşturma ve Girişleri Ekleme

`Archive` sınıfı, Aspose.Zip'in bellek içinde bir zip konteynerini temsil eden temel nesnesidir. Bir `Archive` nesnesi oluşturun, ardından her `FileInfo` için `CreateEntry` çağırın. İlk argüman, dosyanın zip içinde alacağı isim, ikinci argüman ise kaynak `FileInfo`'dır:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` yöntemi arşive yeni bir dosya girişi ekler, giriş adını kaynak `FileInfo` ile bağlayarak arşiv kaydedildiğinde verinin doğrudan diskten akışını sağlar.

### Adım 5: Zip Arşivini İstenen Kodlamayla Kaydetme

Son olarak, arşivi daha önce açtığınız `FileStream`'e kaydedin. Burada giriş adları için ASCII kodlaması kullanıyoruz, ancak dosya adlarınız ASCII dışı karakterler içeriyorsa UTF‑8'e geçebilirsiniz:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` blokları sona erdiğinde, akışlar otomatik olarak kapanır ve zip dosyası kullanıma hazır olur.

## Aspose.Zip Kullanarak Klasörü Zip'e Nasıl Eklenir?

Hedef dizini yükleyin, tüm dosyaları listeleyin ve her birini klasör adını içeren bir göreli yol ile ekleyin. Bu yaklaşım, **klasörü zip'e eklemenizi** her dosyayı manuel olarak listelemeden sağlar. Giriş adlarında klasör hiyerarşisini koruyarak, ortaya çıkan arşiv orijinal dizin yapısını koruyarak çıkarılabilir; bu, birçok dağıtım senaryosu için önemlidir.

1. Sıkıştırmak istediğiniz klasörü göstermek için `DirectoryInfo` kullanın.  
2. Tüm dosyaları özyinelemeli olarak almak için `GetFiles("*", SearchOption.AllDirectories)` çağırın.  
3. Her dosya için bir `FileInfo` oluşturun ve `"MyFolder/Report.pdf"` gibi bir yol ile `CreateEntry` çağırın.

API `FileInfo` ile çalıştığı için, her dosyayı doğrudan diskten akıtarak, yüzlerce megabayt içeren klasörlerde bile bellek kullanımını düşük tutar.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|-------|-----|
| **Boş zip dosyası** | `FileInfo` mevcut olmayan bir yola işaret ediyor | `dataDir` ve dosya adlarını doğrulayın; giriş oluşturmadan önce `File.Exists` ile kontrol edin. |
| **Yanlış dosya adı kodlaması** | ASCII dışı adlarla varsayılan kodlamanın kullanılması | `ArchiveSaveOptions` içinde `Encoding = Encoding.UTF8` ayarlayın. |
| **Büyük dosyalarda OutOfMemoryException** | Tüm dosyanın belleğe yüklenmesi | `FileInfo` dosyayı akıtır; dosyayı başka bir yerde byte dizisine okumadığınızdan emin olun. |
| **İzin reddedildi** | Uygulamanın çıktı klasörü için yazma izni yok | Uygulamayı uygun izinlerle çalıştırın veya yazılabilir bir dizin seçin. |

## Sıkça Sorulan Sorular

**S: Tek bir çağrı ile bir zip arşivine tüm klasörü ekleyebilir miyim?**  
C: Tek bir çağrı yöntemi yoktur, ancak `DirectoryInfo` ile dosyaları listeleyip her birini `CreateEntry` ile eklemek aynı sonucu verimli bir şekilde elde eder.

**S: Aspose.Zip şifre korumasını destekliyor mu?**  
C: Evet, arşivi kaydetmeden önce `Archive` nesnesine bir şifre belirleyerek tüm arşivi şifreleyebilirsiniz.

**S: Aspose.Zip ne kadar büyük bir zip dosyasını işleyebilir?**  
C: Kütüphane 4 GB'den büyük dosyaları işler ve tüm arşivi belleğe yüklemeden 10 GB'i aşan arşivler oluşturabilir.

**S: API .NET 6 ve .NET 8 ile uyumlu mu?**  
C: Kesinlikle. Aspose.Zip .NET 5'ten .NET 10'a kadar destekler, mevcut tüm LTS sürümlerini kapsar.

**S: Hangi sıkıştırma seviyeleri mevcut?**  
C: Hız ve boyutu dengelemek için `CompressionLevel.NoCompression`, `Fast`, `Normal` veya `Maximum` seçeneklerini kullanabilirsiniz.

## Ek Kaynaklar

- En son Aspose.Zip paketini indirin: [Aspose.Zip indirme sayfası](https://releases.aspose.com/zip/net/)  
- Üretim kullanımı için lisans satın alın: [satın alma sayfası](https://purchase.aspose.com/buy)  
- Topluluktan yardım alın: [Aspose.Zip forumu](https://forum.aspose.com/c/zip/37)  
- Aspose.Zip'i ücretsiz deneyin: [buradan ücretsiz deneme](https://releases.aspose.com/)  
- Değerlendirme için geçici lisans alın: [bu bağlantı](https://purchase.aspose.com/temporary-license/)

## Sonuç

Artık Aspose.Zip for .NET kullanarak **klasörü zip'e nasıl ekleyeceğinizi** ve **zip arşivi nasıl oluşturacağınızı**, **dosyaları zip'e nasıl ekleyeceğinizi** ve bu yöntemin ASP.NET ve diğer .NET uygulamaları için neden ideal olduğunu biliyorsunuz. Farklı sıkıştırma seviyeleri, kodlamalar ve şifreleme seçenekleriyle deneyler yaparak arşivi tam ihtiyaçlarınıza göre özelleştirin. İyi sıkıştırmalar!

---

**Son Güncelleme:** 2026-07-18  
**Test Edilen:** Aspose.Zip for .NET 24.12 (latest)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Zip for .NET ile Klasör Nasıl Zip'lenir](/zip/net/directory-and-folder-compression/compress-directory/)
- [c# ile birden fazla dosyayı zip'leme – Aspose.Zip for .NET ile Sorunsuz Sıkıştırma](/zip/net/file-compression/compress-multiple-files/)
- [Zip Arşivi Oluşturma .NET – Aspose.Zip ile Dosya Sıkıştırma](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}