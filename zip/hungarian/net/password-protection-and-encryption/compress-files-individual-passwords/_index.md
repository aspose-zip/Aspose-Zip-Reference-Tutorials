---
title: Biztonságos fájltömörítés .NET-ben az Aspose.Zip segítségével
linktitle: Fájlok tömörítése egyéni jelszavakkal
second_title: Aspose.Zip .NET API fájlok tömörítéséhez és archiválásához
description: Ismerje meg, hogyan javíthatja a fájlbiztonságot .NET-alkalmazásokban! Kövesse lépésenkénti útmutatónkat a fájlok egyéni jelszavakkal történő tömörítéséhez az Aspose.Zip for .NET használatával.
weight: 16
url: /hu/net/password-protection-and-encryption/compress-files-individual-passwords/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Biztonságos fájltömörítés .NET-ben az Aspose.Zip segítségével


## Bevezetés

.NET fejlesztés világában a fájlok hatékony kezelése és tömörítése kulcsfontosságú feladat. Az Aspose.Zip for .NET hatékony megoldást kínál a fájltömörítésre, különféle funkciókat kínálva az alkalmazások fejlesztéséhez. Az egyik figyelemre méltó funkció a fájlok egyedi jelszavakkal történő tömörítése, ami további biztonsági réteget biztosít. Ebben az oktatóanyagban végigvezetjük a fájlok egyéni jelszavakkal történő tömörítésén az Aspose.Zip for .NET használatával.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Zip .NET-hez: Győződjön meg arról, hogy az Aspose.Zip könyvtár telepítve van a .NET-projektben. Megtalálhatja a szükséges dokumentációt[itt](https://reference.aspose.com/zip/net/).

-  Letöltés: Ha még nem tette meg, töltse le az Aspose.Zip for .NET könyvtárat innen[ez a link](https://releases.aspose.com/zip/net/).

- Dokumentumkönyvtár: Készítsen egy könyvtárat, amely a tömöríteni kívánt fájlokat tartalmazza.

## Névterek importálása

A .NET-projektben feltétlenül importálja a szükséges névtereket:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 1. lépés: Állítsa be az erőforrás-könyvtár elérési útját

Határozza meg annak az erőforrás-könyvtárnak az elérési útját, ahol a fájlok találhatók.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Fájlok tömörítése egyéni jelszavakkal

Most tömörítsük a fájlokat egyedi jelszavakkal. Három mintafájlt fogunk használni (`alice29.txt`, `asyoulik.txt` , és`fields.c`) mindegyikhez külön jelszóval.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Tömörítse az egyes fájlokat egyedi jelszóval
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Mentse el a tömörített fájlokat
        archive.Save(zipFile);
    }
}
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan lehet tömöríteni a fájlokat egyedi jelszavakkal az Aspose.Zip for .NET segítségével. Ez a funkció egy extra biztonsági réteget ad a tömörített fájlokhoz, biztosítva a bizalmasságot.

## Gyakran Ismételt Kérdések (GYIK)

### Használhatok különböző titkosítási módszereket minden fájlhoz?
Igen, az Aspose.Zip for .NET lehetővé teszi az egyes fájlokhoz különböző titkosítási módszerek használatát a tömörítés során.

### Létezik próbaverzió?
 Igen, elérheti az Aspose.Zip .NET ingyenes próbaverzióját[itt](https://releases.aspose.com/).

### Hogyan kaphatok támogatást, ha problémákba ütközöm?
 Meglátogatni a[Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) a közösség segítségéért és az Aspose támogatásáért.

### Hol találom az Aspose.Zip for .NET részletes dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/zip/net/).

### Vásárolhatok ideiglenes licencet tesztelési célból?
 Igen, szerezhet ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
