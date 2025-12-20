---
date: 2025-12-20
description: Ismerje meg, hogyan hozhat létre jelszóval védett zip archívumokat .NET-ben
  az Aspose.Zip segítségével. Ez a lépésről‑lépésre útmutató bemutatja, hogyan tömöríthet
  fájlokat jelszóval, hogyan állíthat be zip bejegyzés jelszót, és hogyan használhat
  AES titkosítást.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jelszóval védett ZIP-fájlok létrehozása .NET-ben az Aspose.Zip segítségével
url: /hu/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jelszóval védett ZIP fájlok létrehozása .NET-ben az Aspose.Zip segítségével

## Bevezetés

Ha **jelszóval védett zip** archívumokat kell létrehoznia egy .NET alkalmazásban, az Aspose.Zip egyszerű megoldást kínál. Egyedi jelszót rendelhet minden egyes bejegyzéshez, így a bizalmas dokumentumok védve maradnak, miközben továbbra is élvezheti a ZIP tömörítés kényelmét. Ebben az útmutatóban megtanulja, hogyan tömörítsen fájlokat egyedi jelszavakkal, hogyan válasszon különböző titkosítási módszereket, és hogyan állítson be zip bejegyzés jelszót – mindezt világos, termelésre kész kóddal.

## Gyors válaszok
- **Melyik könyvtárat használjam?** Aspose.Zip for .NET.
- **Lehet-e külön jelszót adni fájlonként?** Igen, minden bejegyzésnek saját jelszava lehet.
- **Mely titkosítási algoritmusok támogatottak?** Hagyományos ZipCrypto, AES‑128 és AES‑256.
- **Szükség van licencre a fejlesztéshez?** Ingyenes próba verzió teszteléshez; kereskedelmi licenc a termeléshez kötelező.
- **Kompatibilis-e a .NET 6+-tal?** Teljesen – az API a .NET Standard 2.0 és újabb verziókat célozza.

## Mi az a „jelszóval védett zip”?
A jelszóval védett zip létrehozása azt jelenti, hogy titkosítást alkalmazunk egy vagy több bejegyzésre a ZIP archívumban, így a tartalmat csak a helyes jelszó megadása után lehet megnyitni. Ideális bizalmas fájlok továbbításához, biztonsági mentések tárolásához vagy adatvédelmi előírások betartásához.

## Miért használjuk az Aspose.Zip-et jelszóval védett archívumokhoz?
- **Finomhangolt vezérlés** – külön jelszó beállítása fájlonként.
- **Több titkosítási lehetőség** – a régi ZipCrypto-tól a erős AES‑128/256-ig.
- **Külső függőségek nélkül** – tiszta .NET könyvtár, könnyű integrálás.
- **Átfogó dokumentáció** – tartalmaz egy **aspose zip tutorial**-t a mélyebb forgatókönyvekhez.

## Előfeltételek

Mielőtt elkezdené a gyakorlati példát, győződjön meg róla, hogy rendelkezik a következőkkel:

- Aspose.Zip for .NET: Győződjön meg róla, hogy az Aspose.Zip könyvtár telepítve van a .NET projektjében. A szükséges dokumentációt megtalálja [itt](https://reference.aspose.com/zip/net/).

- Letöltés: Ha még nem tette meg, töltse le az Aspose.Zip for .NET könyvtárat a [következő hivatkozásról](https://releases.aspose.com/zip/net/).

- Dokumentum könyvtár: Készítsen egy könyvtárat, amely a tömöríteni kívánt fájlokat tartalmazza.

## Névterek importálása

A .NET projektjében importálja a szükséges névtereket:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 1. lépés: Az erőforrás könyvtár útvonalának beállítása

Határozza meg az erőforrás könyvtár útvonalát, ahol a forrásfájlok találhatók.

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Fájlok tömörítése egyedi jelszavakkal

Most tömörítsük a fájlokat egyedi jelszavakkal. Három mintafájlt (`alice29.txt`, `asyoulik.txt`, és `fields.c`) használunk, mindegyikhez külön jelszó tartozik. Ez bemutatja, hogyan **tömörítsen fájlokat jelszóval**, valamint hogyan **állítson be zip bejegyzés jelszót** különböző titkosítási sémákkal, beleértve egy **zip archívumot aes-szel**.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Hogyan működik
- **TraditionalEncryptionSettings** a régebbi ZipCrypto algoritmust használja (kompatibilis a legtöbb ZIP segédeszközzel).
- **AesEcryptionSettings** lehetővé teszi az AES‑128 vagy AES‑256 kiválasztását a magasabb biztonság érdekében.
- Minden `CreateEntry` hívás egy `ArchiveEntrySettings` objektumot kap, ahol megadjuk a tömörítési módot és a titkosítási beállításokat, ezáltal **jelszóval védett zip archívum** bejegyzéseket hozunk létre.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| “Invalid password” hiba a ZIP megnyitásakor | A kódban használt jelszó és a kicsomagolóban megadott jelszó nem egyezik | Ellenőrizze a `TraditionalEncryptionSettings` vagy `AesEcryptionSettings`‑nek átadott pontos karakterláncot. |
| Régebbi kicsomagoló eszközök nem tudják megnyitni az AES‑titkosított bejegyzéseket | Nem minden ZIP segédeszköz támogatja az AES titkosítást | Használja a hagyományos ZipCrypto módszert a legnagyobb kompatibilitás érdekében, vagy javasolja a felhasználóknak a modern eszközök (pl. 7‑Zip) használatát. |
| Nagy fájlok `OutOfMemoryException`‑t okoznak | A fájlok teljes betöltése a memóriába a tömörítés előtt | Streamelje a fájlt közvetlenül `FileStream`‑el, anélkül, hogy a teljes fájlt egy `FileInfo` objektumba töltené. |

## Gyakran feltett kérdések (FAQ)

### Használhatok különböző titkosítási módszereket fájlonként?
Igen, az Aspose.Zip for .NET lehetővé teszi, hogy a tömörítés során minden fájlhoz más titkosítási módszert alkalmazzon.

### Elérhető-e próba verzió?
Igen, az Aspose.Zip for .NET ingyenes próbaverzióját [itt](https://releases.aspose.com/) érheti el.

### Hogyan kaphatok támogatást, ha problémáim adódnak?
Látogasson el az [Aspose.Zip fórumra](https://forum.aspose.com/c/zip/37) a közösség és az Aspose támogatásának segítségéért.

### Hol találok részletes dokumentációt az Aspose.Zip for .NET-hez?
A dokumentáció elérhető [itt](https://reference.aspose.com/zip/net/).

### Vásárolhatok ideiglenes licencet teszteléshez?
Igen, ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

## További gyors FAQ

**K: Támogatja a könyvtár a .NET Core és a .NET 5/6 verziókat?**  
V: Igen, az Aspose.Zip .NET Standard-ra épül, így kompatibilis a .NET Framework, .NET Core és a .NET 5/6 verziókkal.

**K: Hozzáadhatok megjegyzést minden ZIP bejegyzéshez?**  
V: Bár az Aspose.Zip elsősorban a tömörítésre és titkosításra fókuszál, metaadatokat tárolhat egy külön manifest fájlban az archívumban.

**K: Lehetséges-e az egész archívum titkosítása egyetlen jelszóval?**  
V: Beállíthat jelszót minden bejegyzésre külön-külön (ahogy a példában látható), vagy ugyanazt a jelszót alkalmazhatja az összes bejegyzésre egy egyszerűbb “zip archívum aes-szel” megközelítéshez.

## Összegzés

Most már elsajátította, hogyan **hozzon létre jelszóval védett zip** fájlokat .NET-ben az Aspose.Zip segítségével. Egyedi jelszavak és a megfelelő titkosítási módszer kiválasztásával adatát védheti anélkül, hogy feláldozná a ZIP tömörítés kényelmét. Fedezze fel az Aspose.Zip további funkcióit, például a nagy fájlok streamelését, egyedi metaadatok hozzáadását és a felhő tárolókkal való integrációt a még hatékonyabb megoldásokért.

---

**Utolsó frissítés:** 2025-12-20  
**Tesztelt verzió:** Aspose.Zip for .NET 23.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}