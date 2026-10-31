---
date: 2026-10-31
description: Ismerje meg, hogyan hozhat létre tar archívumot és tömörítheti TarBz2
  fájlba .NET-ben az Aspose.Zip használatával. A lépésről-lépésre útmutató bemutatja
  a tar létrehozását, a Bzip2 tömörítést és a legjobb gyakorlatok tippeit.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Tömörítés TarBz2-re
og_description: Ismerje meg, hogyan hozhat létre tar archívumot és tömörítheti TarBz2
  fájlba az Aspose.Zip for .NET használatával. A lépésről-lépésre útmutató bemutatja
  a tar létrehozását, a Bzip2 tömörítést és a legjobb gyakorlatok tippeit.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Tar archívum létrehozása és tömörítése TarBz2 formátumba .NET-el
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: Hogyan hozzunk létre tar archívumot és tömörítsük TarBz2 formátumba .NET-el
url: /hu/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre tar archívumot és tömörítsünk TarBz2 formátumba .NET‑el

Ebben az útmutatóban megtanulja, hogyan **hozzon létre tar archívum** fájlokat, majd egy kompakt **TarBz2** csomaggá tömörítse őket a **Aspose.Zip** .NET könyvtár segítségével. Akár biztonsági mentési segédprogramot épít, akár telepítési csomagokat készít, vagy könnyű súlyú terjesztési formátumra van szüksége, az alábbi lépések végigvezetik a fájlok tar konténerbe helyezésén, a Bzip2 tömörítés alkalmazásán és a végső `.tar.bz2` fájl írásán.

## Gyors válaszok
- **Milyen könyvtárat használjak?** Aspose.Zip for .NET  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc  
- **Szükségem van licencre?** Ideiglenes licenc szükséges a termeléshez; ingyenes próba elérhető  
- **Tömöríthetek több fájlt egyszerre?** Igen – annyi bejegyzést adhat hozzá, amennyit csak szeret a tar archívumhoz  
- **Kompatibilis a .NET 6+ verzióval?** Teljesen, az Aspose.Zip támogatja a .NET Framework‑ot és a .NET Core/5/6‑ot  

## Mi az a TarBz2 archívum?

A TarBz2 fájl a hagyományos **tar** konténert (amely megőrzi a könyvtárstruktúrát és a fájl metaadatait) kombinálja a **Bzip2** tömörítéssel, így egy erősen tömörített `.tar.bz2` csomagot hoz létre. Ez a formátum népszerű Unix‑szerű rendszereken, mivel jó egyensúlyt kínál a tömörítési arány és a kitömörítési sebesség között.

## Miért tömörítsük a fájlokat TarBz2 formátumba az Aspose.Zip‑szel?

Az Aspose.Zip **két API hívással** képes TarBz2 archívumot generálni, miközben hatékonyan kezeli a streameket. Támogat **50+ archívum- és tömörítési formátumot**, akár **2 GB** méretű fájlokat is feldolgoz anélkül, hogy az egész archívumot a memóriába töltené, és működik Windows, Linux és macOS .NET futtatókörnyezeteken. A könyvtár finomhangolt vezérlést biztosít a bejegyzésnevek, időbélyegek és tömörítési szintek felett, így ideális mind konzolos segédprogramok, mind webszolgáltatások számára.

## Előfeltételek

- **Aspose.Zip for .NET** – töltse le a legújabb csomagot a hivatalos oldalról: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – egy mappa, amely a archiválni kívánt fájlokat tartalmazza. A példákban a `dataDir` változóval hivatkozunk rá.

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

> Cserélje le a `"Your Document Directory"` értéket a forrásmappájának abszolút vagy relatív útvonalára.

## 2. lépés: fájlok hozzáadása a tar-hoz és TarBz2 archívum létrehozása

