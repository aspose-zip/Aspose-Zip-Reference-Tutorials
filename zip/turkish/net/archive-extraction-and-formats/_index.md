---
date: 2026-06-19
description: Aspose.Zip for .NET kullanarak tar dosyalarını sıkıştırmayı, targz arşivleri
  oluşturmayı ve şifre korumalı zip dosyalarını çıkarmayı öğrenin – depolama verimliliğini
  ve güvenliği artırır.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Arşiv Çıkarma ve Formatlar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET ile Tar Dosyalarını Sıkıştırma
url: /tr/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET ile Tar Dosyalarını Sıkıştırma

## Giriş

Bu kılavuzda **tar dosyalarını nasıl sıkıştıracağınızı** Aspose.Zip for .NET kullanarak keşfedecek, TarGz arşivleri oluşturmayı öğrenecek ve şifre korumalı zip arşivlerini nasıl çıkaracağınızı göreceksiniz. Verimli arşiv yönetimi, modern .NET geliştiricileri için temel bir beceridir—ister bir yedekleme servisi, ister bulut depolama istemcisi, ister veri işleme hattı geliştirin, bu formatları ustalıkla kullanmak depolama maliyetlerini düşürür, aktarım hızını artırır ve hassas verileri güvende tutar.

## Hızlı Yanıtlar
- **TarBz2 nedir?** TAR paketlemesini BZIP2 sıkıştırmasıyla birleştirerek yüksek sıkıştırma oranları elde eden bir sıkıştırılmış arşiv.  
- **Aspose.Zip for .NET neden tercih edilmeli?** Harici bağımlılıklar olmadan birçok arşiv formatını oluşturup çıkartmak için tek, akıcı bir API sunar.  
- **TarGz arşivi oluşturabilir miyim?** Evet – Aspose.Zip TarGz, TarLz, TarXz, TarZ ve daha fazlasını destekler.  
- **Şifre korumalı bir zip arşivini nasıl çıkarırım?** Çıkarma sırasında `ArchiveEntry` nesnesinin `Password` özelliğini kullanın.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Üretim için ticari bir lisans gereklidir; değerlendirme için ücretsiz bir deneme sürümü mevcuttur.

## Tar Sıkıştırması Nedir?
Tar (Tape Archive), birden çok dosya ve dizini sıkıştırma olmadan tek bir akışta birleştiren bir konteyner formatıdır. BZIP2, GZip, LZMA veya XZ gibi bir sıkıştırma algoritması uygulandığında sonuç **tar‑tabanlı bir arşiv** (`.tar.bz2`, `.tar.gz`, `.tar.lz` vb.) olur. Bu formatlar Linux, macOS ve Windows üzerinde yaygın olarak desteklenir ve çapraz platform veri alışverişi için idealdir.

## Bu Formatları İşlemek İçin Aspose.Zip for .NET Neden Kullanılmalı?
Aspose.Zip **birleşik, bağımlılıksız bir API** sunar ve TarBz2, TarGz, TarLz, TarXz, TarZ dahil 50+ arşiv ve sıkıştırma formatını destekler. Windows, Linux ve macOS üzerinde çalışır; akış‑tabanlı mimarisi, çok‑yüz‑megabaytlık arşivlerde bile bellek kullanımını 10 MB’ın altında tutar. Şifre koruması yerleşiktir ve ek kütüphanelere ihtiyaç duymadan giriş‑bazlı şifreleme sağlar.

## Ön Koşullar
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 veya .NET 5–10.  
- Aspose.Zip for .NET NuGet paketi yüklü (`Install-Package Aspose.Zip`).  
- C# dosya I/O ve .NET proje sistemi hakkında temel bilgi.

## Adım‑Adım Kılavuz

