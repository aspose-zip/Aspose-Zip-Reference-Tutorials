---
date: 2025-12-21
description: Tanulja meg, hogyan hozhat létre jelszóval védett zip fájlokat .NET-ben,
  titkosíthat mappákat, és módosíthatja a zip jelszót az Aspose.Zip segítségével.
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

Ebben az útmutatóban **jelszóval védett zip** archívumokat hozol létre teljes könyvtárakhoz az Aspose.Zip .NET könyvtár használatával. Akár **mappát kell titkosítanod**, biztonságos mentési fájlokat szeretnél, vagy egyszerűen csak korlátozni akarod az érzékeny adatok hozzáférését, ez a lépésről‑lépésre útmutató pontosan megmutatja, hogyan teheted ezt tiszta C# kóddal.

## Gyors válaszok
- **Melyik könyvtár ajánlott?** Aspose.Zip for .NET  
- **Titkosíthatok egy teljes mappát?** Igen – csak mutasd a API-t arra a mappára, amelyet zip‑elni szeretnél.  
- **Támogatott a zip jelszó módosítása?** Teljesen, használd a `TraditionalEncryptionSettings`‑t.  
- **Szükség van licencre a termeléshez?** Érvényes Aspose.Zip licenc szükséges kereskedelmi használathoz.  
- **Működik .NET Core/5/6‑tal?** Igen, az API teljesen kompatibilis a modern .NET futtatókörnyezetekkel.  

## Mi az a „jelszóval védett zip létrehozása”?
A jelszóval védett zip létrehozása azt jelenti, hogy fájlokat vagy könyvtárakat tömörítesz egy ZIP archívumba, miközben titkosítást alkalmazol, így az archívum csak a helyes jelszó megadásával nyitható meg. Ez megvédi a tartalmat az illetéktelen hozzáféréstől.

## Miért használjuk az Aspose.Zip-et a könyvtár jelszóval való védelméhez .NET‑ben?
Az Aspose.Zip egy egyszerű, nagy teljesítményű API‑t kínál, amely támogatja a **c# zip password protection**‑t, a hagyományos ZipCrypto titkosítást és az AES titkosítást. Nagy könyvtárakat is hatékonyan kezel, és zökkenőmentesen integrálható bármely .NET projektbe.

## Előfeltételek
- Alapvető C# programozási ismeretek.  
- Visual Studio (bármely friss kiadás).  
- Aspose.Zip for .NET könyvtár – töltsd le **[itt](https://releases.aspose.com/zip/net/)**.  
- Egy mappa a lemezen, amelyet jelszóval szeretnél védeni.

## Névterek importálása
Add hozzá a szükséges névtereket a C# fájlodhoz, hogy a fordító tudja, hol találja az Aspose.Zip osztályait.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 1. lépés: Az erőforrás könyvtár elérési útjának beállítása
Határozd meg azt az útvonalat, amely a zip‑elni és védeni kívánt könyvtárra mutat.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: A könyvtár jelszóval való védelme
Használd a `TraditionalEncryptionSettings`‑t a jelszó megadásához, és hozd létre a titkosított archívumot. Ez a **c# zip password protection** központi része.

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
- **A kimeneti fájl létrehozása:** `File.Open(..., FileMode.Create)` megnyitja (vagy létrehozza) a ZIP fájlt, amely a titkosított adatot tartalmazza.  
- **A forrásmappa kiválasztása:** `new DirectoryInfo(".\\CanterburyCorpus")` megmondja az Aspose.Zip‑nek, melyik könyvtárat kell tömöríteni.  
- **A jelszó alkalmazása:** `new TraditionalEncryptionSettings("p@s$")` beállítja a jelszót, amely a archívumot védi.  
- **Bejegyzések hozzáadása és mentés:** `archive.CreateEntries(corpus)` minden fájlt hozzáad a mappához, a `archive.Save(zipFile)` pedig a titkosított ZIP‑et lemezre írja.

## Hogyan változtatható meg a zip jelszó később?
Ha **meg kell változtatni a zip jelszót**, egyszerűen hozd létre újra az archívumot egy új `TraditionalEncryptionSettings` példányzal, amely a új jelszót tartalmazza, majd mentsd el újra.

## Gyakori problémák és tippek
- **Nagy mappák:** Az Aspose.Zip adatfolyamot használ, így a memóriahasználat alacsony marad még hatalmas könyvtárak esetén is.  
- **Jelszó komplexitás:** Használj erős jelszót (betűk, számok, szimbólumok keveréke) a biztonság növeléséhez.  
- **Licenc hibák:** Győződj meg róla, hogy érvényes licencfájlt alkalmaztál; ellenkező esetben a könyvtár értékelési módban fut korlátozásokkal.

## Gyakran feltett kérdések

### Alkalmas-e az Aspose.Zip for .NET nagy könyvtárakhoz?
Igen, az Aspose.Zip for .NET úgy van tervezve, hogy nagy könyvtárakat hatékonyan kezeljen, optimális teljesítményt biztosítva.

### Megváltoztatható-e a már védett könyvtár jelszava?
Igen, a jelszót a kódban a `TraditionalEncryptionSettings` módosításával tudod megváltoztatni.

### Vannak-e licencelési követelmények az Aspose.Zip for .NET használatához?
Igen, érvényes licenc szükséges az Aspose.Zip for .NET használatához egy termelési környezetben. Licencet **[itt](https://purchase.aspose.com/buy)** szerezhetsz be.

### Elérhető-e ingyenes próba az Aspose.Zip for .NET‑hez?
Igen, ingyenes próbaverziót **[itt](https://releases.aspose.com/)** tölthetsz le.

### Hol találok további támogatást az Aspose.Zip for .NET‑hez?
Látogasd meg a **[Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37)** bármilyen támogatás vagy kérdés esetén.

---

**Utoljára frissítve:** 2025-12-21  
**Tesztelve:** Aspose.Zip for .NET (legújabb kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}