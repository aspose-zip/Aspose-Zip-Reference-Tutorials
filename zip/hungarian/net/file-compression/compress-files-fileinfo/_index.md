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

### GYIK

#### 1. kérdés: Az Aspose.Zip kompatibilis az összes fájltípussal?

1. válasz: Az Aspose.Zip számos fájltípust támogat, így biztosítva a sokoldalú tömörítést.

#### 2. kérdés: Használhatom az Aspose.Zip-et kereskedelmi projektekhez?

2. válasz: Természetesen! Látogassa meg a [vásárlási oldalunkat](https://purchase.aspose.com/buy) a licencelési lehetőségek megismeréséhez.

#### 3. kérdés: Hogyan kaphatok támogatást az Aspose.Zip-hez?

3. válasz: Csatlakozzon közösségünkhöz az [Aspose.Zip fórumon](https://forum.aspose.com/c/zip/37) segítségért és beszélgetésekért.

#### 4. kérdés: Van elérhető ingyenes próbaverzió?

4. válasz: Igen, letöltheti az [ingyenes próbaverziót itt](https://releases.aspose.com/).

#### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip-hez?

5. válasz: Az ideiglenes licenc beszerzésével kapcsolatos információkért látogassa meg [ezt a linket](https://purchase.aspose.com/temporary-license/).

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