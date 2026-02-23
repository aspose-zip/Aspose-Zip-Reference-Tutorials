---
date: 2026-02-23
description: Tanulja meg, hogyan lehet több fájlt tar formátumban tömöríteni az Aspose.Zip
  for .NET használatával, és hatékonyan tar.lz archívumokat létrehozni.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tömörítsünk több fájlt tar-ral az Aspose.Zip for .NET segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk több fájlt tar formátumban az Aspose.Zip for .NET segítségével

A modern .NET fejlesztésben a fájlok hatékony csomagolása drámaian javíthatja a telepítési méretet és a hálózati átvitel idejét. **Compress multiple files tar** gyakori követelmény, amikor könnyű, LZ‑tömörített TAR archívumra van szükség biztonsági mentésekhez, terjesztéshez vagy felhőfeltöltésekhez. Ebben az útmutatóban egyértelmű, lépésről‑lépésre **tar.lz compression example** példán keresztül mutatjuk be az Aspose.Zip könyvtár használatát, így gyorsan létrehozhat egy **tar.lz archive**‑t saját alkalmazásaiban.

## Gyors válaszok
- **What library should I use?** Aspose.Zip for .NET.  
- **How long does the implementation take?** Körülbelül 5‑10 perc egy alap példához.  
- **Do I need a license?** Az ingyenes próba verzió tesztelésre működik; a kereskedelmi licenc szükséges a termeléshez.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I compress multiple files at once?** Igen – csak adjon hozzá több bejegyzést a mentés előtt.

## Hogyan tömörítsünk több fájlt tar formátumban
Ez a szakasz közvetlenül a fő kulcsszóra reagál, és bemutatja a pontos lépéseket a **compress multiple files tar** használatához az Aspose.Zip segítségével. A megközelítés bármennyi fájlra működik, és könnyen alkalmazkodik saját mappaszerkezeteihez.

## Mi az a tar.lz tömörítés?
`tar.lz` egy TAR archívum, amelyet az LZMA algoritmus (gyakran egyszerűen **LZ**‑ként emlegetik) tömörített. Ötvözi a TAR fájlcsoportosításának egyszerűségét a LZ magas tömörítési arányával, így ideális biztonsági mentési fájlokhoz, csomag terjesztéshez vagy bármely olyan helyzetben, ahol a sávszélesség számít.

## Miért használjuk az Aspose.Zip for .NET-et?
Aspose.Zip elrejti az archiválás alacsony szintű részleteit, tiszta, objektum‑orientált API‑t biztosítva. Kapja meg:

* **Zero external dependencies** – tiszta .NET megvalósítás.  
* **Cross‑platform support** – Windows, Linux és macOS rendszereken működik.  
* **Built‑in LZ compression** – nincs szükség további natív eszközök telepítésére.  
* **Strong error handling** – a kivételek leíróak, ami megkönnyíti a hibakeresést.

## Előkövetelmények
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** library – töltse le [itt](https://releases.aspose.com/zip/net/).  
- Egy mappa, amely tartalmazza a archiválni kívánt fájlokat. Ennek a mappának az elérési útja a `dataDir` változóban lesz tárolva (a 3. lépésben állítja be).

## Névterek importálása
Adja hozzá a szükséges névtereket, hogy a fordító tudja, hol találja a használandó osztályokat.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan hozzunk létre tar.lz archívumot – Lépésről‑lépésre útmutató

### 1. lépés: Egyetlen fájl tömörítése
Az első példa a legegyszerűbb helyzetet mutatja – egy fájl hozzáadása egy TAR archívumhoz, majd mentése **tar.lz** fájlként.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Magyarázat**

- `new TarArchive()` egy üres TAR tárolót hoz létre.  
- `CreateEntry` hozzáadja az `alice29.txt` fájlt a `dataDir`‑ből.  
- `SaveLzipped` a lemezre írja az archívumot, és LZ tömörítést alkalmaz, így létrehozza a `archive.tar.lz`‑t.

### 2. lépés: Több fájl tömörítése egy archívumban
Gyakran szükség van több fájl egyesítésére. Csak hívja meg a `CreateEntry`‑t minden fájlra a mentés előtt. Ez bemutatja a **add files to tar lz** és hatékonyan a **compress multiple files tar**.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Magyarázat**

- A kód ugyanazt a mintát követi, mint az 1. lépés, de hozzáad egy második bejegyzést (`lcet10.txt`).  
- A `CreateEntry`‑t annyiszor ismételheti, ahányszor szükséges; a könyvtár automatikusan kezeli a belső TAR struktúrát.

### 3. lépés: Adja meg a dokumentum könyvtárát
Cserélje le a helyőrzőt a tényleges útvonalra, ahol a forrásfájlok találhatók. Ezt az útvonalat használják a fenti példák.

```csharp
string dataDir = "Your Document Directory";
```

**Magyarázat**

- `dataDir`‑t állítsa egy teljes elérési útra, például `@"C:\\MyFiles\\"`.  
- A könyvtár változóban tartása újrahasználhatóvá és könnyebben karbantarthatóvá teszi a kódot.

## Gyakori buktatók és hibaelhárítás
| Tünet | Valószínű ok | Javítás |
|---------|--------------|-----|
| `FileNotFoundException` a minta futtatásakor | `dataDir` egy nem létező mappára mutat, vagy a fájlnév el van gépelve | Ellenőrizze az útvonalat és a fájlneveket; a biztonság kedvéért használja a `Path.Combine`‑t. |
| A kimeneti fájl **0 KB** | `archive.SaveLzipped` hívása előtt nem lett bejegyzés hozzáadva | Győződjön meg arról, hogy legalább egy `CreateEntry` hívás megelőzi a `SaveLzipped`‑et. |
| A tömörítés lassúnak tűnik | Nagy fájlok az alapértelmezett puffer mérettel | Fontolja meg a fájlok darabokban történő feldolgozását vagy aszinkron I/O használatát, ha a teljesítmény kritikus. |

## Következtetés
Most már tudja, **how to compress tar.lz** fájlok létrehozását az Aspose.Zip for .NET segítségével, legyen szó egyetlen dokumentumról vagy fájlgyűjteményről. Ez a **tar.lz compression example** bemutat egy tiszta, termelésre kész módot a **create tar lz archive** fájlok létrehozására, amelyek könnyen áthelyezhetők vagy tárolhatók.

## Gyakran Ismételt Kérdések

**Q:** Tömöríthetek bármilyen méretű fájlokat az Aspose.Zip for .NET használatával?  
**A:** Igen, a könyvtár kezeli a kis és nagyon nagy fájlokat is; csak győződjön meg róla, hogy elegendő memória és lemezterület áll rendelkezésre a temporális TAR struktúrához.

**Q:** Kompatibilis a kód a legújabb Aspose.Zip kiadással?  
**A:** A példa a jelenlegi verzióra van célzva; mindig tartsa naprakészen a NuGet csomagot a hibajavítások és új funkciók miatt.

**Q:** Vannak licencelési szempontok?  
**A:** A termelési használathoz kereskedelmi licenc szükséges. Lásd a licenc részleteket az [Aspose weboldalon](https://purchase.aspose.com/buy).

**Q:** Használhatom ezt kereskedelmi projektben?  
**A:** Természetesen – ha érvényes licencet szerez, a könyvtárat bármely kereskedelmi alkalmazásba beágyazhatja.

**Q:** Hol kaphatok segítséget, ha problémákba ütközöm?  
**A:** Látogassa meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37) a közösségi támogatás és hivatalos segítség érdekében.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose