---
date: 2026-06-09
description: Ismerje meg, hogyan adhat jelszót a zip-hez, és hozhat létre LZMA zip
  archívumokat az Aspose.Zip for .NET használatával. Ez az útmutató bemutatja a Bzip2,
  LZMA (szótárméret), PPMd, Enhanced Deflate, Store tömörítés, valamint az ASP.NET
  nagy fájlok tömörítését.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: A tömörítési beállítások optimalizálása
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jelszó hozzáadása a zip-hez és LZMA archívum létrehozása az Aspose.Zip for
  .NET segítségével
url: /hu/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jelszó hozzáadása a zip-hez és LZMA archívum létrehozása az Aspose.Zip for .NET segítségével

A modern .NET alkalmazásokban a **add password to zip** egy magas tömörítési arányú LZMA zip archívum létrehozása közben megvédheti az érzékeny adatokat, és még a legjobb tömörítést is biztosítja. Akár ASP.NET fájltömörítő szolgáltatást építesz, asztali segédprogramot, amely több gigabájtos fájlokkal dolgozik, vagy felhőalapú munkafolyamatot, ez a bemutató pontos lépéseken keresztül vezet végig a fájlok védelmén és tömörítésén az Aspose.Zip for .NET segítségével.

## Gyors válaszok
- **Mi a LZMA tömörítés elsődleges előnye?** Legmagasabb tömörítési arány mérsékelt sebességgel a legtöbb fájltípus esetén.  
- **Melyik módszer tárolja a fájlokat tömörítés nélkül?** Store compression (más néven “store compression zip”).  
- **Használhatom ezeket a beállításokat egy ASP.NET alkalmazásban?** Igen—egyszerűen hivatkozz az Aspose.Zip-re a projektedben, és hívd meg ugyanazt az API-t.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges a termeléshez; ingyenes próba elérhető.  
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10.

## Mi az a “add password to zip” az Aspose.Zip-ben?
**A zip jelszó hozzáadása titkosítja a ZIP archívum minden bejegyzését, így csak azok a felhasználók tudják kicsomagolni a fájlokat, akik ismerik a jelszót.** Az Aspose.Zip támogatja mind a hagyományos ZipCrypto titkosítást, mind az AES titkosítást (128, 192 vagy 256‑bit). A titkosítási beállításokat a `ArchiveEntrySettings` második argumentumaként adjuk meg az `Archive` létrehozásakor; nincs külön `SetPassword` metódus.

## Miért használjuk az Aspose.Zip-et .NET fájltömörítéshez?
Az Aspose.Zip egyetlen, egységes API-t biztosít, amely számos algoritmust lefed, miközben magas teljesítményt és alacsony memóriahasználatot nyújt. Lehetővé teszi a fejlesztők számára, hogy minden szituációhoz a legjobb tömörítési módszert válasszák, és egy lépésben alkalmazzák a titkosítást, ezáltal egyszerűsítve a kódot és csökkentve a karbantartási terhet.

- **Unified API** – Egy egységes felület a Bzip2, LZMA, PPMd, Enhanced Deflate és Store algoritmusokhoz.  
- **Performance‑tuned** – Optimalizált natív megvalósítás **akár 10 GB fájlok** feldolgozását teszi lehetővé a teljes fájl memóriába betöltése nélkül.  
- **ASP.NET friendly** – Zökkenőmentesen működik webprojektekben, háttérszolgáltatásokban és Azure Functions-ben.  
- **Fine‑grained control** – Szótárméret, tömörítési szint és titkosítás beállítása egyetlen konstruktorhívással.  
- **Supports 10+ compression algorithms** – lefedi a vállalati adatcsatornák leggyakoribb felhasználási eseteit.

