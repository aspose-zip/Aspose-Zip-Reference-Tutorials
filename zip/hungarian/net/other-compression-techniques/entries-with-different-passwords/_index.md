---
date: 2025-12-18
description: Ismerje meg, hogyan titkosíthat zip-fájlokat különböző jelszavakkal az
  Aspose.Zip for .NET segítségével. Ez az útmutató bemutatja, hogyan lehet jelszóval
  tömöríteni fájlokat, és C#-ban 7z archívumot létrehozni.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hogyan titkosítsunk ZIP-fájlokat különböző jelszavakkal az Aspose.Zip for .NET-ben
url: /hu/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan titkosítsunk ZIP fájlokat különböző jelszavakkal az Aspose.Zip for .NET-ben

## Bevezetés

Ha **how to encrypt zip** archívumokat kell titkosítania, miközben minden bejegyzésnek saját jelszót ad, jó helyen jár. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan hozhat létre egy 7‑zip archívumot, ahol minden fájl egyedi jelszóval van védve, az Aspose.Zip .NET könyvtár segítségével. A végére megérti, miért fontos a bejegyzésenkénti titkosítás, hogyan állíthatja be, és hogyan ellenőrizheti az eredményt saját projektjeiben.

## Gyors válaszok
- **Mit jelent a “encrypt zip”?** Azt jelenti, hogy jelszó‑alapú védelmet (AES vagy ZipCrypto) alkalmazunk egy ZIP/7z archívum tartalmára.  
- **Lehet minden bejegyzésnek külön jelszava?** Igen – az Aspose.Zip lehetővé teszi, hogy minden fájlhoz külön jelszót rendeljünk.  
- **Mely .NET verziók támogatottak?** Minden modern .NET Framework, .NET Core és .NET 5/6 verzió.  
- **Szükség van licencre a termeléshez?** Kereskedelmi licenc szükséges a termelési használathoz; ingyenes próba elérhető.  
- **Milyen tömörítési formátumot használ a példában?** A minta egy 7z archívumot hoz létre AES‑256 titkosítással.

## Mi az a “how to encrypt zip” az Aspose.Zip használatával?

A ZIP (vagy 7z) fájl titkosítása azt jelenti, hogy a bejegyzéseket úgy védjük, hogy a megfelelő jelszó nélkül ne lehessen őket megnyitni. Az Aspose.Zip for .NET támogatja a klasszikus ZipCrypto‑t és a erősebb AES titkosítást is, és lehetővé teszi, hogy bejegyzésenként adjon meg titkosítási beállításokat, így finomhangolt biztonsági kontrollt biztosít.

## Miért használjunk különböző jelszavakat minden bejegyzéshez?

