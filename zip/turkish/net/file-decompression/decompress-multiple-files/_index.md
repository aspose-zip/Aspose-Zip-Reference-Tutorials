---
title: Aspose.Zip for .NET kullanarak Çoklu Dosyaları Açma
linktitle: Birden Çok Dosyanın Sıkıştırılmasını Açma
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Aspose.Zip for .NET kullanarak birden fazla dosyanın sıkıştırmasını nasıl açacağınızı öğrenin. Verimli dosya yönetimi için adım adım kılavuzumuzu izleyin.
type: docs
weight: 11
url: /tr/net/file-decompression/decompress-multiple-files/
---
## giriiş

Aspose.Zip for .NET kullanarak birden fazla dosyanın sıkıştırmasını açmaya yönelik kapsamlı eğitimimize hoş geldiniz! Birden fazla giriş içeren sıkıştırılmış dosyaları verimli bir şekilde işlemek istiyorsanız doğru yerdesiniz. Bu kılavuzda, Aspose.Zip for .NET'i kullanarak süreç boyunca size adım adım yol göstereceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Zip for .NET: Aspose.Zip for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/zip/net/).

- Belge Dizini: Belgelerinizin saklanacağı bir dizin ayarlayın. Bunu kodda temel dizin olarak kullanacaksınız.

Şimdi adım adım kılavuza başlayalım.

## Ad Alanlarını İçe Aktar

.NET projenize Aspose.Zip için gerekli ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Birden Çok Dosyayı Sıkıştırma

Birden çok dosyanın sıkıştırmasını açmak için öncelikle birden çok girişi olan sıkıştırılmış bir dosyaya ihtiyacınız vardır. Bir tane oluşturalım:

```csharp
string dataDir = "Your Document Directory";

// Sıkıştırma yöntemini çalıştırın
CompressMultipleFiles.Run();
```

## Adım 2: Dosyaların Sıkıştırılmasını Açma

Şimdi dosyaları adım adım sıkıştıralım:

### Adım 2.1: Sıkıştırılmış Dosyayı Açma

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Adım 2.2: Girişleri Listeleme ve İlerlemeyi Takip Etme

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Adım 2.3: İlk Girişin Çıkarılması

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Sıkıştırılmış akıştan veriyi okuma ve çıkarma dosyasına yazma.
    }
}
```

### Adım 2.4: İkinci Girişin Çıkarılması

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

İşte buyur! Aspose.Zip for .NET'i kullanarak birden fazla dosyanın sıkıştırmasını başarıyla açtınız.

## Çözüm

Bu eğitimde Aspose.Zip for .NET kullanarak birden fazla dosyanın sıkıştırmasını açmak için gerekli adımları ele aldık. Bu kılavuzu takip ederek sıkıştırılmış dosyaları kolaylıkla ve verimli bir şekilde yönetebilirsiniz.

## SSS'ler

### S1: Aspose.Zip for .NET'i hem ticari hem de kişisel projelerde kullanabilir miyim?

 Cevap1: Evet, Aspose.Zip for .NET hem ticari hem de kişisel projelerde kullanılabilir. Lisans ayrıntıları için bkz.[Aspose'un lisans bilgileri](https://purchase.aspose.com/buy).

### S2: Aspose.Zip for .NET'in ücretsiz deneme sürümü mevcut mu?

 C2: Evet, Aspose.Zip for .NET'in ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/zip/net).

### S3: Aspose.Zip for .NET için ek desteği nerede bulabilirim?

 A3: Ziyaret edin[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37) topluluk desteği ve tartışmalar için.

### S4: Aspose.Zip for .NET için nasıl geçici lisans satın alabilirim?

 Cevap4: Aspose.Zip for .NET için geçici bir lisans edinin[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Zip for .NET'i kullanmak için herhangi bir özel sistem gereksinimi var mı?

 A5: Bkz.[dokümantasyon](https://reference.aspose.com/zip/net/) ayrıntılı sistem gereksinimleri için.