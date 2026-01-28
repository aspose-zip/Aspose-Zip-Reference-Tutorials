---
date: 2026-01-28
description: Parola ile arşiv çıkarmayı, dosyaları TarBz2 formatına sıkıştırmayı ve
  Aspose.Zip for .NET kullanarak TarGz arşivleri oluşturmayı öğrenin. Depolama verimliliğini
  ve güvenliğini artırın.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Şifreli Arşivi Çıkar ve TarBz2'ye Sıkıştır (.NET)
url: /tr/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Şifreli Arşivi Çıkar ve TarBz2'ye Sıkıştır (.NET)

Bu rehberde **şifreli arşivi nasıl çıkaracağınızı** ve Aspose.Zip for .NET kullanarak **dosyaları TarBz2'ye nasıl sıkıştıracağınızı** öğreneceksiniz. Yedekleme hizmeti, bulut depolama istemcisi ya da veri işleme hattı oluşturuyor olsanız da, bu teknikler depolama alanını azaltmanıza, aktarım hızını artırmanıza ve hassas verileri korumanıza yardımcı olur.

## Hızlı Yanıtlar
- **TarBz2 nedir?** TAR paketlemesini BZIP2 sıkıştırmasıyla birleştirerek yüksek sıkıştırma oranları sağlayan bir sıkıştırılmış arşiv.  
- **Neden Aspose.Zip for .NET tercih edilmeli?** Yerel bağımlılıkları olmadan birçok arşiv formatı için tek, akıcı bir API sunar.  
- **TarGz arşivi oluşturabilir miyim?** Evet – Aspose.Zip TarGz, TarLz, TarXz, TarZ ve daha fazlasını destekler.  
- **Şifre korumalı bir arşivi nasıl çıkarırım?** Çıkarma işleminden önce her `ArchiveEntry` nesnesinin `Password` özelliğini ayarlayın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Üretim için ticari bir lisans gereklidir; değerlendirme amacıyla ücretsiz deneme sürümü mevcuttur.

## Aspose.Zip for .NET Kullanarak Şifreli Arşivi Nasıl Çıkarılır
Şifre korumalı bir **zip arşivi** çıkarmak oldukça basittir. Arşivi açarsınız, ihtiyacınız olan girdiyi bulursunuz, şifresini atarsınız ve ardından `Extract` metodunu çağırırsınız. Bu yöntem TarBz2, TarGz ve diğer desteklenen formatlar için çalışır.

## “Dosyaları TarBz2'ye sıkıştırmak” ne anlama geliyor?
Dosyaları TarBz2'ye sıkıştırmak, önce birden fazla dosya ve dizini tek bir **TAR** konteynerine paketlemek, ardından **BZIP2** sıkıştırması uygulamak anlamına gelir. Sonuç, hem taşınması kolay hem de yüksek sıkıştırmalı bir `.tar.bz2` dosyasıdır.

