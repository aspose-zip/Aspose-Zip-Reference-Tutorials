---
title: Aspose.Zip for .NET – Biztonságos fájltárolás oktatóanyaga
linktitle: Tároljon több fájlt tömörítés nélkül jelszóval
second_title: Aspose.Zip .NET API fájlok tömörítéséhez és archiválásához
description: Fedezze fel, hogyan használhatja az Aspose.Zip for .NET-et több fájl biztonságos, tömörítés nélküli tárolására. Egyszerű lépések a jelszavas védelemhez. Oldja fel a fájlkezelés erejét!
type: docs
weight: 13
url: /hu/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

A .NET fejlesztés világában a fájlok kezelése és manipulálása gyakori feladat. Az Aspose.Zip for .NET egy hatékony könyvtár, amely a fejlesztők számára lehetővé teszi a zip-archívumok zökkenőmentes tömörítését, kicsomagolását és kezelését. Ebben az oktatóanyagban egy konkrét forgatókönyvet vizsgálunk meg: több fájl tárolása tömörítés nélkül, és jelszóval védve. Ennek az útmutatónak a végére birtokában lesz a funkciónak az Aspose.Zip for .NET használatával való megvalósításához.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.Zip for .NET Library: Győződjön meg arról, hogy az Aspose.Zip for .NET könyvtár telepítve van. Letöltheti[itt](https://releases.aspose.com/zip/net/).

-  Dokumentumkönyvtár: Készítsen egy könyvtárat, ahol a forrásfájlok találhatók. A megadott példában a változó`dataDir` a dokumentumkönyvtárat képviseli.

## Névterek importálása

Kezdésként importáljuk a kódunkhoz szükséges névtereket:

```csharp
// Az erőforrás-könyvtár elérési útja.
string dataDir = "Your Document Directory"

// Importálja az Aspose.Zip névtereket
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 1. lépés: Nyissa meg a Zip fájlt

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Ez a lépés magában foglalja egy új zip fájl létrehozását a használatával`FileStream`. A fájl neve „StoreMutlipleFilesWithoutCompressionWithPassword_out.zip” lesz.

## 2. lépés: Nyissa meg a forrásfájlt

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Itt megnyitjuk az első forrásfájlt, az „alice29.txt”-et, amely a zip-archívumban lesz tárolva.

## 3. lépés: Hozzon létre egy archívumot

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 Ebben a lépésben létrehozzuk a`Archive` osztályban, megadva a tömörítési és titkosítási beállításokat. Használjuk a`StoreCompressionSettings` fájlok tárolására tömörítés nélkül és`AesEcryptionSettings` jelszóval ("p@s$") alkalmazza az AES titkosítást.

## 4. lépés: Archív bejegyzés létrehozása és mentése

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Ez az utolsó lépés magában foglalja az „alice29.txt” bejegyzés létrehozását az archívumban, az archívum mentését, valamint a fájl tömörítés nélküli és jelszavas védelemmel történő tárolásának folyamatát.

Fejezze be az oktatóanyagot a legfontosabb pontok összefoglalásával, és bátorítsa az olvasókat, hogy fedezzék fel a további lehetőségeket az Aspose.Zip for .NET segítségével.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan használható az Aspose.Zip for .NET több fájl tömörítés nélküli tárolására és jelszóval történő biztosítására. Ahogy folytatja útját a .NET fejlesztéssel, használja ki az Aspose.Zip képességeit a fájlkezelési feladatok egyszerűsítésére és alkalmazásai biztonságának fokozására.

---

### GYIK

### Használhatom az Aspose.Zip for .NET fájlt más titkosítási módszerekkel?
 Igen, az Aspose.Zip különféle titkosítási módszereket támogat. Ellenőrizze a dokumentációt[itt](https://reference.aspose.com/zip/net/) a részletekért.

### Hol kaphatok támogatást az Aspose.Zip for .NET-hez?
 Meglátogatni a[Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) közösségi támogatásra és beszélgetésekre.

### Létezik ingyenes próbaverzió az Aspose.Zip for .NET számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Zip for .NET számára?
 Kérjen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).

### Hol vásárolhatom meg az Aspose.Zip-et .NET-hez?
 Megvásárolhatja az Aspose.Zip-et .NET-hez[itt](https://purchase.aspose.com/buy).
