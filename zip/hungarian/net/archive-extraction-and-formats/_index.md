---
date: 2026-06-19
description: Ismerje meg, hogyan tömöríthet tar fájlokat, hozhat létre targz archívumokat,
  és nyerhet ki jelszóval védett zip fájlokat az Aspose.Zip for .NET használatával
  – növelve a tárolási hatékonyságot és a biztonságot.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Archívumok kibontása és formátumok
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
title: Hogyan tömörítsünk tar fájlokat az Aspose.Zip for .NET segítségével
url: /hu/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk Tar fájlokat az Aspose.Zip for .NET segítségével

## Bevezetés

Ebben az útmutatóban megtudja, **hogyan tömörítsen tar** fájlokat az Aspose.Zip for .NET használatával, megtanulja a TarGz archívumok létrehozását, és megismeri a jelszóval védett zip archívumok kicsomagolását. A hatékony archívumkezelés alapvető készség a modern .NET fejlesztők számára – legyen szó biztonsági mentési szolgáltatásról, felhő‑tároló kliensről vagy adatfeldolgozó csővezetről, ezeknek a formátumoknak a elsajátítása csökkenti a tárolási költségeket, felgyorsítja az átviteleket, és megvédi az érzékeny adatokat.

## Gyors válaszok
- **Mi az a TarBz2?** Egy tömörített archívum, amely a TAR csomagolást kombinálja a BZIP2 tömörítéssel a magas tömörítési arány érdekében.  
- **Miért válassza az Aspose.Zip for .NET-et?** Egyetlen, folyékony API-t kínál sok archívumformátum létrehozásához és kicsomagolásához külső függőségek nélkül.  
- **Létrehozhatok-e TarGz archívumot?** Igen – az Aspose.Zip támogatja a TarGz, TarLz, TarXz, TarZ és további formátumokat.  
- **Hogyan tudok kicsomagolni egy jelszóval védett zip archívumot?** Használja a `Password` tulajdonságot az `ArchiveEntry` objektumon a kicsomagolás során.  
- **Szükségem van licencre a termelésben való használathoz?** A termeléshez kereskedelmi licenc szükséges; ingyenes próba elérhető értékeléshez.

## Mi a Tar tömörítés?
A Tar (Tape Archive) egy konténerformátum, amely több fájlt és könyvtárat egyetlen adatfolyamba csomagol össze tömörítés nélkül. Amikor egy tömörítési algoritmust, például BZIP2, GZip, LZMA vagy XZ alkalmaz, az eredmény egy **tar‑alapú archívum** lesz, mint a `.tar.bz2`, `.tar.gz`, `.tar.lz` stb. Ezek a formátumok széles körben támogatottak Linuxon, macOS-en és Windowson, így ideálisak a platformok közötti adatcseréhez.

## Miért használja az Aspose.Zip for .NET-et ezen formátumok kezelésére?
Az Aspose.Zip egy **egységes, függőség‑mentes API-t** biztosít, amely több mint 50 archívum- és tömörítési formátumot támogat, köztük a TarBz2, TarGz, TarLz, TarXz és TarZ formátumokat. Windows, Linux és macOS rendszereken fut, és a stream‑alapú architektúrája a memóriahasználatot 10 MB alá tartja még több száz megabájtos archívumok esetén is. A jelszóvédelem beépített, lehetővé téve a bejegyzésenkénti titkosítást extra könyvtárak nélkül.

## Előfeltételek
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, vagy .NET 5–10.  
- Aspose.Zip for .NET NuGet csomag telepítve (`Install-Package Aspose.Zip`).  
- Alapvető ismeretek a C# fájl‑I/O‑ról és a .NET projekt rendszeréről.

## Lépésről‑lépésre útmutató

### Hogyan tömörítsünk Tar fájlokat – Közvetlen válasz
`Archive` egy archívumfájlt képvisel, és metódusokat biztosít a bejegyzések hozzáadásához és a mentéshez.  
Hozzon létre egy `Archive` példányt, adja hozzá a csomagolni kívánt fájlokat, állítsa be a `CompressionType.BZip2` értéket, majd hívja a `Save` metódust `ArchiveFormat.TarBz2` paraméterrel. A könyvtár egyetlen streaming lépésben írja a TAR konténert és tömöríti azt, így soha nem kell az egész archívumot a memóriába betölteni.

### 1. lépés: Válassza ki a szükséges archívumformátumot
Döntse el, melyik tar‑alapú formátum felel meg legjobban a tömörítési‑sebességi kompromisszumnak:

- **TarBz2** – Legmagasabb tömörítési arány (≈30 % kisebb, mint a TarGz), de lassabb.  
- **TarGz** – Jó egyensúly a sebesség és a méret között; ideális a legtöbb felhő‑tárolási szituációhoz.  
- **TarLz / TarXz** – Nagyon magas tömörítés közepes sebességgel, hasznos archiváláshoz.  
- **TarZ** – Örökölt formátum, kompatibilis a régebbi Unix eszközökkel.

### 2. lépés: Hozzon létre egy új `Archive` példányt
`Archive` a felső szintű objektum, amely egyetlen archívumfájlt képvisel a memóriában.  

Az `Archive` osztály kezeli a csomagolási és tömörítési munkafolyamatot, metódusokat biztosít a bejegyzések hozzáadásához és a végleges fájl írásához.

### 3. lépés: Fájlok és mappák hozzáadása
Teljes könyvtárfát adhat hozzá az `AddAll` metódussal, vagy egyedi fájlokat az `AddFile` segítségével. Az eredeti mappaszerkezet megőrzése egyszerűen a kiindulási könyvtár útvonalának megadásával történik.

