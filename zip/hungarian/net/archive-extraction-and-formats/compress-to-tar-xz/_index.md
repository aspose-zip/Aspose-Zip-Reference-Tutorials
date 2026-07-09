---
date: 2026-07-09
description: Ismerje meg, hogyan adhat fájlokat a tar-hoz, és tömörítheti a fájlokat
  tarxz archívumba .NET környezetben az Aspose.Zip használatával. Kövesse ezt a lépésről‑lépésre
  útmutatót a hatékony tárolás és továbbítás érdekében.
keywords:
- add files to tar
- compress files to tarxz
- how to create tarxz
- compress tar with xz
lastmod: 2026-07-09
linktitle: Tömörítés TarXz-re
og_description: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip
  segítségével. Ismerje meg, hogyan tömörítheti a fájlokat TarXz formátumba .NET környezetben
  gyorsan, kódról‑független lépésekkel és magas tömörítési hatékonysággal.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-09'
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
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
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

# Fájlok hozzáadása a tar-hez és tarxz archívum létrehozása az Aspose.Zip segítségével

## Bevezetés

Ha **fájlokat kell hozzáadni a tar-hez**, majd **tarxz archívumot kell létrehozni .net környezetben**, az Aspose.Zip for .NET egyszerűvé és megbízhatóvá teszi a folyamatot. Legyen szó naplókról, konfigurációs fájlokról vagy bármilyen egyéb eszközről, amelyet tárolni vagy továbbítani szeretne, a TarXz formátumba történő tömörítés magas tömörítési arányt biztosít, miközben megőrzi a jól ismert tar struktúrát. Ebben az oktatóanyagban lépésről‑lépésre bemutatjuk a pontos eljárást – kódrészletekkel együtt –, hogy magabiztosan integrálhassa a tarxz létrehozását .NET alkalmazásaiba. A végére megérti, miért az „fájlok hozzáadása a tar-hez” az első lépés egy kompakt, platform‑független csomag felé.

## Gyors válaszok
- **Mi a fő osztály?** `TarArchive` a `Aspose.Zip.Tar`‑ból
- **Hogyan tömöríthetek tarxz formátumba?** Hívja a `SaveXzCompressed`‑t a bejegyzések hozzáadása után
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10
- **Szükség van licencre?** Igen, érvényes Aspose.Zip licenc szükséges a termelési használathoz
- **Megvalósítási idő?** Körülbelül 5‑10 perc egy alap archívumhoz

## Mi az a TarXz archívum?

A **TarXz archívum** a hagyományos Unix `tar` tárolót kombinálja az XZ tömörítéssel. A tar rész több fájlt csomagol egyetlen adatfolyamba, míg az XZ erős, veszteségmentes tömörítést biztosít. Ez a formátum népszerű forráskód, biztonsági mentések és nagy adatállományok terjesztésére, mivel megőrzi a könyvtárstruktúrákat és kisebb fájlméreteket eredményez, mint a sima tar vagy zip.

## Miért hozzunk létre tarxz archívumot .net környezetben az Aspose.Zip használatával?

