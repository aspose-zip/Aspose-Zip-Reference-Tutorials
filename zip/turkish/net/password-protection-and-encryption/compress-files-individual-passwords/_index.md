---
date: 2026-03-02
description: Aspose.Zip kullanarak .NET’te şifre korumalı zip arşivi oluşturmayı ve
  dosyaları şifreyle sıkıştırmayı öğrenin. Adım adım rehberimizi izleyin.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip ile .NET'te Şifre Koruması Olan ZIP Arşivi Oluşturma
url: /tr/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET'te Aspose.Zip ile Şifre Koruması Olan ZIP Arşivi Oluşturma

## Giriş

Hassas verileri paylaşmanız gerektiğinde, **şifre korumalı zip arşivi** bilgileri güvende tutmanın en basit ama en etkili yollarından biridir. .NET uygulamalarında Aspose.Zip, **parolalı dosya sıkıştırmayı** kolaylaştırır ve her dosyaya kendi şifreleme anahtarını verir. Bu öğreticide tam olarak böyle bir arşivin nasıl oluşturulacağını, neden önemli olduğunu ve gerçek dünya projelerinde nerelerde kullanılabileceğini öğreneceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphaneyi kullanmalıyım?** .NET için Aspose.Zip, dosya başına şifre ve birden fazla şifreleme yöntemi için yerleşik destek sağlar.  
- **Kaç satır kod?** Kurulum ve arşivin kaydedilmesi dahil yaklaşık 30 satır.  
- **Her dosyanın farklı bir şifresi olabilir mi?** Evet – her girişe benzersiz bir şifre atayabilirsiniz.  
- **Hangi şifreleme yöntemleri mevcut?** Geleneksel ZipCrypto, AES‑128 ve AES‑256.  
- **Üretim için lisansa ihtiyacım var mı?** Üretim kullanımında ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.

## Şifre korumalı zip arşivi nedir?
Şifre korumalı zip arşivi, içeriğini çıkarmak için bir şifre gerektiren sıkıştırılmış bir dosyadır (ZIP). Şifre, tüm arşivi ya da tek tek girişleri koruyabilir ve AES‑128/256 gibi modern algoritmalar güçlü şifreleme sağlar.

## Neden Aspose.Zip ile şifreli dosyalar sıkıştırmalıyım?
- **Granüler güvenlik** – dosya başına ayrı bir şifre atayın, çok kiracılı senaryolar için idealdir.  
- **Birden fazla şifreleme standardı** – eski ZipCrypto ve güçlü AES arasında seçim yapın.  
- **Harici araç gerekmez** – her şey .NET kod tabanınız içinde programatik olarak yönetilir.  
- **Performans** – Deflate ile hızlı sıkıştırma ve arşiv boyutunu küçük tutma.

## Önkoşullar

Başlamadan önce şunların olduğundan emin olun:

- **Aspose.Zip for .NET** – kütüphaneyi projenize kurun. Ayrıntılı belgeler [burada](https://reference.aspose.com/zip/net/) mevcuttur.  
- **En son paketi indirin** eğer henüz indirmediyseniz, [bu bağlantıdan](https://releases.aspose.com/zip/net/).  
- Sıkıştırmak istediğiniz dosyaları içeren bir klasör.

## Ad Alanlarını İçe Aktarın

Gerekli ad alanlarını C# dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Adım 1: Kaynak Dizin Yolunu Ayarlayın

Kodu, kaynak dosyaları içeren klasöre yönlendirin:

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Dosyaları Bireysel Şifrelerle Sıkıştırın

Şimdi her dosyanın kendi şifresi ve şifreleme yöntemini kullandığı bir **şifre korumalı zip arşivi** oluşturacağız. Örnek, farklı şifrelerle üç örnek dosya (`alice29.txt`, `asyoulik.txt` ve `fields.c`) kullanıyor.

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
- **CreateEntry** bir dosyayı arşive ekler.  
- Dördüncü argüman (`ArchiveEntrySettings`), hem sıkıştırmayı (`DeflateCompressionSettings`) hem de şifrelemeyi (`TraditionalEncryptionSettings` veya `AesEcryptionSettings`) belirtmenizi sağlar.  
- Her giriş için farklı bir şifre dizesi geçirerek, her dosyanın yalnızca kendi anahtarıyla açılabildiği bir **şifre korumalı zip arşivi** elde edersiniz.

## Yaygın Sorunlar ve Sorun Giderme

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|------|
| “Yanlış şifre” hatasıyla çıkarma başarısız oluyor | Şifre uyumsuzluğu veya yanlış şifreleme yöntemi | Tam şifre dizesini doğrulayın ve çıkarma sırasında aynı `EncryptionMethod` kullanıldığından emin olun. |
| Arşiv boyutu beklenenden büyük | Küçük metin dosyalarında AES‑256 kullanmak ek yük oluşturabilir | Küçük dosyalar için AES‑128 yeterli olabilir ve daha küçük bir arşiv üretir. |
| `archive.Save` sırasında çalışma zamanı istisnası | Hedef klasörde yazma izni eksikliği | Uygulamanın `dataDir` üzerine yazma izni olduğundan emin olun veya farklı bir çıktı yolu kullanın. |

## Sıkça Sorulan Sorular (SSS)

### Her dosya için farklı şifreleme yöntemleri kullanabilir miyim?
Evet, .NET için Aspose.Zip, dosya başına geleneksel ZipCrypto, AES‑128 ve AES‑256 gibi şifreleme yöntemlerini karıştırmanıza izin verir.

### Deneme sürümü mevcut mu?
Evet, Aspose.Zip for .NET'in ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Sorunlarla karşılaşırsam nasıl destek alabilirim?
Topluluk ve Aspose desteğinden yardım almak için [Aspose.Zip forumunu](https://forum.aspose.com/c/zip/37) ziyaret edin.

### Aspose.Zip for .NET için ayrıntılı belgeleri nerede bulabilirim?
Belgeler [burada](https://reference.aspose.com/zip/net/) mevcuttur.

### Test amaçlı geçici bir lisans satın alabilir miyim?
Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-02  
**Test Edilen:** Aspose.Zip for .NET (latest release)  
**Yazar:** Aspose  

---