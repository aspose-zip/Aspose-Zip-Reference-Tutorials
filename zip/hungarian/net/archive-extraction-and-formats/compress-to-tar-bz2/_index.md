---
date: 2026-08-07
description: Ismerje meg, hogyan adhat fájlokat a tar-hoz, és hozhat létre TarBz2
  archívumot .NET környezetben az Aspose.Zip használatával. Lépésről‑lépésre útmutató
  a tar létrehozásáról, Bzip2 tömörítésről és a legjobb gyakorlatokról.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Tömörítés TarBz2 formátumba
og_description: Fájlok hozzáadása a tar-hoz és TarBz2 archívum generálása .NET-ben
  az Aspose.Zip használatával. Ez az útmutató a tar létrehozását, Bzip2 tömörítést
  és a hibaelhárítási tippeket tárgyalja.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Fájlok hozzáadása a tar-hoz és TarBz2 archívum létrehozása az Aspose.Zip
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Fájlok hozzáadása a tar-hoz és TarBz2 archívum létrehozása az Aspose.Zip segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fájlok hozzáadása a tar-hoz és TarBz2 archívum létrehozása az Aspose.Zip segítségével

Ebben az útmutatóban megtudja, **hogyan adhat fájlokat a tar** archívumokhoz, és alakíthatja őket egy kompakt **TarBz2** fájlba az **Aspose.Zip** .NET könyvtár segítségével. Akár biztonsági mentési segédprogramot épít, akár telepítési csomagokat publikál, vagy könnyű csomagra van szüksége a terjesztéshez, az alábbi lépések végigvezetik a fájlok tar konténerbe való hozzáadásán, a Bzip2 tömörítés alkalmazásán és egy megosztható archívum előállításán.

## Gyors válaszok
- **Milyen könyvtárat használjak?** Aspose.Zip for .NET  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc  
- **Szükségem van licencre?** Ideiglenes licenc szükséges a termeléshez; ingyenes próba elérhető  
- **Tömöríthetek több fájlt?** Igen – annyi bejegyzést adhat hozzá, amennyit csak szeret a tar archívumhoz  
- **Kompatibilis a .NET 6+-tal?** Teljesen, az Aspose.Zip támogatja a .NET Framework-ot és a .NET Core/5/6-ot  

## Mi az a TarBz2 archívum?

A TarBz2 fájl egyesíti a hagyományos **tar** konténert (amely megőrzi a könyvtárstruktúrát és a fájl metaadatait) a **Bzip2** tömörítéssel, így egy erősen tömörített `.tar.bz2` csomagot hoz létre. Ez a formátum népszerű Unix‑szerű rendszereken, mivel jó egyensúlyt kínál a tömörítési arány és a kitömörítési sebesség között.

## Miért tömörítsük a fájlokat TarBz2 formátumba az Aspose.Zip segítségével?

Az Aspose.Zip **két API hívás** segítségével képes TarBz2 archívumot generálni, miközben hatékonyan kezeli a stream-eket. Támogat **50+ archívum- és tömörítési formátumot**, akár **2 GB** méretű fájlokat is feldolgoz anélkül, hogy az egész archívumot a memóriába töltené, és fut Windows, Linux és macOS .NET futtatókörnyezeteken. A könyvtár finomhangolt vezérlést biztosít a bejegyzésnevek, időbélyegek és tömörítési szintek felett, így ideális mind konzolsegédprogramok, mind webszolgáltatások számára.

## Előfeltételek

- **Aspose.Zip for .NET** – töltse le a legújabb csomagot a hivatalos oldalról: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – egy mappa, amely tartalmazza a archiválni kívánt fájlokat. A példákban a `dataDir` változóval hivatkozunk rá.

> **Pro tipp:** Tartsa a forrásfájlokat egy dedikált mappában, hogy elkerülje a nem kívánt fájlok véletlen beillesztését.

## Névterek importálása

Először importálja a szükséges névtereket, hogy hozzáférhessen az Aspose.Zip Tar és Bzip2 osztályaihoz.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 1. lépés: a dokumentumkönyvtár beállítása