A `TarArchive` osztály egy memóriában lévő tar konténert képvisel, míg a `Bzip2Archive` a Bzip2 algoritmust használva tömöríti a streameket.  
A `CreateEntry` metódus új fájlbemenetet ad hozzá a tar archívumhoz.

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

- `CreateEntry` **fájlokat ad hozzá a tar-hoz** – ezt a metódust minden archívumban szükséges fájlhoz meghívhatja.  
- `bz2.SetSource(archive)` azt mondja a Bzip2 archívumnak, hogy tömörítse az egész tar streamet.  
- `bz2.Save(...)` a végleges **TarBz2** fájlt a lemezre írja.

**Tipp:** A **fájlok tar-hoz való hozzáadásához** tömegesen egyszerűen ismételje meg az `archive.CreateEntry` hívást minden fájlra, mielőtt meghívná a `bz2.Save`-t.

## Hogyan adjunk fájlokat a tar-hoz?

Töltse be a forráskönyvtárat, hozza létre a `TarArchive` példányt, adja hozzá minden fájlt a `CreateEntry` segítségével, majd csomagolja be a tar streamet egy `Bzip2Archive`-ba és hívja meg a `Save`-et. Ez a kéts lépéses minta tetszőleges számú fájlt ad hozzá, és egyetlen folytonos folyamatban hoz létre egy `.tar.bz2` fájlt, kiküszöbölve az ideiglenes fájlok vagy külső eszközök szükségességét.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Fájl nem található** hiba | Helytelen `dataDir` útvonal vagy hiányzó fájlkiterjesztés | Ellenőrizze a teljes útvonalat, és győződjön meg róla, hogy a fájl létezik. |
| **Üres archívum** | Nem adtak hozzá bejegyzéseket a `bz2.Save` előtt | Adjon hozzá legalább egy `CreateEntry` hívást. |
| **Hozzáférés megtagadva** | Az alkalmazásnak nincs írási joga a kimeneti mappához | Futtassa az alkalmazást megfelelő jogosultságokkal, vagy válasszon írható könyvtárat. |

## Gyakran ismételt kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET alkalmazással?**  
A: Igen. Működik .NET Framework‑kel, .NET Core‑ral, .NET 5/6‑tal és az újabb futtatókörnyezetekkel.

**Q: Tömöríthetek több fájlt egyszerre?**  
A: Teljesen. Hívja meg a `CreateEntry`-t minden fájlra, mielőtt elmenti az archívumot.

**Q: Hol találok további dokumentációt?**  
A: Részletes dokumentáció elérhető az **Aspose.Zip .NET API referencia**‑ban: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip‑hez?**  
A: **Ideiglenes licencet kérhet** itt: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Elérhető ingyenes próba?**  
A: Igen, **töltse le a próbaverziót az Aspose kiadásokból**: [download a trial version](https://releases.aspose.com/).

Szintén [letöltheti a      próbaverziót](https://releases.aspose.com/).

## Következtetés

Most már tudja, **hogyan hozzon létre tar archívumot**, hogyan tömörítse a tar streamet Bzip2‑vel, és hogyan generáljon **TarBz2** archívumot az Aspose.Zip for .NET segítségével. A megközelítés gyors, memóriahatékony, és minden modern .NET platformon működik. Nyugodtan kísérletezzen nagyobb fájlkészletekkel, egyedi bejegyzésnevekkel, vagy integrálja a kódot saját biztonsági mentési vagy telepítési folyamataiba.

Ha bármilyen nehézségbe ütközik, az Aspose.Zip közösség készen áll segíteni – csak látogasson el az **Aspose.Zip támogatási fórumra**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Legutóbb frissítve:** 2026-10-31  
**Tesztelve a következővel:** Aspose.Zip for .NET (legújabb kiadás)  
**Szerző:** Aspose  

## Kapcsolódó útmutatók

- [Tar archívum létrehozása és fájlok hozzáadása a tar-hoz az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Fájlok hozzáadása a tar-hoz és tömörítés TarZ formátumba az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}