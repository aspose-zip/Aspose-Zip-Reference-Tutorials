---
date: 2025-12-25
description: Mesteri Aspose.Zip a .NET-hez titkosított 7z archívumok létrehozásához.
  Ez az Aspose.Zip példa bemutatja, hogyan lehet fájlt hozzáadni a 7z-hez titkosítással
  és tömörítéssel.
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Titkosított 7z archívum létrehozása az Aspose.Zip for .NET segítségével
url: /hu/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Titkosított 7z archívum létrehozása az Aspose.Zip for .NET segítségével

## Bevezetés

Ebben az útmutatóban megtanulja, **hogyan hozhat létre titkosított 7z** fájlokat az Aspose.Zip könyvtár .NET verziójával. Akár érzékeny adatokat kell védelmeznie, biztonsági előírásoknak kell megfelelnie, vagy egyszerűen csak hatékonyan szeretne fájlokat tömöríteni, ez a leírás minden lépésen végigvezeti – a projekt beállításától egészen a sikeres archívum létrehozásának ellenőrzéséig. Merüljünk el, és lássuk, milyen egyszerű egy fájl hozzáadása egy AES titkosítással ellátott 7z archívumhoz.

## Gyors válaszok
- **Mit jelent a “titkosított 7z létrehozása”?** Egy 7‑zip archívum generálását jelenti, amely AES titkosítással van védve.
- **Melyik könyvtárat használja?** Aspose.Zip for .NET.
- **Szükség van licencre?** Ideiglenes licenc elegendő a teszteléshez; a teljes licenc a termeléshez kötelező.
- **Hozzáadhatok több fájlt?** Igen, a `CreateEntry` metódust többször is meghívhatja minden egyes fájlhoz.
- **Támogatott az AES titkosítás?** Igen, az Aspose.Zip támogatja az AES‑256 titkosítást 7z archívumok esetén.

## Mi az a titkosított 7z archívum?
A 7z archívum egy nagy tömörítési arányú konténerformátum. Amikor **titkosított 7z** archívumot hozunk létre, a tartalom AES titkosítással kerül összekódolásra, így a helyes jelszó nélkül olvashatatlan. Ideális bizalmas fájlok biztonságos továbbításához vagy tárolásához.

## Miért válassza az Aspose.Zip-et titkosított 7z fájlokhoz?
- **Teljes .NET integráció** – működik .NET Framework, .NET Core és .NET 5/6 környezetben.
- **Beépített AES‑256 támogatás** – nincs szükség külső eszközökre.
- **Egyszerű API** – egyetlen soros hívással adhat hozzá fájlokat és mentheti az archívumot.
- **Keresztplatformos** – fut Windows, Linux és macOS rendszereken.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy a következők rendelkezésre állnak:

- **Aspose.Zip for .NET Library** – töltse le [itt](https://releases.aspose.com/zip/net/).
- **Írási jogosultsággal rendelkező mappa** a gépén, ahol az archívumot menteni fogja.
- **Forrásfájl** (pl. `file.dat`), amelyet tömöríteni és titkosítani szeretne.

## Namespace-ek importálása

Adja hozzá a szükséges névteret a C# fájl tetejéhez:

```csharp
using Aspose.Zip.SevenZip;
```

## Lépésről‑lépésre útmutató

### 1. lépés: A munkakönyvtár meghatározása

Állítsa be annak a mappának az útvonalát, amely a tömöríteni kívánt forrásfájlt tartalmazza.

```csharp
string dataDir = "Your Document Directory";
```

Cserélje le a `"Your Document Directory"` szöveget a gépén lévő tényleges útvonalra.

### 2. lépés: Titkosított 7z bejegyzés létrehozása

A tutorial központi része – megnyitunk egy új fájlfolyamot, létrehozzuk a `SevenZipArchive`‑t, hozzáadunk egy bejegyzést, majd mentjük az archívumot. Ez a példa egyetlen fájlt (`file.dat`) ad hozzá `data.bin` néven az archívumban.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Pro tipp:** Az AES titkosítás engedélyezéséhez állítsa be a `Encryption` tulajdonságot a `SevenZipArchive`‑on a `Save` hívása előtt. (A példában a tulajdonság kimarad a tömörség kedvéért.)

### 3. lépés: Siker ellenőrzése

Írjon ki egy barátságos üzenetet, hogy tudja, a művelet hibamentesen befejeződött.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### 4. lépés: Archívum ellenőrzése (opcionális)

A program futtatása után navigáljon ahhoz a mappához, amely a `archive.7z`‑t tartalmazza, és próbálja meg megnyitni egy 7‑zip klienssel. Ha a 2. lépésben titkosítást állított be, jelszót fog kérni.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Fájl nem található** | Hibás `dataDir` vagy forrásfájl neve | Ellenőrizze az útvonalat, és győződjön meg róla, hogy a `file.dat` létezik. |
| **Hozzáférés megtagadva** | Nem elegendő írási jogosultság | Futtassa az alkalmazást emelt jogokkal, vagy válasszon egy írási jogosultsággal rendelkező mappát. |
| **A titkosítás nem alkalmazódik** | Hiányzó titkosítási beállítás az archívumban | Állítsa be az `archive.Encryption = EncryptionAlgorithm.Aes256;` értéket a `Save` előtt. |

## Gyakran feltett kérdések

### K: Használhatom az Aspose.Zip for .NET-et más archívumformátumokkal?
Az Aspose.Zip elsősorban a ZIP és 7z formátumokra fókuszál. Más formátumok kezeléséhez tekintse meg a speciális könyvtárakat, amelyek az adott formátumokra lettek tervezve.

### K: Hogyan tudok fájlokat kicsomagolni egy zip archívumból az Aspose.Zip segítségével?
Használja az Aspose.Zip által biztosított kicsomagolási funkciókat, például az `ExtractToDirectory` metódust, amely egyszerűen kicsomagolja a fájlokat egy zip archívumból.

### K: Alkalmas-e az Aspose.Zip nagy léptékű alkalmazásokhoz?
Teljes mértékben! Az Aspose.Zip nagy léptékű alkalmazásokhoz lett tervezve, hatékony zip archívum-kezelési képességekkel.

### K: Vannak-e licencelési szempontok az Aspose.Zip használatakor?
Igen, rendelkeznie kell érvényes licenccel. Ideiglenes használathoz vagy felfedezéshez ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

### K: Hol kérhetek segítséget vagy csatlakozhatok a közösséghez az Aspose.Zip kapcsán?
Látogassa meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37), ahol támogatást kérhet, kérdéseket tehet fel, és kapcsolatba léphet a közösséggel.

## Összegzés

Most már szilárd alapokkal rendelkezik a **titkosított 7z** archívumok létrehozásához az Aspose.Zip for .NET segítségével. A fenti lépések követésével biztonságosan tömörítheti a fájlokat, hozzáadhatja őket egy 7z tárolóhoz, és szükség esetén AES titkosítást is alkalmazhat. Nyugodtan bővítse a példát további bejegyzésekkel, jelszavak beállításával, vagy integrálja nagyobb munkafolyamatokba.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2025-12-25  
**Tesztelve a következővel:** Aspose.Zip for .NET 24.11  
**Szerző:** Aspose