Határozza meg azt az útvonalat, amely a archiválni kívánt fájlokat tartalmazó mappára mutat.

```csharp
string dataDir = "Your Document Directory";
```

> Cserélje le a `"Your Document Directory"`-t a forrásmappája abszolút vagy relatív útvonalára.

## 2. lépés: fájlok hozzáadása a tar-hoz és TarBz2 archívum létrehozása

`TarArchive` egy memóriában lévő tar konténert képvisel, amely több fájlbemenetet is tárolhat.  
`Bzip2Archive` a Bzip2 algoritmust használva tömörít egy stream-et.  
A `CreateEntry` metódus egy fájlt ad hozzá a tar archívumhoz új bejegyzésként.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **fájlok hozzáadása a tar-hoz** – ezt a metódust minden archiválandó fájlhoz meghívhatja.  
- `bz2.SetSource(archive)` azt mondja a Bzip2 archívumnak, hogy tömörítse az egész tar stream-et.  
- `bz2.Save(...)` a végleges **TarBz2** fájlt a lemezre írja.

**Tipp:** A **fájlok hozzáadása a tar-hoz** tömegesen egyszerűen ismételje meg az `archive.CreateEntry`-t minden fájlra, mielőtt meghívná a `bz2.Save`-t.

## Hogyan adjunk fájlokat a tar-hoz?

Töltse be a forráskönyvtárat, hozzon létre egy `TarArchive` példányt, adja hozzá minden fájlt a `CreateEntry`-vel, majd csomagolja be a tar stream-et egy `Bzip2Archive`-ba, és hívja meg a `Save`-et. Ez a kétlépéses minta tetszőleges számú fájlt ad hozzá, és egy `.tar.bz2` fájlt hoz létre egyetlen folyékony lépésben, kiküszöbölve az ideiglenes fájlok vagy külső eszközök szükségességét.

## Gyakori problémák és megoldások

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** hiba | Helytelen `dataDir` útvonal vagy hiányzó fájlkiterjesztés | Ellenőrizze a teljes útvonalat, és győződjön meg arról, hogy a fájl létezik. |
| **Empty archive** | Nincsenek bejegyzések hozzáadva a `bz2.Save` előtt | Adjon hozzá legalább egy `CreateEntry` hívást. |
| **Permission denied** | Az alkalmazásnak nincs írási jogosultsága a kimeneti mappához | Futtassa az alkalmazást megfelelő jogosultságokkal, vagy válasszon írható könyvtárat. |

## Gyakran feltett kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET alkalmazással?**  
A: Igen. Működik a .NET Framework, .NET Core, .NET 5/6 és az újabb futtatókörnyezetekkel.

**Q: Tömöríthetek több fájlt egyszerre?**  
A: Teljesen. Hívja meg a `CreateEntry`-t minden fájlra, mielőtt elmenti az archívumot.

**Q: Hol találok további dokumentációt?**  
A: Részletes dokumentáció elérhető az **Aspose.Zip .NET API referencia**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip-hez?**  
A: **Ideiglenes licencet kérhet** itt: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Van elérhető ingyenes próba?**  
A: Igen, **letölthet egy próbaverziót az Aspose kiadásokból**: [download a trial version](https://releases.aspose.com/).

## Összegzés

Most már tudja, **hogyan adjon fájlokat a tar-hoz**, tömörítse a tar stream-et Bzip2-vel, és generáljon egy **TarBz2** archívumot az Aspose.Zip for .NET segítségével. A megközelítés gyors, memóriahatékony, és minden modern .NET platformon működik. Nyugodtan kísérletezzen nagyobb fájlkészletekkel, egyedi bejegyzésnevekkel, vagy integrálja a kódot saját biztonsági mentési vagy telepítési folyamatába.

Ha bármilyen nehézségbe ütközik, az Aspose.Zip közösség készen áll segíteni – látogasson el az **Aspose.Zip támogatási fórumra**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-08-07  
**Tesztelve:** Aspose.Zip for .NET (latest release)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Tar archívum létrehozása és fájlok hozzáadása a tar-hoz az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Fájlok hozzáadása a tar-hoz és tömörítés TarZ formátumba az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}