### 4. lépés: A kívánt tömörítési típus beállítása
A `CompressionType` felsorolja a támogatott algoritmusokat.  

A `CompressionType` határozza meg, hogy melyik algoritmus (BZip2, GZip, LZMA, XZ stb.) kerül alkalmazásra a TAR adatfolyamon a mentés során.

### 5. lépés: Az archívum mentése
Az `ArchiveFormat` egy enum halmaz (pl. `TarBz2`, `TarGz`), amely megmondja az írónak, hogy melyik konténert és tömörítést használja.  

A `Save` hívás a kiválasztott formátummal írja a lemezre az archívumot.

### 6. lépés: Archívumok kicsomagolása jelszóval
Az `ArchiveEntry` egyetlen fájl‑ vagy könyvtárbejegyzést képvisel egy archívumban.  

Jelszóval védett zip kicsomagolásához nyissa meg az archívumot, keresse meg az egyes `ArchiveEntry` elemeket, állítsa be a `Password` tulajdonságot, majd hívja az `Extract` metódust. Ez a bejegyzésenkénti jelszómodell lehetővé teszi az egyes fájlok védelmét egyetlen zipben.

### 7. lépés: Az eredmény ellenőrzése
Kicsomagolás után hasonlítsa össze a fájlméreteket és a SHA‑256 ellenőrzőösszegeket, hogy megerősítse, az archívum körutazása megőrizte az adat integritását.

## Általános felhasználási esetek
- **Biztonsági mentés eszközök** – Napi mentéseket `.tar.bz2` formátumban tárolva akár 30 %-kal csökkenthető a tárolási költség.  
- **Kereszt‑platform adatcsere** – A Tar‑alapú formátumokat natívan felismerik a Linux, macOS és Windows eszközök.  
- **Biztonságos terjesztés** – Jelszavakat adhat a érzékeny bejegyzésekhez, ezzel megfelelve a megfelelőségi követelményeknek extra titkosító eszközök nélkül.

## Hibakeresés és tippek
- **Nagy archívumok** – Használja a streaming API‑t (`Archive.CreateEntryFromFile`) a memóriahasználat alacsonyan tartásához.  
- **Jelszó eltérések** – Minden `ArchiveEntry`-hez beállított jelszónak pontosan meg kell egyeznie; ellenkező esetben `InvalidPasswordException` kerül dobásra.  
- **Tömörítési szint** – A BZIP2 nem tesz lehetővé egyéni szinteket; ha finomabb vezérlésre van szükség, válassza az LZMA (`CompressionType.LZMA`) vagy XZ (`CompressionType.XZ`) opciót.  

## Gyakran ismételt kérdések

**K: Hogyan hozhatok létre egy TarGz archívumot?**  
A: Állítsa be a `CompressionType.GZip` értéket, és a `Save` híváskor használja az `ArchiveFormat.TarGz`-t. Ez egyetlen lépésben `.tar.gz` fájlt hoz létre.

**K: Kicsomagolhatok-e egy jelszóval védett archívumot a jelszó ismerete nélkül?**  
A: Nem. Minden bejegyzéshez a helyes jelszót kell megadni; ellenkező esetben `InvalidPasswordException` keletkezik.

**K: Az Aspose.Zip támogatja-e a különböző jelszavakkal rendelkező bejegyzések kicsomagolását?**  
A: Igen. Minden `ArchiveEntry`-hez külön jelszót lehet hozzárendelni a `Extract` hívása előtt.

**K: Melyik formátum nyújtja a legjobb tömörítést?**  
A: A TarBz2 általában a legkisebb méretet eredményezi, ezt követi a TarLz és a TarXz. A TarGz gyorsabb, de még mindig hatékony alternatíva.

**K: Van korlát a fájlok számában, amelyeket egy TAR archívumba felvehet?**  
A: Gyakorlatilag nincs, de nagyon nagy archívumok (>10 GB) esetén érdemes több részre bontani a könnyebb kezelhetőség érdekében.

## Archívum kicsomagolás és formátumok oktatóanyagai
### [Fájlok tömörítése TarBz2 formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-bz2/)
Ismerje meg, hogyan tömöríthet fájlokat TarBz2 formátumba .NET-ben az Aspose.Zip használatával. Kövesse lépésről‑lépésre útmutatónkat a hatékony fájltömörítéshez.  
### [Tömörítés TarGz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-gz/)
Fedezze fel a hatékony fájltömörítést .NET-ben az Aspose.Zip segítségével. Tömörítsen TarGz formátumba könnyedén.  
### [Tömörítés TarLz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-lz/)
Könnyedén tömöríthet fájlokat .NET-ben az Aspose.Zip segítségével. Tanulja meg lépésről‑lépésre a TarLz archívumok létrehozását.  
### [Tömörítés TarXz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-xz/)
Ismerje meg, hogyan tömöríthet fájlokat TarXz formátumba .NET-ben az Aspose.Zip használatával. Kövesse útmutatónkat a hatékony tároláshoz és továbbításhoz.  
### [Tömörítés TarZ formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-z/)
Fedezze fel a lépésről‑lépésre történő tömörítést TarZ formátumba az Aspose.Zip for .NET segítségével. Hatékony fájlkezelés .NET projektjeihez.  
### [Archívumbejegyzések kicsomagolása különböző jelszavakkal az Aspose.Zip for .NET-ben](./extract-archive-different-passwords/)
Ismerje meg, hogyan csomagolhat ki archívumbejegyzéseket különböző jelszavakkal az Aspose.Zip for .NET-ben. Növelje alkalmazásai biztonságát és rugalmasságát.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Tar archívum létrehozása és fájlok hozzáadása a tar-hoz az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hogyan tömörítsünk tar-t és hozzunk létre TarBz2 archívumot az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}