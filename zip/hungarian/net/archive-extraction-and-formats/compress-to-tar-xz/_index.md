---
date: 2026-02-23
description: Ismerje meg, hogyan adhat fájlokat a tar-archívumhoz, és hogyan tömörítheti
  a fájlokat tarxz archívumba .NET környezetben az Aspose.Zip segítségével. Kövesse
  ezt a lépésről‑lépésre útmutatót a hatékony tárolás és átvitel érdekében.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

:** 2026-02-23 -> keep date.

**Tested With:** Aspose.Zip for .NET 24.11 -> keep.

**Author:** Aspose -> keep.

Then closing shortcodes.

Now produce final content with same markdown.

Let's translate.

I'll write Hungarian translations.

Be careful with bold formatting.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fájlok hozzáadása a tar-hez és tarxz archívum létrehozása az Aspose.Zip segítségével

## Bevezetés

Ha **fájlokat kell hozzáadni a tar-hez** és aztán **tarxz archívumot kell létrehozni .net környezetben**, az Aspose.Zip for .NET egyszerűvé és megbízhatóvá teszi a folyamatot. Akár naplókat, konfigurációs fájlokat vagy bármilyen egyéb erőforrást csomagol el tárolás vagy átvitel céljából, a TarXz formátumba történő tömörítés magas tömörítési arányt biztosít, miközben megőrzi a jól ismert tar struktúrát. Ebben az útmutatóban lépésről‑lépésre bemutatjuk a pontos lépéseket – kódrészletekkel együtt –, hogy magabiztosan integrálhassa a tarxz létrehozását .NET alkalmazásaiba.

## Gyors válaszok
- **Mi a fő osztály?** `TarArchive` a `Aspose.Zip.Tar`‑ból
- **Hogyan tömörítsünk tarxz‑et?** Használja a `SaveXzCompressed`‑t a bejegyzések hozzáadása után
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Szükséges licenc?** Igen, érvényes Aspose.Zip licenc a termeléshez
- **Átlagos megvalósítási idő?** ~5‑10 perc

## Mi az a TarXz archívum?

A **TarXz archívum** a hagyományos Unix `tar` konténert kombinálja az XZ tömörítéssel. A tar rész több fájlt csomagol egyetlen adatfolyamba, míg az XZ erős, veszteségmentes tömörítést biztosít. Ez a formátum népszerű forráskód, biztonsági mentés és nagy adathalmazok terjesztésére, mivel megőrzi a könyvtárstruktúrákat és kisebb fájlméretet ér el, mint a sima tar vagy zip.

## Miért hozzunk létre tarxz archívumot .net környezetben az Aspose.Zip segítségével?

- **Magas tömörítési arány** – Az XZ gyakran 30‑50 %-kal kisebb, mint a gzip.  
- **Keresztplatformos kompatibilitás** – TarXz fájlok nyithatók Linuxon, macOS‑on és Windowson.  
- **Egyszerű API** – Az Aspose.Zip elrejti az alacsony szintű részleteket, így csak az üzleti logikára koncentrálhat.  
- **Nincs külső eszköz** – Minden a .NET folyamaton belül fut, ami tökéletes felhő- vagy CI‑pipeline‑okhoz.

