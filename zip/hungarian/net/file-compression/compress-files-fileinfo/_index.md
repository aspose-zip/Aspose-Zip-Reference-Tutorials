---
date: 2026-02-28
description: Tudja meg, hogyan adhat hozzá mappát a zip-hez, és hogyan adhat fájlokat
  a zip-hez az Aspose.Zip for .NET használatával. Ez a lépésről‑lépésre útmutató bemutatja,
  hogyan tömöríthet fájlokat a FileInfo segítségével ASP.NET projektekben.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan adjon hozzá mappát a ZIP-hez az Aspose.Zip for .NET használatával –
  Fájlok tömörítése FileInfo-val
url: /hu/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá mappát zip-hez az Aspose.Zip for .NET használatával

## Bevezetés

Ha programozott módon **zip archívumot kell létrehoznod**, az Aspose.Zip for .NET egy tiszta, nagy teljesítményű API‑t biztosít, amely bármely .NET (beleértve az ASP.NET‑et) alkalmazásban működik. Ebben az útmutatóban végigvezetünk a fájlok tömörítésén a `FileInfo` osztállyal, megmutatjuk, hogyan **adj fájlokat a zip‑hez**, és elmagyarázzuk, miért ideális ez a megközelítés a modern .NET projektekhez. Kitérünk arra is, hogyan **adj mappát a zip‑hez**, hogy egy lépésben egész könyvtárakat is becsomagolj. Kezdjük el!

## Gyors válaszok
- **Mi a legegyszerűbb módja egy zip archívum létrehozásának?** Használd az Aspose.Zip `Archive` osztályát `FileInfo` objektumokkal együtt.  
- **Hozzáadhatok több fájlt egyszerre?** Igen – csak hozz létre egy `FileInfo`‑t minden fájlhoz, és hívd meg a `CreateEntry`‑t.  
- **Szükségem van speciális licencre ASP.NET‑hez?** Egy kereskedelmi Aspose.Zip licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez elegendő.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Az API szálbiztos?** Igen, amennyiben minden szál a saját `Archive` példányával dolgozik.

## Mi az a Zip archívum és miért hozunk létre ilyet?
A zip archívum egy vagy több fájlt egyetlen, tömörített konténerbe csomagol. Ez csökkenti a tárhelyigényt, felgyorsítja a hálózati átviteleket, és egyszerűsíti a terjesztést. Legyen szó naplófájlok szállításáról, jelentések exportálásáról vagy ügyfélnek szánt eszközök csomagolásáról, a **zip archívum programozott létrehozása** értékes képesség minden .NET fejlesztő számára.

## Miért használjuk az Aspose.Zip-et fájlok zip‑hez adásához?
- **Nulla külső függőség** – tisztán .NET megvalósítás.  
- **Teljes kontroll a tömörítési szint és a kódolás (ASCII, UTF‑8, stb.) felett**.  
- **Nagy fájlok támogatása** (> 4 GB) és jelszóvédelem.  
- **Konzisztens API a .NET Framework, .NET Core és .NET 5+ között**.

## Előfeltételek

Mielőtt a kódba merülnénk, győződj meg róla, hogy:

