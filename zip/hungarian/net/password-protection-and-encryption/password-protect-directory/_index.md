---
date: 2026-03-08
description: Ismerje meg, hogyan hozhat létre jelszóval védett zip fájlokat, jelszóval
  védheti a zip mappát, és módosíthatja a zip jelszót az Aspose.Zip for .NET segítségével.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jelszóval védett zip létrehozása .NET könyvtárakhoz – Aspose.Zip útmutató
url: /hu/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jelszóval védett zip létrehozása .NET könyvtárakhoz – Aspose.Zip útmutató

Ebben az útmutatóban **jelszóval védett zip** archívumokat hozol létre teljes könyvtárakhoz az Aspose.Zip .NET könyvtár segítségével. Akár **mappát szeretnél titkosítani**, biztonságos mentési fájlokat készíteni, vagy egyszerűen korlátozni szeretnéd az érzékeny adatok hozzáférését, ez a lépésről‑lépésre tutorial pontosan megmutatja, hogyan teheted meg tiszta C# kóddal.

## Gyors válaszok
- **Melyik könyvtár ajánlott?** Aspose.Zip for .NET  
- **Titkosíthatok egy teljes mappát?** Igen – csak mutasd az API-t arra a mappára, amelyet zip‑elni szeretnél.  
- **Támogatott a zip jelszó megváltoztatása?** Teljesen, használd a `TraditionalEncryptionSettings`-t.  
- **Szükség van licencre a termeléshez?** Érvényes Aspose.Zip licenc szükséges kereskedelmi használathoz.  
- **Működik .NET Core/5/6-tal?** Igen, az API teljesen kompatibilis a modern .NET futtatókörnyezetekkel.  

## Mi az a „jelszóval védett zip létrehozása”?
A jelszóval védett zip létrehozása azt jelenti, hogy fájlokat vagy könyvtárakat tömörítesz egy ZIP archívumba, miközben titkosítást alkalmazol, így az archívum csak a helyes jelszóval nyitható meg. Ez megvédi a tartalmat az illetéktelen hozzáféréstől.

## Hogyan hozzunk létre jelszóval védett zip-et egy könyvtárhoz
Az alábbiakban egy teljes, ember által olvasható útmutatót találsz, amely mindent lefed a projekt beállításától a jelszó későbbi megváltoztatásáig.

## Miért használjuk az Aspose.Zip-et a könyvtár .NET jelszóval való védelméhez?
Az Aspose.Zip egy egyszerű, nagy teljesítményű API-t kínál, amely támogatja a **c# zip jelszóvédelmet**, a hagyományos ZipCrypto titkosítást és az AES titkosítást. Nagy könyvtárakat hatékonyan kezel, és zökkenőmentesen integrálódik bármely .NET projekttel.

## Gyakori felhasználási esetek
- **Biztonsági mentés védelme:** Tömöríts egy napi mentési mappát, és zárd le erős jelszóval.  
- **Biztonságos fájlcsere:** Küldj egy zip mappajelszót az ügyfélnek anélkül, hogy a tartalmat felfednéd.  
- **Szabályozási megfelelés:** Tárold a személyes azonosításra alkalmas információkat (PII) egy titkosított zip archívumban, hogy megfelelj az adatvédelmi előírásoknak.  

## Előfeltételek
- Alapvető C# programozási ismeretek.  
- Visual Studio (bármely friss kiadás).  
- Aspose.Zip for .NET könyvtár – töltsd le **[itt](https://releases.aspose.com/zip/net/)**.  
- Egy mappa a lemezen, amelyet jelszóval szeretnél védeni.

## Névterek importálása
Add the required namespaces to your C# file so the compiler knows where to find the Aspose.Zip classes.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 1. lépés: Állítsd be az erőforrás könyvtár elérési útját
Határozd meg az elérési utat, amely arra a könyvtárra mutat, amelyet zip‑elni és védeni szeretnél.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Jelszóval védd a könyvtárat
Használd a `TraditionalEncryptionSettings`-t a jelszó megadásához és a titkosított archívum létrehozásához. Ez a **c# zip jelszóvédelem** központi eleme.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## 3. lépés: A kód magyarázata
- **Kimeneti fájl létrehozása:** `File.Open(..., FileMode.Create)` megnyitja (vagy létrehozza) a ZIP fájlt, amely a titkosított adatot tárolja.  
- **Forrásmappa kiválasztása:** `new DirectoryInfo(".\\CanterburyCorpus")` megmondja az Aspose.Zip-nek, melyik könyvtárat tömörítse.  
- **Jelszó alkalmazása:** `new TraditionalEncryptionSettings("p@s$")` beállítja a jelszót, amely a archívumot védi.  
- **Bejegyzések hozzáadása és mentés:** `archive.CreateEntries(corpus)` hozzáadja a mappa minden fájlját, és `archive.Save(zipFile)` a titkosított ZIP-et a lemezre írja.  

## Hogyan változtassuk meg a zip jelszót később?
Ha **meg kell változtatni a zip jelszót**, egyszerűen hozd létre újra az archívumot egy új `TraditionalEncryptionSettings` példánnyal, amely az új jelszót tartalmazza, majd mentsd el újra. Ez a megközelítés akkor is működik, ha egy meglévő mappából **titkosított zip archívumot** szeretnél létrehozni más jelszóval.

## Tippek egy erős zip mappa jelszóhoz
- Használj vegyesen nagy- és kisbetűket, számokat és szimbólumokat.  
- Célj legalább 12 karaktert; a hosszabb jelszavak exponenciálisan nehezebben feltörhetők.  
- Kerüld a gyakori szavakat vagy mintákat; fontold meg egy jelszómondat használatát.

## Gyakori problémák és tippek
- **Nagy mappák:** Az Aspose.Zip adatfolyamot használ, így a memóriahasználat alacsony marad még hatalmas könyvtárak esetén is.  
- **Jelszó komplexitás:** Használj erős jelszót (betűk, számok, szimbólumok keveréke) a biztonság növeléséhez.  
- **Licenc hibák:** Győződj meg róla, hogy érvényes licencfájlt alkalmaztál; ellenkező esetben a könyvtár értékelő módban fut korlátozásokkal.  
- **A zip mappa jelszó nem ismerhető fel:** Ellenőrizd, hogy a megnyitáskor ugyanazt a titkosítási módszert (`TraditionalEncryptionSettings`) használod-e.

## Gyakran ismételt kérdések

### Az Aspose.Zip for .NET alkalmas nagy könyvtárakra?
Igen, az Aspose.Zip for .NET úgy van tervezve, hogy hatékonyan kezelje a nagy könyvtárakat, optimális teljesítményt nyújtva.

### Megváltoztathatom egy már védett könyvtár jelszavát?
Igen, a jelszót módosíthatod a kódban a `TraditionalEncryptionSettings` megfelelő beállításával.

### Vannak licencelési követelmények az Aspose.Zip for .NET használatához?
Igen, érvényes licenc szükséges az Aspose.Zip for .NET termelési környezetben való használatához. Licencet **[itt](https://purchase.aspose.com/buy)** szerezhetsz.

### Van ingyenes próba az Aspose.Zip for .NET-hez?
Igen, ingyenes próbát **[itt](https://releases.aspose.com/)** érhetsz el.

### Hol találok további támogatást az Aspose.Zip for .NET-hez?
Látogasd meg a **[Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37)** bármilyen támogatás vagy kérdés esetén.

## Gyors GYIK (AI‑barát)

**K: Hogyan titkosítok egy mappát zip‑el az Aspose.Zip segítségével?**  
A: Használd a `TraditionalEncryptionSettings`-t az `Archive` objektum létrehozásakor, majd hívd meg a `CreateEntries`-t a célmappán.

**K: Beállíthatok zip mappa jelszót az archívum létrehozása után?**  
A: Nem, a jelszót a létrehozáskor kell megadni; a módosításhoz hozd létre újra az archívumot új jelszóval.

**K: Támogatja az Aspose.Zip az AES titkosítást a nagyobb biztonság érdekében?**  
A: Igen, átválthatsz `AesEncryptionSettings`-re AES‑256 titkosításhoz a hagyományos ZipCrypto helyett.

**K: Kompatibilis a könyvtár a .NET 6-tal és .NET 7-tel?**  
A: Teljesen – a jelenlegi kiadás működik minden modern .NET futtatókörnyezettel.

**K: Mi történik, ha jelszóval védett zip‑et próbálok megnyitni jelszó nélkül?**  
A: Az Aspose.Zip `PasswordRequiredException`-t dob, amely a helyes jelszó megadására kér.

**Utolsó frissítés:** 2026-03-08  
**Tesztelve:** Aspose.Zip for .NET (legújabb kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}