## Előkövetelmények

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve (töltse le a hivatalos [Aspose.Zip dokumentációból](https://reference.aspose.com/zip/net/)).  
- Egy mappával, amely a becsomagolandó fájlokat tartalmazza. Az alábbi példákban ez a mappa a `dataDir` változóval van hivatkozva.  
- Érvényes Aspose.Zip licenccel (opcionális értékeléshez, kötelező a termeléshez).

## Névterek importálása

Először importálja azokat a névtereket, amelyek a TarXz funkcionalitást biztosítják.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan adjunk fájlokat a tar-hez az Aspose.Zip használatával

Az alábbi lépés‑ről‑lépésre útmutató pontosan bemutatja, hogyan **adjunk fájlokat a tar-hez** a tömörítés előtt.

### 1. lépés: `TarArchive` inicializálása

Hozzon létre egy új `TarArchive` példányt, amely a tömöríteni kívánt fájlokat fogja tartalmazni.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tipp:** A `using` utasítás biztosítja, hogy az archívum megfelelően legyen felszabadítva, és minden nem kezelt erőforrás elengedésre kerüljön.

### 2. lépés: Fájlok hozzáadása az archívumhoz

Adja hozzá az összes beilleszteni kívánt fájlt. Ebben a példában két szövegfájlt adunk hozzá, de tetszőleges számú bejegyzést felvehet.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Miért fontos:** A bejegyzések hozzáadása a tömörítés előtt lehetővé teszi, hogy az Aspose.Zip először felépítse a tar konténert, majd egy lépésben alkalmazza az XZ tömörítést.

### 3. lépés: Archívum mentése XZ tömörítéssel

Végül írja a tar archívumot a lemezre XZ tömörítéssel. A kapott fájl `.tar.xz` kiterjesztésű lesz.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Eredmény:** Most már rendelkezik egy teljesen tömörített `archive.tar.xz` fájllal, amely átvihető, tárolható vagy kicsomagolható bármely, TarXz‑ot támogató platformon.

## Hogyan tömörítsünk tarxz fájlokat az Aspose.Zip segítségével

A fenti folyamat lényegében **hogyan tömörítsünk tarxz fájlokat**: először fájlokat adunk hozzá egy tar konténerhez (`add files to tar`), majd meghívjuk a `SaveXzCompressed`‑t. Ez az egyetlen hívású megközelítés megszünteti a külső parancssori eszközök szükségességét, és mindent a .NET kódbázisban tart.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **„File not found” kivétel** | Hibás `dataDir` útvonal | Ellenőrizze, hogy a könyvtárútvonal backslash‑szel (`\`) végződik, vagy használja a `Path.Combine`‑t. |
| **Nagy memóriahasználat** | Nagyon nagy fájlok memóriában történő tömörítése | Használja a `TarArchive`‑t streaming módban (`SaveXzCompressed` túlterhelése, amely `Stream`‑et fogad). |
| **Licenc nincs alkalmazva** | Hiányzó licencfájl | Töltse be a licencet az alkalmazás indításakor: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Gyakran feltett kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET környezettel?**  
A: Igen, az Aspose.Zip működik .NET Framework 4.5+, .NET Core 3.1+, valamint .NET 5/6+ verziókkal. Lásd a [dokumentációt](https://reference.aspose.com/zip/net/) a részletekért.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip‑hez?**  
A: Ideiglenes licencet kérhet a [Aspose ideiglenes licenc oldaláról](https://purchase.aspose.com/temporary-license/).

**Q: Vannak-e további példák más archívumformátumokra?**  
A: Természetesen – tekintse meg a teljes példakészletet a [Aspose.Zip API referenciában](https://reference.aspose.com/zip/net/).

**Q: Hol kaphatok segítséget vagy vitathatok problémákat?**  
A: Csatlakozzon a beszélgetéshez az [Aspose.Zip fórumon](https://forum.aspose.com/c/zip/37) a közösségi támogatás és a hivatalos válaszok érdekében.

**Q: Próbálhatom-e ingyenesen az Aspose.Zip‑et vásárlás előtt?**  
A: Igen, ingyenes próbaverzió elérhető a [Aspose.Zip letöltési oldalon](https://releases.aspose.com/zip/net).

## Összegzés

A fenti lépések követésével most már tudja, **hogyan adjunk fájlokat a tar-hez** és **hogyan tömörítsünk tarxz fájlokat**, valamint, ami még fontosabb, **hogyan hozzunk létre tarxz archívumot .net környezetben** az Aspose.Zip segítségével. Ez a megközelítés egy kompakt, hordozható csomagot biztosít, amely könnyedén integrálható bármely .NET munkafolyamatba – legyen szó asztali segédprogramról, webszolgáltatásról vagy automatizált CI/CD pipeline‑ról.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}