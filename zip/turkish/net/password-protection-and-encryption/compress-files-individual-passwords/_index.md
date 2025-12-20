---
date: 2025-12-20
description: Aspose.Zip kullanarak .NET’te şifre korumalı zip arşivleri oluşturmayı
  öğrenin. Bu adım adım kılavuz, dosyaları şifreyle sıkıştırmayı, zip girişi şifresini
  ayarlamayı ve AES şifrelemesini kullanmayı gösterir.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip ile .NET’te Şifre Koruması Olan ZIP Dosyaları Oluşturma
url: /tr/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te Aspose.Zip ile Şifre Koruması Olan ZIP Dosyaları Oluşturma

## Giriş

Bir .NET uygulamasında **şifre korumalı zip** arşivleri oluşturmanız gerekiyorsa, Aspose.Zip bunu kolaylaştırır. Her bir girişe benzersiz bir şifre atayarak, hassas belgeleri güvende tutabilir ve ZIP sıkıştırmanın sağladığı kolaylıktan yararlanabilirsiniz. Bu öğreticide, dosyaları bireysel şifrelerle sıkıştırmayı, farklı şifreleme yöntemlerini seçmeyi ve bir zip girişine şifre ayarlamayı öğreneceksiniz — hepsi net, üretim‑hazır kodla.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Zip for .NET.
- **Her dosya için farklı bir şifre atayabilir miyim?** Evet, her giriş kendi şifresine sahip olabilir.
- **Hangi şifreleme algoritmaları destekleniyor?** Geleneksel ZipCrypto, AES‑128 ve AES‑256.
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.
- **Bu .NET 6+ ile uyumlu mu?** Kesinlikle – API .NET Standard 2.0 ve üzerini hedefler.

## “Şifre korumalı zip oluşturma” nedir?
Şifre korumalı bir zip oluşturmak, bir ZIP arşivindeki bir veya daha fazla girişe şifreleme eklemek anlamına gelir; böylece içerikler doğru şifre olmadan açılamaz. Bu, gizli dosyaları iletmek, yedekleme yapmak veya veri koruma politikalarına uymak için idealdir.

## Şifre korumalı arşivler için Aspose.Zip'i neden kullanmalısınız?
- **İnce ayarlı kontrol** – dosya başına ayrı bir şifre belirleyin.
- **Çoklu şifreleme seçenekleri** – eski ZipCrypto'dan güçlü AES‑128/256'ya.
- **Harici bağımlılık yok** – saf .NET kütüphanesi, entegrasyonu kolay.
- **Kapsamlı dokümantasyon** – daha derin senaryolar için bir **aspose zip tutorial** içerir.

## Önkoşullar

Öğreticiye başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Zip for .NET: Aspose.Zip kütüphanesinin .NET projenize kurulu olduğundan emin olun. Gerekli dokümantasyonu [burada](https://reference.aspose.com/zip/net/) bulabilirsiniz.
- İndirme: Henüz yapmadıysanız, Aspose.Zip for .NET kütüphanesini [bu bağlantıdan](https://releases.aspose.com/zip/net/) indirin.
- Belge Dizini: Sıkıştırmak istediğiniz dosyaları içeren bir dizin hazırlayın.

## Ad Alanlarını İçe Aktarın

In your .NET project, make sure to import the necessary namespaces:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Adım 1: Kaynak Dizin Yolunu Ayarlayın

Define the path to the resource directory where your source files are located.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Dosyaları Bireysel Şifrelerle Sıkıştırın

Şimdi, dosyaları bireysel şifrelerle sıkıştıralım. Her biri için farklı şifreler kullanılan üç örnek dosya (`alice29.txt`, `asyoulik.txt` ve `fields.c`) kullanacağız. Bu, **şifreli dosyaları sıkıştırma** ve farklı şifreleme şemalarıyla **zip girişine şifre ayarlama** nasıl yapılır gösterir; ayrıca bir **aes ile zip arşivi** örneği de içerir.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Nasıl Çalışır
- **TraditionalEncryptionSettings** eski ZipCrypto algoritmasını kullanır (çoğu ZIP aracına uyumludur).
- **AesEcryptionSettings** daha güçlü güvenlik için AES‑128 veya AES‑256 seçmenizi sağlar.
- Her `CreateEntry` çağrısı, sıkıştırma yöntemini ve şifreleme ayarlarını belirttiğimiz bir `ArchiveEntrySettings` nesnesi alır; böylece **zip arşiv girişlerini şifre korumalı** hâle getirir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| ZIP açılırken “Geçersiz şifre” hatası | Kodda kullanılan şifre ile çıkarıcıda girilen şifre arasında eşleşme yok | `TraditionalEncryptionSettings` veya `AesEcryptionSettings` içine geçirilen tam dizeyi doğrulayın. |
| Eski çıkarma araçları AES‑şifreli girişleri açamıyor | Tüm ZIP araçları AES şifrelemeyi desteklemez | Maksimum uyumluluk için geleneksel ZipCrypto yöntemini kullanın veya kullanıcılara modern bir araç (ör. 7‑Zip) kullanmalarını önerin. |
| Büyük dosyalar `OutOfMemoryException` hatasına neden olur | Sıkıştırmadan önce büyük dosyaların belleğe yüklenmesi | Tüm dosyayı bir `FileInfo` nesnesine yüklemeden, `FileStream` ile doğrudan akışlayarak sıkıştırın. |

## Sıkça Sorulan Sorular (SSS)

### Her dosya için farklı şifreleme yöntemleri kullanabilir miyim?
Evet, Aspose.Zip for .NET sıkıştırma sırasında her dosya için farklı şifreleme yöntemleri kullanmanıza izin verir.

### Deneme sürümü mevcut mu?
Evet, Aspose.Zip for .NET'in ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Sorun yaşarsam nasıl destek alabilirim?
Topluluk ve Aspose desteğinden yardım almak için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

### Aspose.Zip for .NET için ayrıntılı dokümantasyonu nerede bulabilirim?
Dokümantasyon [burada](https://reference.aspose.com/zip/net/) mevcuttur.

### Test amaçlı geçici bir lisans satın alabilir miyim?
Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Ek Hızlı SSS

**S: Kütüphane .NET Core ve .NET 5/6'yı destekliyor mu?**  
C: Evet, Aspose.Zip .NET Standard'ı hedefler, bu da .NET Framework, .NET Core ve .NET 5/6 ile uyumlu olmasını sağlar.

**S: Her ZIP girişine bir yorum ekleyebilir miyim?**  
C: Aspose.Zip sıkıştırma ve şifrelemeye odaklansa da, arşiv içinde ayrı bir manifest dosyasında meta verileri depolayabilirsiniz.

**S: Tüm arşivi tek bir şifreyle şifrelemek mümkün mü?**  
C: Her girişe ayrı ayrı şifre atayabilirsiniz (gösterildiği gibi) veya daha basit bir “aes ile zip arşivi” yaklaşımı için aynı şifreyi tüm girişlere uygulayabilirsiniz.

## Sonuç

Artık Aspose.Zip kullanarak .NET'te **şifre korumalı zip** dosyaları oluşturmayı öğrendiniz. Bireysel şifreler atayarak ve uygun şifreleme yöntemini seçerek, ZIP sıkıştırmanın sağladığı kolaylıktan ödün vermeden verilerinizi güvende tutabilirsiniz. Büyük dosyaları akış olarak işleme, özel meta veri ekleme ve bulut depolama ile entegrasyon gibi diğer Aspose.Zip özelliklerini keşfedin.

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen Versiyon:** Aspose.Zip for .NET 23.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}