## Bu formatları işlemek için neden Aspose.Zip for .NET kullanılmalı?
- **Birleştirilmiş API** – Tek bir kütüphane, birçok format (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Yerel bağımlılık yok** – Windows, Linux ve macOS'ta kutudan çıkar çıkmaz çalışır.  
- **Şifre desteği** – Giriş başına şifrelerle arşivleri güvenli bir şekilde korur ve çıkarır.  
- **Performansa odaklı** – Akış tabanlı işleme bellek kullanımını en aza indirir.

## Ön Koşullar
- .NET 6.0 veya daha yeni (veya .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip for .NET NuGet paketi kurulu (`Install-Package Aspose.Zip`).  
- C# ve dosya I/O temel bilgisi.

## Adım‑Adım Kılavuz

### Adım 1: İhtiyacınız olan arşiv formatını seçin
**TarBz2**, **TarGz**, **TarLz**, **TarXz** veya **TarZ**'nin sıkıştırma oranı ve uyumluluk gereksinimlerinize en uygun olup olmadığını belirleyin.  
- **TarBz2** – En yüksek sıkıştırma, daha yavaş işleme.  
- **TarGz** – Hız ve boyut arasında iyi bir denge (ikincil anahtar kelime *compress files to targz*'i kapsar).  
- **TarZ** – Eski Unix araçları için miras format.

### Adım 2: Yeni bir `Archive` örneği oluşturun
`Archive` sınıfının bir örneğini oluşturun ve çıktı dosya yolunu belirtin. Bu nesne paketleme ve sıkıştırma sürecini yönetecek.

### Adım 3: Dosya ve klasörleri ekleyin
Sıkıştırmak istediğiniz dosyaları eklemek için `AddAll` veya `AddFile` metodlarını kullanın. Temel bir klasör ekleyerek dizin yapısını koruyun.

### Adım 4: İstenen sıkıştırma tipini ayarlayın
Arşivi kaydederken sıkıştırma algoritmasını (`CompressionType.BZip2`, `CompressionType.GZip` vb.) belirtin. İşte **dosyaları tarbz2'ye sıkıştırdığınız** veya başka bir formatta sıkıştırdığınız yer.

### Adım 5: Arşivi kaydedin
Uygun format enumu (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz` vb.) ile `Save` metodunu çağırın. Kütüphane TAR konteynerini yazar ve seçilen sıkıştırmayı tek bir geçişte uygular.

### Adım 6: Şifreli arşivleri çıkarın
**Farklı şifrelerle arşiv girdilerini çıkarmanız** gerektiğinde (ikincil anahtar kelime *how to extract password protected archive*), arşivi açın, her girdiyi bulun, şifresini atayın ve ardından çıkarın.

### Adım 7: Sonucu doğrulayın
Çıkarma işleminden sonra, arşivin doğru oluşturulduğunu ve açıldığını doğrulamak için dosya boyutlarını ve kontrol toplamlarını karşılaştırın.

## Yaygın Kullanım Senaryoları
- **Yedekleme araçları** – Depolama maliyetlerini azaltmak için günlük yedekleri `.tar.bz2` olarak saklayın.  
- **Çapraz platform veri alışverişi** – Tar tabanlı formatlar Linux, macOS ve Windows'ta evrensel olarak anlaşılır.  
- **Güvenli dağıtım** – Uyumluluk odaklı ortamlar için bireysel girdileri şifrelerle koruyun.

## Sorun Giderme ve İpuçları
- **Büyük arşivler** – Tüm dosyaları belleğe yüklemekten kaçınmak için akış API'lerini (`Archive.CreateEntryFromFile`) kullanın.  
- **Şifre uyumsuzlukları** – Her `ArchiveEntry` için ayarlanan şifrenin çıkarma sırasında kullanılan şifreyle aynı olduğundan emin olun; aksi takdirde `InvalidPasswordException` ile karşılaşırsınız.  
- **Desteklenmeyen sıkıştırma seviyesi** – BZIP2 özel sıkıştırma seviyelerini desteklemez; daha ince kontrol gerekiyorsa TarLz veya TarXz'i düşünün.  
- **Performans ipucu** – **tarbz2 arşivi oluştururken**, yazma hızını artırmak için temel akışta tamponlamayı etkinleştirin.

## Sıkça Sorulan Sorular

**Q: TarGz arşivi nasıl oluştururum?**  
A: `Save` metodunu çağırırken sıkıştırma tipini `CompressionType.GZip` ve formatı `ArchiveFormat.TarGz` olarak ayarlayın.

**Q: Şifre korumalı bir arşivi şifreyi bilmeden çıkarabilir miyim?**  
A: Hayır. Her giriş doğru şifreyle sağlanmalıdır; aksi takdirde çıkarma başarısız olur.

**Q: Aspose.Zip, giriş başına farklı şifrelerle arşiv çıkarmayı destekliyor mu?**  
A: Evet. Çıkarma işleminden önce her `ArchiveEntry` için ayrı ayrı şifre atayabilirsiniz.

**Q: Hangi format en iyi sıkıştırmayı sağlar?**  
A: TarBz2 genellikle en yüksek sıkıştırma oranını verir, ardından TarLz ve TarXz gelir. TarGz ise iyi bir hız‑boyut dengesi sunar.

**Q: Bir TAR arşivine ekleyebileceğim dosya sayısında bir sınırlama var mı?**  
A: Pratikte hayır, ancak çok büyük arşivler daha kolay yönetim için birden fazla parçaya bölünerek fayda sağlayabilir.

## Arşiv Çıkarma ve Formatlar Eğitimleri
### [Aspose.Zip for .NET ile TarBz2 Dosya Sıkıştırma](./compress-to-tar-bz2/)
Aspose.Zip kullanarak .NET'te dosyaları TarBz2 formatına nasıl sıkıştıracağınızı öğrenin. Verimli dosya sıkıştırması için adım‑adım rehberimizi izleyin.

### [Aspose.Zip for .NET ile TarGz Sıkıştırma](./compress-to-tar-gz/)
Aspose.Zip ile .NET'te verimli dosya sıkıştırmasını keşfedin. TarGz'ye zahmetsizce sıkıştırın.

### [Aspose.Zip for .NET ile TarLz Sıkıştırma](./compress-to-tar-lz/)
Aspose.Zip ile .NET'te dosyaları zahmetsizce sıkıştırın. TarLz arşivlerini adım‑adım oluşturmayı öğrenin.

### [Aspose.Zip for .NET ile TarXz Sıkıştırma](./compress-to-tar-xz/)
Aspose.Zip kullanarak .NET'te dosyaları TarXz formatına nasıl sıkıştıracağınızı öğrenin. Verimli dosya depolama ve aktarım için adım‑adım rehberimizi izleyin.

### [Aspose.Zip for .NET ile TarZ Sıkıştırma](./compress-to-tar-z/)
Aspose.Zip for .NET kullanarak TarZ'ye adım‑adım sıkıştırmayı keşfedin. .NET projeleriniz için verimli dosya yönetimi.

### [Aspose.Zip for .NET ile Farklı Şifreli Arşiv Girdilerini Çıkarma](./extract-archive-different-passwords/)
Aspose.Zip for .NET'te farklı şifrelerle arşiv girdilerini nasıl çıkaracağınızı öğrenin. Uygulamalarınızda güvenliği ve esnekliği artırın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-28  
**Test Edilen Versiyon:** Aspose.Zip for .NET 24.11  
**Yazar:** Aspose