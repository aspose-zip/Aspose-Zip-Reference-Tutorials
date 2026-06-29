---
date: 2026-06-29
description: Ismerje meg, hogyan lehet mappát 7z formátumba tömöríteni az Aspose.Zip
  for .NET segítségével, bemutatva a 7z tömörítési módszereket, mint például az LZMA2,
  a BZip2 és a Store. Tökéletes 7z archívumok programozott létrehozásához.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip különböző tömörítési módszerekkel
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Mappa tömörítése 7z formátumba – Aspose.Zip for .NET oktatóanyag
url: /hu/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk mappát 7z – Aspose.Zip for .NET útmutató

## Bevezetés

Ha programozott módon kell **compress folder to 7z** archívumokat készíteni egy .NET alkalmazásban, jó helyen jár. Az Aspose.Zip for .NET egyszerűvé teszi a Seven Zip archívumok generálását a támogatott tömörítési algoritmusok bármelyikével, akár egy teljes könyvtárat szeretne csomagolni terjesztéshez, akár csak egy megbízható **seven zip archive .net** megoldásra van szüksége. Ebben az útmutatóban három népszerű tömörítési módszert – LZMA2, BZip2 és Store (nincs tömörítés) – mutatunk be, és pontosan megmutatjuk, hogyan állíthat elő egy 7z fájlt néhány C# sorral.

## Gyors válaszok
- **Milyen könyvtárat használjak?** Az Aspose.Zip for .NET a legteljesebb Seven Zip funkciókészletet biztosítja.  
- **Melyik tömörítési módszer adja a legjobb arányt?** Az LZMA2 általában a legmagasabb tömörítést nyújt vegyes adatok esetén.  
- **Létrehozhatok 7z fájlt tömörítés nélkül?** Igen – használja a Store (nincs tömörítés) módszert.  
- **Szükségem van licencre a fejlesztéshez?** Elérhető ingyenes próba; licenc szükséges a termelési használathoz.  
- **Kompatibilis ez a .NET 6/7-tel?** Teljesen – az Aspose.Zip támogatja a .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 és a .NET 5–10 verziókat.

## Mik a Seven Zip tömörítési módszerek?

A Seven Zip több algoritmust támogat, mindegyik különböző helyzetekhez optimalizált. **LZMA2** a legmagasabb tömörítési arányt kínál (gyakran 30‑40 %-kal kisebb, mint a BZip2), **BZip2** stabil tömörítést biztosít szélesebb régi eszközök támogatásával, és **Store** egyszerűen archiválja a fájlokat anélkül, hogy zsugorítaná őket, így tökéletesen megőrzi az eredeti időbélyegeket.

## Előfeltételek

