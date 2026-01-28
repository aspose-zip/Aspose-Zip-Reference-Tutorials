---
date: 2026-01-28
description: Tanulja meg, hogyan lehet jelszóval ellátott archívumot kicsomagolni,
  fájlokat TarBz2 formátumba tömöríteni, TarGz archívumokat létrehozni az Aspose.Zip
  for .NET segítségével. Növelje a tárolási hatékonyságot és a biztonságot.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Archívum kibontása jelszóval és tömörítés TarBz2-re (.NET)
url: /hu/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Archívum kicsomagolása jelszóval és tömörítése TarBz2-re (.NET)

Ebben az útmutatóban megtudja, **hogyan lehet kicsomagolni jelszóval védett archívumot**, valamint elsajátíthatja a **fájlok TarBz2 formátumba tömörítését** az Aspose.Zip for .NET segítségével. Akár biztonsági mentési szolgáltatást, felhő‑tároló klienset vagy adatfeldolgozó csővezetéket épít, ezek a technikák csökkentik a tárhelyigényt, felgyorsítják az átviteleket és megvédik a bizalmas adatokat.

## Gyors válaszok
- **Mi az a TarBz2?** Egy tömörített archívum, amely a TAR csomagolást kombinálja a BZIP2 tömörítéssel a magas tömörítési arány érdekében.  
- **Miért válassza az Aspose.Zip for .NET-et?** Egyetlen, folyékony API-t biztosít számos archívumformátumhoz natív függőségek nélkül.  
- **Létrehozhatok TarGz archívumot?** Igen – az Aspose.Zip támogatja a TarGz, TarLz, TarXz, TarZ és további formátumokat.  
- **Hogyan lehet kicsomagolni jelszóval védett archívumot?** Állítsa be a `Password` tulajdonságot minden `ArchiveEntry`‑nél a kicsomagolás előtt.  
- **Szükségem van licencre a termeléshez?** A termeléshez kereskedelmi licenc szükséges; ingyenes próbaverzió elérhető értékeléshez.

## Hogyan lehet kicsomagolni jelszóval védett archívumot az Aspose.Zip for .NET használatával
A **jelszóval védett zip archívum** kicsomagolása egyszerű. Megnyitja az archívumot, megtalálja a kívánt bejegyzést, beállítja a jelszót, majd meghívja a `Extract` metódust. Ez a megközelítés működik TarBz2, TarGz és más támogatott formátumok esetén is.

## Mit jelent valójában a „fájlok TarBz2 formátumba tömörítése”?
A fájlok TarBz2 formátumba tömörítése először több fájlt és könyvtárat egyetlen **TAR** tárolóba csomagol, majd **BZIP2** tömörítést alkalmaz. Az eredmény egy `.tar.bz2` fájl, amely egyszerűen szállítható és erősen tömörített.

