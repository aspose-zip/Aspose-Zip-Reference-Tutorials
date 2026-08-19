---
date: 2026-07-18
description: Ismerje meg, hogyan adhat hozzá mappát a zip-hez és fájlokat a zip-hez
  az Aspose.Zip for .NET használatával. Ez a lépésről‑lépésre útmutató bemutatja,
  hogyan tömöríthet fájlokat FileInfo-val ASP.NET projektekben.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Fájlok tömörítése FileInfo-val
og_description: Mappa hozzáadása zip-hez az Aspose.Zip for .NET használatával. Ismerje
  meg, hogyan hozhat létre zip-archívumot, adhat hozzá fájlokat a zip-hez, és tömöríthet
  mappákat hatékonyan ASP.NET-ben.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Mappa hozzáadása zip-hez – Fájlok tömörítése Aspose.Zip for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Mappa hozzáadása zip-hez az Aspose.Zip for .NET használatával – Fájlok tömörítése
  FileInfo-val
url: /hu/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mappa hozzáadása zip-hez az Aspose.Zip for .NET használatával

## Bevezetés

Ha programozott módon **mappát szeretne zip‑be adni**, az Aspose.Zip for .NET tiszta, nagy teljesítményű API‑t kínál, amely bármely .NET (beleértve az ASP.NET‑et) alkalmazásban működik. Ebben az útmutatóban végigvezetjük a fájlok tömörítését a `FileInfo` osztállyal, megmutatjuk, hogyan **fájlokat adhat hozzá a zip‑hez**, és elmagyarázzuk, miért ideális ez a megközelítés a modern .NET projektekhez. Emellett bemutatjuk a **mappa zip‑be adásának** pontos lépéseit, hogy egyetlen művelettel egész könyvtárakat csomagolhasson. Kezdjük!

## Gyors válaszok
- **Mi a legegyszerűbb módja egy zip archívum létrehozásának?** Használja az Aspose.Zip `Archive` osztályát `FileInfo` objektumokkal.  
- **Hozzáadhatok több fájlt egyszerre?** Igen – egyszerűen hozzon létre egy `FileInfo`‑t minden fájlhoz, és hívja a `CreateEntry`‑t.  
- **Szükségem van speciális licencre az ASP.NET‑hez?** A kereskedelmi Aspose.Zip licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez is működik.  
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10.  
- **A API szálbiztos?** Igen, amennyiben minden szál a saját `Archive` példányával dolgozik.

## Mi az a zip archívum és miért hozunk létre ilyet?

Egy zip archívum egy vagy több fájlt egyetlen, tömörített tárolóba csomagol. Ez csökkenti a tárhelyigényt, felgyorsítja a hálózati átviteleket, és egyszerűsíti a terjesztést. Akár naplókat szállít, jelentéseket exportál, vagy eszközöket csomagol egy ügyfélnek, a **zip archívumok programozott létrehozásának** ismerete értékes készség minden .NET fejlesztő számára.

## Miért használja az Aspose.Zip-et fájlok zip‑be adásához?

Aspose.Zip egy tisztán .NET megoldást kínál, amely kiküszöböli a külső függőségeket, miközben a fejlesztőknek részletes irányítást ad a tömörítés, kódolás és biztonság felett. Támogatja a nagy fájlokat, a jelszóvédelmet, és következetesen működik minden támogatott .NET verzióban, így megbízható választás a régi és modern alkalmazások számára.

- **Nulla külső függőség** – tiszta .NET megvalósítás.  
- **Teljes irányítás a tömörítési szint és a kódolás felett** (ASCII, UTF‑8 stb.).  
- **Támogatja a 4 GB-nál nagyobb fájlokat** és a jelszóvédelmet.  
- **Következetes API 50+ .NET verzióban** – a .NET Framework 2.0‑tól a .NET 10‑ig.  

## Előfeltételek

Mielőtt a kódba merülnénk, győződjön meg róla, hogy rendelkezik:

