---
date: 2025-12-21
description: Aspose.Zip kullanarak .NET’te şifre korumalı zip dosyaları oluşturmayı,
  klasörleri şifrelemeyi ve zip şifresini değiştirmeyi öğrenin.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET dizinleri için şifre korumalı zip oluşturma – Aspose.Zip Öğreticisi
url: /tr/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET dizinleri için şifre korumalı zip oluşturma – Aspose.Zip Öğreticisi

Bu rehberde, Aspose.Zip kütüphanesini .NET için kullanarak tüm dizinler için **şifre korumalı zip** arşivleri **oluşturacaksınız**. **Bir klasörü şifrelemek**, yedek dosyalarını güvence altına almak veya sadece hassas verilere erişimi kısıtlamak isteseniz, bu adım adım öğretici, temiz C# kodu ile bunu nasıl yapacağınızı tam olarak gösterir.

## Hızlı Yanıtlar
- **Önerilen kütüphane nedir?** Aspose.Zip for .NET  
- **Bir klasörü tamamen şifreleyebilir miyim?** Evet – API'yi ziplemek istediğiniz klasöre yönlendirmeniz yeterlidir.  
- **Zip şifresini değiştirmek destekleniyor mu?** Kesinlikle, `TraditionalEncryptionSettings` kullanın.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari kullanım için geçerli bir Aspose.Zip lisansı gereklidir.  
- **.NET Core/5/6 ile çalışıyor mu?** Evet, API modern .NET çalışma zamanlarıyla tamamen uyumludur.  

## “Şifre korumalı zip oluşturma” nedir?
Şifre korumalı bir zip oluşturmak, dosyaları veya dizinleri bir ZIP arşivine sıkıştırırken şifreleme uygulamak anlamına gelir; böylece arşiv yalnızca doğru şifreyle açılabilir. Bu, içeriği yetkisiz erişime karşı korur.

## Neden Aspose.Zip'i .NET dizin şifreleme için kullanmalısınız?
Aspose.Zip, **c# zip password protection** desteği, geleneksel ZipCrypto şifrelemesi ve AES şifrelemesi sunan basit ve yüksek performanslı bir API sağlar. Büyük dizinleri verimli bir şekilde işler ve herhangi bir .NET projesiyle sorunsuz bir şekilde bütünleşir.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlamaya temel bilgi.  
- Visual Studio (herhangi bir yeni sürüm).  
- Aspose.Zip for .NET kütüphanesi – **[buradan](https://releases.aspose.com/zip/net/)** indirin.  
- Şifreyle korumak istediğiniz bir klasör.

## Namespace'leri İçe Aktarın
C# dosyanıza gerekli namespace'leri ekleyin, böylece derleyici Aspose.Zip sınıflarını bulabilir.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Adım 1: Kaynak Dizininin Yolunu Ayarlayın
Zipleyip korumak istediğiniz dizine işaret eden yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Dizini Şifreyle Koruyun
Şifreyi belirtmek ve şifreli arşivi oluşturmak için `TraditionalEncryptionSettings` kullanın. Bu, **c# zip password protection**'ın temelidir.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Adım 3: Kodun Açıklaması
- **Çıktı dosyasını oluşturma:** `File.Open(..., FileMode.Create)` şifreli veriyi tutacak ZIP dosyasını açar (veya oluşturur).  
- **Kaynak klasörü seçme:** `new DirectoryInfo(".\\CanterburyCorpus")` Aspose.Zip'e hangi dizini sıkıştıracağını söyler.  
- **Şifreyi uygulama:** `new TraditionalEncryptionSettings("p@s$")` arşivi koruyacak şifreyi ayarlar.  
- **Girişleri ekleme ve kaydetme:** `archive.CreateEntries(corpus)` klasördeki her dosyayı ekler, `archive.Save(zipFile)` ise şifreli ZIP'i diske yazar.

## Zip şifresini daha sonra nasıl değiştiririm?
**Zip şifresini değiştirmek** gerektiğinde, yeni şifreyi içeren yeni bir `TraditionalEncryptionSettings` örneğiyle arşivi yeniden oluşturun ve tekrar kaydedin.

## Yaygın Sorunlar ve İpuçları
- **Büyük klasörler:** Aspose.Zip veriyi akış olarak işler, bu sayede çok büyük dizinlerde bile bellek kullanımı düşük kalır.  
- **Şifre karmaşıklığı:** Güvenliği artırmak için harf, sayı ve sembol karışımından oluşan güçlü bir şifre kullanın.  
- **Lisans hataları:** Geçerli bir lisans dosyası uyguladığınızdan emin olun; aksi takdirde kütüphane sınırlı özelliklerle değerlendirme modunda çalışır.

## Sıkça Sorulan Sorular

### Aspose.Zip for .NET büyük dizinler için uygun mu?
Evet, Aspose.Zip for .NET büyük dizinleri verimli bir şekilde işlemek üzere tasarlanmıştır ve optimum performans sağlar.

### Zaten korunan bir dizinin şifresini değiştirebilir miyim?
Evet, kodda `TraditionalEncryptionSettings` ayarını yeni şifreyle değiştirerek şifreyi güncelleyebilirsiniz.

### Aspose.Zip for .NET kullanımı için lisans gereksinimleri var mı?
Evet, Aspose.Zip for .NET'i üretim ortamında kullanmak için geçerli bir lisans gereklidir. Lisansı **[buradan](https://purchase.aspose.com/buy)** temin edebilirsiniz.

### Aspose.Zip for .NET için ücretsiz deneme sürümü var mı?
Evet, ücretsiz deneme sürümüne **[buradan](https://releases.aspose.com/)** ulaşabilirsiniz.

### Aspose.Zip for .NET için ek destek nereden bulunur?
Herhangi bir destek veya soru için **[Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37)** ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen:** Aspose.Zip for .NET (en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}