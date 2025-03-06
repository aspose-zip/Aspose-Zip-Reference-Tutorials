---
title: Dosyalarınızı Güvenceye Alın - Aspose.Zip ile AES Şifreleme
linktitle: AES ile Şifre Koruması
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: AES şifrelemeli Aspose.Zip for .NET kullanarak dosya güvenliğinizi nasıl artıracağınızı öğrenin. Optimum koruma için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dosyalarınızı Güvenceye Alın - Aspose.Zip ile AES Şifreleme


## giriiş

Günümüzün dijital çağında hassas dosyalarınızın güvenliğini sağlamak çok önemlidir ve Aspose.Zip for .NET, Gelişmiş Şifreleme Standardı (AES) kullanarak arşivlerinizi parolayla korumak için güçlü bir çözüm sunar. Bu eğitimde, sıkıştırılmış dosyalarınız için en yüksek düzeyde güvenlik sağlayan üç anahtar uzunluğunda (128 bit, 192 bit ve 256 bit) AES şifrelemesinin nasıl uygulanacağını keşfedeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

-  Aspose.Zip for .NET: Aspose.Zip kütüphanesinin .NET projenize entegre olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/zip/net/).

- Belge Dizini: Kaynak dosyalarınızın bulunduğu bir dizine sahip olun.

## Ad Alanlarını İçe Aktar

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Adım 1: AES-128 ile Şifre Koruması

```csharp
//ExStart:PasswordProtectWithAES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES128
```

Bu adımda bir zip dosyası oluşturup onu AES-128 şifrelemeyle koruyoruz. "p@s$" şifresi arşivinizin güvenliğini sağlar.

## Adım 2: AES-192 ile Şifre Koruması

```csharp
//ExStart:PasswordProtectWithAES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES192
```

Bu adım, gelişmiş güvenlik için AES-192 şifrelemesinin nasıl uygulanacağını gösterir. Tutarlılık için aynı şifre "p@s$" kullanılır.

## Adım 3: AES-256 ile Şifre Koruması

```csharp
//ExStart:PasswordProtectWithAES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: PasswordProtectWithAES256
```

Bu son adımda, sıkıştırılmış dosyalarınız için ek bir güvenlik katmanı sağlayan en yüksek düzeyde şifreleme olan AES-256'yı uyguluyoruz.

## Çözüm

Bu eğitimde, Aspose.Zip for .NET'te AES şifrelemesini kullanarak arşivlerinizi parolayla korumaya yönelik temel adımları ele aldık. İster 128 bit, ister 192 bit veya 256 bit şifrelemeyi seçin, dosyalarınız yetkisiz erişime karşı güvende olacaktır.

## Sıkça Sorulan Sorular

### Aspose.Zip for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Zip öncelikli olarak .NET uygulamaları için tasarlanmış olup kusursuz entegrasyon ve optimum performans sağlar.

### AES şifreleme yöntemi hassas veriler için güvenli midir?
Evet, AES şifrelemesi, hassas bilgilerin korunmasına yönelik güvenli ve sağlam bir yöntem olarak geniş çapta kabul görmektedir.

### Zaten şifrelenmiş bir arşivin şifresini değiştirebilir miyim?
Hayır, şifrelenmiş bir arşivin şifresi belirlendikten sonra değiştirilemez. Farklı bir şifreyle yeni bir şifrelenmiş arşiv oluşturmanız gerekecektir.

### Aspose.Zip kullanılarak şifrelenebilecek dosya türlerinde herhangi bir sınırlama var mı?
Aspose.Zip çeşitli dosya türlerinin şifrelenmesini destekleyerek farklı türdeki verilerin güvenliğinde esneklik sağlar.

### Şifrelenmiş bir arşivin şifresini unutursam ne olur?
Maalesef şifrelenmiş bir arşivin şifresini kurtarmanın bir yolu yoktur. Şifreyi güvenli bir yerde tutmak çok önemlidir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
