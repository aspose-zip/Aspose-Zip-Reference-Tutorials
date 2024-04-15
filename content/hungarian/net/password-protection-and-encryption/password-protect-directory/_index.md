---
title: Jelszóvédett könyvtárak a .NET-ben az Aspose.Zip oktatóanyaggal
linktitle: Jelszóvédett könyvtár
second_title: Aspose.Zip .NET API fájlok tömörítéséhez és archiválásához
description: Ismerje meg, hogyan védheti jelszóval a .NET-ben található könyvtárakat az Aspose.Zip segítségével. Ezzel a lépésenkénti oktatóanyaggal könnyedén biztonságba helyezheti fájljait.
type: docs
weight: 10
url: /hu/net/password-protection-and-encryption/password-protect-directory/
---

## Bevezetés

A .NET fejlesztés világában a könyvtárak kezelése és biztonsága a fájlkezelés kulcsfontosságú szempontja. Az Aspose.Zip for .NET robusztus megoldást kínál a címtárak jelszavas védelmére, biztosítva az érzékeny adatok bizalmasságát és integritását. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a címtárak jelszavas védelmének folyamatán az Aspose.Zip for .NET használatával.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- A C# programozási nyelv alapvető ismerete.
- A Visual Studio telepítve van a gépedre.
-  Aspose.Zip a .NET könyvtárhoz. Letöltheti[itt](https://releases.aspose.com/zip/net/).
- A jelszóval védeni kívánt fájlokat tartalmazó könyvtár.

## Névterek importálása

kezdéshez importálnia kell a szükséges névtereket a C# projektbe. Ezek a névterek kulcsfontosságúak az Aspose.Zip for .NET által biztosított funkciók kihasználásához.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 1. lépés: Állítsa be az erőforrás-könyvtár elérési útját

Először is adja meg a jelszóval védeni kívánt fájlokat tartalmazó könyvtár elérési útját.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Védje jelszóval a címtárat

 Most pedig ássuk be azt a kódot, amely a címtár jelszavas védelmét végzi. Használjuk a`TraditionalEncryptionSettings` osztályt, hogy beállítson egy jelszót és alkalmazza azt a megadott könyvtárban.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## 3. lépés: A kódex magyarázata

Bontsuk fel a kódot, hogy megértsük az egyes lépéseket:

-  A kimeneti fájl beállítása:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` létrehoz egy új ZIP fájlt a titkosított kimenethez.

-  A címtár meghatározása:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` megadja a jelszóval védett könyvtárat.

-  Bejegyzések létrehozása és mentése:`archive.CreateEntries(corpus)` bejegyzéseket hoz létre a megadott könyvtárban lévő fájlokhoz, és`archive.Save(zipFile)`elmenti a jelszóval védett archívumot.

## Következtetés

Ebben az oktatóanyagban végigjártuk a címtárak jelszavas védelmének folyamatát az Aspose.Zip for .NET használatával. Az alábbi lépések követésével felhasználóbarát és hatékony módon biztosíthatja érzékeny fájljainak biztonságát.

---

## Gyakran Ismételt Kérdések

### Az Aspose.Zip for .NET alkalmas nagy könyvtárak számára?
Igen, az Aspose.Zip for .NET úgy lett kialakítva, hogy hatékonyan kezelje a nagy könyvtárakat, optimális teljesítményt biztosítva.

### Módosíthatom egy már védett könyvtár jelszavát?
 Igen, módosíthatja a jelszót a`TraditionalEncryptionSettings` a kódban ennek megfelelően.

### Vannak-e licenckövetelmények az Aspose.Zip for .NET használatához?
 Igen, az Aspose.Zip for .NET éles környezetben való használatához érvényes licenc szükséges. Engedélyt szerezhet[itt](https://purchase.aspose.com/buy).

### Létezik ingyenes próbaverzió az Aspose.Zip for .NET számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).

### Hol találok további támogatást az Aspose.Zip for .NET számára?
 Meglátogathatja a[Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) bármilyen támogatás vagy kérdés esetén.