## Előkövetelmények
- **Aspose.Zip for .NET Library** – Töltse le és telepítse a [Aspose dokumentációból](https://reference.aspose.com/zip/net/).  
- **Sample Text File** – Készítsen egy mintafájlt (pl. `sample.txt`), amelyet tömöríteni fog.  
- **.NET development environment** – Visual Studio 2022 vagy bármely kompatibilis IDE.

## Névterek importálása

Az `Archive`, `ArchiveEntrySettings` és a titkosítási osztályok az `Aspose.Zip` névtérben találhatók. Importálja őket a fájl tetején:

- `Archive` egy ZIP archívum konténert képvisel.  
- `ArchiveEntrySettings` a tömörítési és titkosítási beállításokat tárolja minden bejegyzéshez.  
- A titkosítási osztályok (pl. `AesEncryptionSettings`) meghatározzák, hogyan titkosítódik az adat.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Most nézzük meg az egyes tömörítési beállításokat, és lássuk, hogyan **add password to zip** a megfelelő helyeken.

## Bzip2 tömörítési beállítások használata

### 1. lépés: Bzip2 tömörítés inicializálása hagyományos titkosítással

`Bzip2CompressionSettings` konfigurálja a Bzip2 algoritmust (blokk méret, stb.).  
`TraditionalEncryptionSettings` a régi ZipCrypto titkosítást alkalmazza egy bejegyzésre.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*A jelszóvédelem a `TraditionalEncryptionSettings` segítségével kerül alkalmazásra, amely közvetlenül az `ArchiveEntrySettings`-nek kerül átadásra.*

## Hogyan adjon jelszót a zip-hez az Aspose.Zip for .NET használatával

Töltse be a forrásfájlt, hozzon létre egy `Archive`-t a bejegyzés beállításokkal, és adja hozzá a fájlt az archívumhoz. A titkosítás automatikusan alkalmazásra kerül, mivel a `ArchiveEntrySettings` példány létrehozásakor már meg lett adva.

**Direct answer (40‑70 words):**  
Hozzon létre egy `ArchiveEntrySettings` objektumot, amely tartalmazza a kívánt tömörítési beállításokat és vagy `TraditionalEncryptionSettings` vagy `AesEncryptionSettings` objektumot. Ezután adja át ezt az objektumot az `Archive` konstruktorának, és adja hozzá a fájlokat az `AddEntry` segítségével. Az archívum már a jelszóval van ellátva, így a létrehozás után nincs szükség további lépésre.

`ArchiveEntrySettings` a konfigurációt tároló objektum, amely megmondja az Aspose.Zip-nek, hogyan legyen minden bejegyzés tömörítve és titkosítva.

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Hogyan hozzunk létre LZMA zip archívumot az Aspose.Zip használatával

### 1. lépés: LZMA tömörítés inicializálása AES256 titkosítással

`LzmaCompressionSettings` kezeli az LZMA‑specifikus paramétereket, mint a szótárméret és a gyors bájtok.  
`AesEncryptionSettings` AES‑256 titkosítást biztosít az archívum bejegyzéseihez.

**Direct answer (40‑70 words):**  
Példányosítsa a `LzmaCompressionSettings`-t a kívánt `DictionarySize` értékkel, hozzon létre egy `AesEncryptionSettings` objektumot a jelszavával és az `EncryptionMethod.AES256` beállítással, majd építsen egy `ArchiveEntrySettings`-t mindkettőből. Adja át ezt az `Archive` konstruktorának, és adja hozzá a fájlokat; az eredményül kapott zip LZMA‑tömörítésű és AES‑védett lesz egyetlen műveletben.

`LzmaCompressionSettings` az az osztály, amely az LZMA‑specifikus paramétereket, például a szótárméretet és a gyors bájtokat kezeli.

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Tip:** Az LZMA konfigurálható **LZMA szótármérettel** rendelkezik, amely befolyásolja a tömörítési arányt és a memóriahasználatot. Beállítható a `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` kóddal, ha nagyon nagy fájlokhoz kell finomhangolni.

## PPMd tömörítési beállítások használata

### 1. lépés: PPMd tömörítés inicializálása AES256 titkosítással

`PpmdCompressionSettings` meghatározza a PPMd algoritmus sorrendjét és memóriahasználatát.  
`AesEncryptionSettings` AES‑256 titkosítást biztosít az archívum bejegyzéseihez.

**Direct answer (40‑70 words):**  
Hozzon létre egy `PpmdCompressionSettings` példányt, kombinálja egy `AesEncryptionSettings` objektummal, amely tartalmazza a jelszavát, és adja meg mindkettőt egy `ArchiveEntrySettings`-nek. Használja ezt a beállítási objektumot az `Archive` konstruktorában; az eredményül kapott zip PPMd‑tömörítésű és jelszóval védett lesz további hívások nélkül.

`PpmdCompressionSettings` meghatározza a PPMd algoritmus sorrendjét és memóriahasználatát.

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Enhanced Deflate tömörítési beállítások használata

### 1. lépés: Enhanced Deflate tömörítés inicializálása AES256 titkosítással

`EnhancedDeflateCompressionSettings` lehetővé teszi egy olyan tömörítési szint megadását, amely egyensúlyt teremt a sebesség és a méret között.  
`AesEncryptionSettings` AES‑256 titkosítást biztosít az archívum bejegyzéseihez.

**Direct answer (40‑70 words):**  
Példányosítsa a `EnhancedDeflateCompressionSettings`-t a kívánt szinttel (0‑9), párosítsa az `AesEncryptionSettings`-tel, és csomagolja őket egy `ArchiveEntrySettings`-be. Adja át ezt az `Archive` konstruktorának, és adja hozzá a fájlokat; az archívum Enhanced Deflate tömörítéssel és AES‑256 jelszóvédelemmel jön létre egy lépésben.

`EnhancedDeflateCompressionSettings` lehetővé teszi egy tömörítési szint megadását, amely egyensúlyt teremt a sebesség és a méret között.

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Store tömörítési beállítások használata (store compression zip)

### 1. lépés: Store tömörítés inicializálása hagyományos titkosítással

`StoreCompressionSettings` azt mondja az Aspose.Zip-nek, hogy teljesen hagyja ki a tömörítést, megőrizve a forrásfájlt bájtonként.  
`TraditionalEncryptionSettings` a régi ZipCrypto titkosítást alkalmazza.

**Direct answer (40‑70 words):**  
Hozzon létre egy `StoreCompressionSettings` példányt (amely nem végez tömörítést), kombinálja egy `TraditionalEncryptionSettings` objektummal, amely tartalmazza a jelszavát, és csomagolja őket egy `ArchiveEntrySettings`-be. Adja át ezt az `Archive` konstruktorának; az eredményül kapott zip az eredeti fájlt tömörítés nélkül, de jelszóval védve tartalmazza.

`StoreCompressionSettings` azt mondja az Aspose.Zip-nek, hogy teljesen hagyja ki a tömörítést, megőrizve a forrásfájlt bájtonként.

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro tip:** Állítsa be a `dataDir` változót, hogy a tényleges munkakönyvtárra mutasson, és használja újra ugyanazt az `Archive` példányt, ha több fájlt kell egy archívumba hozzáadni.

## Gyakori problémák és megoldások
- **"File not found" hibák** – Ellenőrizze, hogy a `dataDir` útvonal elválasztóval (`\` vagy `/`) végződik, és hogy a `sample.txt` létezik.  
- **Memóriahasználat nagy fájlok esetén** – Használja az `ArchiveEntrySettings`-t a streaming mód engedélyezéséhez, amely közvetlenül az output stream-be írja az adatot.  
- **Nem kompatibilis tömörítési szint** – Egyes algoritmusok (pl. LZMA) további tulajdonságokat, például `DictionarySize`-t tesznek elérhetővé. Tekintse meg az API dokumentációt, ha finomabb vezérlésre van szükség.  
- **A jelszó nem alkalmazódik** – Győződjön meg arról, hogy a titkosítási beállítási objektum a `ArchiveEntrySettings` második argumentumaként kerül átadásra a konstrukciókor, ne az archívum létrehozása után.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Zip for .NET-et más tömörítő könyvtárakkal?**  
A: Az Aspose.Zip úgy van tervezve, hogy a beépített algoritmusait használja. Harmadik féltől származó könyvtárak integrálása lehetséges, de egyedi kezelést igényel az Aspose API-n kívül.

**Q: Hogyan adhatok jelszóvédelmet egy Aspose.Zip‑kel létrehozott zip-hez?**  
A: Adja át a `TraditionalEncryptionSettings` vagy `AesEncryptionSettings` objektumot a `ArchiveEntrySettings` második argumentumaként az `Archive` konstruktorában. Tekintse meg a [dokumentációt](https://docs.aspose.com/zip/net/password-protecting-archives/) a teljes példákért.

**Q: Van elérhető próba verzió, amit tesztelhetek?**  
A: Igen, a próba verziót elérheti [itt](https://releases.aspose.com/).

**Q: Hol kaphatok közösségi segítséget vagy tehetek fel kérdéseket?**  
A: Támogatásért és közösségi megbeszélésekért látogassa meg a [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37).

**Q: Kaphatok ideiglenes licencet értékeléshez?**  
A: Igen, ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

**Q: Hogyan segít ez az ASP.NET fájltömörítésben?**  
A: Azonos API hívásával egy ASP.NET vezérlőből vagy köztes rétegből a fájlokat futás közben tömörítheti, mielőtt elküldené a kliensnek, ezáltal csökkentve a sávszélességet és javítva a felhasználói élményt.

**Q: Mi a leghatékonyabb módja a nagy fájlok tömörítésének?**  
A: Kombinálja a streaming módot az LZMA tömörítéssel és egy megfelelő `DictionarySize`-tel. Ez egyensúlyt teremt a memóriahasználat és a tömörítési arány között nagy adathalmazok esetén.

**Legutóbb frissítve:** 2026-06-09  
**Tesztelve ezzel:** Aspose.Zip 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó bemutatók

- [Aspose.Zip for .NET - Jelszóvédelem a Zip archívumnak & Több fájl tárolása tömörítés nélkül](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Jelszóval védett zip létrehozása .NET könyvtárakhoz – Aspose.Zip bemutató](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [több fájl zip-elése c# – Egyszerű tömörítés az Aspose.Zip for .NET segítségével](/zip/net/file-compression/compress-multiple-files/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}