---
date: 2025-12-01
description: Tanulja meg, hogyan tömöríthet egy könyvtárat zip fájlba, és hogyan csomagolhat
  ki egy zip-et könyvtárba az Aspose.Zip for .NET segítségével – egy teljes útmutató
  a zip tömörítéshez .net és zip archívum létrehozásához .net.
language: hu
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Könyvtár tömörítése ZIP-be és kitömörítése – Aspose.Zip .NET-hez
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Könyvtár tömörítése zip-re és kitömörítés – Aspose.Zip for .NET

Ha **könyvtár tömörítése zip-re**-t kell végrehajtania, majd ki szeretné csomagolni azt az archívumot egy .NET alkalmazásban, jó helyen jár. Ebben az útmutatóban végigvezetjük az egész folyamatot – a zip archívum létrehozásától kezdve, egészen egy tiszta, lépésről‑lépésre bemutatott kitömörítésig az Aspose.Zip for .NET használatával. A végére egy újrahasználható mintát kap a zip tömörítéshez .NET projektekben, és alapos megértést a .NET stílusú kitömörítésről.

## Gyors válaszok
- **Mi jelent a “compress directory to zip”?** Ez azt jelenti, hogy egy mappa tartalmát egyetlen .zip fájlba csomagolja.  
- **Hogyan csomagolhatom ki a zip-et egy könyvtárba?** Használja a `Archive.ExtractToDirectory` metódust, ahogy a útmutatóban látható.  
- **Mely .NET verziók támogatottak?** Minden modern .NET Framework, .NET Core és .NET 5/6+ verzió.  
- **Szükséges licenc a termeléshez?** Igen, kereskedelmi Aspose.Zip licenc szükséges a nem próba használathoz.  
- **Automatizálhatom ezt CI/CD pipeline-okban?** Természetesen – csak adja hozzá ugyanazt a kódot a build szkriptekhez.

## Mi a “compress directory to zip”?
A könyvtár zip-re tömörítése minden fájlt és almappát egyetlen tömörített archívumba csomagol. Ez csökkenti a tárolási méretet, egyszerűsíti az átvitelét, és szabványos módja a források csomagolásának a telepítéshez.

## Miért használja az Aspose.Zip for .NET-et?
Az Aspose.Zip **pure‑managed** API-t kínál, amely natív függőségek nélkül működik, nagy fájlokat támogat, és nagy teljesítményű zip tömörítési .NET képességeket biztosít. Emellett kezeli az olyan speciális eseteket, mint a jelszóval védett archívumok és a Unicode fájlnevek, mindezt alapból.

## Előfeltételek
- **Aspose.Zip for .NET** könyvtár telepítve (töltse le [ide](https://releases.aspose.com/zip/net/)).  
- Egy mappa a lemezen, amelyet archiválni szeretne – állítsa be az elérési útját a `dataDir` változóban.  
- .NET fejlesztői környezet (Visual Studio, VS Code vagy bármely kedvelt IDE).

## Névterek importálása
Először hozza be a szükséges névtereket a hatókörbe:

```csharp
using Aspose.Zip;
using System.IO;
```

## 1. lépés: Könyvtár tömörítése zip-re
Létrehozunk egy zip fájlt a könyvtárból, amelyet később ki szeretne csomagolni. A `CompressDirectory.Run()` segédprogram végzi a nehéz munkát.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** A `CompressDirectory` minta minden fájlt a `dataDir`-ben a `CompressDirectory_out.zip` fájlba csomagol. Nyugodtan nevezze át a kimeneti fájlt, hogy megfeleljen a névadási konvencióinak.

## 2. lépés: Mappa kitömörítése (Hogyan csomagoljuk ki .NET-ben)

### 2.1. lépés: Zip fájl megnyitása
Nyissa meg a generált archívumot egy `FileStream`-mel. Ez előkészíti a fájlt az olvasáshoz.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### 2.2. lépés: Archive példány létrehozása
Példányosítsa az `Archive` objektumot, amely a zip tárolót képviseli.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### 2.3. lépés: Kitömörítés könyvtárba
Végül csomagolja ki a tartalmat egy új mappába. Ez a **extract zip to directory** lépés.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Gratulálunk! Sikeresen **compressed a directory to zip** és aztán **extracted the zip to a directory** műveleteket hajtotta végre az Aspose.Zip for .NET használatával. Ez a megközelítés garantálja az adat integritását, miközben a kódot tömör és olvasható marad.

## Gyakori problémák és megoldások
| Tünet | Valószínű ok | Megoldás |
|-------|--------------|----------|
| `UnauthorizedAccessException` when extracting | A célmappa csak olvasható vagy használatban van | Győződjön meg róla, hogy a cél útvonal írható és nincs zárolva |
| Üres kimeneti mappa a kitömörítés után | Helytelen forrás zip útvonal | Ellenőrizze, hogy a `dataDir + "CompressDirectory_out.zip"` a helyes fájlra mutat |
| Nagy fájlok OutOfMemoryException-t okoznak | Alapértelmezett pufferméret használata nagyon nagy archívumoknál | Használja az `ArchiveOptions`-t a pufferméret növeléséhez vagy a fájlok darabokban történő streameléséhez |

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Zip for .NET-et bármilyen fájltípussal?**  
A: Igen, az Aspose.Zip minden fájltípust támogat – szöveg, bináris, képek, PDF-ek, amit csak el tud nevezni.

**K: Alkalmas az Aspose.Zip nagy léptékű alkalmazásokhoz?**  
A: Teljesen. Kifejezetten nagy teljesítményű zip tömörítés .NET helyzetekhez tervezték, több gigabájtos archívumok kezelésével alacsony memóriaigénnyel.

**K: Hol találhatom meg az Aspose.Zip for .NET átfogó dokumentációját?**  
A: Tekintse meg a részletes dokumentációt [itt](https://reference.aspose.com/zip/net/).

**K: Próbálhatom ki az Aspose.Zip-et vásárlás előtt?**  
A: Igen, ingyenes próba elérhető a [Aspose.Zip letöltési oldalon](https://releases.aspose.com/).

**K: Hogyan kaphatok támogatást az Aspose.Zip for .NET-hez?**  
A: Látogassa meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37) a közösségi segítségért és hivatalos támogatásért.

---

**Utolsó frissítés:** 2025-12-01  
**Tesztelve:** Aspose.Zip 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}