## Miért használja az Aspose.Zip for .NET-et ezeknek a formátumoknak a kezelésére?
- **Egységes API** – Egy könyvtár, sok formátum (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Nincs natív függőség** – Windows, Linux és macOS rendszereken működik „out of the box”.  
- **Jelszó támogatás** – Biztonságosan védhet és csomagolhat ki archívumokat bejegyzésenkénti jelszavakkal.  
- **Teljesítmény‑központú** – Stream‑alapú feldolgozás minimalizálja a memóriahasználatot.

## Előfeltételek
- .NET 6.0 vagy újabb (vagy .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip for .NET NuGet csomag telepítve (`Install-Package Aspose.Zip`).  
- Alapvető C# és fájl‑I/O ismeretek.

## Lépésről‑lépésre útmutató

### Step 1: Válassza ki a szükséges archívumformátumot
Döntse el, hogy a **TarBz2**, **TarGz**, **TarLz**, **TarXz** vagy **TarZ** melyik felel meg legjobban a tömörítési aránynak és a kompatibilitási követelményeknek.  
- **TarBz2** – Legjobb tömörítés, lassabb feldolgozás.  
- **TarGz** – Jó egyensúly a sebesség és a méret között (magában foglalja a *compress files to targz* másodlagos kulcsszót).  
- **TarZ** – Régi formátum régebbi Unix eszközökhöz.

### Step 2: Hozzon létre egy új `Archive` példányt
Példányosítsa az `Archive` osztályt, és mutassa a kimeneti fájl útvonalára. Ez az objektum kezeli a csomagolási és tömörítési folyamatot.

### Step 3: Adjon hozzá fájlokat és mappákat
Használja az `AddAll` vagy `AddFile` metódusokat a tömöríteni kívánt fájlok bevonásához. A könyvtárstruktúra megőrzése érdekében adjon hozzá egy alapmappát.

### Step 4: Állítsa be a kívánt tömörítési típust
Adja meg a tömörítési algoritmust (`CompressionType.BZip2`, `CompressionType.GZip`, stb.) az archívum mentésekor. Itt történik a **fájlok tarbz2 formátumba tömörítése** vagy bármely más formátum.

### Step 5: Mentse az archívumot
Hívja meg a `Save` metódust a megfelelő formátum‑enummal (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, stb.). A könyvtár egy lépésben írja a TAR tárolót és alkalmazza a kiválasztott tömörítést.

### Step 6: Archívumok kicsomagolása jelszavakkal
Ha **archívumbejegyzéseket kell kicsomagolni különböző jelszavakkal** (*how to extract password protected archive*), nyissa meg az archívumot, keresse meg minden bejegyzést, állítsa be a jelszót, majd csomagolja ki.

### Step 7: Ellenőrizze az eredményt
Kicsomagolás után hasonlítsa össze a fájlméreteket és ellenőrzőösszegeket, hogy megbizonyosodjon arról, az archívum helyesen lett létrehozva és kibontva.

## Gyakori felhasználási esetek
- **Biztonsági mentési segédprogramok** – Napi mentéseket `.tar.bz2` formátumban tárolva minimalizálja a tárhelyköltséget.  
- **Kereszt‑platform adatcsere** – A Tar‑alapú formátumok univerzálisan érthetőek Linuxon, macOS‑on és Windowson.  
- **Biztonságos terjesztés** – Egyedi bejegyzéseket jelszóval védve a megfelelőségi környezetek igényeihez.

## Hibaelhárítás és tippek
- **Nagy archívumok** – Használjon streaming API‑kat (`Archive.CreateEntryFromFile`) a teljes fájlok memóriába töltésének elkerülésére.  
- **Jelszó eltérések** – Győződjön meg arról, hogy minden `ArchiveEntry`‑nél beállított jelszó megegyezik a kicsomagoláshoz használt jelszóval; ellenkező esetben `InvalidPasswordException` hibát kap.  
- **Nem támogatott tömörítési szint** – A BZIP2 nem támogat egyedi tömörítési szinteket; ha finomabb vezérlésre van szükség, fontolja meg a TarLz vagy TarXz használatát.  
- **Teljesítmény tipp** – **TarBz2 archívum létrehozásakor** engedélyezze a pufferelést az alaprendszer‑streamen a írási sebesség javítása érdekében.

## Gyakran feltett kérdések

**Q: Hogyan hozhatok létre egy TarGz archívumot?**  
A: Állítsa be a tömörítési típust `CompressionType.GZip`‑re, és a formátumot `ArchiveFormat.TarGz`‑re a `Save` hívásakor.

**Q: Kicsomagolhatok jelszóval védett archívumot anélkül, hogy ismerném a jelszót?**  
A: Nem. Minden bejegyzéshez a helyes jelszót kell megadni, különben a kicsomagolás sikertelen lesz.

**Q: Az Aspose.Zip támogatja-e a különböző jelszavakkal rendelkező bejegyzések kicsomagolását?**  
A: Igen. Minden `ArchiveEntry`‑hez egyenként hozzárendelhet jelszót a kicsomagolás előtt.

**Q: Melyik formátum nyújtja a legjobb tömörítést?**  
A: A TarBz2 általában a legmagasabb tömörítési arányt biztosítja, ezt követi a TarLz és a TarXz. A TarGz jó sebesség‑méret egyensúlyt kínál.

**Q: Van korlátozás a fájlok számában, amelyeket egy TAR archívumba felvehetünk?**  
A: Gyakorlatilag nincs, de rendkívül nagy archívumok esetén érdemes több részre bontani a könnyebb kezelhetőség érdekében.

## Archívum kicsomagolási és formátum‑tutorialok
### [Fájlok tömörítése TarBz2 formátumba az Aspose.Zip for .NET segítségével](./compress-to-tar-bz2/)
Ismerje meg, hogyan tömöríthet fájlokat TarBz2 formátumba .NET‑ben az Aspose.Zip használatával. Kövesse lépésről‑lépésre útmutatónkat a hatékony fájltömörítéshez.  
### [Tömörítés TarGz formátumba az Aspose.Zip for .NET‑el](./compress-to-tar-gz/)
Fedezze fel a hatékony fájltömörítést .NET‑ben az Aspose.Zip‑el. Tömörítsen TarGz formátumba egyszerűen.  
### [Tömörítés TarLz formátumba az Aspose.Zip for .NET‑el](./compress-to-tar-lz/)
Könnyedén tömöríthet fájlokat .NET‑ben az Aspose.Zip‑el. Tanulja meg, hogyan hozhat létre TarLz archívumokat lépésről‑lépésre.  
### [Tömörítés TarXz formátumba az Aspose.Zip for .NET‑el](./compress-to-tar-xz/)
Tanulja meg, hogyan tömöríthet fájlokat TarXz formátumba .NET‑ben az Aspose.Zip használatával. Kövesse útmutatónkat a hatékony tároláshoz és átvitelhez.  
### [Tömörítés TarZ formátumba az Aspose.Zip for .NET‑el](./compress-to-tar-z/)
Fedezze fel a lépésről‑lépésre történő tömörítést TarZ formátumba az Aspose.Zip for .NET‑el. Hatékony fájlkezelés .NET‑projektjeihez.  
### [Archívumbejegyzések kicsomagolása különböző jelszavakkal az Aspose.Zip for .NET‑ben](./extract-archive-different-passwords/)
Ismerje meg, hogyan csomagolhat ki archívumbejegyzéseket különböző jelszavakkal az Aspose.Zip for .NET‑ben. Növelje alkalmazásai biztonságát és rugalmasságát.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Legutóbb frissítve:** 2026-01-28  
**Tesztelt verzió:** Aspose.Zip for .NET 24.11  
**Szerző:** Aspose