TarXz archívum létrehozása az Aspose.Zip‑el gyors, egylépéses megoldást nyújt, amely kiküszöböli a külső eszközök használatát. **30‑50 % kisebb fájlokat kap, mint a gzip**, és **20+ archívumformátumot** kezel anélkül, hogy elhagyná a .NET folyamatot. Az Aspose.Zip több száz oldalas archívumokat dolgoz fel anélkül, hogy a teljes fájlt a memóriába töltené, így ideális felhőszolgáltatásokhoz és CI pipeline‑okhoz.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve (töltse le a hivatalos [Aspose.Zip dokumentációból](https://reference.aspose.com/zip/net/)).  
- Egy mappával, amely a becsomagolandó fájlokat tartalmazza. Az alábbi példákban ez a mappa a `dataDir` változóval van hivatkozva.  
- Érvényes Aspose.Zip licenccel (értékeléshez opcionális, termeléshez kötelező).

## Névterek importálása

Először importálja azokat a névtereket, amelyek a TarXz funkcionalitást biztosítják.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan adjunk fájlokat a tar-hez az Aspose.Zip használatával

A `TarArchive` osztály egy tar tárolót képvisel, és kezeli annak bejegyzéseit.

Töltse be a forrásfájlokat, hozza létre a `TarArchive`‑t, és adja hozzá minden bejegyzést – ez a „fájlok hozzáadása a tar-hez” művelet magja. A `TarArchive` osztály a tar tárolót memóriában építi fel, majd egyetlen hívással alkalmazhat XZ tömörítést.

### 1. lépés: `TarArchive` inicializálása

A `TarArchive` a legfelső szintű objektum, amely a tar tárolót képviseli az Aspose.Zip‑ben. Kezeli a bejegyzéseket, és módszereket biztosít az archívum mentéséhez.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tipp:** A `using` utasítás biztosítja, hogy az archívum megfelelően legyen felszabadítva, és minden nem kezelt erőforrást elengedjen.

### 2. lépés: Fájlok hozzáadása az archívumhoz

Adja hozzá az összes kívánt fájlt. Ebben a példában két szövegfájlt adunk hozzá, de tetszőleges számú bejegyzést felvehet.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Miért fontos:** A bejegyzések hozzáadása a tömörítés előtt lehetővé teszi, hogy az Aspose.Zip először felépítse a tar tárolót, majd egy lépésben alkalmazza az XZ tömörítést.

### 3. lépés: Archívum mentése XZ tömörítéssel

A `SaveXzCompressed` a tar archívumot a lemezre írja, miközben XZ tömörítést alkalmaz, egyetlen műveletben létrehozva a `.tar.xz` fájlt.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Eredmény:** Most már rendelkezik egy teljesen tömörített `archive.tar.xz` fájllal, amely átvihető, tárolható vagy kibontható bármely platformon, amely támogatja a TarXz‑et.

## Hogyan tömörítsünk tarxz fájlokat az Aspose.Zip segítségével

A tarxz tömörítés az Aspose.Zip‑el egy kéts lépésből álló folyamat, amely egyetlen metódushívásba van összefoglalva: először **fájlokat adunk hozzá a tar-hez**, majd meghívjuk a `SaveXzCompressed`‑t. Ez megszünteti a külső parancssori segédeszközök szükségességét, és a teljes munkafolyamatot a .NET kódbázisban tartja.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **„File not found” kivétel** | Helytelen `dataDir` útvonal | Ellenőrizze, hogy a könyvtár útvonala backslash‑sel (`\`) végződik‑e, vagy használja a `Path.Combine` metódust. |
| **Nagy memóriahasználat** | Nagyon nagy fájlok memóriában történő tömörítése | Használja a `TarArchive` streaming módot (`SaveXzCompressed` túlterhelés, amely `Stream`‑et fogad). |
| **Licenc nincs alkalmazva** | Hiányzó licencfájl | Töltse be a licencet az alkalmazás indításakor: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Gyakran Ismételt Kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET környezettel?**  
A: Igen, az Aspose.Zip működik a .NET Framework 2.0–4.8.1, a .NET Core 2.0–3.1, valamint a .NET 5–10 verziókkal. Lásd a [dokumentációt](https://reference.aspose.com/zip/net/) a részletekért.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip-hez?**  
A: Ideiglenes licencet kérhet a [Aspose ideiglenes licenc oldaláról](https://purchase.aspose.com/temporary-license/).

**Q: Vannak további példák más archívumformátumokra?**  
A: Természetesen – tekintse meg a teljes példakészletet az [Aspose.Zip API referenciában](https://reference.aspose.com/zip/net/).

**Q: Hol kaphatok segítséget vagy vitathatok problémákat?**  
A: Csatlakozzon a közösséghez a [Aspose.Zip fórumon](https://forum.aspose.com/c/zip/37), ahol támogatást és hivatalos válaszokat talál.

**Q: Próbálhatom-e ingyen az Aspose.Zip-et vásárlás előtt?**  
A: Igen, ingyenes próbaverzió elérhető az [Aspose.Zip letöltési oldalon](https://releases.aspose.com/zip/net).

## Következtetés

A fenti lépések követésével most már tudja, **hogyan adjon fájlokat a tar-hez** és **hogyan tömörítsen tarxz fájlokat**, valamint, ami még fontosabb, **hogyan hozza létre a tarxz archívumot .net környezetben** az Aspose.Zip segítségével. Ez a megközelítés kompakt, hordozható csomagot biztosít, amely zökkenőmentesen integrálható bármely .NET munkafolyamatba – legyen szó asztali segédprogramról, webszolgáltatásról vagy automatizált CI/CD pipeline‑ról.

---

**Last Updated:** 2026-07-09  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Tar archívum létrehozása és fájlok hozzáadása a tar-hez az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hogyan tömörítsünk tar-t és hozzunk létre TarBz2-t az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Hogyan tömörítsünk több fájlt tar-ral az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}