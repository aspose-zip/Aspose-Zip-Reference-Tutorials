---
date: 2026-02-28
description: Ismerje meg, hogyan tömöríthet fájlokat jelszóval és titkosíthat ZIP-archívumokat
  az Aspose.Zip for .NET használatával, beleértve a 7z jelszóvédelmet és a fájlonkénti
  ZIP-jelszót C#-ban.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan tömörítsünk fájlokat jelszóval, és titkosítsuk a ZIP-bejegyzéseket különböző
  jelszavakkal az Aspose.Zip for .NET használatával
url: /hu/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan tömörítsünk fájlokat jelszóval, és titkosítsuk a ZIP-bejegyzéseket különböző jelszavakkal az Aspose.Zip for .NET használatával

## Bevezetés

Ha **fájlok jelszóval történő tömörítésére** van szüksége, és minden bejegyzésnek saját jelszót szeretne adni, jó helyen jár. Ebben az útmutatóban lépésről‑lépésre bemutatjuk, hogyan hozhat létre egy 7‑zip archívumot, ahol minden fájl egyedi jelszóval van védve, az Aspose.Zip .NET könyvtár segítségével. A végére megérti, miért fontos a bejegyzésenkénti titkosítás, hogyan állíthatja be, és hogyan ellenőrizheti az eredményt saját projektjeiben.

## Gyors válaszok
- **Mit jelent az „encrypt zip”?** Azt, hogy jelszó‑alapú védelmet (AES vagy ZipCrypto) alkalmazunk egy ZIP/7z archívum tartalmára.  
- **Lehet-e minden bejegyzésnek más jelszó?** Igen – az Aspose.Zip lehetővé teszi, hogy fájlonként különböző jelszavakat rendeljünk.  
- **Mely .NET verziók támogatottak?** Minden modern .NET Framework, .NET Core és .NET 5/6 verzió.  
- **Szükség van-e licencre a termeléshez?** Igen, a kereskedelmi felhasználáshoz licenc szükséges; ingyenes próba elérhető.  
- **Milyen tömörítési formátumot használ a példa?** A minta 7z archívumot hoz létre AES‑256 titkosítással.

## Hogyan tömörítsünk fájlokat jelszóval az Aspose.Zip for .NET segítségével
Ebben a részben közvetlenül a fő kérdésre válaszolunk, és felkészítjük a további lépés‑ről‑lépésre útmutatót.

## Mi az a „how to encrypt zip” az Aspose.Zip‑el?
Egy ZIP (vagy 7z) fájl titkosítása azt jelenti, hogy a benne lévő bejegyzéseket úgy védjük, hogy a megfelelő jelszó nélkül ne lehessen őket megnyitni. Az Aspose.Zip for .NET támogatja a klasszikus ZipCrypto‑t és a erősebb AES titkosítást is, és lehetővé teszi a titkosítási beállítások megadását bejegyzésenként, így finomhangolt biztonságot biztosít.

## Miért használjunk különböző jelszavakat minden bejegyzéshez?
- **Biztonsági szegmentáció:** Ha egy jelszó kompromittálódik, a többi fájl továbbra is védett marad.  
- **Szabályozási megfelelés:** Egyes iparágak külön hitelesítő adatokat követelnek meg különböző adatkategóriákhoz.  
- **Felhasználó‑specifikus hozzáférés:** Egyetlen archívumot több felhasználónak is kiadhat, akik csak a számukra engedélyezett fájlokat nyithatják meg.

## Előfeltételek

