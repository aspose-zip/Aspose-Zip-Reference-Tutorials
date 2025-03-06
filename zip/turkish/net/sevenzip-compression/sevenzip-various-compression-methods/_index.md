---
title: Yedi Zip Dosyası Oluşturma - Aspose.Zip for .NET Eğitimi
linktitle: Çeşitli Sıkıştırma Yöntemleriyle SevenZip
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Aspose.Zip for .NET ile farklı sıkıştırma yöntemleri kullanarak Seven Zip dosyaları oluşturmayı öğrenin. LZMA2, BZip2 ve Store için kolay adımlar (sıkıştırma yok).
weight: 12
url: /tr/net/sevenzip-compression/sevenzip-various-compression-methods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yedi Zip Dosyası Oluşturma - Aspose.Zip for .NET Eğitimi


## giriiş

.NET geliştirme alanında dosyaları yönetmek ve sıkıştırmak yaygın bir görevdir. Aspose.Zip for .NET, sıkıştırılmış arşivlerle çalışmak için çeşitli sıkıştırma yöntemleri sunan güçlü bir çözüm sunar. Bu eğitimde, Aspose.Zip for .NET'in farklı sıkıştırma yöntemleriyle Seven Zip dosyaları oluşturmak için nasıl kullanılacağını keşfedeceğiz.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlamanın temel anlayışı.
- Makinenizde Visual Studio yüklü.
-  .NET kütüphanesi için Aspose.Zip. İndirebilirsin[Burada](https://releases.aspose.com/zip/net/).

## Ad Alanlarını İçe Aktar

Gerekli Ad Alanlarını C# projenize aktararak başlayın. Başlamak için aşağıdaki kod parçacığını kullanın:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2 Sıkıştırma

```csharp
//ExStart: Çeşitli Sıkıştırma Yöntemleriyle SevenZip

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: Çeşitli Sıkıştırma Yöntemleriyle SevenZip
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## BZip2 Sıkıştırma

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Mağaza, Sıkıştırma Yok

```csharp
//Depolama, sıkıştırma yok
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Çözüm

Bu eğitimde Aspose.Zip for .NET'in çeşitli sıkıştırma yöntemleriyle Seven Zip dosyaları oluşturmadaki çok yönlülüğünü araştırdık. İster yüksek sıkıştırma oranlarına ihtiyacınız olsun ister hiç sıkıştırmamayı tercih edin, Aspose.Zip gereksinimlerinizi karşılayacak esnekliği sağlar.

## SSS

### Aspose.Zip for .NET'i herhangi bir dosya türüyle kullanabilir miyim?
Evet, Aspose.Zip for .NET çok çeşitli dosya türlerini destekleyerek çeşitli formatları sıkıştırmanıza ve sıkıştırmasını açmanıza olanak tanır.

### Aspose.Zip for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Zip for .NET belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/zip/net/).

### Aspose.Zip for .NET için nasıl geçici lisans alabilirim?
 Geçici lisans alınabilecek[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Zip for .NET için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
