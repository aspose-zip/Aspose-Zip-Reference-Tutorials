---
date: 2026-02-20
description: Tanulja meg, hogyan tömörítsen tarbz2 fájlokat, hogyan hozzon létre targz
  archívumokat, valamint a .NET archívumok kicsomagolását jelszóval védett zip kicsomagolással
  az Aspose.Zip for .NET használatával. Növelje a tárolási hatékonyságot és a biztonságot.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tömörítsünk TarBz2 fájlokat az Aspose.Zip for .NET segítségével
url: /hu/net/archive-extraction-and-formats/
weight: 23
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk TarBz2 fájlokat az Aspose.Zip for .NET segítségével

## Bevezetés

Ebben az útmutatóban megtanulja, **hogyan tömörítsen tarbz2 fájlokat** az Aspose.Zip for .NET segítségével, miközben felfedezi, hogyan hozhat létre TarGz archívumokat, és hogyan végezhet .net archívumkicsomagolást jelszóval védett zip fájlok esetén. A hatékony fájlkezelés a modern .NET fejlesztés egyik alappillére, és ezen formátumok elsajátítása lehetővé teszi a tárolási költségek csökkentését, az adatátvitel felgyorsítását, valamint az érzékeny információk védelmét. Akár egy biztonsági mentési szolgáltatást, egy felhő‑tároló klienst vagy egy adatfeldolgozó csővezetéket épít, az itt bemutatott technikák gördülékenyebbé és megbízhatóbbá teszik a fájlkezelési feladatokat.

## Gyors válaszok
- **Mi az a TarBz2?** Egy tömörített archívum, amely a TAR csomagolást BZIP2 tömörítéssel kombinálja a magas tömörítési arányok érdekében.  
- **Miért válassza az Aspose.Zip for .NET-et?** Egyetlen, folyékony API-t kínál számos archívumformátum létrehozásához és kicsomagolásához külső függőségek nélkül.  
- **Létrehozhatok TarGz archívumot?** Igen – az Aspose.Zip támogatja a TarGz, TarLz, TarXz, TarZ és további formátumokat.  
- **Hogyan csomagoljak ki egy jelszóval védett zip archívumot?** Használja a `Password` tulajdonságot a `ArchiveEntry` objektumon a kicsomagolás során.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges a termeléshez; egy ingyenes próba elérhető értékeléshez.

## Hogyan tömörítsünk TarBz2 fájlokat
A fájlok TarBz2 formátumba történő tömörítése azt jelenti, hogy először több fájlt és könyvtárat egyetlen **TAR** tárolóba csomagolunk, majd **BZIP2** tömörítést alkalmazunk. Az eredmény egy `.tar.bz2` fájl, amely egyszerre könnyen szállítható és erősen tömörített.