- Alapvető C# és Visual Studio ismeretek.  
- Az Aspose.Zip for .NET könyvtár telepítve van. Szerezze be a hivatalos letöltési oldalról **[itt](https://releases.aspose.com/zip/net/)**.  
- Egy mappa (`dataDir`), amely a archiválni kívánt fájlokat tartalmazza.

## Névterek importálása

Először adja hozzá a szükséges névtereket a C# fájlhoz:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Ezek a osztályok hozzáférést biztosítanak a tömörítési beállításokhoz és az archívum kezeléséhez.

## LZMA2 tömörítés – Hogyan hozzunk létre 7z fájlt maximális aránnyal

Az `Archive` osztály egy 7z archívumot képvisel, amely több fájlt is tartalmazhat.  
Az LZMA2 algoritmus a legmagasabb tömörítési arányt nyújtja a támogatott módszerek közül. A bemenetet blokkokra osztja, és kifinomult szótár tömörítést alkalmaz. Az Aspose.Zip-ben a `CompressionMethod`-ot `CompressionMethod.Lzma2`-ra állítja az `Archive` objektumon, mielőtt fájlokat adna hozzá.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tipp:** Az LZMA2 a legjobban működik, ha a forrásfájlok nagyobbak 1 MB-nál. Sok kis fájl esetén a BZip2 gyorsabb lehet.

## BZip2 tömörítés – Kiegyensúlyozott választás

Az `Archive` osztály egy 7z archívumot képvisel, amely több fájlt is tartalmazhat.  
A BZip2 stabil tömörítést kínál jó kompatibilitással a régebbi eszközökhöz. A Burrows‑Wheeler transzformációt és a Huffman kódolást használja a méret csökkentésére. Az Aspose.Zip-ben a `CompressionMethod.BZip2`-t választja az `Archive` példány konfigurálásakor, ami egyensúlyt teremt a sebesség és a tömörítési arány között a legtöbb szöveges és bináris fájl esetén.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

A BZip2 stabil tömörítést biztosít, miközben ésszerű sebességet tart fenn, így jó alternatíva, ha a célkörnyezet nem támogatja az LZMA2-t.

## Store (nincs tömörítés) – Amikor a méret nem számít

Az `Archive` osztály egy 7z archívumot képvisel, amely több fájlt is tartalmazhat.  
A Store módszer archívumot hoz létre anélkül, hogy a adatot tömörítené. Egyszerűen átmásolja az eredeti fájlokat a 7z tárolóba, megőrizve az időbélyegeket és a könyvtárstruktúrát. Az Aspose.Zip-ben a `CompressionMethod.Store`-t kell beállítani az `Archive`-on, mielőtt hozzáadná a csomagolni kívánt fájlokat.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Használja a Store módszert, ha egyszerűen csak fájlokat szeretne összevonni méretük megváltoztatása nélkül – tökéletes az eredeti időbélyegek megőrzéséhez vagy ha az archívumot futás közben fogják kicsomagolni.

## Hogyan adhatok fájlokat a 7z-hez?

Fájlokat adhat hozzá egy 7z archívumhoz egy `Archive` példány létrehozásával, a kívánt `CompressionMethod` beállításával, és az `AddAllFiles(dataDir)` hívásával. A metódus rekurzívan beolvassa a megadott mappát, megőrizve a könyvtárhierarchiát az archívumban. Ez a megközelítés lehetővé teszi, hogy **compress folder to 7z** egyetlen kódsorral a kezdeti beállítás után.

## Gyakori felhasználási esetek

| Forgatókönyv | Ajánlott módszer |
|--------------|-------------------|
| Nagy telepítők terjesztése | LZMA2 |
| Naplók megosztása régi eszközökkel | BZip2 |
| Fájlok csomagolása gyors kicsomagoláshoz | Store (no compression) |
| Szükség van **compress folder to 7z** valós időben egy webszolgáltatásban | LZMA2 (for best ratio) |

## Hibaelhárítás és tippek

- **Hiányzó fájlok az archívumban?** Ellenőrizze, hogy a `dataDir` a megfelelő könyvtárra mutat-e, és hogy a folyamatnak olvasási jogosultsága van-e.  
- **Az archívum nem nyílik meg régebbi 7‑Zip verziókon?** Maradjon a BZip2 vagy Store mellett, mivel az LZMA2 újabb kitömörítő könyvtárakat igényelhet.  
- **Teljesítmény szűk keresztmetszet?** Nagy adathalmazok esetén fontolja meg az archívum streamelését ahelyett, hogy az összes bejegyzést memóriába töltené.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Zip for .NET-et bármilyen típusú fájllal?**  
A: Igen, az Aspose.Zip széles körű fájlformátumot támogat, lehetővé téve, hogy gyakorlatilag bármilyen fájltípust tömörítsen és kitömörítsen.

**Q: Elérhető ingyenes próba az Aspose.Zip for .NET-hez?**  
A: Igen, ingyenes próbát szerezhet **[itt](https://releases.aspose.com/)**.

**Q: Hol találom az Aspose.Zip for .NET dokumentációját?**  
A: A teljes API referencia **[itt](https://reference.aspose.com/zip/net/)** érhető el.

**Q: Hogyan szerezhetek ideiglenes licenceket az Aspose.Zip for .NET-hez?**  
A: Ideiglenes licenceket **[itt](https://purchase.aspose.com/temporary-license/)** szerezhet.

**Q: Hol kaphatok támogatást az Aspose.Zip for .NET-hez?**  
A: Támogatást kérhet a **[Aspose.Zip fórumon](https://forum.aspose.com/c/zip/37)**.

---

**Utolsó frissítés:** 2026-06-29  
**Tesztelve a következővel:** Aspose.Zip for .NET 24.12  
**Szerző:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [fájlok tömörítése c# – 7z archívum létrehozása az Aspose.Zip for .NET segítségével](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Hogyan zipeljünk mappát az Aspose.Zip for .NET használatával](/zip/net/directory-and-folder-compression/compress-directory/)
- [Hogyan tömörítsünk LZMA-t az Aspose.Zip for .NET-ben](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}