1. **Aspose.Zip for .NET** telepítve. Töltse le a legújabb csomagot a [Aspose.Zip letöltési oldalról](https://releases.aspose.com/zip/net/).  
2. Egy mappa a gépén, amely tartalmazza a tömöríteni kívánt fájlokat (pl. `alice29.txt` és `fields.c`).  

## Névterek importálása

Bármely C# fájlban, ahol zip archívumokkal dolgozik, adja hozzá a következő `using` utasításokat:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Ezek a névterek hozzáférést biztosítanak az `Archive` osztályhoz, a mentési beállításokhoz és a szabványos I/O segédeszközökhöz.

## Lépésről‑lépésre útmutató

### 1. lépés: Dokumentumkönyvtár beállítása

Először határozza meg a forrásfájlokat tartalmazó mappát. Cserélje le a helyőrzőt a rendszerén lévő abszolút vagy relatív útra:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tipp:** Használja a `Path.Combine`‑t az utak platformfüggetlen összeállításához.

### 2. lépés: Zip fájl megnyitása íráshoz

Hozzon létre egy `FileStream`‑et, amely a kimeneti zip fájlra mutat. A stream **Create** módban nyílik, amely felülírja az azonos nevű meglévő fájlt:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 3. lépés: `FileInfo` objektumok előkészítése minden forrásfájlhoz

`FileInfo` közvetlen hozzáférést biztosít az Aspose.Zip számára a lemezen lévő fizikai fájlokhoz. Hozzon létre egy példányt minden tömöríteni kívánt fájlhoz:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Miért használja a `FileInfo`‑t?** Elkerüli a teljes fájl memóriába töltését, ami különösen hasznos nagy fájlok esetén.

### 4. lépés: Archívum létrehozása és bejegyzések hozzáadása

Az `Archive` osztály az Aspose.Zip központi objektuma, amely egy zip tárolót reprezentál a memóriában. Hozzon létre egy `Archive` objektumot, majd hívja a `CreateEntry`‑t minden `FileInfo`‑hoz. Az első argumentum a fájl neve a zip‑en belül, a második argumentum a forrás `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

A `CreateEntry` metódus új fájlbejegyzést ad az archívumhoz, összekapcsolva a bejegyzés nevét a forrás `FileInfo`‑val, így az adat közvetlenül a lemezről kerül be a mentéskor.

### 5. lépés: Zip archívum mentése a kívánt kódolással

Végül mentse az archívumot a korábban megnyitott `FileStream`‑be. Itt ASCII kódolást használunk a bejegyzésneveknél, de átállíthat UTF‑8-ra, ha a fájlnevek nem ASCII karaktereket tartalmaznak:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Amikor a `using` blokkok kilépnek, a streamek automatikusan bezáródnak, és a zip fájl használatra kész.

## Hogyan adjon hozzá mappát zip‑hez az Aspose.Zip használatával?

Töltse be a célkönyvtárat, sorolja fel az összes fájlt, és adja hozzá mindegyiket egy relatív úttal, amely tartalmazza a mappa nevét. Ez a megközelítés lehetővé teszi, hogy **mappát adjon hozzá zip‑hez** anélkül, hogy manuálisan felsorolná minden fájlt. A mappaszerkezet megőrzésével a bejegyzésnevekben a létrejött archívum az eredeti könyvtárstruktúra megőrzésével lesz kicsomagolható, ami számos telepítési forgatókönyvben elengedhetetlen.

1. Használja a `DirectoryInfo`‑t a tömöríteni kívánt mappa megjelöléséhez.  
2. Hívja a `GetFiles("*", SearchOption.AllDirectories)`‑t az összes fájl rekurzív lekéréséhez.  
3. Minden fájlhoz hozza létre a `FileInfo`‑t, és hívja a `CreateEntry`‑t egy olyan úttal, mint például `"MyFolder/Report.pdf"`.

Mivel az API a `FileInfo`‑val dolgozik, minden fájlt közvetlenül a lemezről streamel, így alacsony memóriahasználatot biztosít még a több száz megabájtot tartalmazó mappák esetén is.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|-------|-------|-----|
| **Üres zip fájl** | `FileInfo` egy nem létező útra mutat | Ellenőrizze a `dataDir` és a fájlneveket; használja a `File.Exists`‑t a bejegyzések létrehozása előtt. |
| **Helytelen fájlnév kódolás** | Alapértelmezett kódolás használata nem ASCII nevek esetén | Állítsa be `Encoding = Encoding.UTF8`‑t az `ArchiveSaveOptions`‑ban. |
| **OutOfMemoryException nagy fájloknál** | A teljes fájl betöltése a memóriába | A `FileInfo` streameli a fájlt; győződjön meg róla, hogy máshol nem olvassa be a fájlt byte tömbbe. |
| **Hozzáférés megtagadva** | Az alkalmazásnak nincs írási joga a kimeneti mappához | Futtassa az alkalmazást megfelelő jogosultságokkal vagy válasszon írható könyvtárat. |

## Gyakran feltett kérdések

**Q: Hozzáadhatok egy teljes mappát egy zip archívumhoz egyetlen hívással?**  
A: Nem létezik egyetlen hívásos módszer, de a `DirectoryInfo`‑val történő fájlok felsorolása és mindegyik `CreateEntry`‑val való hozzáadása hatékonyan eléri ugyanazt az eredményt.

**Q: Támogatja az Aspose.Zip a jelszóvédelmet?**  
A: Igen, a `Archive` objektumra mentés előtt beállíthat jelszót, hogy az egész archívum titkosítva legyen.

**Q: Milyen nagy zip fájlokat képes kezelni az Aspose.Zip?**  
A: A könyvtár 4 GB‑nál nagyobb fájlokat is feldolgoz, és 10 GB‑t meghaladó archívumokat is létrehozhat anélkül, hogy az egész archívumot memóriába töltené.

**Q: Kompatibilis az API a .NET 6 és .NET 8 verziókkal?**  
A: Teljesen. Az Aspose.Zip a .NET 5‑től a .NET 10‑ig támogatja, lefedve az összes jelenlegi LTS kiadást.

**Q: Milyen tömörítési szintek érhetők el?**  
A: Választhatja a `CompressionLevel.NoCompression`, `Fast`, `Normal` vagy `Maximum` szinteket a sebesség és méret egyensúlyozásához.

## További források

- Töltse le a legújabb Aspose.Zip csomagot: [Aspose.Zip letöltési oldal](https://releases.aspose.com/zip/net/)  
- Licenc vásárlása termelési használathoz: [vásárlási oldal](https://purchase.aspose.com/buy)  
- Segítség a közösségtől: [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37)  
- Próbálja ki az Aspose.Zip-et ingyen: [ingyenes próba itt](https://releases.aspose.com/)  
- Ideiglenes licenc beszerzése értékeléshez: [ez a link](https://purchase.aspose.com/temporary-license/)

## Következtetés

Most már tudja, hogyan **adjunk mappát zip‑hez** és hogyan **hozzunk létre zip archívum** fájlokat az Aspose.Zip for .NET használatával, hogyan **adjunk fájlokat zip‑hez**, és miért ideális ez a módszer az ASP.NET és más .NET alkalmazások számára. Kísérletezzen különböző tömörítési szintekkel, kódolásokkal és titkosítási beállításokkal, hogy az archívumot pontosan az igényeihez igazítsa. Boldog tömörítést!

---

**Legutóbb frissítve:** 2026-07-18  
**Tesztelve a következővel:** Aspose.Zip for .NET 24.12 (latest)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan zip‑eljünk mappát az Aspose.Zip for .NET használatával](/zip/net/directory-and-folder-compression/compress-directory/)
- [több fájl zip‑elése C# – Könnyed tömörítés az Aspose.Zip for .NET használatával](/zip/net/file-compression/compress-multiple-files/)
- [Zip archívum létrehozása .NET – Fájl tömörítés az Aspose.Zip használatával](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}