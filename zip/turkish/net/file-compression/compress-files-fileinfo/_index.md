---
title: Aspose.Zip for .NET'te FileInfo kullanarak Dosyaları Sıkıştırın
linktitle: FileInfo'yu Kullanarak Dosyaları Sıkıştırın
second_title: Dosya Sıkıştırma ve Arşivleme için Aspose.Zip .NET API
description: Aspose.Zip for .NET ile dosya bilgilerini kullanarak dosyaları sıkıştırmayı öğrenin. Verimli dosya yönetimi için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/net/file-compression/compress-files-fileinfo/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET'te FileInfo kullanarak Dosyaları Sıkıştırın

## giriiş

Aspose.Zip for .NET kullanarak dosyaları sıkıştırmaya ilişkin kapsamlı kılavuzumuza hoş geldiniz! Dosya depolamanızı veya aktarımınızı optimize etmek istiyorsanız Aspose.Zip sizin çözümünüzdür. Bu eğitimde, FileInfo sınıfını kullanarak dosyaları sıkıştırma sürecinde size ayrıntılı bir adım adım kılavuz sağlayarak yol göstereceğiz. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Zip for .NET: Aspose.Zip kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/zip/net/).

2. Belge Dizini: Sıkıştırmak istediğiniz dosyaları depolamak için sisteminizde bir dizin oluşturun.

## Ad Alanlarını İçe Aktar

.NET projenize gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgelerinizin saklandığı dizini tanımlayın. Aşağıdaki kodu kullanabilirsiniz:

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: FileInfo'yu kullanarak Dosyaları Sıkıştırın

 Şimdi sürecin özüne geçelim. biz kullanacağız`FileInfo` Dosyaları sıkıştırmak için Aspose.Zip ile birlikte sınıf kullanın. Bu adımları takip et:

### Adım 2.1: Bir Zip Dosyası Açın

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Adım 2.2: FileInfo Nesneleri Oluşturun

 Yaratmak`FileInfo` sıkıştırmak istediğiniz dosyalara ilişkin nesneler:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### Adım 2.3: Arşiv Oluşturun ve Girişleri Ekleyin

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Adım 2.4: Zip Dosyasını Kaydedin

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Tebrikler! Aspose.Zip for .NET'te FileInfo sınıfını kullanarak dosyaları başarıyla sıkıştırdınız.

## Çözüm

Bu eğitimde Aspose.Zip for .NET kullanarak dosyaları verimli bir şekilde nasıl sıkıştıracağımızı araştırdık. Bu adımları izleyerek dosya yönetimi yeteneklerinizi geliştirebilir ve alan kullanımını optimize edebilirsiniz. Aspose.Zip'in tüm potansiyelini deneyimlemek için farklı dosya türleri ve boyutlarını deneyin.

## SSS'ler

### S1: Aspose.Zip tüm dosya türleriyle uyumlu mudur?

Cevap1: Aspose.Zip çok çeşitli dosya türlerini destekleyerek sıkıştırmada çok yönlülük sağlar.

### S2: Aspose.Zip'i ticari projeler için kullanabilir miyim?

 A2: Kesinlikle! Ziyaret edin[satın alma sayfası](https://purchase.aspose.com/buy) Lisanslama seçeneklerini keşfetmek için.

### S3: Aspose.Zip için nasıl destek alabilirim?

 A3: Topluluğumuza katılın[Aspose.Zip forumu](https://forum.aspose.com/c/zip/37) Yardım ve tartışmalar için.

### S4: Ücretsiz deneme sürümü mevcut mu?

 A4: Evet, alabilirsin[ücretsiz deneme burada](https://releases.aspose.com/).

### S5: Aspose.Zip için nasıl geçici lisans alabilirim?

 A5: Ziyaret edin[bu bağlantı](https://purchase.aspose.com/temporary-license/) Geçici lisans alma konusunda bilgi için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