- **Biztonsági szegmentálás:** Ha egy jelszó kompromittálódik, a többi fájl továbbra is védett marad.  
- **Szabályozási megfelelés:** Egyes iparágak külön hitelesítő adatokat követelnek meg különböző adatkategóriákhoz.  
- **Felhasználó‑specifikus hozzáférés:** Egyetlen archívumot több felhasználónak is kiadhat, ahol mindenki csak azokat a fájlokat tudja feloldani, amelyekhez jogosultsága van.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- **Aspose.Zip for .NET** telepítve – a letöltési és telepítési útmutatóért tekintse meg a hivatalos [documentation](https://reference.aspose.com/zip/net/) oldalt.  
- Egy mappa a gépén, ahol a forrásfájlokat tárolja (a „Document Directory”).  
- Alapvető ismeretek C#‑ban és Visual Studio‑ban (vagy a kedvenc .NET IDE‑jában).

## Névtér importálása

Kezdjük azzal, hogy beimportáljuk azokat a névtereket, amelyek tartalmazzák a szükséges osztályokat.

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

## 1. lépés: Állítsa be a Document Directory‑t

Határozza meg az útvonalat, amely a archiválni kívánt fájlokat tartalmazza.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Hozzon létre bejegyzéseket különböző jelszavakkal

Itt van az útmutató központi része. Megnyitunk egy új 7z fájlt, három `FileInfo` objektumot hozunk létre, és mindegyiket egy saját AES jelszóval ellátott bejegyzésként adjuk hozzá.

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

### Hogyan működik ez

- `SevenZipArchive` a 7‑z archívum tárolója.  
- `CreateEntry` a bejegyzés nevét, a forrásfájlt, egy felülírási jelzőt és egy `SevenZipEntrySettings` objektumot vár.  
- A `SevenZipEntrySettings`‑ben két beállítási objektumot adunk meg: egyet a tömörítéshez (`SevenZipStoreCompressionSettings`) és egyet a titkosításhoz (`SevenZipAESEncryptionSettings`).  
- Minden hívás **különböző jelszót** ad meg (`"test1"`, `"test2"`, `"test3"`), ezzel bejegyzésenkénti védelmet biztosítva.

## 3. lépés: Ellenőrzés

Miután az archívum mentésre került, kiírhat egy egyszerű megerősítő üzenetet.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Futtassa a programot, majd próbálja meg megnyitni az `archive.7z` fájlt egy, például a 7‑Zip‑et használó eszközzel. Minden bejegyzéshez jelszót kér, ezzel megerősítve, hogy a jelszavak valóban különböznek.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Helytelen jelszó hiba** | A jelszó karakterlánc felesleges szóközöket vagy láthatatlan karaktereket tartalmaz. | Vágja le a jelszó karakterláncokat (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Az archívum nem nyílik meg régebbi eszközökben** | Néhány régi ZIP eszköz nem támogatja a 7z által használt AES‑256 titkosítást. | Használjon modern kibontót (7‑Zip 19.00+). |
| **A fájl nem lett hozzáadva az archívumhoz** | A forrásfájl útvonala hibás vagy a fájl nem létezik. | Ellenőrizze a `dataDir` és a fájlneveket, vagy használja a `Path.Combine(dataDir, "data1.bin")`-t. |

## Gyakran feltett kérdések

### Q1: Az Aspose.Zip for .NET kompatibilis-e az összes .NET verzióval?

**A1:** Igen, az Aspose.Zip for .NET úgy lett tervezve, hogy zökkenőmentesen integrálódjon az összes .NET keretrendszer verzióval.

### Q2: Használhatom az Aspose.Zip for .NET-et kereskedelmi projektjeimben?

**A2:** Természetesen! Az Aspose.Zip for .NET kereskedelmi licenceket kínál, és a vásárlás módjáról további információkat találhat [itt](https://purchase.aspose.com/buy).

### Q3: Elérhető ingyenes próba?

**A3:** Igen, az Aspose.Zip for .NET funkcióit ingyenes próba verzióval is kipróbálhatja. Kezdje el [itt](https://releases.aspose.com/).

### Q4: Hogyan kaphatok támogatást az Aspose.Zip for .NET-hez?

**A4:** Bármilyen kérdés vagy segítség esetén látogassa meg az [Aspose.Zip Fórumot](https://forum.aspose.com/c/zip/37).

### Q5: Használhatom az Aspose.Zip for .NET-et állandó licenc nélkül?

**A5:** Igen, ideiglenes licencet szerezhet rövid távú igényeihez. További részletek [itt](https://purchase.aspose.com/temporary-license/).

## Összegzés

Most megtanulta, hogyan **encrypt zip** archívumokat hozhat létre bejegyzésenkénti jelszavakkal az Aspose.Zip for .NET használatával. Ez a technika rugalmasságot biztosít, hogy minden fájlt egyenként védjen, szigorúbb biztonsági követelményeknek megfeleljen, és egyszerűsítse a felhasználó‑specifikus terjesztést. Nyugodtan kísérletezzen más tömörítési beállításokkal, nagyobb fájlkészletekkel, vagy integrálja ezt a logikát egy webszolgáltatásba, amely futás közben generál biztonságos archívumokat.

---

**Utolsó frissítés:** 2025-12-18  
**Tesztelve:** Aspose.Zip for .NET 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}