Mielőtt belevágna, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve – lásd a hivatalos [documentation](https://reference.aspose.com/zip/net/) a letöltéshez és a telepítési útmutatóhoz.  
- Egy mappával a gépén, ahol a forrásfájlokat tárolja (a „Document Directory”).  
- Alapvető C# és Visual Studio (vagy a kedvenc .NET IDE‑je) ismeretekkel.

## Namespace‑ek importálása

Kezdjük azzal, hogy betöltjük azokat a namespace‑eket, amelyek a szükséges osztályokat tartalmazzák.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: A Document Directory beállítása

Határozza meg azt az elérési utat, amely a tömöríteni kívánt fájlokat tartalmazza.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Bejegyzések létrehozása különböző jelszavakkal

Ez a tutorial központi része. Megnyitunk egy új 7z fájlt, három `FileInfo` objektumot hozunk létre, és mindegyiket saját AES jelszóval adjuk hozzá bejegyzésként.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Hogyan működik

- A `SevenZipArchive` a 7‑z archívum tárolója.  
- A `CreateEntry` megkapja a bejegyzés nevét, a forrásfájlt, egy felülírási jelzőt, valamint egy `SevenZipEntrySettings` objektumot.  
- A `SevenZipEntrySettings`‑ben két beállítási objektumot adunk meg: egyet a tömörítéshez (`SevenZipStoreCompressionSettings`) és egyet a titkosításhoz (`SevenZipAESEncryptionSettings`).  
- Minden hívás **más jelszót** ad meg (`"test1"`, `"test2"`, `"test3"`), így elérhető a bejegyzésenkénti védelem.

## 3. lépés: Ellenőrzés

Az archívum mentése után egyszerű megerősítő üzenetet írhatunk ki.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Futtassa a programot, majd próbálja meg megnyitni az `archive.7z`‑t egy, például a 7‑Zip‑el. Minden bejegyzéshez külön jelszót kér, ami igazolja, hogy a jelszavak valóban eltérnek.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Helytelen jelszó hiba** | A jelszó karakterlánc felesleges szóközöket vagy láthatatlan karaktereket tartalmaz. | Trimmelje a jelszókat (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Az archívum nem nyílik meg régebbi eszközökben** | Egyes régi ZIP eszközök nem támogatják a 7z‑ben használt AES‑256 titkosítást. | Használjon modern kicsomagolót (7‑Zip 19.00+). |
| **Fájl nem került az archívumba** | A forrásfájl elérési útja hibás vagy a fájl nem létezik. | Ellenőrizze a `dataDir`‑t és a fájlneveket, vagy használja a `Path.Combine(dataDir, "data1.bin")`‑t. |

## Gyakran ismételt kérdések

### Q1: Az Aspose.Zip for .NET kompatibilis-e minden .NET verzióval?

A1: Igen, az Aspose.Zip for .NET úgy lett tervezve, hogy zökkenőmentesen integrálódjon minden .NET keretrendszer verzióval.

### Q2: Használhatom az Aspose.Zip for .NET‑et kereskedelmi projektjeimben?

A2: Természetesen! Az Aspose.Zip for .NET kereskedelmi licenceket kínál, a vásárlási információkért tekintse meg [itt](https://purchase.aspose.com/buy).

### Q3: Van ingyenes próba verzió?

A3: Igen, az Aspose.Zip for .NET funkcióit ingyenes próba verzióval is kipróbálhatja. Kezdje el [itt](https://releases.aspose.com/).

### Q4: Hogyan kaphatok támogatást az Aspose.Zip for .NET‑hez?

A4: Bármilyen kérdés vagy segítségkérés esetén látogasson el az [Aspose.Zip Fórumra](https://forum.aspose.com/c/zip/37).

### Q5: Használhatom az Aspose.Zip for .NET‑et állandó licenc nélkül?

A5: Igen, ideiglenes licencet is kérhet rövid távú igényeihez. További részletek [itt](https://purchase.aspose.com/temporary-license/).

## Összegzés

Most már tudja, **hogyan tömörítsen fájlokat jelszóval**, és hogyan titkosítsa a ZIP archívumokat bejegyzésenként külön‑külön jelszavakkal az Aspose.Zip for .NET‑el. Ez a technika rugalmasságot biztosít az egyes fájlok egyedi védelméhez, szigorúbb biztonsági követelményeknek felel meg, és egyszerűsíti a felhasználó‑specifikus terjesztést. Nyugodtan kísérletezzen más tömörítési beállításokkal, nagyobb fájlkészletekkel, vagy integrálja ezt a logikát egy webszolgáltatásba, amely valós időben generál biztonságos archívumokat.

---

**Utoljára frissítve:** 2026-02-28  
**Tesztelve:** Aspose.Zip for .NET 24.12 (a cikk írásakor elérhető legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}