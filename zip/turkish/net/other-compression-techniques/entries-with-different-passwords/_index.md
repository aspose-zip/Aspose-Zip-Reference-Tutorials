---
date: 2026-02-28
description: Aspose.Zip for .NET kullanarak şifreli dosya sıkıştırma ve ZIP arşivlerini
  şifreleme yöntemlerini öğrenin; 7z şifre koruması ve C#'ta dosya bazında zip şifresi
  konularını kapsar.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile dosyaları şifreyle sıkıştırma ve ZIP girişlerini farklı
  şifrelerle şifreleme
url: /tr/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

 answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET kullanarak şifreli dosya sıkıştırma ve ZIP girişlerini farklı şifrelerle şifreleme

## Giriş

Şifreyle **dosyaları sıkıştırmanız** ve her girişe ayrı bir şifre vermeniz gerekiyorsa doğru yerdesiniz. Bu öğreticide, Aspose.Zip .NET kütüphanesini kullanarak her dosyanın benzersiz bir şifreyle korunduğu bir 7‑zip arşivi oluşturmak için gerekli adımları adım adım göstereceğiz. Sonunda, giriş‑başına şifrelemenin neden önemli olduğunu, nasıl yapılandırılacağını ve sonucu kendi projelerinizde nasıl doğrulayacağınızı anlayacaksınız.

## Hızlı Yanıtlar
- **“encrypt zip” ne anlama geliyor?** Bir ZIP/7z arşivinin içeriğine şifre‑tabanlı koruma (AES veya ZipCrypto) uygulanması demektir.  
- **Her giriş farklı bir şifreye sahip olabilir mi?** Evet—Aspose.Zip, dosya başına ayrı şifreler atamanıza izin verir.  
- **Hangi .NET sürümleri destekleniyor?** Tüm modern .NET Framework, .NET Core ve .NET 5/6 sürümleri.  
- **Üretim için lisansa ihtiyacım var mı?** Üretim kullanımında ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Örnekte hangi sıkıştırma formatı kullanılıyor?** Örnek, AES‑256 şifreleme ile bir 7z arşivi oluşturur.

## Aspose.Zip for .NET kullanarak şifreli dosyaları sıkıştırma
Bu bölümde temel soruyu doğrudan yanıtlayıp, ardından gelen adım‑adım kılavuz için zemin hazırlıyoruz.

## Aspose.Zip ile “zip nasıl şifrelenir” nedir?
Bir ZIP (veya 7z) dosyasını şifrelemek, girişlerini doğru şifre olmadan açılamaz hâle getirmek anlamına gelir. Aspose.Zip for .NET, klasik ZipCrypto ve daha güçlü AES şifrelemeyi destekler ve her giriş için şifreleme ayarlarını belirlemenize olanak tanır; bu da güvenlik üzerinde ince ayar yapmanızı sağlar.

## Her giriş için farklı şifreler neden kullanılmalı?
- **Güvenlik segmentasyonu:** Bir şifre ele geçirilirse, diğer dosyalar korunmaya devam eder.  
- **Regülasyon uyumu:** Bazı sektörler, farklı veri kategorileri için ayrı kimlik bilgileri gerektirir.  
- **Kullanıcı‑özgü erişim:** Tek bir arşivi birden fazla kullanıcıya dağıtabilir, her kullanıcı yalnızca yetkili olduğu dosyaları açabilir.

## Önkoşullar

İlerlemeye başlamadan önce şunların kurulu olduğundan emin olun:

- **Aspose.Zip for .NET** yüklü – indirme ve kurulum talimatları için resmi [belgelendirme](https://reference.aspose.com/zip/net/) sayfasına bakın.  
- Kaynak dosyalarınızı tutacağınız bir klasör (“Document Directory”).  
- C# ve Visual Studio (veya tercih ettiğiniz .NET IDE) hakkında temel bilgi.

## Ad Alanlarını İçe Aktarma

İhtiyacımız olan sınıfların bulunduğu ad alanlarını içe aktarıyoruz.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Adım 1: Belge Dizinini Ayarlayın

Arşivlemek istediğiniz dosyaların bulunduğu yolu tanımlayın.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: Farklı Şifrelerle Girişler Oluşturun

İşte öğretinin çekirdeği. Yeni bir 7z dosyası açıyor, üç `FileInfo` nesnesi oluşturuyor ve her birini kendi AES şifresiyle bir giriş olarak ekliyoruz.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Bu Nasıl Çalışır

- `SevenZipArchive`, bir 7‑z arşivi için kapsayıcıdır.  
- `CreateEntry`, giriş adını, kaynak dosyayı, üzerine yazma bayrağını ve bir `SevenZipEntrySettings` nesnesini alır.  
- `SevenZipEntrySettings` içinde iki ayar nesnesi sağlarız: sıkıştırma için (`SevenZipStoreCompressionSettings`) ve şifreleme için (`SevenZipAESEncryptionSettings`).  
- Her çağrı **farklı bir şifre** (`"test1"`, `"test2"`, `"test3"`) sağlar ve giriş‑başına koruma elde edilir.

## Adım 3: Doğrulama

Arşiv kaydedildikten sonra basit bir onay mesajı yazdırabilirsiniz.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Programı çalıştırın, ardından `archive.7z` dosyasını 7‑Zip gibi bir araçla açmayı deneyin. Her giriş için bir şifre sorulacak ve şifrelerin gerçekten farklı olduğu doğrulanacaktır.

## Yaygın Sorunlar ve Çözümler

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Yanlış şifre hatası** | Şifre dizesi gereksiz boşluklar veya görünmez karakterler içeriyor. | Şifre dizelerini kırpın (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Arşiv eski araçlarda açılamıyor** | Bazı eski ZIP araçları, 7z tarafından kullanılan AES‑256 şifrelemeyi desteklemiyor. | Modern bir çıkarıcı kullanın (7‑Zip 19.00+). |
| **Dosya arşive eklenmedi** | Kaynak dosya yolu hatalı veya dosya mevcut değil. | `dataDir` ve dosya adlarını doğrulayın, ya da `Path.Combine(dataDir, "data1.bin")` kullanın. |

## Sıkça Sorulan Sorular

### S1: Aspose.Zip for .NET tüm .NET sürümleriyle uyumlu mu?

C1: Evet, Aspose.Zip for .NET, .NET framework'ün tüm sürümleriyle sorunsuz entegrasyon sağlamak üzere tasarlanmıştır.

### S2: Aspose.Zip for .NET'i ticari projelerimde kullanabilir miyim?

C2: Kesinlikle! Aspose.Zip for .NET ticari lisanslar sunar ve satın alma hakkında daha fazla bilgiyi [buradan](https://purchase.aspose.com/buy) bulabilirsiniz.

### S3: Ücretsiz bir deneme sürümü mevcut mu?

C3: Evet, Aspose.Zip for .NET'in özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. Başlamak için [buraya](https://releases.aspose.com/) tıklayın.

### S4: Aspose.Zip for .NET için destek nasıl alınır?

C4: Her türlü soru ve yardım için [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) adresini ziyaret edin.

### S5: Aspose.Zip for .NET'i kalıcı bir lisans olmadan kullanabilir miyim?

C5: Evet, kısa vadeli ihtiyaçlarınız için geçici bir lisans alabilirsiniz. Ayrıntılar için [buraya](https://purchase.aspose.com/temporary-license/) bakın.

## Sonuç

**Şifreli dosya sıkıştırma** ve giriş‑başına şifrelerle ZIP arşivlerini şifreleme konusunu Aspose.Zip for .NET ile öğrendiniz. Bu teknik, her dosyayı ayrı ayrı koruma esnekliği sunar, daha katı güvenlik gereksinimlerini karşılar ve kullanıcı‑özgü dağıtımı basitleştirir. Diğer sıkıştırma ayarları, daha büyük dosya setleriyle denemeler yapabilir veya bu mantığı anlık güvenli arşivler üreten bir web servisine entegre edebilirsiniz.

---

**Son Güncelleme:** 2026-02-28  
**Test Edilen:** Aspose.Zip for .NET 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}