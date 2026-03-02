---
date: 2026-03-02
description: Tanulja meg, hogyan hozhat létre jelszóval védett zip archívumot, és
  hogyan tömöríthet fájlokat jelszóval .NET‑ben az Aspose.Zip segítségével. Kövesse
  lépésről‑lépésre útmutatónkat.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jelszóval védett ZIP archívum létrehozása .NET-ben az Aspose.Zip segítségével
url: /hu/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jelszóval védett ZIP archívum létrehozása .NET-ben az Aspose.Zip segítségével

## Bevezetés

Amikor érzékeny adatokat kell megosztani, a **jelszóval védett zip archívum** az egyik legegyszerűbb, mégis leghatékonyabb módja az információk biztonságban tartásának. .NET alkalmazásokban az Aspose.Zip megkönnyíti a **fájlok jelszóval történő tömörítését**, minden fájlhoz saját titkosítási kulcsot biztosítva. Ebben az útmutatóban pontosan megmutatjuk, hogyan hozhatsz létre ilyen archívumot, miért fontos, és hol alkalmazhatod a valós projektekben.

## Gyors válaszok
- **Melyik könyvtárat használjam?** Aspose.Zip for .NET beépített támogatást nyújt fájlonkénti jelszavakhoz és több titkosítási módszerhez.  
- **Hány sor kódra van szükség?** Körülbelül 30 sor, beleértve a beállítást és az archívum mentését.  
- **Lehet, hogy minden fájlnak más jelszava legyen?** Igen – minden bejegyzéshez egyedi jelszót rendelhetsz.  
- **Milyen titkosítási módszerek érhetők el?** Hagyományos ZipCrypto, AES‑128 és AES‑256.  
- **Szükség van licencre a termeléshez?** A termelési használathoz kereskedelmi licenc szükséges; ingyenes próba verzió is elérhető.

## Mi az a jelszóval védett zip archívum?
A jelszóval védett zip archívum egy tömörített fájl (ZIP), amelynek tartalmának kibontásához jelszó szükséges. A jelszó védheti az egész archívumot vagy az egyes bejegyzéseket, és a modern algoritmusok, például az AES‑128/256 erős titkosítást biztosítanak.

## Miért tömörítsünk fájlokat jelszóval az Aspose.Zip használatával?
- **Részletes biztonság** – minden fájlhoz külön jelszó rendelhető, ami ideális több‑bérlős (multi‑tenant) környezetekben.  
- **Több titkosítási szabvány** – választhatsz a régi ZipCrypto és a erős AES között.  
- **Nincs külső eszköz** – minden programozottan, a .NET kódbázisodban kezelhető.  
- **Teljesítmény** – gyors tömörítés a Deflate‑al, miközben az archívum mérete kicsi marad.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- **Aspose.Zip for .NET** – telepítsd a könyvtárat a projektedbe. Részletes dokumentáció [itt](https://reference.aspose.com/zip/net/).  
- **Töltsd le a legújabb csomagot**, ha még nem tetted meg, a [következő hivatkozásról](https://releases.aspose.com/zip/net/).  
- Egy mappával, amely a tömöríteni kívánt fájlokat tartalmazza.

## Névterek importálása

Add hozzá a szükséges névtereket a C# fájlod tetejéhez:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 1. lépés: Állítsa be az erőforrás könyvtár útvonalát

Iranyítsd a kódot arra a mappára, amely a forrásfájlokat tartalmazza:

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: Fájlok tömörítése egyedi jelszavakkal

Most létrehozunk egy **jelszóval védett zip archívumot**, ahol minden fájl saját jelszót és titkosítási módszert használ. A példában három mintafájl szerepel (`alice29.txt`, `asyoulik.txt`, és `fields.c`) különböző jelszavakkal.

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
- **CreateEntry** egy fájlt ad az archívumhoz.  
- A negyedik argumentum (`ArchiveEntrySettings`) lehetővé teszi a tömörítés (`DeflateCompressionSettings`) és a titkosítás (`TraditionalEncryptionSettings` vagy `AesEcryptionSettings`) megadását.  
- Ha minden bejegyzéshez más jelszókarakterláncot adsz meg, akkor egy **jelszóval védett zip archívumot** kapsz, ahol minden fájlt csak a saját kulcsával lehet feloldani.

## Gyakori problémák és hibaelhárítás

| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| Kicsomagolás sikertelen a “Wrong password” hibaüzenettel | Jelszóeltérés vagy helytelen titkosítási módszer | Ellenőrizd a pontos jelszókarakterláncot, és győződj meg róla, hogy ugyanazt az `EncryptionMethod`-ot használtad a kicsomagoláskor. |
| Az archívum mérete nagyobb a vártnál | AES‑256 használata kis szövegfájlokon túlzott terhelést okozhat | Kis fájlok esetén az AES‑128 elegendő lehet, és kisebb archívumot eredményez. |
| Futtatási időbeli kivétel a `archive.Save` hívásnál | Írási jogosultság hiánya a célmappában | Bizonyosodj meg arról, hogy az alkalmazásnak írási joga van a `dataDir` mappához, vagy használj másik kimeneti útvonalat. |

## Gyakran Ismételt Kérdések (GYIK)

### Használhatok különböző titkosítási módszereket minden fájlhoz?
Igen, az Aspose.Zip for .NET lehetővé teszi, hogy a fájlonkénti szinten keverd a titkosítási módszereket – hagyományos ZipCrypto, AES‑128 és AES‑256.

### Elérhető próba verzió?
Igen, az Aspose.Zip for .NET ingyenes próba verziója [itt](https://releases.aspose.com/) érhető el.

### Hogyan kaphatok támogatást, ha problémáim vannak?
Látogasd meg az [Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37), ahol a közösség és az Aspose támogatás segíthet.

### Hol találom az Aspose.Zip for .NET részletes dokumentációját?
A dokumentáció [itt](https://reference.aspose.com/zip/net/) érhető el.

### Vásárolhatok ideiglenes licencet tesztelési célokra?
Igen, ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhetsz be.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-03-02  
**Tesztelve:** Aspose.Zip for .NET (legújabb kiadás)  
**Szerző:** Aspose  

---