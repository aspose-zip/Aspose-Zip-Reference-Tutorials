---
date: 2026-06-19
description: Ismerje meg, hogyan adhat hozzá több fájlt a tar-hoz, és tömörítheti
  a fájlokat tar.gz formátumba az Aspose.Zip for .NET használatával – egy gyors, platformfüggetlen
  mód a TarGz archívumok létrehozásához.
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: Fájlok hozzáadása a tar-hoz
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Több fájl hozzáadása a tar-hoz és tar.gz archívum létrehozása az Aspose.Zip
  for .NET segítségével
url: /hu/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több fájl hozzáadása a tar-hoz és tar.gz archívum létrehozása az Aspose.Zip for .NET segítségével

## Bevezetés

Modern .NET alkalmazásokban a **több fájl hozzáadása a tar-hoz** és aztán a **fájlok tömörítése tar.gz formátumba** gyakori igény—legyen szó naplófájlok csomagolásáról, adatok felhő tárolásra való előkészítéséről vagy Linux szerverekhez készült telepítőcsomagok létrehozásáról. Az Aspose.Zip for .NET tiszta, nagy teljesítményű API-t biztosít, amely lehetővé teszi tar archívum építését, tetszőleges számú fájl hozzáadását, és opcionálisan a tar.gz fájlba való tömörítést—mind mind külső eszközök nélkül. Ebben az útmutatóban végigvezetünk a teljes munkafolyamaton, a projekt beállításától egy termelésre kész `archive.tar.gz`-ig.

## Gyors válaszok

- **Melyik könyvtárat kell használnom?** Aspose.Zip for .NET – támogatja a tar, tar.gz, zip és sok más formátumot.  
- **Hogyan adhatok hozzá több fájlt a tar-hoz?** Hívja meg a `TarArchive.CreateEntry` metódust minden egyes fájlhoz, amelyet fel szeretne venni.  
- **Tömöríthetek közvetlenül tar.gz formátumba?** Igen—hívja meg a `SaveGzipped` metódust a `TarArchive` példányon.  
- **Szükség van licencre a termeléshez?** Érvényes Aspose licenc szükséges a nem‑próba használathoz.  
- **Mely .NET verziók támogatottak?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10.

## Mi az a „több fájl hozzáadása a tar-hoz”?

A több fájl hozzáadása egy tar archívumhoz azt jelenti, hogy több fájlt (és opcionálisan könyvtárakat) egyetlen, tömörítetlen tárolóba csomagolunk, miközben megőrzik az eredeti hierarchiát és metaadatokat. A keletkezett `.tar` fájl később gzip-pel tömöríthető, így `tar.gz` archívumot hozva létre, amely széles körben használatos terjesztésre és biztonsági mentésre.

## Miért használjuk az Aspose.Zip-et a fájlok tar.gz formátumba tömörítéséhez?

Az Aspose.Zip kezeli a teljes tar és gzip folyamatot memóriában, kiküszöbölve a natív segédprogramok szükségességét. Képes **akár 500 GB archívum** feldolgozására anélkül, hogy a teljes fájlt a memóriába töltené, köszönhetően a stream‑alapú architektúrájának. A könyvtár támogat **50+ bemeneti és kimeneti formátumot**, fut Windows, Linux és macOS rendszereken, és további funkciókat kínál, mint titkosítás, jelszóvédelem és egyedi bejegyzés attribútumok—mind egyetlen .NET API-ból.

## Előkövetelmények

- Alap .NET fejlesztési tapasztalat.  
- Visual Studio (vagy bármely kedvelt IDE).  
- Aspose.Zip for .NET telepítve – lásd a hivatalos dokumentációt [itt](https://reference.aspose.com/zip/net/).  
- Az Aspose.Zip könyvtár letöltve [erről a linkről](https://releases.aspose.com/zip/net/).

## Névterek importálása

In .NET projektjében importálja azokat a névtereket, amelyek a tar‑hoz kapcsolódó osztályokat tartalmazzák:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hogyan adhatunk hozzá több fájlt a tar-hoz az Aspose.Zip for .NET használatával

Az Aspose.Zip használatával először betölti a forrásmappát, példányosít egy `TarArchive`‑t, majd végigiterál minden fájlon, meghívva a `CreateEntry`‑t a hozzáadásukhoz az archívumba. Miután az összes bejegyzés hozzá lett adva, meghívja a `SaveGzipped`‑et egy tömörített `archive.tar.gz` létrehozásához. Ez a teljes folyamat csak néhány sor tiszta, típus‑biztos .NET kódot igényel.

### 1. lépés: Állítsa be a dokumentum könyvtárát

Adja meg azt a mappát, amely a archiválni kívánt fájlokat tartalmazza.

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tipp:** Használja a `Path.Combine`‑t útvonalak építésekor, hogy elkerülje a platform‑specifikus elválasztó problémákat.  
> A `Path.Combine` metódus biztonságosan összekapcsolja a könyvtár- és fájlneveket a megfelelő elválasztóval az operációs rendszerhez.

### 2. lépés: TarGz archívum létrehozása

Most létrehozzuk a tar archívumot, hozzáadjuk a bejegyzéseket, és egy folytonos lépésben tömörítjük.

#### 2.1 A TarArchive inicializálása

A `TarArchive` osztály az Aspose.Zip legfelső szintű objektuma, amely egy memóriában lévő tar tárolót képvisel. Példányosítása egy üres archívumot készít fel a bejegyzések számára.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Fájlok hozzáadása – a „több fájl hozzáadása a tar-hoz” magja

`CreateEntry` új bejegyzést hoz létre a tar archívumban. A metódus a **bejegyzés nevét** (a tar‑on belüli útvonal) és a **forrásfájl útvonalát** a lemezen veszi át. Hívja meg többször, hogy a szükséges számú fájlt hozzáadja.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Minden `CreateEntry` hívás egyetlen fájlt ad hozzá; egy könyvtárgyűjteményen ciklizálva tucatnyi vagy akár száz fájlt is hozzáadhat minimális kóddal.

#### 2.3 Mentés Gzipped Tar-ként (hogyan tömörítsük a fájlokat tar.gz formátumba)

`SaveGzipped` a tar tartalmat egy gzip áramba írja, egy kompakt `archive.tar.gz` fájlt hozva létre, amely készen áll a terjesztésre vagy tárolásra.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

A metódus automatikusan kezeli a gzip fejléceket és lábléceket, így extra lépések nélkül kap egy szabványosnak megfelelő tar.gz fájlt.

## Általános felhasználási esetek

| Forgatókönyv | Miért segít a „több fájl hozzáadása a tar-hoz” |
|--------------|-----------------------------------------------|
| **Naplógyűjtés** | Csomagolja a napi naplókat egyetlen archívumba, mielőtt fel töltené a felhő tárolóba. |
| **Telepítőcsomagok** | Hozzon létre hordozható tar.gz csomagokat Linux szerverekhez egy Windows build folyamatból. |
| **Adatmentés** | Megőrzi a könyvtárhierarchiát és a metaadatokat, miközben alacsony méretű mentést biztosít. |

## Gyakori problémák és megoldások

- **Fájl nem található hiba** – Győződjön meg róla, hogy a `dataDir` a megfelelő útvonalelválasztóval végződik, vagy használja a `Path.Combine`‑t.  
- **Nagy fájlok memória nyomást okoznak** – Használja a `CreateEntry` stream‑alapú túlterhelését (`CreateEntry(string entryName, Stream source)`) a teljes fájlok memóriába betöltésének elkerüléséhez.  
- **A gzip kimenet sérült** – Ellenőrizze, hogy a `TarArchive` el lett-e engedve (egy `using` blokk segítségével) a `SaveGzipped` meghívása előtt.  

## Gyakran feltett kérdések

**Q: Az Aspose.Zip for .NET kompatibilis minden .NET alkalmazással?**  
A: Igen, működik .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, és .NET 5–10 projektekben.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Zip for .NET-hez?**  
A: Látogassa meg a [temporary‑license oldalát](https://purchase.aspose.com/temporary-license/), hogy kérjen próba licencet.

**Q: Vannak fájlméret korlátozások?**  
A: A könyvtár nagy fájlokra van optimalizálva; nincs szigorú méretkorlát a rendelkezésre álló rendszermemórián kívül, és képes 100 GB-nál nagyobb archívumok streamelésére.

**Q: Hol kaphatok támogatást?**  
A: Használja a közösség‑alapú támogatási fórumot [itt](https://forum.aspose.com/c/zip/37), ahol az Aspose mérnökök és más fejlesztők segítenek.

**Q: Próbálhatom ingyenesen az Aspose.Zip for .NET-et?**  
A: Természetesen—töltse le az ingyenes próbaverziót a [Aspose Zip kiadási oldalról](https://releases.aspose.com/zip/net/).

## Összegzés

Most már tudja, hogyan **adjunk hozzá több fájlt a tar-hoz**, hozzunk létre egy tar archívumot, és **tömörítsük a fájlokat tar.gz formátumba** az Aspose.Zip for .NET használatával. Ez a megközelítés eltávolítja a külső függőségeket, teljes irányítást ad az archívum tartalma felett, és nagyon nagy adathalmazokra is skálázható. Fedezze fel a további funkciókat, mint a titkosítás, egyedi bejegyzés attribútumok és a streaming API-k, hogy tovább fejlessze az archiválási munkafolyamatát.

---

**Utolsó frissítés:** 2026-06-19  
**Tesztelt verzió:** Aspose.Zip 24.11 for .NET  
**Szerző:** Aspose

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan tömörítsünk több fájlt tar formátumba az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Fájlok hozzáadása a tar-hoz és tarxz archívum létrehozása az Aspose.Zip segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Hogyan tömörítsünk tar-t és hozzunk létre TarBz2-t az Aspose.Zip for .NET segítségével](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}