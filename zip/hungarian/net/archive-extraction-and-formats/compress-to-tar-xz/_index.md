---
date: 2026-11-18
description: Ismerje meg, hogyan adhat fájlokat a tar-hoz, és tömörítheti a fájlokat
  tarxz archívumba .NET használatával az Aspose.Zip segítségével. Kövesse ezt a lépésről‑lépésre
  útmutatót a hatékony tárolás és átvitel érdekében.
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: Tömörítés TarXz-re
og_description: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip
  segítségével. Ismerje meg, hogyan tömörítheti a fájlokat TarXz-re .NET-ben gyorsan,
  magas tömörítési hatékonysággal és platformfüggetlen kompatibilitással.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével

## Bevezetés

Ha **add files to tar**-t kell végrehajtania, majd **create a tarxz archive .net**-et, az Aspose.Zip for .NET egyszerűvé és megbízhatóvá teszi a folyamatot. Akár naplókat, konfigurációs fájlokat vagy bármilyen egyéb eszközt csomagol tárolás vagy átvitel céljából, a TarXz formátumba történő tömörítés magas tömörítési arányt biztosít, miközben megőrzi a jól ismert tar struktúrát. Ebben az útmutatóban lépésről lépésre végigvezetjük a pontos lépéseken – kódrészletekkel együtt –, hogy magabiztosan integrálhassa a tarxz létrehozását .NET alkalmazásaiba. A végére megérti, miért az “add files to tar” az első lépés egy kompakt, platformok közötti csomag felé.

## Gyors válaszok

- **Mi a fő osztály?** `TarArchive` from `Aspose.Zip.Tar`
- **Hogyan tömöríthetek tarxz-re?** Call `SaveXzCompressed` after adding entries
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **Szükség van licencre?** Igen, egy érvényes Aspose.Zip licenc szükséges a termelési használathoz
- **Megvalósítási idő?** Körülbelül 5‑10 perc egy alap archívumhoz

## Mi az a TarXz archívum?

A TarXz archívum a hagyományos Unix `tar` tárolót kombinálja az XZ tömörítéssel. A tar rész több fájlt egyetlen adatfolyamba csomagol, míg az XZ erős, veszteségmentes tömörítést biztosít. Ez a formátum népszerű forráskód, biztonsági mentések és nagy adathalmazok terjesztésére, mivel megőrzi a könyvtárstruktúrákat, és kisebb fájlméreteket ér el, mint a sima tar vagy zip.

## Miért hozzunk létre tarxz archívumot .net-hez az Aspose.Zip segítségével?

A TarXz archívum létrehozása az Aspose.Zip segítségével gyors, egylépéses megoldást kínál külső eszközök nélkül. A fájlok 30‑50 %-kal kisebbek, mint a gzip, és több mint 20 archívumformátumot kezelhet közvetlenül .NET-ben. A könyvtár nagy archívumokat dolgoz fel anélkül, hogy a teljes fájlt memóriába töltené, így ideális felhőszolgáltatásokhoz és CI csővezetékekhez. Emellett több mint 50 bemeneti és kimeneti formátumot támogat.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve (töltse le a hivatalos [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) oldalról).  
- Egy mappával, amely tartalmazza a archiválni kívánt fájlokat. Az alábbi példákban ez a mappa a `dataDir` változóval van hivatkozva.  
- Érvényes Aspose.Zip licenccel (értékeléshez opcionális, termeléshez kötelező).

## Névterek importálása

Csak azokat a névtereket kell importálnia, amelyek a TarXz funkcionalitást biztosítják. A core Aspose.Zip könyvtáron kívül nincs szükség további csomagokra.

## Hogyan adjunk hozzá fájlokat a tar-hoz az Aspose.Zip használatával

A `TarArchive` az az osztály, amely a tar tárolót képviseli az Aspose.Zip-ben. Fájlokat a tar archívumhoz úgy adhat hozzá, hogy létrehoz egy `TarArchive` példányt, majd minden hozzáadni kívánt fájlhoz meghívja az `AddEntry` metódust, megadva a forrás útvonalát és egy opcionális bejegyzésnevet. Az archívum memóriában építi fel a tar tárolót, készen állva a későbbi XZ tömörítésre.

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tipp:** A `using` utasítás biztosítja, hogy az archívum megfelelően legyen eldobva, felszabadítva minden nem kezelt erőforrást.

### 1. lépés: `TarArchive` inicializálása

Hozza létre a `TarArchive` objektumot egy `using` blokkban, hogy a művelet befejezésekor az összes nem kezelt erőforrás automatikusan felszabaduljon.

```csharp
using (TarArchive archive = new TarArchive())
{
```

### 2. lépés: fájlok hozzáadása az archívumhoz

Adja hozzá az összes beilleszteni kívánt fájlt. Ebben a példában két szövegfájlt adunk hozzá, de tetszőleges számú bejegyzést hozzáadhat. Az `AddEntry` metódus a teljes fájlútvonalat és egy opcionális bejegyzésnevet fogad, amely a tar-ban fog megjelenni.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Miért fontos:** A bejegyzések hozzáadása a tömörítés előtt lehetővé teszi, hogy az Aspose.Zip először felépítse a tar tárolót, majd egy lépésben alkalmazza az XZ tömörítést.

### 3. lépés: archívum mentése XZ tömörítéssel

A `SaveXzCompressed` metódus egy lépésben írja a tar archívumot egy fájlba, miközben XZ tömörítést alkalmaz, így egy `.tar.xz` fájlt hoz létre, amely készen áll a terjesztésre.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Eredmény:** Most már rendelkezik egy teljesen tömörített `archive.tar.xz` fájllal, amely bármely, a TarXz-et támogató platformon átvitelre, tárolásra vagy kicsomagolásra alkalmas.

## Hogyan tömörítsünk tarxz fájlokat az Aspose.Zip segítségével

A tarxz-re történő tömörítés az Aspose.Zip segítségével egy kétlépéses folyamat, amely egyetlen metódushívásba van csomagolva: először **add files to tar**, majd meghívja a `SaveXzCompressed`-t. Ez megszünteti a külső parancssori eszközök szükségességét, és a teljes munkafolyamatot a .NET kódbázisban tartja.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|-------|-------|-----|
| **“File not found” exception** | Hibás `dataDir` útvonal | Ellenőrizze, hogy a könyvtár útvonala backslash-szel (`\`) végződik-e, vagy használja a `Path.Combine`-t. |
| **Large memory usage** | Nagyon nagy fájlok memóriában történő tömörítése | Használja a `TarArchive` streaming módot (`SaveXzCompressed` túlterhelés, amely `Stream`-et fogad). |
| **License not applied** | Hiányzó licencfájl | Töltse be a licencet az alkalmazás indításakor: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Gyakran feltett kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET környezettel?**  
A: Igen, az Aspose.Zip működik a .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 és a .NET 5–10 verziókkal. A részletekért tekintse meg a [documentation](https://reference.aspose.com/zip/net/) oldalt.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip-hez?**  
A: Ideiglenes licencet kérhet a [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) oldalon.

**Q: Van további példa más archívumformátumokra?**  
A: Természetesen—tekintse meg a teljes példakészletet a [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) oldalon.

**Q: Hol kaphatok segítséget vagy vitathatok problémákat?**  
A: Csatlakozzon a beszélgetéshez a [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) oldalon a közösségi támogatás és hivatalos válaszok érdekében.

**Q: Kipróbálhatom ingyen az Aspose.Zip-et vásárlás előtt?**  
A: Igen, ingyenes próba elérhető a [Aspose.Zip download page](https://releases.aspose.com/zip/net) oldalon.

## Összegzés

A fenti lépések követésével most már tudja, hogyan **add files to tar**, hogyan **compress tarxz** fájlokat, és ami még fontosabb, hogyan **create tarxz archive .net** az Aspose.Zip segítségével. Ez a megközelítés egy kompakt, hordozható csomagot biztosít, amely zökkenőmentesen integrálható bármely .NET munkafolyamatba – legyen szó asztali segédprogramról, webszolgáltatásról vagy automatizált CI/CD csővezetékről.

---

**Utolsó frissítés:** 2026-11-18  
**Tesztelve:** Aspose.Zip for .NET 24.11  
**Szerző:** Aspose  

## Kapcsolódó útmutatók

- [Tar archívum létrehozása és fájlok hozzáadása a tar-hoz az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hogyan tömörítsünk tar-t és hozzunk létre TarBz2-t az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Hogyan tömörítsünk több fájlt tar-ba az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}