---
date: 2025-12-10
description: .NET'te Aspose.Zip kullanarak paralel dosya sıkıştırmayı öğrenin. Adım
  adım rehberimizle birden fazla dosyayı verimli bir şekilde sıkıştırın.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile Paralel Dosya Sıkıştırma
url: /tr/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Parallel Dosya Sıkıştırma Aspose.Zip for .NET ile

## Giriş

.NET geliştirme dünyasında **paralel dosya sıkıştırma**, depolama alanını optimize etmek ve veri aktarımını hızlandırmak için kritik öneme sahiptir. Aspose.Zip for .NET güçlü bir çözüm sunar ve öne çıkan özelliklerinden biri, dosya sıkıştırma için paralellikten yararlanma yeteneğidir. Bu öğreticide, Aspose.Zip for .NET ile **birden fazla dosyayı** verimli bir şekilde sıkıştırmak için paralelliği nasıl kullanacağınızı adım adım göstereceğiz.

## Hızlı Cevaplar
- **Paralel dosya sıkıştırma nedir?** Birkaç dosyayı aynı anda sıkıştıran, birden çok CPU çekirdeğini kullanarak toplam işleme süresini azaltan bir tekniktir.  
- **.NET’te bunu destekleyen kütüphane hangisidir?** Aspose.Zip for .NET yerleşik paralel sıkıştırma seçenekleri sunar.  
- **Lisans gerekir mi?** Test için geçici bir lisans mevcuttur; üretim için tam lisans gereklidir.  
- **Zip’e dosyaları anlık olarak ekleyebilir miyim?** Evet—eklemek istediğiniz her dosya için `Archive.CreateEntry` kullanın.  
- **.NET Core/5/6 ile uyumlu mu?** Kesinlikle, API tüm modern .NET çalışma zamanlarında çalışır.

## Paralel Dosya Sıkıştırma Nedir?
Paralel dosya sıkıştırma, sıkıştırma iş yükünü birden çok iş parçacığına veya çekirdeğe bölerek, birkaç dosyanın (veya büyük bir dosyanın parçalarının) aynı anda sıkıştırılmasını sağlar. Bu yaklaşım, geleneksel sıralı sıkıştırmaya kıyasla **zip arşivi c#** oluşturma süresini büyük ölçüde kısaltır.

## Neden Aspose.Zip ile Paralel Sıkıştırma Kullanmalı?
- **Hız:** Çok çekirdekli CPU’ların tam gücünden yararlanır.  
- **Ölçeklenebilirlik:** İşleme süresinde orantısal bir artış olmadan büyük dosya gruplarını yönetir.  
- **Basitlik:** Yüksek seviyeli API, iş parçacığı karmaşıklılarını soyutlar.  
- **Esneklik:** Herhangi bir .NET sürümüyle çalışır ve mevcut kod tabanlarıyla sorunsuz entegrasyon sağlar.

## Ön Koşullar

Başlamadan önce şunların olduğundan emin olun:

- C# ve .NET geliştirme konusunda temel bilgi.  
- Aspose.Zip for .NET kütüphanesi yüklü. **[buradan](https://releases.aspose.com/zip/net/)** indirebilirsiniz.  
- Standart dosya sıkıştırma kavramlarına aşina olmak.

## Ad Alanlarını İçe Aktarın

İlk olarak, C# dosyanıza gerekli ad alanlarını ekleyin; böylece derleyici sınıfların nerede olduğunu bilir.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Adım 1: Belge Dizinini Ayarlayın

Sıkıştırmak istediğiniz dosyaların bulunduğu klasörü tanımlayın. Bu yol `dataDir` değişkeninde saklanır.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Sıkıştırma İşlemini Başlatın

Yeni bir ZIP dosyasını yazma modunda açın. `using` ifadesi, işlem tamamlandığında dosya akışının düzgün bir şekilde serbest bırakılmasını sağlar.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Adım 3: Dosyaları Paralel Olarak Oku ve Sıkıştır

Arşive eklemek istediğiniz her kaynak dosyayı açın. Bu örnekte iki klasik metinle çalışıyoruz, ancak **zip’e dosya ekleme** işlemini istediğiniz sayıda belge için yapabilirsiniz.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Adım 4: Arşiv Girdileri Oluşturun

Bir `Archive` örneği oluşturun ve her dosyayı ayrı bir giriş olarak ekleyin. İşte **create zip archive c#** adımının gerçekleştiği yer.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Adım 5: Paralellik Kriterini Tanımlayın

`ParallelOptions` ayarlayarak sıkıştırmanın paralel çalışmasını yapılandırın. `ParallelCompressInMemory` bayrağı, Aspose.Zip’in her zaman paralel işleme kullanmasını sağlar.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Adım 6: Sıkıştırılmış Arşivi Kaydedin

Son olarak, arşivi istenen seçeneklerle (kodlama, yorum ve daha önce tanımlanan paralel ayarlar dahil) diske yazın.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

Tebrikler! Aspose.Zip for .NET kullanarak **paralel dosya sıkıştırma** işlemini başarıyla gerçekleştirdiniz ve **birden fazla dosyayı** tek bir arşive verimli bir şekilde sıkıştırdınız.

## Yaygın Sorunlar ve İpuçları

- **Büyük Dosyalar:** Bellek baskısıyla karşılaşırsanız, tüm dosyayı belleğe yüklemek yerine dosyaları parçalar halinde sıkıştırmayı düşünün.  
- **İş Parçacığı Güvenliği:** Aspose.Zip API’si paralel modda iş parçacığı‑güvenlidir; kütüphane dışındaki aynı akışı birden çok iş parçacığından değiştirmekten kaçının.  
- **Performans Ayarı:** Paylaşımlı sunucularda CPU kullanımını sınırlamanız gerekiyorsa `ParallelOptions.MaxDegreeOfParallelism` ile deney yapın.  

## SSS

### S1: Aspose.Zip for .NET’i diğer .NET kütüphaneleriyle birlikte kullanabilir miyim?

C1: Evet, Aspose.Zip for .NET diğer .NET kütüphaneleriyle sorunsuz bir şekilde bütünleşecek şekilde tasarlanmıştır.

### S2: Test amaçlı geçici bir lisans alabilir miyim?

C2: Evet, **[buradan](https://purchase.aspose.com/temporary-license/)** test için geçici lisans edinebilirsiniz.

### S3: Ek destek bulabileceğim veya soru sorabileceğim bir yer var mı?

C3: Topluluk desteği ve tartışmalar için **[Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37)** ziyaret edin.

### S4: Örnekler veya dokümantasyon mevcut mu?

C4: Kapsamlı örnekler ve dokümantasyon için **[Aspose.Zip belgelerini](https://reference.aspose.com/zip/net/)** inceleyin.

### S5: Aspose.Zip for .NET’i nasıl satın alabilirim?

C5: Aspose.Zip for .NET’i **[buradan](https://purchase.aspose.com/buy)** satın alabilirsiniz.

---

**Son Güncelleme:** 2025-12-10  
**Test Edilen Versiyon:** Aspose.Zip 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}