### Tar Dosyalarını Sıkıştırma – Direkt Cevap
`Archive` bir arşiv dosyasını temsil eder ve giriş ekleme ile kaydetme yöntemleri sağlar.  
Bir `Archive` örneği oluşturun, birleştirmek istediğiniz dosyaları ekleyin, `CompressionType.BZip2` ayarlayın ve `ArchiveFormat.TarBz2` ile `Save` çağırın. Kütüphane TAR konteynerini yazar ve tek bir akış geçişinde sıkıştırır, böylece tüm arşivi belleğe yüklemezsiniz.

### Adım 1: İhtiyacınız olan arşiv formatını seçin
Sıkıştırma‑hız dengesine en uygun tar‑tabanlı formatı belirleyin:

- **TarBz2** – En yüksek sıkıştırma oranı (TarGz’den ≈%30 daha küçük) ancak daha yavaştır.  
- **TarGz** – Hız ve boyut arasında iyi bir denge; çoğu bulut‑depolama senaryosu için idealdir.  
- **TarLz / TarXz** – Çok yüksek sıkıştırma ve orta hız; arşivleme depolaması için uygundur.  
- **TarZ** – Eski Unix araçlarıyla uyumluluk için legacy format.

### Adım 2: Yeni bir `Archive` örneği oluşturun
`Archive`, bellekte tek bir arşiv dosyasını temsil eden üst‑seviye nesnedir.  

`Archive` sınıfı paketleme ve sıkıştırma iş akışını yönetir, giriş ekleme ve son dosyayı yazma yöntemlerini sunar.

### Adım 3: Dosya ve klasörleri ekleyin
`AddAll` ile bir bütün klasör ağacını ekleyebilir veya `AddFile` ile tek tek dosyalar ekleyebilirsiniz. Orijinal klasör hiyerarşisini korumak, temel dizin yolunu vermek kadar basittir.

### Adım 4: İstenen sıkıştırma tipini ayarlayın
`CompressionType` desteklenen algoritmaları listeler.  

`CompressionType`, kaydetme sırasında TAR akışına uygulanacak algoritmayı (BZip2, GZip, LZMA, XZ vb.) tanımlar.

### Adım 5: Arşivi kaydedin
`ArchiveFormat` bir enum kümesidir (ör. `TarBz2`, `TarGz`) ve yazarın hangi konteyner ve sıkıştırmayı kullanacağını belirtir.  

`Save` çağrısı, seçilen formatı kullanarak arşivi diske yazar.

### Adım 6: Şifreli arşivleri çıkarma
`ArchiveEntry` bir arşiv içindeki tek bir dosya veya klasör girişini temsil eder.  

Şifre korumalı bir zip’i çıkarmak için arşivi açın, her `ArchiveEntry` nesnesinin `Password` özelliğini atayın ve `Extract` çağırın. Bu giriş‑bazlı şifre modeli, tek bir zip içinde bireysel dosyaları korumanıza olanak tanır.

### Adım 7: Sonucu doğrulayın
Çıkarma sonrası dosya boyutlarını ve SHA‑256 kontrol toplamlarını karşılaştırarak arşivin veri bütünlüğünü koruduğunu teyit edin.

## Yaygın Kullanım Senaryoları
- **Yedekleme araçları** – Günlük yedekleri `.tar.bz2` olarak saklayarak depolama maliyetlerini %30’a kadar azaltın.  
- **Çapraz‑platform veri alışverişi** – Tar‑tabanlı formatlar Linux, macOS ve Windows araçları tarafından doğal olarak anlaşılır.  
- **Güvenli dağıtım** – Hassas girişlere şifre atayarak ek şifreleme araçlarına ihtiyaç duymadan uyumluluk gereksinimlerini karşılayın.

