---
date: 2026-06-29
description: Aspose.Zip for .NET ile klasörü 7z’ye nasıl sıkıştıracağınızı öğrenin;
  LZMA2, BZip2 ve Store gibi 7z sıkıştırma yöntemlerini kapsar. Programlı olarak 7z
  arşivleri oluşturmak için mükemmeldir.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip ile Çeşitli Sıkıştırma Yöntemleri
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Klasörü 7z’ye Nasıl Sıkıştırılır – Aspose.Zip for .NET Öğreticisi
url: /tr/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Klasörü 7z’ye Sıkıştırma – Aspose.Zip for .NET Öğreticisi

## Giriş

Bir .NET uygulamasında programlı olarak **compress folder to 7z** arşivleri oluşturmanız gerekiyorsa, doğru yerdesiniz. Aspose.Zip for .NET, Seven Zip arşivlerini desteklenen sıkıştırma algoritmalarından herhangi biriyle oluşturmayı basitleştirir, ister bir dizini dağıtım için paketlemek isteyin, ister sadece güvenilir bir **seven zip archive .net** çözümüne ihtiyacınız olsun. Bu rehberde üç popüler sıkıştırma yöntemi—LZMA2, BZip2 ve Store (sıkıştırma yok)—üzerinden geçecek ve sadece birkaç C# satırıyla bir 7z dosyası üretmeyi göstereceğiz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET, Seven Zip özelliklerinin en eksiksiz setini sağlar.  
- **Hangi sıkıştırma yöntemi en iyi oranı verir?** LZMA2 genellikle karışık veriler için en yüksek sıkıştırmayı sağlar.  
- **Sıkıştırma olmadan bir 7z oluşturabilir miyim?** Evet—Store (sıkıştırma yok) yöntemini kullanın.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim kullanımı için lisans gereklidir.  
- **Bu .NET 6/7 ile uyumlu mu?** Kesinlikle—Aspose.Zip, .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ve .NET 5–10'u destekler.

## Seven Zip Sıkıştırma Yöntemleri Nelerdir?

