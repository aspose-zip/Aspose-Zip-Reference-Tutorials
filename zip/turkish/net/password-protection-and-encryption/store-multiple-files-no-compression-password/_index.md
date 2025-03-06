---
title: Aspose.Zip for .NET - Güvenli Dosya Depolama Eğitimi
linktitle: Birden Fazla Dosyayı Şifreyle Sıkıştırmadan Saklayın
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Birden fazla dosyayı sıkıştırma olmadan güvenli bir şekilde depolamak için Aspose.Zip for .NET'in nasıl kullanılacağını keşfedin. Parola koruması için kolay adımlar. Dosya yönetiminin gücünün kilidini açın!
weight: 13
url: /tr/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET - Güvenli Dosya Depolama Eğitimi


.NET geliştirme dünyasında dosyaları yönetmek ve değiştirmek ortak bir görevdir. Aspose.Zip for .NET, geliştiricilere zip arşivlerini sorunsuz bir şekilde sıkıştırma, açma ve yönetme yeteneği sağlayan güçlü bir kitaplıktır. Bu eğitimde belirli bir senaryoyu inceleyeceğiz: birden fazla dosyayı sıkıştırmadan depolamak ve bunları bir parolayla korumak. Bu kılavuzun sonunda, Aspose.Zip for .NET kullanarak bu işlevselliği uygulayacak bilgiyle donatılmış olacaksınız.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Zip for .NET Library: Aspose.Zip for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/zip/net/).

-  Belge Dizini: Kaynak dosyalarınızın bulunduğu bir dizin hazırlayın. Verilen örnekte değişken`dataDir` belge dizininizi temsil eder.

## Ad Alanlarını İçe Aktar

Başlamak için kodumuz için gerekli ad alanlarını içe aktaralım:

```csharp
// Kaynak dizininin yolu.
string dataDir = "Your Document Directory"

// Aspose.Zip ad alanlarını içe aktar
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Adım 1: Zip Dosyasını Açın

```csharp
//ExStart: Çoklu Dosyaları Sıkıştırmadan SaklayınWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Bu adım, kullanarak yeni bir zip dosyası oluşturmayı içerir.`FileStream`. Dosyanın adı "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip" olacaktır.

## Adım 2: Kaynak Dosyayı Açın

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Burada zip arşivinde saklanacak olan ilk kaynak dosya olan "alice29.txt"yi açıyoruz.

## 3. Adım: Arşiv Oluşturun

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 Bu adımda örneğinin bir örneğini oluşturuyoruz.`Archive` sıkıştırma ve şifreleme ayarlarını belirten sınıf. biz kullanıyoruz`StoreCompressionSettings` dosyaları sıkıştırılmadan depolamak ve`AesEcryptionSettings` AES şifrelemesini bir parolayla ("p@s$") uygulamak için.

## 4. Adım: Arşiv Girişi Oluşturun ve Kaydedin

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Bu son adım, arşivde "alice29.txt" için bir giriş oluşturmayı ve arşivi kaydetmeyi, bir dosyayı sıkıştırma olmadan ve şifre korumasıyla saklama işlemini tamamlamayı içerir.

Önemli noktaları özetleyerek ve okuyucuları Aspose.Zip for .NET ile daha fazla olasılığı keşfetmeye teşvik ederek eğitiminizi sonlandırın.

## Çözüm

Bu eğitimde, Aspose.Zip for .NET'in birden fazla dosyayı sıkıştırmadan depolamak ve bunları bir parola ile güvence altına almak için nasıl kullanılacağını araştırdık. .NET geliştirme yolculuğunuza devam ederken Aspose.Zip'in özelliklerinden yararlanarak dosya yönetimi görevlerini kolaylaştırın ve uygulamalarınızın güvenliğini artırın.

---

### SSS

### Aspose.Zip for .NET'i diğer şifreleme yöntemleriyle birlikte kullanabilir miyim?
 Evet, Aspose.Zip çeşitli şifreleme yöntemlerini destekler. Belgeleri kontrol edin[Burada](https://reference.aspose.com/zip/net/) detaylar için.

### Aspose.Zip for .NET için nereden destek alabilirim?
 Ziyaret edin[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37) topluluk desteği ve tartışmalar için.

### Aspose.Zip for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Zip for .NET için nasıl geçici lisans alabilirim?
 Geçici lisans isteyin[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Zip for .NET'i nereden satın alabilirim?
 .NET için Aspose.Zip'i satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
