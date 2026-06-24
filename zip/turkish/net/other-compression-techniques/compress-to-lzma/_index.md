---
date: 2026-06-24
description: Aspose.Zip for .NET'te LZMA'yı nasıl sıkıştıracağınızı öğrenin, depolama
  ve veri transferi verimliliğini optimize edin.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Lzma'ya Sıkıştır
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET'te LZMA Nasıl Sıkıştırılır
url: /tr/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET'te LZMA Nasıl Sıkıştırılır

## Giriş

Bu öğreticide, Aspose.Zip for .NET'te **LZMA nasıl sıkıştırılır** öğrenecek, bu da depolama alanını optimize etmek ve veri aktarım verimliliğini artırmak için kritik bir beceridir. LZMA (Lempel‑Ziv‑Markov chain algorithm) geleneksel ZIP'e kıyasla %70'e kadar daha küçük arşivler sunar ve hızlı açma işlemini korur; bu da bant genişliği sınırlı senaryolar için idealdir.

## Hızlı Yanıtlar
- **Gerekli kütüphane nedir?** Aspose.Zip for .NET  
- **Bu kılavuz hangi algoritmayı kapsar?** LZMA compression  
- **Bir lisansa ihtiyacım var mı?** Test için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **Uygulama ne kadar sürer?** Temel bir dosya için genellikle 10 dakikadan az sürer.

## LZMA sıkıştırması nedir?

LZMA, sözlük sıkıştırması ve aralık kodlaması kullanan yüksek oranlı kayıpsız bir sıkıştırma algoritmasıdır. Metin dosyalarını %30‑70 oranında küçültebilir ve açma hızını ZIP ile karşılaştırılabilir seviyede tutar. Büyük veri setleri için LZMA, depolama maliyetlerini azaltır ve veri bütünlüğünden ödün vermeden ağ transferlerini hızlandırır.

## Neden LZMA için Aspose.Zip Kullanılmalı?

Aspose.Zip **5 sıkıştırma algoritmasını** (ZIP, Deflate, BZIP2, LZMA ve ZSTD) destekler ve tüm dosyayı belleğe yüklemeden **4 GB**'a kadar arşivleri işleyebilir. Kütüphane, tipik bir sunucuda çok sayıda sayfalık belgeleri **2 saniyenin** altında işler ve hem performans hem de ölçeklenebilirlik sunar.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Zip for .NET: Aspose.Zip kütüphanesinin kurulu olduğundan emin olun. Belgeleri [burada](https://reference.aspose.com/zip/net/) bulabilirsiniz.
- Belge Dizini: Sıkıştırmak istediğiniz dosyaları içeren bir klasör seçin veya oluşturun.

## Ad Alanlarını İçe Aktarın

C# dosyanızın en üstüne gerekli ad alanlarını ekleyin, böylece Aspose.Zip'in LZMA işlevselliğine erişebilirsiniz:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Sıkıştırma için kaynak klasörü nasıl ayarlarım?

Arşivlemek istediğiniz dosyaları tutan klasörü belirtin. Ayrı bir kaynak dizini sağlamak, yalnızca istenen dosyaların işlenmesini garanti eder, istenmeyen verilerin eklenme riskini azaltır ve aynı projede birden fazla sıkıştırma göreviyle çalışırken yol yönetimini basitleştirir.

```csharp
string dataDir = "Your Document Directory";
```

## LZMA kullanarak bir dosyayı nasıl sıkıştırırım?

`LzmaArchive`, LZMA arşivleri oluşturmak ve yönetmek için Aspose.Zip'in sınıfıdır.

Bir `LzmaArchive` örneği oluşturun, kaynak dosyaya yönlendirin ve `.lzma` arşivini oluşturmak için `Save` metodunu çağırın. Bu iki satırlık desen, tüm sıkıştırma iş akışını gerçekleştirir, akış yönetimini dahili olarak ele alır ve dağıtım veya depolama için hazır kompakt bir dosya üretir.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Sıkıştırmanın başarılı olduğunu nasıl doğrularım?

`Console.WriteLine`, standart çıktı konsoluna bir metin satırı yazar.

Arşiv kaydedildikten sonra `Console.WriteLine` kullanarak kısa bir onay mesajı yazdırın. Bu anlık geri bildirim, geliştiricilerin sıkıştırma adımının hatasız tamamlandığını doğrulamasına yardımcı olur, otomatik derlemeler sırasında hata ayıklamayı basitleştirir ve rutin daha büyük uygulamalara veya betiklere entegre edildiğinde net durum bilgisi sağlar.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Yaygın Sorunlar ve Çözümler

- **Dosya bulunamadı** – Yol dizesinin çift ters eğik çizgi (`\\`) veya doğrudan dize (`@"C:\Path"`) kullandığını doğrulayın.  
- **Yetersiz bellek** – Aspose.Zip verileri akış olarak işler, ancak çok büyük dosyalar işlem belleği limitinin artırılmasını gerektirebilir.  
- **Lisans uygulanmadı** – Herhangi bir Aspose.Zip işlemi öncesinde `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` kodunu çağırdığınızdan emin olun.

## Sıkça Sorulan Sorular

**S: Birden fazla dosyayı tek bir LZMA arşivine sıkıştırabilir miyim?**  
C: Evet. `archive.Save()`'ı çağırmadan önce her dosya için `archive.AddFile()` metodunu çağırın.

**S: LZMA için sıkıştırma seviyesini ayarlamanın bir yolu var mı?**  
C: `LzmaArchive` sınıfı varsayılan sıkıştırma seviyesini kullanır; bu, hız ve boyut arasında iyi bir denge sağlar. Daha ince ayar kontrolüne ihtiyacınız varsa `LzmaEncoder` aracılığıyla gelişmiş ayarlar mevcuttur.

**S: Oluşturulan .lzma dosyası Windows dışı platformlarda çalışır mı?**  
C: Kesinlikle. LZMA formatı platformdan bağımsızdır, bu yüzden arşiv herhangi bir işletim sisteminde LZMA uyumlu bir araçla açılabilir.

**S: Aspose.Zip kullanarak bir LZMA arşivini nasıl açarım?**  
C: Arşiv yolunu kullanarak `LzmaArchive` yapıcı metodunu çağırın, ardından içeriğini çıkarmak için `ExtractToDirectory()` metodunu kullanın.

**S: Aspose.Zip, tüm dosyaları belleğe yüklemeden akış tabanlı sıkıştırmayı destekliyor mu?**  
C: Evet. `SetSource()` ve `Save()` metodlarına `Stream` nesneleri geçirerek akışlarla çalışabilirsiniz.

---

**Son Güncelleme:** 2026-06-24  
**Test Edilen:** Aspose.Zip for .NET (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Zip for .NET ile Dosyaları Nasıl Sıkıştırılır](/zip/net/file-compression/compress-file/)
- [Aspose.Zip for .NET ile GZip Arşivi ve Diğer Sıkıştırma Teknikleri Nasıl Açılır](/zip/net/other-compression-techniques/)
- [compress files c# – Aspose.Zip for .NET ile 7z arşivi oluşturma](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}