Seven Zip, farklı senaryolar için optimize edilmiş birkaç algoritma destekler. **LZMA2**, en yüksek sıkıştırma oranını sunar (genellikle BZip2'den %30‑40 daha küçüktür), **BZip2**, daha geniş eski araç desteğiyle sağlam bir sıkıştırma sağlar ve **Store**, dosyaları küçültmeden arşivler, orijinal zaman damgalarını mükemmel şekilde korur.

## Önkoşullar

- C# ve Visual Studio hakkında temel bilgi.  
- Aspose.Zip for .NET kütüphanesi yüklü. Resmi indirme sayfasından **[buradan](https://releases.aspose.com/zip/net/)** edinebilirsiniz.  
- Arşivlemek istediğiniz dosyaları içeren bir klasör (`dataDir`).

## Ad Alanlarını İçe Aktarma

İlk olarak, C# dosyanıza gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Bu sınıflar, sıkıştırma ayarlarına ve arşiv yönetimine erişim sağlar.

## LZMA2 Sıkıştırma – En Yüksek Oranla 7z Nasıl Oluşturulur

`Archive` sınıfı, birden çok dosya içerebilen bir 7z arşivini temsil eder.  
LZMA2 algoritması, desteklenen yöntemler arasında en yüksek sıkıştırma oranını sağlar. Girişi bloklara bölerek ve gelişmiş bir sözlük sıkıştırması uygulayarak çalışır. Aspose.Zip'te, dosyaları eklemeden önce `Archive` nesnesinde `CompressionMethod`'u `CompressionMethod.Lzma2` olarak ayarlarsınız.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2, kaynak dosyalar 1 MB'den büyük olduğunda en iyi performansı gösterir. Birçok küçük dosya için BZip2 daha hızlı olabilir.

## BZip2 Sıkıştırma – Dengeli Bir Seçim

`Archive` sınıfı, birden çok dosya içerebilen bir 7z arşivini temsil eder.  
BZip2, makul bir hızı korurken sağlam bir sıkıştırma sunar ve hedef ortam LZMA2'yi desteklemediğinde iyi bir yedek seçenektir.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2, makul bir hızı korurken sağlam bir sıkıştırma sunar, bu da LZMA2 hedef ortam tarafından desteklenmediğinde iyi bir geri dönüş seçeneği olur.

## Store (Sıkıştırma Yok) – Boyut Önemli Olmadığında

`Archive` sınıfı, birden çok dosya içerebilen bir 7z arşivini temsil eder.  
Store yöntemi, verileri sıkıştırmadan bir arşiv oluşturur. Orijinal dosyaları 7z konteynerine basitçe kopyalar, zaman damgalarını ve dizin yapısını korur. Aspose.Zip'te kullanmak için, birleştirmek istediğiniz dosyaları eklemeden önce `Archive` üzerinde `CompressionMethod.Store` ayarlayın.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Dosyaları boyutlarını değiştirmeden bir araya getirmeniz gerektiğinde Store yöntemini kullanın—orijinal zaman damgalarını korumak veya arşivin anında sıkıştırılmadan açılacağı durumlar için mükemmeldir.

## 7z'ye Nasıl Dosya Eklerim?

Bir `Archive` örneği oluşturarak, istenen `CompressionMethod`'u ayarlayarak ve `AddAllFiles(dataDir)` çağırarak bir 7z arşivine dosya ekleyin. Metot, belirtilen klasörü özyinelemeli olarak tarar, arşiv içindeki dizin hiyerarşisini korur. Bu yaklaşım, ilk ayarlamadan sonra tek bir kod satırıyla **compress folder to 7z** yapmanızı sağlar.

## Yaygın Kullanım Senaryoları

| Senaryo | Önerilen Yöntem |
|----------|--------------------|
| Büyük kurulum paketlerini dağıtma | LZMA2 |
| Kayıtları eski araçlarla paylaşma | BZip2 |
| Dosyaları hızlı çıkarma için paketleme | Store (no compression) |
| Web hizmetinde anında **compress folder to 7z** yapma ihtiyacı | LZMA2 (for best ratio) |

## Sorun Giderme ve İpuçları

- **Arşivde dosyalar eksik mi?** `dataDir`'in doğru dizine işaret ettiğini ve işlemin okuma izinlerine sahip olduğunu doğrulayın.  
- **Arşiv, eski 7‑Zip sürümlerinde açılamıyor mu?** LZMA2 daha yeni açma kütüphaneleri gerektirebileceği için BZip2 veya Store kullanın.  
- **Performans darboğazı mı?** Büyük veri setleri için, tüm girdileri belleğe yüklemek yerine arşivi akış olarak oluşturmayı düşünün.

## Sıkça Sorulan Sorular

**S: Aspose.Zip for .NET'ı herhangi bir dosya türüyle kullanabilir miyim?**  
C: Evet, Aspose.Zip geniş bir dosya formatı yelpazesini destekler, neredeyse her dosya türünü sıkıştırıp açmanıza olanak tanır.

**S: Aspose.Zip for .NET için ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz deneme **[buradan](https://releases.aspose.com/)** alabilirsiniz.

**S: Aspose.Zip for .NET belgelerini nerede bulabilirim?**  
C: Tam API referansı **[burada](https://reference.aspose.com/zip/net/)** mevcuttur.

**S: Aspose.Zip for .NET için geçici lisansları nasıl alabilirim?**  
C: Geçici lisanslar **[buradan](https://purchase.aspose.com/temporary-license/)** alınabilir.

**S: Aspose.Zip for .NET için desteği nereden alabilirim?**  
C: Desteği **[Aspose.Zip forumunda](https://forum.aspose.com/c/zip/37)** bulabilirsiniz.

---

**Son Güncelleme:** 2026-06-29  
**Test Edilen Versiyon:** Aspose.Zip for .NET 24.12  
**Yazar:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [dosyaları sıkıştır c# – Aspose.Zip for .NET ile 7z arşivi oluşturma](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Aspose.Zip for .NET ile Klasörü Zipleme](/zip/net/directory-and-folder-compression/compress-directory/)
- [Aspose.Zip for .NET ile LZMA Sıkıştırma](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}