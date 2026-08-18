---
date: 2026-07-04
description: Ismerje meg, hogyan lehet több fájlt tar formátumban tömöríteni az Aspose.Zip
  for .NET használatával, és hatékonyan tar.lz archívumokat létrehozni.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Tömörítés TarLz formátumba
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tömörítsünk több fájlt tar formátumban az Aspose.Zip for .NET segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk több fájlt tar formátumban az Aspose.Zip for .NET segítségével

A modern .NET fejlesztésben a fájlok hatékony csomagolása jelentősen javíthatja a telepítési méretet és a hálózati átvitel idejét. **Több fájl tar tömörítése** gyakori követelmény, amikor könnyű, LZ‑tömörített TAR archívumra van szükség biztonsági mentésekhez, terjesztéshez vagy felhő feltöltésekhez. Ebben az útmutatóban egy világos, lépésről‑lépésre **tar.lz tömörítési példa**-t mutatunk be az Aspose.Zip könyvtár használatával, hogy gyorsan létrehozhass egy **tar.lz archívum**-ot a saját alkalmazásaidban.

## Gyors válaszok
- **Melyik könyvtárat kell használnom?** Aspose.Zip for .NET.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alap példához.  
- **Szükségem van licencre?** Egy ingyenes próba verzió teszteléshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Tömöríthetek több fájlt egyszerre?** Igen – csak adj hozzá több bejegyzést a mentés előtt.

## Hogyan tömöríthetek több fájlt tar formátumban az Aspose.Zip for .NET segítségével?
Töltsd be a forrásfájlokat, hozz létre egy `TarArchive` példányt, add hozzá minden fájlt a `CreateEntry` segítségével, majd fejezd be a `SaveLzipped` hívásával. A könyvtár belsőleg kezeli a TAR struktúrát és az LZ tömörítést, így néhány kódsorral egyetlen `*.tar.lz` fájlt kapsz. Ez a megközelítés Windows, Linux és macOS rendszereken is működik natív függőségek nélkül.

## Mi az a tar.lz tömörítés?
`tar.lz` egy TAR archívum, amelyet az LZMA algoritmussal (gyakran egyszerűen **LZ**‑nek nevezik) tömörítettek. Összekapcsolja a TAR egyszerű fájlcsoportosítását a LZ magas tömörítési arányával, így ideális biztonsági mentésekhez, csomag terjesztéshez vagy bármely olyan helyzetben, ahol a sávszélesség számít.