## Miért használja az Aspose.Zip for .NET-et ezen formátumok kezeléséhez?
- **Egységes API** – Egy könyvtár, sok formátum (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Nincs natív függőség** – Alapból működik Windows, Linux és macOS rendszereken.  
- **Jelszó támogatás** – Biztonságosan védje és csomagolja ki az archívumokat bejegyzésenkénti jelszavakkal.  
- **Teljesítmény‑orientált** – Az adatfolyam‑alapú feldolgozás minimalizálja a memóriahasználatot.

## Előfeltételek
- .NET 6.0 vagy újabb (vagy .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip for .NET NuGet csomag telepítve (`Install-Package Aspose.Zip`).  
- Alapvető C# és fájl I/O ismeretek.

## Lépésről‑lépésre útmutató

### 1. lépés: Válassza ki a szükséges archívumformátumot
Döntse el, hogy a **TarBz2**, **TarGz**, **TarLz**, **TarXz**, vagy **TarZ** melyik illik legjobban a tömörítési arány és a kompatibilitási követelményekhez.  
- **TarBz2** – Legjobb tömörítés, lassabb feldolgozás.  
- **TarGz** – Jó egyensúly a sebesség és a méret között (lefedi a másodlagos kulcsszót *how to create targz*).  
- **TarZ** – Örökölt formátum, hasznos a régebbi Unix eszközökkel való kompatibilitáshoz.

### 2. lépés: Hozzon létre egy új `Archive` példányt
Példányosítsa az `Archive` osztályt, és mutassa az kimeneti fájl útvonalára. Ez az objektum kezeli a csomagolási és tömörítési folyamatot.

### 3. lépés: Fájlok és mappák hozzáadása
Használja a `AddAll` vagy `AddFile` metódusokat a tömöríteni kívánt fájlok hozzáadásához. A könyvtárstruktúra megőrizhető egy alapmappa hozzáadásával.

### 4. lépés: A kívánt tömörítési típus beállítása
Adja meg a tömörítési algoritmust (`CompressionType.BZip2`, `CompressionType.GZip`, stb.) az archívum mentésekor. Itt történik a tényleges **fájlok TarBz2 formátumba tömörítése** vagy bármely más formátum.

### 5. lépés: Archívum mentése
Hívja meg a `Save` metódust a megfelelő formátum enummal (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, stb.). A könyvtár egy lépésben írja a TAR tárolót és alkalmazza a kiválasztott tömörítést.

### 6. lépés: Archívumok kicsomagolása jelszóval
Ha **archívumbejegyzéseket kell kicsomagolni különböző jelszavakkal** (másodlagos kulcsszó *password protected zip extraction*), nyissa meg az archívumot, keresse meg az egyes bejegyzéseket, állítsa be a jelszavukat, majd csomagolja ki őket.

### 7. lépés: Az eredmény ellenőrzése
A kicsomagolás után hasonlítsa össze a fájlméreteket és ellenőrzőösszegeket, hogy megbizonyosodjon arról, hogy az archívum helyesen lett létrehozva és kicsomagolva.

## Gyakori felhasználási esetek
- **Biztonsági mentési segédprogramok** – Napi mentéseket `.tar.bz2` formátumban tároljon a tárolási költségek minimalizálása érdekében.  
- **Keresztplatformos adatcsere** – A Tar‑alapú formátumok univerzálisan érthetőek Linuxon, macOS-en és Windowson.  
- **Biztonságos terjesztés** – Védje az egyes bejegyzéseket jelszóval a megfelelőségi környezetekben.

## Hibaelhárítás és tippek
- **Nagy archívumok** – Használjon streaming API‑kat (`Archive.CreateEntryFromFile`), hogy elkerülje a teljes fájlok memóriába betöltését.  
- **Jelszó eltérések** – Győződjön meg arról, hogy az egyes `ArchiveEntry` beállított jelszava megegyezik a kicsomagolás során használt jelszóval; ellenkező esetben `InvalidPasswordException` hibát kap.  
- **Nem támogatott tömörítési szint** – A BZIP2 nem támogat egyéni tömörítési szinteket; ha finomabb vezérlésre van szükség, fontolja meg a TarLz vagy TarXz használatát.

## Gyakran Ismételt Kérdések

**K: Hogyan hozhatok létre TarGz archívumot?**  
V: Állítsa be a tömörítési típust `CompressionType.GZip`‑re, és a formátumot `ArchiveFormat.TarGz`‑re a `Save` hívásakor.

**K: Kicsomagolhatok jelszóval védett archívumot a jelszó ismerete nélkül?**  
V: Nem. Minden bejegyzéshez a helyes jelszót kell megadni; ellenkező esetben a kicsomagolás sikertelen lesz.

**K: Az Aspose.Zip támogatja a különböző jelszavakkal rendelkező bejegyzések kicsomagolását?**  
V: Igen. Minden `ArchiveEntry` számára egyedileg beállíthat jelszót a kicsomagolás előtt.

**K: Melyik formátum nyújtja a legjobb tömörítést?**  
V: A TarBz2 általában a legmagasabb tömörítési arányt biztosítja, ezt követi a TarLz és a TarXz. A TarGz jó egyensúlyt kínál a sebesség és a méret között.

**K: Van korlát a TAR archívumba hozzáadható fájlok számát illetően?**  
V: Gyakorlatilag nincs, de rendkívül nagy archívumok esetén előnyös lehet több részre bontani a könnyebb kezelés érdekében.

## Archívumkicsomagolási és formátumok oktatóanyagai
### [Fájlok tömörítése TarBz2 formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-bz2/)
Tanulja meg, hogyan tömörítsen fájlokat TarBz2 formátumba .NET‑ben az Aspose.Zip használatával. Kövesse lépésről‑lépésre útmutatónkat a hatékony fájltömörítéshez.
### [Tömörítés TarGz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-gz/)
Fedezze fel a hatékony fájltömörítést .NET‑ben az Aspose.Zip‑kel. Tömörítsen TarGz‑ba könnyedén.
### [Tömörítés TarLz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-lz/)
Könnyedén tömörítsen fájlokat .NET‑ben az Aspose.Zip‑kel. Tanulja meg, hogyan hozhat létre TarLz archívumokat lépésről‑lépésre.
### [Tömörítés TarXz formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-xz/)
Tanulja meg, hogyan tömörítsen fájlokat TarXz formátumba .NET‑ben az Aspose.Zip használatával. Kövesse lépésről‑lépésre útmutatónkat a hatékony fájltároláshoz és átvitelhez.
### [Tömörítés TarZ formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-z/)
Fedezze fel a lépésről‑lépésre történő tömörítést TarZ formátumba az Aspose.Zip for .NET‑el. Hatékony fájlkezelés .NET‑projektekhez.
### [Archívumbejegyzések kicsomagolása különböző jelszavakkal az Aspose.Zip for .NET‑ben](./extract-archive-different-passwords/)
Tanulja meg, hogyan csomagoljon ki archívumbejegyzéseket különböző jelszavakkal az Aspose.Zip for .NET‑ben. Növelje alkalmazásai biztonságát és rugalmasságát.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose