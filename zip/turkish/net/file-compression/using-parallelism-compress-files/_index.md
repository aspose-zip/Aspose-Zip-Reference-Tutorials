---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip Paralel Sıkıştırma ile birden fazla dosyayı c#'ta zipleme

## Giriş

Eğer **zip multiple files c#** işlemini hızlı ve verimli bir şekilde yapmanız gerekiyorsa, paralel işleme yararlanmak en doğru yol. Modern .NET uygulamalarında büyük zip arşivleri oluşturmak bir darboğaz haline gelebilir—özellikle onlarca ya da yüzlerce dosyayla çalışırken. Aspose.Zip for .NET, yerleşik **parallel zip compression** özelliğiyle işi tüm mevcut CPU çekirdeklerine dağıtarak bu sorunu ortadan kaldırır. Bu öğreticide, ortamı kurmaktan paralel sıkıştırma etkinleştirilmiş bir zip arşivi kaydetmeye kadar tüm süreci adım adım gösterecek ve **create zip archive c#**'ın .NET Core üzerinde sorunsuz çalışmasını da anlatacağız.

## Hızlı Yanıtlar
- **Parallel zip compression nedir?** Birden fazla dosyayı aynı anda sıkıştırır, işlem süresini azaltmak için birden çok iş parçacığı kullanır.  
- **Hangi .NET kütüphanesi bunu destekliyor?** Aspose.Zip for .NET, paralel sıkıştırma için basit bir API sunar.  
- **Üretim için lisansa ihtiyacım var mı?** Evet—tam bir lisans gereklidir; test için geçici bir lisans mevcuttur.  
- **Zip dosyasına anlık olarak dosya ekleyebilir miyim?** Kesinlikle—eklemek istediğiniz her dosya için `Archive.CreateEntry` kullanın.  
- **.NET 6/7 ile uyumlu mu?** Evet, API tüm modern .NET çalışma zamanlarında çalışır.

## zip multiple files c# nedir?
`zip multiple files c#`, C# kodu kullanarak birçok ayrı dosyayı tek bir ZIP arşivinde birleştirme uygulamasını ifade eder. **parallel zip compression** ile birlikte kullanıldığında, kütüphane her dosyayı ayrı bir iş parçacığında işleyerek nihai arşivin oluşturulma süresini büyük ölçüde azaltır.

## Aspose.Zip paralel sıkıştırma neden kullanılmalı?
Paralel sıkıştırma, çok işlemcili bir makinenin her çekirdeğini kullanmanıza olanak tanır ve tek iş parçacıklı yaklaşıma göre **2‑3× daha hızlı** bir verimlilik sağlar. Ayrıca ölçeklenebilir: daha fazla dosya eklemek, duvar saatindeki süreyi doğrusal olarak artırmaz ve API sizin için iş parçacığı yönetimini yapar, böylece iş mantığınıza odaklanabilirsiniz.  

- **Hız:** Tüm mantıksal işlemcileri kullanarak tipik iş yüklerinde zip oluşturma süresini %70’e kadar azaltır.  
- **Ölçeklenebilirlik:** CPU süresi artışı olmadan 500+ dosyayı sorunsuz işler.  
- **Basitlik:** `System.Threading.Tasks` karmaşıklığını gizleyen yüksek seviyeli yöntemler.  
- **Esneklik:** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ve .NET 5–10, .NET 6/7 dahil olmak üzere bulut‑yerel hizmetlerde desteklenir.

## Önkoşullar

İlerlemeye başlamadan önce şunlara sahip olduğunuzdan emin olun:

- C# ve .NET geliştirme temelleri.  
- Aspose.Zip for .NET yüklü. **[buradan](https://releases.aspose.com/zip/net/)** indirebilirsiniz.  
- Geçici veya tam lisans (bu öğretici için geçici lisans yeterlidir).  

## Ad Alanlarını İçe Aktarma

`Aspose.Zip` ad alanı, ZIP arşivleriyle çalışmak için gereken tüm türleri içerir.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

İlk olarak, C# dosyanıza gerekli ad alanlarını ekleyin, böylece derleyici sınıfların nerede olduğunu bilir.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Adım 1: Belge Dizinini Ayarlama

Sıkıştırmak istediğiniz dosyaların bulunduğu klasörü tanımlayın. Bu yol, `dataDir` değişkeninde saklanır ve diskteki herhangi bir konuma işaret edebilir.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Sıkıştırma İşlemini Başlatma

Yeni bir ZIP dosyasını yazmak için açın. `using` ifadesi, işlem tamamlandıktan sonra dosya akışının düzgün bir şekilde serbest bırakılmasını sağlar ve dosya‑tanıtıcı sızıntılarını önler.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Adım 3: Dosyaları Paralel Olarak Oku ve Sıkıştır

`Parallel.ForEach`, yinelemelerin birden çok iş parçacığında eşzamanlı olarak çalışabileceği bir foreach döngüsü yürütür.  

Arşive eklemek istediğiniz her kaynak dosyayı açın. Bu örnekte iki klasik metinle çalışıyoruz, ancak **add files to zip** işlemini istediğiniz sayıda belge için yapabilirsiniz. `Parallel.ForEach` döngüsü işi otomatik olarak iş parçacıkları arasında dağıtır.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Adım 4: Arşiv Girdileri Oluşturma

`Archive` sınıfı, oluşturduğunuz ZIP konteynerini temsil eden Aspose.Zip'in üst‑seviye nesnesidir.  

`CreateEntry`, belirtilen bir dosya için ZIP arşivinde yeni bir giriş oluşturur. `CreateEntry`'ye yapılan her çağrı, arşive yeni bir dosya girişi ekler.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Adım 5: Paralellik Kriterini Tanımlama

`ParallelOptions`, paralel döngülerin nasıl yürütüleceğini kontrol eden .NET tipidir.  

`ParallelOptions` ayarlayarak sıkıştırmanın paralel çalışmasını sağlayın. `ParallelCompressInMemory` bayrağı, Aspose.Zip'in her zaman paralel işleme kullanmasını söylerken, `MaxDegreeOfParallelism` aynı anda çalışabilecek iş parçacığı sayısını sınırlamanıza izin verir.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Adım 6: Sıkıştırılmış Arşivi Kaydetme

Son olarak, arşivi istenen seçeneklerle, kodlama, yorum ve daha önce tanımlanan paralel ayarlarla birlikte diske yazın. `Save` yöntemi ZIP dosyasını sonlandırır.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro ipucu:** Çok büyük dosyalar sıkıştırıyorsanız, `ParallelOptions.MaxDegreeOfParallelism` değerini mantıksal işlemci sayısından daha düşük bir değere ayarlamayı düşünün. Bu, sunucunuzun yoğun yük altında yanıt verebilirliğini korur.

### Yaygın Kullanım Senaryoları

- **Toplu raporlama:** Günlük CSV raporlarını aşağı akış sistemleri için bir zip paketi halinde oluşturun.  
- **Belge arşivleme:** Yedekleme amacıyla büyük PDF, resim veya günlük koleksiyonlarını tek bir arşivde saklayın.  
- **Veri dışa aktarma API'leri:** Birden fazla veri dosyasını içeren bir zip dosyasını tek bir HTTP yanıtı olarak istemciye gönderin.  

## Yaygın Sorunlar ve İpuçları

- **Büyük dosyalarda bellek baskısı:** Tüm dosyayı belleğe yüklemek yerine dosyayı parçalar halinde akıtın veya `ParallelCompressInMemory` modunu seçici olarak kullanın.  
- **İş parçacığı güvenliği:** Aspose.Zip API'si paralel modda iş parçacığı‑güvenlidir, ancak sıkıştırma sırasında kütüphane dışından aynı `FileStream`'i değiştirmekten kaçının.  
- **Performans ayarı:** Paylaşımlı sunucularda CPU kullanımını sınırlamanız gerekiyorsa `ParallelOptions.MaxDegreeOfParallelism` ile deney yapın.  

## Sıkça Sorulan Sorular

**S: Aspose.Zip for .NET'i diğer sıkıştırma kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Zip diğer .NET kütüphaneleriyle birlikte var olabilir; sadece ad alanlarını ayrı tutun.

**S: Test amaçlı geçici bir lisans mevcut mu?**  
C: Evet, **[buradan](https://purchase.aspose.com/temporary-license/)** geçici bir lisans alabilirsiniz.

**S: Sorun yaşarsam nereden yardım alabilirim?**  
C: Topluluk desteği ve tartışmalar için **[Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37)** ziyaret edin.

**S: Daha fazla kod örneği ve detaylı API belgelerini nereden bulabilirim?**  
C: Kapsamlı örnekler için **[Aspose.Zip dokümantasyonunu](https://reference.aspose.com/zip/net/)** inceleyin.

**S: Aspose.Zip için tam lisans nasıl satın alınır?**  
C: Aspose.Zip for .NET'i **[buradan](https://purchase.aspose.com/buy)** satın alabilirsiniz.

---

**Son Güncelleme:** 2026-06-09  
**Test Edilen:** Aspose.Zip 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [zip multiple files c# – Aspose.Zip for .NET ile Sorunsuz Sıkıştırma](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip for .NET ile Zip Arşivi Oluşturma ve Dosya Ekleme](/zip/net/file-compression/compress-single-file/)
- [Aspose.Zip .NET'te Şifreleme ile Çoklu Dosya Sıkıştırma](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}