## Miért használjuk az Aspose.Zip for .NET-et?
Aspose.Zip egy tisztán menedzselt, platformfüggetlen megoldást nyújt, amely TAR, ZIP és LZ‑alapú archívumokat hoz létre külső eszközök nélkül, több mint 30 archívumformátumot támogat, és akár 30 % jobb tömörítést biztosít nagy fájlok esetén, miközben részletes kivételeket kínál a robusztus hibakezeléshez. Emellett zökkenőmentesen integrálódik a .NET naplózási keretrendszerekkel, és részletes előrehaladási eseményeket biztosít.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- **Aspose.Zip for .NET** könyvtárral – töltsd le [innen](https://releases.aspose.com/zip/net/).  
- Egy mappával, amely tartalmazza a archiválni kívánt fájlokat. Ennek a mappának az elérési útja a `dataDir` változóban lesz tárolva (a 3. lépésben állítod be).

## Névterek importálása
Add hozzá a szükséges névtereket, hogy a fordító tudja, hol találja a használni kívánt osztályokat.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan hozzunk létre tar.lz archívumot – Lépés‑ről‑lépésre útmutató

### 1. lépés: Egyetlen fájl tömörítése
Az első példa a legegyszerűbb forgatókönyvet mutatja – egy fájl hozzáadása egy TAR archívumhoz, majd mentése **tar.lz** fájlként.

A `TarArchive` osztály egy TAR konténert képvisel, amely több fájlt is tartalmazhat egyetlen archívumban.  

**Magyarázat**

- `new TarArchive()` egy üres TAR konténert hoz létre.  
- `CreateEntry` hozzáadja az `alice29.txt` fájlt a `dataDir` könyvtáradból.  
- `SaveLzipped` a lemezre írja az archívumot, és LZ tömörítést alkalmaz, így keletkezik az `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 2. lépés: Több fájl tömörítése egy archívumban
Gyakran szükség van több fájl együttes csomagolására. Hívjuk meg egyszerűen a `CreateEntry`‑t minden fájlra a mentés előtt. Ez demonstrálja a **fájlok hozzáadása tar lz‑hez** és a **több fájl tar‑ként történő tömörítése**.

**Magyarázat**

- A kód ugyanazt a mintát követi, mint az 1. lépés, de egy második bejegyzést (`lcet10.txt`) ad hozzá.  
- A `CreateEntry`‑t annyiszor ismételheted, ahányszor szükséges; a könyvtár automatikusan kezeli a belső TAR struktúrát.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 3. lépés: A dokumentumkönyvtár megadása
Cseréld le a helyőrzőt a tényleges útvonalra, ahol a forrásfájlok találhatók. Ez az útvonal lesz használva a fenti példákban.

**Magyarázat**

- Állítsd be a `dataDir`‑t egy teljes elérési útra, például `@"C:\MyFiles\"`.  
- A könyvtár változóban való tárolása újrahasználhatóvá és könnyebben karbantarthatóvá teszi a kódot.

```csharp
string dataDir = "Your Document Directory";
```

## Gyakori hibák és hibaelhárítás
| Tünet | Valószínű ok | Javítás |
|---------|--------------|-----|
| `FileNotFoundException` a minta futtatásakor | `dataDir` egy nem létező mappára mutat vagy a fájlnév el van gépelve | Ellenőrizd az útvonalat és a fájlneveket; biztonság kedvéért használd a `Path.Combine`‑t. |
| A kimeneti fájl **0 KB** | `archive.SaveLzipped` a bejegyzések hozzáadása előtt lett meghívva | Győződj meg róla, hogy legalább egy `CreateEntry` hívás megelőzi a `SaveLzipped`‑t. |
| A tömörítés lassúnak tűnik | Nagy fájlok alapértelmezett puffermérettel | Fontold meg a fájlok darabokra bontását vagy aszinkron I/O használatát, ha a teljesítmény kritikus. |

## Összegzés
Most már tudod, **hogyan tömöríts tar.lz** fájlokat az Aspose.Zip for .NET segítségével, legyen szó egyetlen dokumentumról vagy fájlgyűjteményről. Ez a **tar.lz tömörítési példa** egy tiszta, termelés‑kész módot mutat be **tar lz archívum** létrehozására, amely könnyen átvihető vagy tárolható. Ugyanazt az API‑t használva a `SaveLzipped` hívásával minden kívánt bejegyzés hozzáadása után tömörítheted a fájlokat tar.lz‑be.

## Gyakran ismételt kérdések

**K:** Tömöríthetek bármilyen méretű fájlt az Aspose.Zip for .NET‑el?  
**V:** Igen, a könyvtár kis és nagyon nagy fájlok egyaránt kezeli; csak győződj meg róla, hogy elegendő memória és lemezterület áll rendelkezésre a ideiglenes TAR struktúrához.

**K:** A kód kompatibilis a legújabb Aspose.Zip kiadással?  
**V:** A minta a jelenlegi verzióra van célzva; mindig tartsd naprakészen a NuGet csomagot a hibajavítások és új funkciók érdekében.

**K:** Vannak licencelési szempontok?  
**V:** Kereskedelmi licenc szükséges a termelési használathoz. Lásd a licenc részleteket az [Aspose weboldalán](https://purchase.aspose.com/buy).

**K:** Használhatom kereskedelmi projektben?  
**V:** Természetesen – amint érvényes licenced van, beágyazhatod a könyvtárat bármely kereskedelmi alkalmazásba.

**K:** Hol kaphatok segítséget, ha problémába ütközöm?  
**V:** Látogasd meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37) a közösségi támogatás és a hivatalos segítség érdekében.

---

**Utoljára frissítve:** 2026-07-04  
**Tesztelve:** Aspose.Zip for .NET (legújabb kiadás)  
**Szerző:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}