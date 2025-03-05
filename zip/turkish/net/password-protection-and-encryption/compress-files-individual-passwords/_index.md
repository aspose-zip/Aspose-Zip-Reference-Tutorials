---
title: Aspose.Zip ile .NET'te Güvenli Dosya Sıkıştırma
linktitle: Dosyaları Bireysel Şifrelerle Sıkıştırın
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: .NET uygulamalarında dosya güvenliğini nasıl geliştireceğinizi öğrenin! Aspose.Zip for .NET kullanarak dosyaları ayrı şifrelerle sıkıştırmaya ilişkin adım adım kılavuzumuzu izleyin.
type: docs
weight: 16
url: /tr/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## giriiş

.NET geliştirme dünyasında, dosyaları verimli bir şekilde yönetmek ve sıkıştırmak çok önemli bir görevdir. Aspose.Zip for .NET, uygulamalarınızı geliştirecek çeşitli özellikler sunarak dosya sıkıştırmaya yönelik güçlü bir çözüm sunar. Dikkate değer özelliklerden biri, dosyaları ayrı parolalarla sıkıştırarak ek bir güvenlik katmanı sağlamasıdır. Bu eğitimde, Aspose.Zip for .NET kullanarak dosyaları ayrı şifrelerle sıkıştırma sürecinde size rehberlik edeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Zip for .NET: .NET projenizde Aspose.Zip kütüphanesinin kurulu olduğundan emin olun. Gerekli belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/zip/net/).

-  İndirin: Henüz yapmadıysanız, Aspose.Zip for .NET kitaplığını şu adresten indirin:[bu bağlantı](https://releases.aspose.com/zip/net/).

- Belge Dizini: Sıkıştırmak istediğiniz dosyaları içeren bir dizin hazırlayın.

## Ad Alanlarını İçe Aktar

.NET projenizde gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 1. Adım: Kaynak Dizini Yolunu Ayarlayın

Dosyalarınızın bulunduğu kaynak dizininin yolunu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Dosyaları Bireysel Şifrelerle Sıkıştırın

Şimdi dosyaları ayrı ayrı şifrelerle sıkıştıralım. Üç örnek dosya kullanacağız (`alice29.txt`, `asyoulik.txt` , Ve`fields.c`) her biri için farklı şifrelerle.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Her dosyayı ayrı bir şifreyle sıkıştırın
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Sıkıştırılmış dosyaları kaydedin
        archive.Save(zipFile);
    }
}
```

## Çözüm

Tebrikler! Aspose.Zip for .NET'i kullanarak dosyaları ayrı parolalarla nasıl sıkıştıracağınızı başarıyla öğrendiniz. Bu özellik, sıkıştırılmış dosyalarınıza ekstra bir güvenlik katmanı ekleyerek gizliliği sağlar.

## Sıkça Sorulan Sorular (SSS)

### Her dosya için farklı şifreleme yöntemleri kullanabilir miyim?
Evet, Aspose.Zip for .NET, sıkıştırma sırasında her dosya için farklı şifreleme yöntemleri kullanmanıza olanak tanır.

### Deneme sürümü mevcut mu?
 Evet, Aspose.Zip for .NET'in ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### Sorunla karşılaşırsam nasıl destek alabilirim?
 Ziyaret edin[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37) topluluktan yardım ve Aspose desteği için.

### Aspose.Zip for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/zip/net/).

### Test amacıyla geçici bir lisans satın alabilir miyim?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
