---
date: 2026-02-12
description: Tanulja meg, hogyan hozhat létre tömörítetlen zip .NET fájlokat az Aspose.Zip
  for .NET segítségével. Ez az útmutató megmutatja, hogyan lehet fájlokat tömörítés
  nélkül zip-olni, tömörítetlenül tárolni, és hatékonyan kezelni az archívumokat.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Nem tömörített zip létrehozása .NET-ben az Aspose.Zip for .NET segítségével
url: /hu/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nem tömörített zip .net létrehozása az Aspose.Zip for .NET segítségével

A modern .NET fejlesztésben a **nem tömörített zip .net** létrehozása drámaian javíthatja az archiválási sebességet és előre jelezhetővé teheti a fájlméreteket. Amikor **fájlokat kell zip‑elni tömörítés nélkül**—például szabályozási előírásoknak való megfelelés vagy az alatta lévő feldolgozás felgyorsítása érdekében—az Aspose.Zip for .NET tiszta, egyszerű API‑t kínál. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan hozhatunk létre egy nem tömörített ZIP archívumot, hogyan adhatunk hozzá fájlokat, és hogyan integrálhatjuk a megoldást az alkalmazásba.

## Gyors válaszok
- **Mi jelent a „nem tömörített zip”?** Ez egy ZIP archívum, ahol minden bejegyzés a „store” módszerrel van tárolva, az eredeti fájlbiteket érintetlenül hagyva.  
- **Miért kerülni a tömörítést?** Az archiválás felgyorsítása, az eredeti fájlméretek megőrzése az alatta lévő feldolgozáshoz, vagy olyan szabályozási követelményeknek való megfelelés, amelyek tiltják az adatok módosítását.  
- **Melyik Aspose.Zip osztály kezeli ezt?** `ArchiveEntrySettings` kombinálva a `StoreCompressionSettings`‑szel.  
- **Szükségem van licencre?** Egy ingyenes próba a teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Támogatott .NET verziók?** .NET Framework, .NET Core, .NET 5/6/7 és későbbi verziók.  

## Mi az a nem tömörített zip .net?
A nem tömörített ZIP létrehozása azt jelenti, hogy minden fájlt a *store* tömörítési módszerrel adunk hozzá egy ZIP konténerhez. A fájlok bájt‑bájton azonosak maradnak az eredetikkel, ami ideális, ha gyors archiválásra vagy az adatok változatlanul tartására van szükség.

## Miért használjuk az Aspose.Zip-et tömörítés nélküli zip fájlokhoz?
- **Sebesség:** Nem futtat CPU‑igényes tömörítési algoritmus.  
- **Előre jelezhető méret:** Az archívum mérete az eredeti fájlok összegével és minimális ZIP többlettel egyezik meg.  
- **Kompatibilitás:** A létrehozott ZIP bármely szabványos kicsomagoló eszközzel működik.  
- **Rugalmasság:** Szükség esetén továbbra is keverhet tömörített és nem tömörített bejegyzéseket ugyanabban az archívumban.  

## Előfeltételek
- **Aspose.Zip for .NET** – integrálva a projektedbe. Lásd a hivatalos [documentation](https://reference.aspose.com/zip/net/) a telepítési lépésekhez.  
- **.NET fejlesztői környezet** – Visual Studio, VS Code vagy bármely kedvelt IDE.  
- **Dokumentum könyvtár** – egy mappa a gépeden, amely a archiválni kívánt fájlokat tartalmazza (pl. „Your Document Directory”).  

## Névterek importálása
Mielőtt kódot írnál, importáld a szükséges névtereket, hogy a fordító tudja, hol találja az Aspose osztályokat.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 1. lépés: Dokumentum könyvtár beállítása
Határozd meg az útvonalat, ahol a forrásfájlok találhatók. Cseréld ki a helyőrzőt a rendszeredben lévő tényleges mappára.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: ZIP archívum létrehozása tömörítés nélkül
A tutorial központi része – létrehozunk egy `Archive` példányt, amely `StoreCompressionSettings`‑kel van konfigurálva. Ez azt mondja az Aspose.Zip-nek, hogy *store* (azaz ne tömörítsen) minden bejegyzést.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Pro tipp:** Ha **fájlokat kell zip‑be menteni**, miközben egyeseket tömörítesz, másokat nem, hozz létre külön `ArchiveEntrySettings` példányokat minden fájlhoz, és add hozzá őket ugyanahhoz a `Archive`‑hez.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Fájl nem található** | Helytelen `dataDir` útvonal vagy hiányzó fájlkiterjesztés. | Ellenőrizd az útvonalat és győződj meg arról, hogy a fájlok léteznek. Használd a `Path.Combine`‑t a biztonságosabb összefűzéshez. |
| **Hozzáférés megtagadva** | A folyamatnak nincs joga a forrásfájlok olvasásához vagy a ZIP írásához. | Futtasd az alkalmazást megfelelő jogosultságokkal, vagy válassz egy írási joggal rendelkező mappát. |
| **Váratlan fájlméret a ZIP-ben** | Az archívum alapértelmezett tömörítéssel lett létrehozva. | Győződj meg arról, hogy a `new StoreCompressionSettings()` át van adva az `ArchiveEntrySettings`‑nek. |

## Gyakran ismételt kérdések

**Q: Tömöríthetek bizonyos fájltípusokat, miközben másokat nem tömörítek?**  
**A:** Igen, létrehozhatsz külön `ArchiveEntrySettings`‑t minden fájlhoz, és keverheted a tömörített és nem tömörített bejegyzéseket ugyanabban az archívumban.

**Q: Az Aspose.Zip for .NET kompatibilis a .NET Core‑ral és a .NET 5/6‑tal?**  
**A:** Teljes mértékben. A könyvtár támogatja a .NET Framework‑ot, a .NET Core‑t, a .NET Standard‑ot és a legújabb .NET verziókat.

**Q: Hogyan kezeljem a kivételeket az archiválási folyamat során?**  
**A:** Tekerd be az archiváló kódot egy `try‑catch` blokkba, és naplózd a kivétel részleteit. Ez biztosítja a szép hibakezelést és a könnyebb hibakeresést.

**Q: Támogatja az Aspose.Zip a több szálon futó archiválást?**  
**A:** Igen, több fájlt is feldolgozhatsz párhuzamosan és hozzáadhatod őket az archívumhoz, de ne feledd, hogy az `Archive` objektum önmagában nem szálbiztos; szinkronizáld a hozzáférést a bejegyzések hozzáadása során.

**Q: Integrálhatom az Aspose.Zip-et egy meglévő projektbe jelentős kódelváltoztatás nélkül?**  
**A:** Természetesen. Az API egyszerű beillesztésre lett tervezve. Tekintsd meg a hivatalos [documentation](https://reference.aspose.com/zip/net/) migrációs útmutatóját.

---

**Utolsó frissítés:** 2026-02-12  
**Tesztelve ezzel:** Aspose.Zip for .NET (latest at time of writing)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}