## Sorun Giderme & İpuçları
- **Büyük arşivler** – Bellek kullanımını düşük tutmak için akış API’si (`Archive.CreateEntryFromFile`) tercih edin.  
- **Şifre uyuşmazlıkları** – Her `ArchiveEntry` için ayarlanan şifre tam olarak aynı olmalıdır; aksi takdirde `InvalidPasswordException` fırlatılır.  
- **Sıkıştırma seviyesi** – BZIP2 özel seviyeler sunmaz; daha ince kontrol gerekiyorsa LZMA (`CompressionType.LZMA`) veya XZ (`CompressionType.XZ`) kullanın.  

## Sıkça Sorulan Sorular

**S: TarGz arşivi nasıl oluştururum?**  
C: `CompressionType.GZip` ayarlayın ve `Save` çağrısında `ArchiveFormat.TarGz` kullanın. Bu, tek adımda bir `.tar.gz` dosyası üretir.

**S: Şifre korumalı bir arşivi şifreyi bilmeden çıkarabilir miyim?**  
C: Hayır. Her giriş için doğru şifre sağlanmalıdır; aksi takdirde `InvalidPasswordException` ile çıkarma başarısız olur.

**S: Aspose.Zip farklı şifrelerle girişleri çıkarabiliyor mu?**  
C: Evet. `Extract` çağrısından önce her `ArchiveEntry` için ayrı ayrı şifre atayabilirsiniz.

**S: Hangi format en iyi sıkıştırmayı sağlar?**  
C: TarBz2 genellikle en küçük boyutu verir, ardından TarLz ve TarXz gelir. TarGz daha hızlı ama hâlâ etkili bir alternatiftir.

**S: TAR arşivine ekleyebileceğim dosya sayısında bir limit var mı?**  
C: Pratikte yoktur, ancak 10 GB’dan büyük arşivler yönetim kolaylığı için birden fazla parçaya bölünerek işlenebilir.

## Arşiv Çıkarma ve Formatlar Öğreticileri
### [Aspose.Zip for .NET ile TarBz2 Dosya Sıkıştırma](./compress-to-tar-bz2/)
Aspose.Zip kullanarak .NET’te dosyaları TarBz2 formatına sıkıştırmayı öğrenin. Verimli dosya sıkıştırması için adım‑adım kılavuzumuzu izleyin.  
### [Aspose.Zip for .NET ile TarGz Sıkıştırma](./compress-to-tar-gz/)
Aspose.Zip ile .NET’te verimli dosya sıkıştırmasını keşfedin. TarGz’ye zahmetsizce sıkıştırın.  
### [Aspose.Zip for .NET ile TarLz Sıkıştırma](./compress-to-tar-lz/)
Aspose.Zip ile .NET’te dosyaları zahmetsizce sıkıştırın. TarLz arşivlerini adım‑adım oluşturmayı öğrenin.  
### [Aspose.Zip for .NET ile TarXz Sıkıştırma](./compress-to-tar-xz/)
Aspose.Zip kullanarak .NET’te dosyaları TarXz formatına sıkıştırmayı öğrenin. Verimli depolama ve aktarım için rehberimizi izleyin.  
### [Aspose.Zip for .NET ile TarZ Sıkıştırma](./compress-to-tar-z/)
Aspose.Zip for .NET ile TarZ’ye adım‑adım sıkıştırmayı keşfedin. .NET projeleriniz için etkili dosya yönetimi.  
### [Aspose.Zip for .NET’te Farklı Şifrelerle Arşiv Girişlerini Çıkarma](./extract-archive-different-passwords/)
Aspose.Zip for .NET’te farklı şifrelerle arşiv girişlerini nasıl çıkaracağınızı öğrenin. Uygulamalarınızda güvenliği ve esnekliği artırın.

---

**Son Güncelleme:** 2026-06-19  
**Test Edilen Sürüm:** Aspose.Zip for .NET 24.11  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Zip for .NET ile tar arşivi oluşturma ve dosyaları tar’a ekleme](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip for .NET ile tar sıkıştırma ve TarBz2 oluşturma](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aspose.Zip ile dosyaları tar’a ekleme ve tarxz arşivi oluşturma](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}