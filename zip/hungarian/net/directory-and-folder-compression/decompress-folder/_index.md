---
date: 2026-02-07
description: Tanulja meg, hogyan lehet mappát zip-olni .NET-ben egy könyvtár zip-fájlba
  tömörítésével és visszakicsomagolásával. Ez az útmutató bemutatja, hogyan lehet
  mappát zip-olni az Aspose.Zip for .NET használatával.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Mappa zipelése – Könyvtár tömörítése az Aspose.Zip használatával
url: /hu/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk mappát – Könyvtár tömörítése az Aspose.Zip segítségével .NET-hez

Ha egyértelmű **hogyan tömörítsünk mappát** megoldást keres egy .NET alkalmazásban, jó helyen jár. Ebben az útmutatóban végigvezetjük a teljes folyamatot – először **compress directory to zip**, majd megmutatjuk a pontos lépéseket a **extract zip to directory** (más néven hogyan csomagoljunk ki egy mappát). A végére egy újrahasználható, programozott mintát kap a zip mappa műveletekhez, amely működik a .NET Framework, .NET Core és a .NET 5/6+ környezetekben.

## Gyors válaszok
- **Mit jelent a “compress directory to zip”?** Ez azt jelenti, hogy egy mappa tartalmát egyetlen .zip fájlba alakítjuk.  
- **Hogyan lehet extract zip to directory?** Használja a `Archive.ExtractToDirectory` metódust, ahogy a útmutatóban látható.  
- **Mely .NET verziók támogatottak?** Minden modern .NET Framework, .NET Core és .NET 5/6+ verzió.  
- **Szükséges licenc a termeléshez?** Igen, egy kereskedelmi Aspose.Zip licenc szükséges a nem‑próba használathoz.  
- **Automatizálható CI/CD pipeline-okban?** Teljesen – csak adja hozzá ugyanazt a kódot a build szkriptekhez.

## Mi az a “hogyan tömörítsünk mappát”?
**Hogyan tömörítsünk mappát** egyszerűen azt jelenti, hogy egy könyvtár minden fájlját és alkönyvtárát egyetlen tömörített archívumba csomagoljuk. Ez csökkenti a tárolási méretet, felgyorsítja az átviteleket, és hordozható csomagot hoz létre a telepítéshez.

## Miért használjuk az Aspose.Zip-et .NET-hez?
Az Aspose.Zip egy **pure‑managed** API-t biztosít, amely nem igényel natív DLL-eket, támogatja a hatalmas archívumokat, és automatikusan kezeli az olyan speciális eseteket, mint a **zip archive password protection** és a Unicode fájlnevek. Emellett teljesítményre optimalizált, így ideális, ha programozottan kell mappát zip‑elni nagy áteresztőképességű szcenáriókban.

## Előfeltételek
- **Aspose.Zip for .NET** könyvtár telepítve (töltse le [itt](https://releases.aspose.com/zip/net/)).  
- Egy mappa a lemezen, amelyet archiválni szeretne – állítsa be az elérési útját a `dataDir` változóban.  
- .NET fejlesztői környezet (Visual Studio, VS Code vagy bármely kedvenc IDE).

## Import Namespaces
Először hozza be a szükséges névtereket:

```csharp
using Aspose.Zip;
using System.IO;
```

## Lépés‑ről‑lépésre útmutató

### 1. lépés: Compress Directory to Zip (zip folder programmatically)
Létrehozunk egy zip fájlt a könyvtárból, amelyet később kicsomagolunk. A `CompressDirectory.Run()` segédprogram végzi a nehéz munkát.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tipp:** A `CompressDirectory` minta minden fájlt a `dataDir`‑ból a `CompressDirectory_out.zip`‑ba csomagol. Nyugodtan nevezze át a kimeneti fájlt a saját elnevezési konvenciói szerint.

### 2. lépés: Decompress the Folder – How to Unzip Folder in .NET

#### 2.1. lépés: Open the Zip File
Nyissa meg a generált archívumot egy `FileStream`‑mel. Ez előkészíti a fájlt az olvasáshoz.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### 2.2. lépés: Create Archive Instance
Hozza létre az `Archive` objektumot, amely a zip konténert képviseli.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### 2.3. lépés: Extract to Directory
Végül csomagolja ki a tartalmat egy új mappába. Ez a **extract zip to directory** lépés.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Miért fontos ez
- **Következetesség:** Ugyanannak a könyvtárnak a használata a tömörítéshez és a kicsomagoláshoz garantálja a kompatibilis archívumformátumot.  
- **Teljesítmény:** Az Aspose.Zip hatékonyan streameli az adatokat, így még több gigabájtos archívumok is alacsony memóriaigénnyel kezelhetők.  
- **Biztonság:** A beépített jelszóvédelem lehetővé teszi a zip archívumok védelmét extra kód nélkül.

## Gyakori felhasználási esetek
- **Automatizált mentések** – naponta zip‑elje a napló mappát, és tárolja felhőben.  
- **Telepítési csomagok** – csomagolja össze a statikus webes erőforrásokat a szerverre való közzététel előtt.  
- **Adatcsere** – küldjön egy fájlgarnitúrát szolgáltatások között egyetlen archívumként.

## Gyakori problémák és megoldások
| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| `UnauthorizedAccessException` a kicsomagolás során | A célmappa csak‑olvasású vagy használatban van | Győződjön meg róla, hogy a célútvonal írható és nincs zárolva |
| Üres kimeneti mappa a kicsomagolás után | Hibás forrás‑zip útvonal | Ellenőrizze, hogy a `dataDir + "CompressDirectory_out.zip"` a helyes fájlra mutat |
| Nagy fájlok OutOfMemoryException‑t okoznak | Alapértelmezett pufferméret használata nagyon nagy archívumoknál | Használja az `ArchiveOptions`‑t a pufferméret növeléséhez vagy streamelje a fájlokat darabokban |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Zip-et .NET‑hez bármilyen fájltípussal?**  
A: Igen, az Aspose.Zip támogat minden fájltípust – szöveg, bináris, képek, PDF‑ek, bármit.

**Q: Alkalmas-e az Aspose.Zip nagy‑léptékű alkalmazásokhoz?**  
A: Teljes mértékben. Kifejezetten nagy‑teljesítményű zip tömörítésre .NET‑es környezetben tervezték, több gigabájtos archívumok kezelésével alacsony memóriaigény mellett.

**Q: Hol találok átfogó dokumentációt az Aspose.Zip for .NET‑hez?**  
A: Tekintse meg a részletes dokumentációt [itt](https://reference.aspose.com/zip/net/).

**Q: Próbálhatom-e ki az Aspose.Zip-et vásárlás előtt?**  
A: Igen, ingyenes próba elérhető a [Aspose.Zip letöltési oldalon](https://releases.aspose.com/).

**Q: Hogyan kaphatok támogatást az Aspose.Zip for .NET‑hez?**  
A: Látogassa meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37) a közösségi segítségért és a hivatalos támogatásért.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}