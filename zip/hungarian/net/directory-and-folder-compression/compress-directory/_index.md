---
date: 2026-05-30
description: Ismerje meg, hogyan tömöríthet mappákat az Aspose.Zip for .NET segítségével,
  hatékonyan hozhat létre zip archívumot .NET-ben, és csökkentheti a tárhelyigényt
  .NET alkalmazásaiban.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Mappa tömörítése
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Mappa tömörítése az Aspose.Zip for .NET használatával
url: /hu/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mappa ZIP-re csomagolása az Aspose.Zip for .NET használatával

Ebben az oktatóanyagban megtudja, **hogyan kell ZIP-re csomagolni egy mappát** gyorsan és megbízhatóan az Aspose.Zip for .NET segítségével. Akár asztali segédprogramot, felhőalapú szolgáltatást vagy automatizált mentési szkriptet épít, egy mappa ZIP archívumba tömörítése drámaian csökkentheti a tárolási igényeket és felgyorsíthatja a hálózati átviteleket. Lépésről lépésre végigvezetjük, elmagyarázzuk, miért fontos minden sor, és kiemeljük a gyakori buktatókat, hogy magabiztosan alkalmazhassa a technikát.

## Gyors válaszok
- **Mi a Aspose.Zip feladata?** Egyszerű .NET API-t biztosít ZIP archívumok létrehozásához és kibontásához külső függőségek nélkül.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 percnél kevesebb egy alap mappa tömörítéshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, és .NET 5‑10.  
- **Szükség van licencre a termeléshez?** Igen, a kereskedelmi licenc szükséges a termelési használathoz.  
- **Tömöríthetek több mappát egyszerre?** Természetesen—használja a `CreateEntries` metódust bármely `DirectoryInfo` gyűjteményen, hogy **több mappát ZIP-re csomagoljon** egyetlen futtatásban.  

`CreateEntries` hozzáadja a könyvtár összes fájlját az archívumhoz.

## Mi az a „hogyan kell ZIP-re csomagolni egy mappát”?

A mappa tömörítése azt jelenti, hogy a megadott könyvtár minden fájlját és alkönyvtárát egyetlen ZIP archívumba csomagolja. Ez csökkenti a teljes méretet, megőrzi az eredeti hierarchiát, és megkönnyíti az adat átvitelét vagy tárolását. A létrehozott ZIP bármely platformon megnyitható speciális szoftver nélkül, és megőrzi a mappaszerkezetet, így kibontáskor az eredeti elrendezés pontosan úgy áll helyre, ahogy volt.

## Miért használjuk az Aspose.Zip-et ehhez a feladathoz?

Az Aspose.Zip lehetővé teszi **zip archívum létrehozását** közvetlenül .NET kódból, konzisztens API-val minden támogatott futtatókörnyezetben. Töltse be az `Archive` osztályt, adjon hozzá bejegyzéseket, állítsa be a `CompressionLevel`‑et, opcionálisan adjon meg jelszót, majd hívja a `Save`‑t. A könyvtár ezrek fájlját egy másodpercnél gyorsabban dolgozza fel tipikus hardveren, és több mint 50 különböző tömörítési formátumot és titkosítási algoritmust támogat.

## Előfeltételek

