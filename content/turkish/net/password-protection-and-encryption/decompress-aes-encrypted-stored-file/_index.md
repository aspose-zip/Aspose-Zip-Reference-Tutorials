---
title: Aspose.Zip for .NET - AES Şifreli Dosyaların Şifresini Çözme
linktitle: AES Şifreli Saklanan Dosyanın Sıkıştırmasını Aç
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Bu kapsamlı adım adım kılavuzla Aspose.Zip for .NET'te AES şifreli depolanan dosyaların sıkıştırmasını nasıl açacağınızı öğrenin. .NET geliştirme becerilerinizi bugün geliştirin!
type: docs
weight: 19
url: /tr/net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

## giriiş

Aspose.Zip for .NET kullanarak AES şifreli depolanan dosyaların sıkıştırmasını açmaya yönelik bu adım adım kılavuza hoş geldiniz. Aspose.Zip, geliştiricilerin sıkıştırılmış dosyalarla zahmetsizce çalışmasını sağlayan güçlü bir .NET kitaplığıdır. Bu eğitimde, süreci net bir şekilde anlamanızı sağlayacak şekilde AES şifreli dosyaların sıkıştırmasını açmaya odaklanacağız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Zip for .NET: Aspose.Zip kütüphanesinin kurulu olduğundan emin olun. Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/zip/net/).

-  Örnek AES Şifreli Dosya: Aşağıdaki adresten örnek bir AES şifreli dosya indirin:[bu bağlantı](https://releases.aspose.com/zip/net/).

- Belge Dizininiz: Sıkıştırılmış dosyayı depolamak istediğiniz bir dizin ayarlayın. Kod pasajındaki "Belge Dizininiz"i gerçek dizin yolunuzla değiştirin.

## Ad Alanlarını İçe Aktar

Sağlanan kod parçacığında çeşitli ad alanlarının kullanıldığını fark edeceksiniz. Bunları projenize eklediğinizden emin olun:

```csharp
using System.IO;
using Aspose.Zip;
```

## 1. Adım: Kaynak Dizinini Tanımlayın

Kaynak dizininizin yolunu belirttiğinizden emin olun. Örnekte, "Belge Dizininiz"i gerçek yolla değiştirin.

```csharp
string dataDir = "Your Document Directory";
```

## 2. Adım: Şifreli Arşivi açın

```csharp
using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
{
    using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
    {
        using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
        {
            // Sonraki adımlara geçin...
        }
    }
}
```

## 3. Adım: Şifreli Girişin Sıkıştırmasını Açın

```csharp
using (var decompressed = archive.Entries[0].Open())
{
    byte[] b = new byte[8192];
    int bytesRead;
    while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
    {
        extracted.Write(b, 0, bytesRead);
    }
}
```

## Çözüm

Tebrikler! Aspose.Zip for .NET kullanarak AES şifreli depolanan dosyaların sıkıştırmasını nasıl açacağınızı başarıyla öğrendiniz. Bu süreç, .NET uygulamalarınızdaki şifrelenmiş arşivlerle verimli bir şekilde çalışmanıza olanak tanır.

## SSS

### Aspose.Zip for .NET'i diğer şifreleme algoritmalarıyla birlikte kullanabilir miyim?
Aspose.Zip öncelikle AES şifrelemesini destekler. En son güncellemeler için belgelere bakın.

### Deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Zip for .NET için nasıl destek alabilirim?
 Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/zip/37) toplumdan yardım almak için.

### Sıkıştırma ve açma için hangi dosya formatları desteklenir?
Aspose.Zip, ZIP, 7z ve TAR dahil çeşitli formatları destekler. Kapsamlı bir liste için belgelere bakın.

### Aspose.Zip'i ticari amaçlarla kullanabilir miyim?
 Evet, lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) ticari kullanım için.

