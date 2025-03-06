---
title: Aspose.Zip Eğitimi ile .NET'te Dizinleri Parolayla Koruyun
linktitle: Şifre Korumalı Dizin
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Aspose.Zip kullanarak .NET'te dizinleri nasıl parolayla koruyacağınızı öğrenin. Bu adım adım eğitimle dosyalarınızı zahmetsizce koruyun.
weight: 10
url: /tr/net/password-protection-and-encryption/password-protect-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip Eğitimi ile .NET'te Dizinleri Parolayla Koruyun


## giriiş

.NET geliştirme dünyasında, dizinleri yönetmek ve güvenliğini sağlamak, dosya işlemenin çok önemli bir yönüdür. Aspose.Zip for .NET, dizinleri parolayla korumak için güçlü bir çözüm sağlayarak hassas verilerinizin gizliliğini ve bütünlüğünü sağlar. Bu eğitimde, Aspose.Zip for .NET'i kullanarak bir dizini parolayla koruma sürecinde size adım adım rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- C# programlama dilinin temel anlayışı.
- Makinenizde Visual Studio yüklü.
-  .NET kütüphanesi için Aspose.Zip. İndirebilirsin[Burada](https://releases.aspose.com/zip/net/).
- Parolayla korumak istediğiniz dosyaları içeren dizin.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu ad alanları Aspose.Zip for .NET tarafından sağlanan işlevsellikten yararlanmak için çok önemlidir.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Adım 1: Kaynak Dizininin Yolunu Ayarlayın

Öncelikle korumak istediğiniz dosyaların bulunduğu dizinin yolunu bir parola ile tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Dizini Parolayla Koruyun

 Şimdi dizinin şifre korumasını gerçekleştiren kodu inceleyelim. biz kullanıyoruz`TraditionalEncryptionSettings` Bir parola ayarlamak ve bunu belirtilen dizine uygulamak için sınıf.

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

Her adımı anlamak için kodu parçalayalım:

-  Çıkış Dosyasını Ayarlama:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` şifrelenmiş çıktı için yeni bir ZIP dosyası oluşturur.

-  Dizinin Tanımlanması:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` parola korumalı olacak dizini belirtir.

-  Girişleri Oluşturma ve Kaydetme:`archive.CreateEntries(corpus)` belirtilen dizindeki dosyalar için girişler oluşturur ve`archive.Save(zipFile)`şifre korumalı arşivi kaydeder.

## Çözüm

Bu eğitimde, Aspose.Zip for .NET kullanarak bir dizini parolayla koruma sürecini anlattık. Bu adımları izleyerek hassas dosyalarınızın güvenliğini kullanıcı dostu ve verimli bir şekilde sağlayabilirsiniz.

---

## Sıkça Sorulan Sorular

### Aspose.Zip for .NET büyük dizinler için uygun mudur?
Evet, Aspose.Zip for .NET büyük dizinleri verimli bir şekilde yönetecek ve optimum performans sağlayacak şekilde tasarlanmıştır.

### Zaten korunan bir dizinin şifresini değiştirebilir miyim?
 Evet, şifreyi ayarlayarak değiştirebilirsiniz.`TraditionalEncryptionSettings` buna göre kodda.

### Aspose.Zip for .NET'i kullanmak için herhangi bir lisans gereksinimi var mı?
 Evet, Aspose.Zip for .NET'i üretim ortamında kullanmak için geçerli bir lisans gereklidir. Lisans alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Aspose.Zip for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Zip for .NET için ek desteği nerede bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37) herhangi bir destek veya sorularınız için.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
