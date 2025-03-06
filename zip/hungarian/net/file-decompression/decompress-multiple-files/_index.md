---
title: Több fájl kicsomagolása az Aspose.Zip for .NET használatával
linktitle: Több fájl kicsomagolása
second_title: Aspose.Zip .NET API fájlok tömörítéséhez és archiválásához
description: Ismerje meg, hogyan bonthat ki több fájlt az Aspose.Zip for .NET használatával. Kövesse lépésenkénti útmutatónkat a hatékony fájlkezelés érdekében.
weight: 11
url: /hu/net/file-decompression/decompress-multiple-files/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több fájl kicsomagolása az Aspose.Zip for .NET használatával

## Bevezetés

Üdvözöljük átfogó oktatóanyagunkban, amely több fájl kicsomagolásáról szól az Aspose.Zip for .NET használatával! Ha hatékonyan szeretné kezelni a több bejegyzést tartalmazó tömörített fájlokat, akkor jó helyen jár. Ebben az útmutatóban lépésről lépésre végigvezetjük a folyamaton az Aspose.Zip for .NET használatával.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.Zip .NET-hez: Győződjön meg arról, hogy telepítve van a .NET-hez készült Aspose.Zip könyvtár. Letöltheti[itt](https://releases.aspose.com/zip/net/).

- Dokumentumkönyvtár: Állítson be egy könyvtárat, ahol a dokumentumokat tárolja. Ezt fogja használni alapkönyvtárként a kódban.

Most pedig kezdjük a lépésről lépésre bemutatott útmutatóval.

## Névterek importálása

A .NET-projektben kezdje az Aspose.Zip szükséges névtereinek importálásával:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Több fájl tömörítése

Több fájl kicsomagolásához először több bejegyzést tartalmazó tömörített fájlra van szükség. Hozzunk létre egyet:

```csharp
string dataDir = "Your Document Directory";

// Futtassa a tömörítési módszert
CompressMultipleFiles.Run();
```

## 2. lépés: A fájlok kicsomagolása

Most pedig bontsuk ki a fájlokat lépésről lépésre:

### 2.1 lépés: Nyissa meg a tömörített fájlt

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### 2.2. lépés: Bejegyzések listázása és a folyamat nyomon követése

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### 2.3. lépés: Az első bejegyzés kibontása

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Adatok olvasása és írása a kicsomagolt adatfolyamból a kicsomagolt fájlba.
    }
}
```

### 2.4. lépés: A második bejegyzés kibontása

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

És megvan! Sikeresen kicsomagolt több fájlt az Aspose.Zip for .NET használatával.

## Következtetés

Ebben az oktatóanyagban az Aspose.Zip for .NET használatával több fájl kicsomagolásának alapvető lépéseit ismertetjük. Az útmutató követésével könnyedén, hatékonyan kezelheti a tömörített fájlokat.

## GYIK

### 1. kérdés: Használhatom az Aspose.Zip for .NET-et kereskedelmi és személyes projektekben is?

 1. válasz: Igen, az Aspose.Zip for .NET használható kereskedelmi és személyes projektekben is. Az engedélyezés részleteit lásd:[Az Aspose licencinformációi](https://purchase.aspose.com/buy).

### 2. kérdés: Elérhető ingyenes próbaverzió az Aspose.Zip for .NET számára?

 2. válasz: Igen, felfedezheti az Aspose.Zip ingyenes próbaverzióját .NET-hez[itt](https://releases.aspose.com/zip/net).

### 3. kérdés: Hol találok további támogatást az Aspose.Zip for .NET számára?

 A3: Látogassa meg a[Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) közösségi támogatásra és beszélgetésekre.

### 4. kérdés: Hogyan vásárolhatok ideiglenes licencet az Aspose.Zip for .NET számára?

 4. válasz: Szerezzen ideiglenes licencet az Aspose.Zip for .NET számára[itt](https://purchase.aspose.com/temporary-license/).

### 5. kérdés: Vannak speciális rendszerkövetelmények az Aspose.Zip for .NET használatához?

 A5: Lásd a[dokumentáció](https://reference.aspose.com/zip/net/) részletes rendszerkövetelményekért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
