---
date: 2025-12-10
description: Ismerje meg, hogyan tárolhat fájlokat tömörítés nélkül az Aspose.Zip
  for .NET használatával. Ez az útmutató megmutatja, hogyan hozhat létre tömörítetlen
  zip fájlt, hogyan menthet fájlokat a zip-be, és hogyan kezelheti hatékonyan az archívumokat.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tároljunk fájlokat tömörítés nélkül az Aspose.Zip for .NET segítségével
url: /hu/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tároljunk fájlokat tömörítés nélkül az Aspose.Zip for .NET segítségével

A modern .NET fejlesztésben a **fájlok hatékony tárolása** jelentős különbséget tehet a teljesítmény és a tárolási költségek tekintetében. Ha a fájlokat pontosan úgy kell megőrizni, ahogy vannak – tömörítés nélkül – az Aspose.Zip for .NET egy tiszta, egyszerű API-t biztosít. Ebben az útmutatóban végigvezetünk a lépéseken, hogyan hozhatunk létre egy tömörítés nélküli ZIP archívumot, hogyan menthetünk fájlokat a ZIP-be, és hogyan integrálhatjuk a megoldást az alkalmazásba.

## Gyors válaszok
- **Mit jelent a „tömörítés nélküli zip”?** Ez egy ZIP archívum, ahol minden bejegyzés a „store” (tárolás) módszerrel van tárolva, az eredeti fájlbiteket érintetlenül hagyva.  
- **Miért kerülni a tömörítést?** Az archiválás felgyorsítása, az eredeti fájlméretek megőrzése a további feldolgozáshoz, vagy olyan szabályozási követelményeknek való megfelelés, amelyek tiltják az adatok módosítását.  
- **Melyik Aspose.Zip osztály kezeli ezt?** `ArchiveEntrySettings` kombinálva a `StoreCompressionSettings`-szel.  
- **Szükségem van licencre?** Egy ingyenes próba verzió teszteléshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Támogatott .NET verziók?** .NET Framework, .NET Core, .NET 5/6/7 és újabbak.

## Mi az a több fájl tömörítés nélküli tárolása?
A több fájl tömörítés nélküli tárolása azt jelenti, hogy minden fájlt a *store* tömörítési módszerrel adunk hozzá egy ZIP konténerhez. A fájlok bájtonként azonosak maradnak az eredetikkel, ami ideális, ha gyors archiválásra van szükség vagy az adatot változatlanul kell megőrizni.

## Miért használjuk az Aspose.Zip-et tömörítés nélküli archívumokhoz?
- **Sebesség:** Nem futtat CPU‑igényes tömörítési algoritmusokat.  
- **Előre látható méret:** Az archívum mérete megegyezik az eredeti fájlok összegével, plusz minimális ZIP overhead.  
- **Kompatibilitás:** A létrehozott ZIP bármely szabványos kicsomagoló eszközzel működik.  
- **Rugalmasság:** Szükség esetén keverhet tömörített és tömörítés nélküli bejegyzéseket ugyanabban az archívumban.

## Előkövetelmények
- **Aspose.Zip for .NET** – integrálva a projektbe. Az installációs lépésekért tekintse meg a hivatalos [dokumentációt](https://reference.aspose.com/zip/net/).  
- **.NET fejlesztői környezet** – Visual Studio, VS Code vagy bármely kedvelt IDE.  
- **Dokumentum könyvtár** – egy mappa a gépén, amely a archiválni kívánt fájlokat tartalmazza (pl. “Your Document Directory”).

## Névterek importálása
Mielőtt kódot írna, importálja a szükséges névtereket, hogy a fordító tudja, hol találja az Aspose osztályokat.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 1. lépés: Dokumentum könyvtár beállítása
Határozza meg az útvonalat, ahol a forrásfájlok találhatók. Cserélje ki a helyőrzőt a rendszerén lévő tényleges mappára.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: ZIP archívum létrehozása tömörítés nélkül
Az útmutató központi része – létrehozunk egy `Archive` példányt, amely `StoreCompressionSettings`-kel van konfigurálva. Ez azt mondja az Aspose.Zip-nek, hogy *tárolja* (azaz ne tömörítse) minden bejegyzést.

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

> **Pro tipp:** Ha **fájlokat kell ZIP-be menteni**, miközben egyeseket tömörít, másokat tömörítés nélkül hagy, hozzon létre külön `ArchiveEntrySettings` példányokat minden fájlhoz, és adja hozzá őket ugyanahhoz az `Archive`-hez.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **File not found** | Helytelen `dataDir` útvonal vagy hiányzó fájlkiterjesztés. | Ellenőrizze az útvonalat és győződjön meg a fájlok létezéséről. Használja a `Path.Combine`-t a biztonságosabb összefűzéshez. |
| **Access denied** | A folyamatnak nincs joga a forrásfájlok olvasásához vagy a ZIP írásához. | Futtassa az alkalmazást megfelelő jogosultságokkal, vagy válasszon egy írási jogosultsággal rendelkező mappát. |
| **Unexpected file size in ZIP** | Az archívum alapértelmezett tömörítéssel lett létrehozva. | Győződjön meg róla, hogy `new StoreCompressionSettings()` van átadva az `ArchiveEntrySettings`-nek. |

## Gyakran Ismételt Kérdések

**K: Kompressálhatok bizonyos fájltípusokat, míg másokat tömörítés nélkül tárolok?**  
V: Igen, létrehozhat különböző `ArchiveEntrySettings`-t minden fájlhoz, és keverheti a tömörített és tömörítés nélküli bejegyzéseket ugyanabban az archívumban.

**K: Az Aspose.Zip for .NET kompatibilis a .NET Core és a .NET 5/6 verziókkal?**  
V: Teljesen. A könyvtár támogatja a .NET Framework, .NET Core, .NET Standard és a legújabb .NET verziókat.

**K: Hogyan kezeljem a kivételeket az archiválási folyamat során?**  
V: Tegye a archiváló kódot egy `try‑catch` blokkba, és naplózza a kivétel részleteit. Ez biztosítja a hibamentes leállást és a könnyebb hibakeresést.

**K.Zip támogatja a több szálas archiválást?**  
V: Igen, több fájlt párhuzamosan feldolgozhat és hozzáadhat az archívumhoz, de ne feledje, hogy az `Archive` objektum önmagában nem szálbiztos; szinkronizálja a hozzáférést a bejegyzések hozzáadásakor.

**K: Integrálhatom az Aspose.Zip-et egy meglévő projektbe jelentős kódelváltoztatás nélkül?**  
V: Határozottan. Az API egyszerű beillesztésre lett tervezve. Tekintse meg a hivatalos [dokumentációt](https://reference.aspose.com/zip/net/) a migrációs útmutatóért.

---

**Last Updated:** 2025-12-10  
**Tesztelve a következővel:** Aspose.Zip for .NET 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}