1. **Aspose.Zip for .NET** telepítve van. Töltsd le a legújabb csomagot a [Aspose.Zip letöltési oldalról](https://releases.aspose.com/zip/net/).  
2. Van egy mappa a gépeden, amely tartalmazza a tömöríteni kívánt fájlokat (pl. `alice29.txt` és `fields.c`).  

## Névterek importálása

Bármely C# fájlban, ahol zip archívumokkal dolgozol, add hozzá a következő `using` utasításokat:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Ezek a névterek biztosítják a `Archive` osztályhoz, a mentési beállításokhoz és a szabványos I/O segédeszközökhöz való hozzáférést.

## Lépésről‑lépésre útmutató

### 1. lépés: Állítsd be a dokumentum könyvtárát

Először definiáld azt a mappát, amely a forrásfájlokat tartalmazza. Cseréld le a helyőrzőt a rendszereden lévő abszolút vagy relatív útra:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Használd a `Path.Combine`‑t az utak platformfüggetlen összeállításához.

### 2. lépés: Nyiss egy zip fájlt írásra

Hozz létre egy `FileStream`‑et, amely a kimeneti zip fájlra mutat. A stream **Create** módban nyílik, ami felülírja az azonos nevű meglévő fájlt:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 3. lépés: Készíts `FileInfo` objektumokat minden forrásfájlhoz

A `FileInfo` közvetlen hozzáférést biztosít az Aspose.Zip‑nek a lemezen lévő fizikai fájlokhoz. Hozz létre egy példányt minden tömöríteni kívánt fájlhoz:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Miért használjuk a `FileInfo`‑t?** Elkerüli a teljes fájl memóriába töltését, ami különösen nagy fájlok esetén hasznos.

### 4. lépés: Hozd létre az archívumot és adj hozzá bejegyzéseket

Példányosíts egy `Archive` objektumot, majd minden `FileInfo`‑hoz hívd meg a `CreateEntry`‑t. Az első argumentum a zip‑en belüli fájlnév, a második a forrás `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 5. lépés: Mentsd el a zip archívumot a kívánt kódolással

Végül írd ki az archívumot a korábban megnyitott `FileStream`‑be. Itt ASCII kódolást használunk a bejegyzésnevekhez, de ha a fájlnevek nem‑ASCII karaktereket tartalmaznak, válthatsz UTF‑8‑ra:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Amikor a `using` blokkok kilépnek, a streamek automatikusan bezáródnak, és a zip fájl készen áll a használatra.

## Hogyan adjunk hozzá mappát zip‑hez az Aspose.Zip használatával

Ha **mappát szeretnél a zip‑hez adni** az egyes fájlok helyett, a folyamat egyszerű:

1. **Sorold fel a mappát** a `DirectoryInfo.GetFiles`‑el (és opcionálisan a `GetDirectories`‑szel a rekurzióhoz).  
2. **Hozz létre egy `FileInfo`‑t** minden megtalált fájlhoz.  
3. **Hívd meg a `CreateEntry`‑t** egy relatív úttal, amely tartalmazza a mappa nevét, pl. `"MyFolder/Report.pdf"`.

Mivel az API a `FileInfo`‑val dolgozik, soha nem kell az egész fájlt memóriába tölteni, ami nagy könyvtárak esetén is biztonságos. Ez a technika **zip multiple files asp.net** forgatókönyvekben is működik, amikor egy jelentéssorozatot generálsz „on‑the‑fly”, és egyetlen archívumban szeretnéd kiszolgálni.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Üres zip fájl** | `FileInfo` egy nem létező útra mutat | Ellenőrizd a `dataDir`‑t és a fájlneveket; használj `File.Exists`‑t a bejegyzések létrehozása előtt. |
| **Helytelen fájlnév kódolás** | Alapértelmezett kódolás használata nem‑ASCII nevekhez | Állítsd be `Encoding = Encoding.UTF8`‑et az `ArchiveSaveOptions`‑ban. |
| **OutOfMemoryException nagy fájloknál** | A teljes fájl betöltése a memóriába | A `FileInfo` streameli a fájlt; ügyelj arra, hogy máshol ne olvasd be bájt‑tömbbe. |
| **Permission denied** | Az alkalmazásnak nincs írási joga a kimeneti mappához | Futtasd az alkalmazást megfelelő jogosultságokkal, vagy válassz írható könyvtárat. |

## Gyakran Ismételt Kérdések

**Q: Hozzáadhatok jelszóvédelmet a zip archívumhoz?**  
A: Igen. Az `Archive` létrehozása után állítsd be `archive.Password = "yourPassword"`‑t a `Save` hívása előtt.

**Q: Lehet-e frissíteni egy már létező zip fájlt?**  
A: Az Aspose.Zip támogatja egy meglévő archívum megnyitását a `Archive.Open`‑nal, majd új bejegyzések hozzáadását.

**Q: Hogyan tömöríthetek fájlokat egy ASP.NET MVC vezérlőben?**  
A: Ugyanez a kód működik; csak győződj meg róla, hogy a kimeneti streamet `FileResult`‑ként adod vissza a kliensnek.

**Q: Támogatja az Aspose.Zip a titkosítási algoritmusokat?**  
A: Igen, támogatja a szabványos ZipCrypto és az AES‑256 titkosítást.

**Q: Mit tegyek, ha rekurzívan kell tömöríteni egy mappát?**  
A: Iterálj a `Directory.GetFiles`‑en (és az almappákon) és minden fájlhoz hozz létre egy `FileInfo`‑t, majd add hozzá az archívumhoz.

## További GYIK

**Q: Hogyan hozhatok létre zip archívumot .net‑en nagy adathalmazokhoz?**  
A: Használd a `FileInfo` objektumokat az adat streameléséhez, és állítsd be a `CompressionLevel`‑t az `ArchiveSaveOptions`‑ban a legjobb teljesítményért.

**Q: Használhatom az Aspose.Zip‑et egy .NET Core web API‑ban (zip files asp.net core)?**  
A: Természetesen – a könyvtár teljesen kompatibilis a .NET Core 3.1‑el és újabb verziókkal.

**Q: Van-e mód a mappa zip‑hez adására anélkül, hogy egyedi ciklust írnánk?**  
A: Az Aspose.Zip nem rendelkezik egyetlen “add folder” metódussal, de a `DirectoryInfo`‑val való iterálás könnyű, és teljes kontrollt ad a bejegyzésnevek felett.

**Q: Befolyásolja a zip archívum jelszóvédelem a tömörítési sebességet?**  
A: A titkosítás kis extra terhet jelent, de a legtöbb esetben a hatás elhanyagolható.

**Q: Milyen licenc szükséges a kereskedelmi üzemeltetéshez?**  
A: Egy fizetett Aspose.Zip licenc szükséges a termeléshez; ingyenes próba használható fejlesztéshez és teszteléshez.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Összegzés

Most már tudod, **hogyan adj mappát a zip‑hez** és **hogyan hozz létre zip archívumot** az Aspose.Zip for .NET segítségével, hogyan **adj fájlokat a zip‑hez**, és miért ideális ez a módszer ASP.NET‑hez és más .NET alkalmazásokhoz. Kísérletezz különböző tömörítési szintekkel, kódolásokkal és titkosítási beállításokkal, hogy az archívum pontosan a te igényeidnek megfelelő legyen. Boldog tömörítést!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}