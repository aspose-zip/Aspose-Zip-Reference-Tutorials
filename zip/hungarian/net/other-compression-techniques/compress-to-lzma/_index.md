---
date: 2026-06-24
description: Ismerje meg, hogyan lehet LZMA-t tömöríteni az Aspose.Zip for .NET-ben,
  optimalizálva a tárolást és az adatátvitel hatékonyságát.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Tömörítés Lzma-ra
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tömörítsük az LZMA-t az Aspose.Zip for .NET-ben
url: /hu/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk LZMA-t az Aspose.Zip for .NET-ben

## Bevezetés

Ebben az oktatóanyagban megtanulja, **hogyan tömörítsen LZMA-t** az Aspose.Zip for .NET-ben, ami kulcsfontosságú képesség a tárolóhely optimalizálásához és az adatátvitel hatékonyságának növeléséhez. Az LZMA (Lempel‑Ziv‑Markov lánc algoritmus) akár 70 %-kal kisebb archívumokat eredményez a hagyományos ZIP-hez képest, miközben gyors kitömörítést biztosít, így ideális a sávszélesség‑korlátozott környezetekben.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Zip for .NET  
- **Melyik algoritmust tárgyalja ez az útmutató?** LZMA tömörítés  
- **Szükségem van licencre?** Ideiglenes licenc elegendő a teszteléshez; teljes licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt egy egyszerű fájl.

## Mi az a LZMA tömörítés?

Az LZMA egy nagy tömörítési arányú veszteségmentes algoritmus, amely szótár‑tömörítést és tartománykódolást használ. Képes a szövegfájlok méretét 30‑70 %-kal csökkenteni, miközben a kitömörítési sebesség összehasonlítható a ZIP‑kel. Nagy adathalmazok esetén az LZMA csökkenti a tárolási költségeket és felgyorsítja a hálózati átviteleket anélkül, hogy a adat integritását veszélyeztetné.

## Miért használjuk az Aspose.Zip-et LZMA-hoz?

Az Aspose.Zip **5 tömörítési algoritmust** támogat (ZIP, Deflate, BZIP2, LZMA és ZSTD), és akár **4 GB**‑os archívumokat is képes kezelni anélkül, hogy a teljes fájlt a memóriába töltené. A könyvtár több száz oldalas dokumentumokat **2 másodperc** alatt dolgoz fel egy tipikus szerveren, ezáltal kiváló teljesítményt és skálázhatóságot biztosítva.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy a következők rendelkezésre állnak:

- Aspose.Zip for .NET: Győződjön meg róla, hogy az Aspose.Zip könyvtár telepítve van. A dokumentációt megtalálja [itt](https://reference.aspose.com/zip/net/).
- Dokumentum könyvtár: Válasszon vagy hozzon létre egy mappát, amely tartalmazza a tömöríteni kívánt fájlokat.

## Névterek importálása

Adja hozzá a szükséges névtereket a C# fájl tetejéhez, hogy elérhesse az Aspose.Zip LZMA funkcióit:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Hogyan állítsam be a forrásmappát a tömörítéshez?

Adja meg azt a mappát, amely a tömöríteni kívánt fájlokat tartalmazza. Egy dedikált forráskönyvtár biztosítja, hogy csak a kívánt fájlok kerüljenek feldolgozásra, csökkenti a nem kívánt adatok bekerülésének kockázatát, és egyszerűbbé teszi az útvonalkezelést több tömörítési feladat esetén ugyanabban a projektben.

```csharp
string dataDir = "Your Document Directory";
```

## Hogyan tömörítsek egy fájlt LZMA-val?

`LzmaArchive` az Aspose.Zip osztálya LZMA archívumok létrehozásához és kezeléséhez.

Hozzon létre egy `LzmaArchive` példányt, mutassa rá a forrásfájlra, majd hívja meg a `Save` metódust a `.lzma` archívum generálásához. Ez a két soros minta végrehajtja a teljes tömörítési munkafolyamatot, belsőleg kezeli a stream‑eket, és egy kompakt fájlt állít elő, amely készen áll a terjesztésre vagy tárolásra.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Hogyan ellenőrizhetem, hogy a tömörítés sikeres volt?

`Console.WriteLine` egy szövegsort ír a szabványos kimeneti konzolra.

Az archívum mentése után írjon ki egy rövid megerősítő üzenetet a `Console.WriteLine` segítségével. Ez a közvetlen visszajelzés segít a fejlesztőknek ellenőrizni, hogy a tömörítési lépés hibamentesen befejeződött, megkönnyíti a hibakeresést automatizált build-ek során, és egyértelmű állapotinformációt nyújt, amikor a rutin nagyobb alkalmazásokba vagy szkriptekbe van integrálva.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Gyakori problémák és megoldások

- **Fájl nem található** – Ellenőrizze, hogy az elérési út dupla backslash‑t (`\\`) vagy verbatim stringet (`@"C:\Path"`) használ.
- **Elégséges memória hiánya** – Az Aspose.Zip adatfolyamot használ, de rendkívül nagy fájlok esetén a folyamat memóriahatárának növelése szükséges lehet.
- **Licenc nincs alkalmazva** – Győződjön meg róla, hogy a `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` hívást a bármely Aspose.Zip művelet előtt végrehajtja.

## Gyakran feltett kérdések

**K: Több fájlt tömöríthetek egyetlen LZMA archívumba?**  
A: Igen. Hívja meg az `archive.AddFile()`‑t minden fájlra, mielőtt meghívná az `archive.Save()`‑t.

**K: Van lehetőség a LZMA tömörítési szint beállítására?**  
A: Az `LzmaArchive` osztály az alapértelmezett tömörítési szintet használja, amely jó egyensúlyt biztosít a sebesség és a méret között. Haladó beállítások a `LzmaEncoder`‑en keresztül érhetők el, ha finomhangolt vezérlésre van szükség.

**K: A létrejött .lzma fájl működik nem‑Windows platformokon is?**  
A: Teljesen. Az LZMA formátum platform‑független, így az archívum bármely operációs rendszeren kicsomagolható egy LZMA‑kompatibilis eszközzel.

**K: Hogyan csomagolok ki egy LZMA archívumot az Aspose.Zip segítségével?**  
A: Használja az `LzmaArchive` konstruktort az archívum útvonalával, majd hívja meg az `ExtractToDirectory()`‑t a tartalom kicsomagolásához.

**K: Támogatja az Aspose.Zip a streaming tömörítést, hogy elkerülje a teljes fájl memóriába töltését?**  
A: Igen. A `Stream` objektumokat átadva a `SetSource()` és `Save()` metódusoknak, stream‑alapú módon dolgozhat.

---

**Utolsó frissítés:** 2026-06-24  
**Tesztelve a következővel:** Aspose.Zip for .NET (legújabb verzió a megírás időpontjában)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan tömörítsünk fájlokat az Aspose.Zip for .NET segítségével](/zip/net/file-compression/compress-file/)
- [Hogyan nyissunk meg GZip archívumot és más tömörítési technikákat az Aspose.Zip for .NET segítségével](/zip/net/other-compression-techniques/)
- [fájlok tömörítése c# – 7z archívum létrehozása az Aspose.Zip for .NET segítségével](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}