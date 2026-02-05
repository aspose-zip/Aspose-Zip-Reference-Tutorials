---
date: 2026-02-05
description: Tanulja meg, hogyan adhat hozzá fájlokat a tar-hoz, és hozhat létre tarxz
  archívumokat .NET-ben az Aspose.Zip használatával. Ez az útmutató bemutatja, hogyan
  tömörítheti a fájlokat tarxz formátumba nagy hatékonysággal.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Fájlok hozzáadása a tar-hoz, tarxz archívum létrehozása .NET-ben az Aspose.Zip
  segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk fájlokat a tar-hoz, és hozzunk létre tarxz archívumot .NET-ben az Aspose.Zip segítségével

## Bevezetés

Ha **fájlokat kell hozzáadni a tar-hoz**, majd azokat tarxz archívumba szeretné tömöríteni .NET környezetben, az Aspose.Zip for .NET egyszerű és megbízható megoldást kínál. Akár naplókat, konfigurációs fájlokat vagy bármilyen egyéb erőforrást szeretne tárolni vagy továbbítani, a TarXz formátum magas tömörítési arányt biztosít, miközben megőrzi a jól ismert tar struktúrát. Ebben az útmutatóban lépésről lépésre bemutatjuk a pontos eljárást – kódrészletekkel illusztrálva –, hogy magabiztosan integrálhassa a tarxz létrehozását .NET alkalmazásaiba.

## Gyors válaszok
- **Mi a fő osztály?** `TarArchive` a `Aspose.Zip.Tar` névtérből
- **Hogyan tömörítsünk tarxz-et?** Használja a `SaveXzCompressed` metódust a bejegyzések hozzáadása után
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Szükséges licenc?** Igen, érvényes Aspose.Zip licenc a termeléshez
- **Tipikus megvalósítási idő?** ~5‑10 perc

## Mi az a TarXz archívum?

A **TarXz archívum** a hagyományos Unix `tar` konténert kombinálja az XZ tömörítéssel. A tar rész több fájlt csomagol egyetlen adatfolyamba, míg az XZ erős, veszteségmentes tömörítést biztosít. Ez a formátum népszerű forráskód, biztonsági mentés és nagy adathalmazok terjesztésére, mivel megőrzi a könyvtárstruktúrákat és kisebb fájlméretet eredményez, mint a sima tar vagy zip.

## Miért adjunk fájlokat a tar-hoz és tömörítsünk tarxz-et az Aspose.Zip segítségével?

- **Magas tömörítési arány** – Az XZ gyakran 30‑50 % kisebb, mint a gzip.  
- **Keresztplatformos kompatibilitás** – TarXz fájlok nyithatók Linuxon, macOS-en és Windowson.  
- **Egyszerű API** – Az Aspose.Zip elrejti az alacsony szintű részleteket, így a üzleti logikára koncentrálhat.  
- **Nincs külső eszköz** – Minden a .NET folyamaton belül fut, ami tökéletes felhő- vagy CI‑pipeline‑okhoz.  

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve (letölthető a hivatalos [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) oldalról).  
- Egy mappával, amely a becsomagolandó fájlokat tartalmazza. Az alábbi példákban ez a mappa a `dataDir` változóval van hivatkozva.  
- Érvényes Aspose.Zip licenccel (értékeléshez opcionális, termeléshez kötelező).

## Névterek importálása

Először importálja azokat a névtereket, amelyek a TarXz funkcionalitást biztosítják.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan adjunk fájlokat a tar-hoz az Aspose.Zip használatával

### 1. lépés: `TarArchive` inicializálása

Hozzon létre egy új `TarArchive` példányt, amely a tömöríteni kívánt fájlokat fogja tartalmazni.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tipp:** A `using` utasítás biztosítja, hogy az archívum megfelelően legyen felszabadítva, és minden nem kezelt erőforrás elengedésre kerüljön.

### 2. lépés: Fájlok hozzáadása az archívumhoz

Adja hozzá az egyes fájlokat, amelyeket be szeretne vonni. Ebben a példában két szövegfájlt adunk hozzá, de tetszőleges számú bejegyzést felvehet.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Miért fontos:** A bejegyzések hozzáadása a tömörítés előtt lehetővé teszi, hogy az Aspose.Zip először felépítse a tar konténert, majd egy lépésben alkalmazza az XZ tömörítést.

### 3. lépés: Archívum mentése XZ tömörítéssel

Végül írja a tar archívumot lemezre XZ tömörítéssel. A kapott fájl `.tar.xz` kiterjesztésű lesz.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Eredmény:** Most már rendelkezik egy teljesen tömörített `archive.tar.xz` fájllal, amely bármely, TarXz‑et támogató platformon átvihető, tárolható vagy kicsomagolható.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **„File not found” kivétel** | Helytelen `dataDir` útvonal | Ellenőrizze, hogy a könyvtár útvonal backslash‑sel (`\`) végződik, vagy használja a `Path.Combine` metódust. |
| **Nagy memóriahasználat** | Nagyon nagy fájlok memóriában történő tömörítése | Használja a `TarArchive` streaming módot (`SaveXzCompressed` túlterhelés, amely `Stream`‑et fogad). |
| **Licenc nincs alkalmazva** | Hiányzó licencfájl | Töltse be a licencet az alkalmazás indításakor: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Gyakran Ismételt Kérdések

**Q: Az Aspose.Zip kompatibilis minden .NET környezettel?**  
A: Igen, az Aspose.Zip működik .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6+. Lásd a [documentation](https://reference.aspose.com/zip/net/) részleteket.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip-hez?**  
A: Ideiglenes licencet kérhet a [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) oldalon.

**Q: Vannak további példák más archívumformátumokra?**  
A: Természetesen—tekintse meg a teljes példakészletet a [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) oldalon.

**Q: Hol kaphatok segítséget vagy vitathatok problémákat?**  
A: Csatlakozzon a beszélgetéshez a [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) közösségi támogatásért és hivatalos válaszokért.

**Q: Próbálhatom ingyenesen az Aspose.Zip-et vásárlás előtt?**  
A: Igen, ingyenes próba elérhető a [Aspose.Zip download page](https://releases.aspose.com/zip/net) oldalon.

## Összegzés

A fenti lépések követésével most már tudja, **hogyan adjunk fájlokat a tar-hoz** és **hogyan hozzunk létre tarxz archívumokat** az Aspose.Zip segítségével .NET környezetben. Ez a megközelítés kompakt, hordozható csomagot biztosít, amely könnyedén integrálható bármely .NET munkafolyamatba – legyen szó asztali segédprogramról, webszolgáltatásról vagy automatizált CI/CD pipeline‑ról.

---

**Utoljára frissítve:** 2026-02-05  
**Tesztelve a következővel:** Aspose.Zip for .NET 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}