- **Aspose.Zip for .NET** – töltse le [itt](https://releases.aspose.com/zip/net/) vagy [itt](https://releases.aspose.com/zip/net).  
- **Fejlesztői környezet** – Visual Studio, Rider, vagy bármely C#-t támogató IDE.  
- **Dokumentum könyvtár** – cserélje le a kódban a `"Your Document Directory"` értéket a tömöríteni kívánt mappa elérési útjára.  
- **Referenciadokumentáció** – tekintse meg a hivatalos dokumentációt [itt](https://reference.aspose.com/zip/net/).

## Névterek importálása

Kezdje a szükséges névterek importálásával. Ezek biztosítják a hozzáférést a fő tömörítési osztályokhoz.

```csharp
using Aspose.Zip;
using System.IO;
```

## Mappa ZIP-re csomagolása az Aspose.Zip használatával

Az alábbi egyszerű példa bemutatja, **hogyan kell ZIP-re csomagolni egy mappa** tartalmát. Ugyanez a minta kiterjeszthető **több fájl .net ZIP-re csomagolására** vagy egyedi archívumstruktúrák létrehozására.

### 1. lépés: A dokumentum könyvtár inicializálása

Állítsa be a `dataDir` változót a tömöríteni kívánt könyvtár elérési útjára.

```csharp
string dataDir = "Your Document Directory";
```

### 2. lépés: Kimeneti ZIP fájlok létrehozása

Nyisson meg két `FileStream` objektumot a kimeneti ZIP fájlokhoz. Ez bemutatja, hogyan hozhat létre egynél több archívumot ugyanabból a forrásból – hasznos verziózott mentésekhez.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 3. lépés: Könyvtár tömörítése

Az `Archive` osztály egy ZIP archívumot képvisel, és módszereket biztosít a bejegyzések hozzáadásához és a fájl mentéséhez. Használja a célkönyvtár minden bejegyzésének hozzáadásához. A példa egy **CanterburyCorpus** nevű minta könyvtárat használ, de bármely könyvtárra mutathat.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Pro tip:** Ha egy adott tömörítési szinttel szeretne **zip archívum .net** létrehozni, állítsa be az `archive.CompressionLevel`‑et a `Save` hívása előtt.

## Gyakori problémák és megoldások

| Tünet | Valószínű ok | Megoldás |
|-------|--------------|----------|
| Üres ZIP fájl | `dataDir` rossz könyvtárra mutat vagy hiányzik a záró perjel | Ellenőrizze az útvonalat, és győződjön meg róla, hogy a mappa tartalmaz fájlokat |
| `UnauthorizedAccessException` | Az alkalmazásnak nincs fájlrendszer‑hozzáférése | Futtassa a Visual Studio‑t rendszergazdaként, vagy adjon olvasási/írási jogokat |
| Nagy memóriahasználat hatalmas könyvtárak esetén | Az összes bejegyzés egyszerre történő betöltése a memóriába | Használja a `Archive.CreateEntryFromFile`‑t egy ciklusban, hogy a fájlokat egyenként streamelje |

## Gyakran Ismételt Kérdések (Továbbiak)

**Q: Hozzáadhatok jelszót a ZIP archívumhoz?**  
A: Igen. Állítsa be az `archive.Password = "yourPassword";` értéket a `Save` hívása előtt.

**Q: Hogyan tudok csak bizonyos fájltípusokat belefoglalni?**  
A: Szűrje a `DirectoryInfo` gyűjteményt a `GetFiles("*.txt")` vagy hasonló metódussal a `CreateEntries` hívása előtt.

**Q: Van mód egy meglévő ZIP frissítésére anélkül, hogy újra létrehoznám?**  
A: Az Aspose.Zip támogatja az inkrementális frissítéseket a `Archive.UpdateEntry` segítségével.

## GYIK

### Q1: Használhatom az Aspose.Zip for .NET-et kereskedelmi és személyes projektekben egyaránt?

A1: Igen, az Aspose.Zip for .NET licencelt mind kereskedelmi, mind személyes felhasználásra.

### Q2: Elérhető ingyenes próba?

A2: Igen, ingyenes próbaverziót tekinthet meg [itt](https://releases.aspose.com/zip/net).

### Q3: Hogyan kaphatok támogatást az Aspose.Zip for .NET-hez?

A3: Látogassa meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37) a közösségi támogatásért, vagy fontolja meg egy [ideiglenes licenc](https://purchase.aspose.com/temporary-license/) megvásárlását a dedikált segítségért.

### Q4: Vannak más példák és oktatóanyagok?

A4: Igen, a [dokumentáció](https://reference.aspose.com/zip/net/) átfogó példákat és oktatóanyagokat tartalmaz.

### Q5: Megvásárolhatom az Aspose.Zip for .NET-et?

A5: Természetesen, vásárlást indíthat [itt](https://purchase.aspose.com/buy).

## Összegzés

Most már rendelkezik egy teljes, termelés‑kész mintával a **hogyan kell ZIP-re csomagolni egy mappát** az Aspose.Zip for .NET használatával. A könyvtár `Archive` osztályának kihasználásával **zip archívum** fájlokat hozhat létre, beállíthat egy egyéni `CompressionLevel`‑et, jelszóvédelmet adhat hozzá, sőt **több mappát is ZIP-re csomagolhat** egyetlen lépésben – ezáltal tökéletes a mappa‑mentési feladatok automatizálásához. Kísérletezzen az API‑val titkosítás hozzáadásához, archívumok felosztásához vagy közvetlen felhő‑tárolóba való streameléshez, és egy robusztus megoldást kap bármely .NET‑alapú tömörítési igényhez.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [zip multiple files c# – Effortless Compression with Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip for .NET - Password Protect Zip Archive & Store Multiple Files Without Compression](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [How to Zip Folder – Compress Directory with Aspose.Zip](/zip/net/directory-and-folder-compression/decompress-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}