---
date: 2026-03-08
description: Naučte se, jak chránit zip archiv heslem pomocí Aspose.Zip pro .NET,
  ukládat více souborů bez komprese a použít ochranu zip souboru heslem s AES šifrováním.
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip pro .NET – Ochrana zip archivu heslem a uložení více souborů bez
  komprese
url: /cs/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip pro .NET – Návod na ochranu zip archivu heslem

V moderním vývoji .NET je zabezpečené archivování souborů častou požadavkou. S **Aspose.Zip for .NET** můžete **chránit zip archiv heslem**, ukládat několik položek bez komprese a použít silné šifrování AES – vše během několika řádků C#. Tento návod vás provede přesnými kroky, jak vytvořit zip, který obsahuje více souborů, používá režim *store* (bez komprese) a je uzamčen heslem.

## Rychlé odpovědi
- **Co znamená „password protect zip archive“?** Šifruje obsah zipu, takže jej lze otevřít pouze se správným heslem.  
- **Jaký šifrovací algoritmus se používá?** AES‑256 přes `AesEcryptionSettings`.  
- **Mohu přidat více než jeden soubor?** Ano – opakujte volání `CreateEntry` pro každý zdrojový soubor.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Je to podporováno na .NET 6/7?** Ano – Aspose.Zip funguje s .NET Framework, .NET Core a .NET 5/6/7.

## Co je ochrana zip archivu heslem?
*Password protect zip archive* je ZIP soubor, jehož položky jsou šifrovány pomocí uživatelem definovaného hesla. Když je archiv otevřen, musí být zadáno heslo; jinak zůstane obsah nečitelné. Aspose.Zip to realizuje pomocí šifrování AES‑256, což poskytuje silnou ochranu citlivých dat.

## Proč použít ochranu zip souboru heslem s Aspose.Zip?
- **Ukládání bez komprese** – `StoreCompressionSettings` zachovává původní velikost souboru, ideální pro již komprimovaná média.  
- **Silné šifrování** – AES‑256 chrání data před útoky hrubou silou.  
- **Plná integrace s .NET** – Funguje s .NET Framework, .NET Core a .NET 5/6/7 bez nativních závislostí.  
- **Jednoduché API** – Vytvořte archiv, nastavte heslo, přidejte položky a uložte – vše během několika řádků.

## Požadavky

Než se ponoříme do kódu, ujistěte se, že máte:

- **Aspose.Zip for .NET** nainstalován. Můžete si jej stáhnout [zde](https://releases.aspose.com/zip/net/).  
- Složku, která obsahuje soubory, které chcete archivovat. V níže uvedených příkladech proměnná `dataDir` ukazuje na tuto složku.

## Importování jmenných prostorů

Nejprve přidejte požadované jmenné prostory do rozsahu:

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Jak chránit zip archiv heslem a uložit více souborů bez komprese

Níže je podrobný návod krok za krokem. Každý krok obsahuje krátké vysvětlení následované původním blokem kódu (beze změny).

### Krok 1: Otevřít zip soubor

Vytvoříme nový `FileStream`, který bude obsahovat výsledný archiv.

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

### Krok 2: Otevřít zdrojový soubor

Otevřete první soubor, který chcete přidat do archivu. Tento blok můžete opakovat pro další soubory.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

### Krok 3: Vytvořit archiv s ukládáním bez komprese a šifrováním AES

Zde nakonfigurujeme archiv tak, aby **ukládal** (bez komprese) soubory a použijeme **ochranu zip souboru heslem** pomocí AES‑256.

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

### Krok 4: Vytvořit položku archivu a uložit – *create archive entry c#*

Nyní přidáme soubor do archivu a zapíšeme šifrovaný zip na disk.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

> **Tip:** Pro přidání dalších souborů stačí zavolat `archive.CreateEntry("anotherFile.txt", anotherStream);` před `archive.Save(zipFile);`.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **„Invalid password“ výjimka** | Špatné heslo nebo nesoulad šifrovací metody. | Ujistěte se, že řetězec hesla v `AesEcryptionSettings` odpovídá tomu, které použijete k otevření zipu, a ověřte, že používáte `EncryptionMethod.AES256`. |
| **Velikost souboru větší než očekávaná** | Náhodné použití komprese. | Ověřte, že používáte `StoreCompressionSettings` (žádná komprese) místo `DeflateCompressionSettings`. |
| **Stream není uzavřen** | Chybí uzavírací závorka u `using` bloků. | Ujistěte se, že každý `using` blok je řádně uzavřen; ukázkový kód ukazuje správné vnoření. |

## Často kladené otázky

**Q: Mohu použít Aspose.Zip pro .NET s jinými šifrovacími metodami?**  
A: Ano, Aspose.Zip podporuje několik šifrovacích algoritmů, včetně AES‑128 a ZipCrypto. Podrobnosti najdete v dokumentaci [zde](https://reference.aspose.com/zip/net/).

**Q: Kde mohu získat podporu pro Aspose.Zip pro .NET?**  
A: Navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pro komunitní pomoc a oficiální podporu.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?**  
A: Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Dočasnou licenci požádejte [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.Zip pro .NET?**  
A: Aspose.Zip pro .NET můžete zakoupit [zde](https://purchase.aspose.com/buy).

## Závěr

V tomto průvodci jsme ukázali, jak **chránit zip archiv heslem**, ukládat více položek bez komprese a použít šifrování AES‑256 pomocí Aspose.Zip pro .NET. Dodržením těchto kroků můžete zabezpečit citlivá data, splnit požadavky na shodu a udržet své archivy lehké. Klidně experimentujte s přidáváním dalších souborů, změnou hesel nebo přechodem na jiné šifrovací metody – Aspose.Zip to dělá jednoduchým.

---

**Poslední aktualizace:** 2026-03-08  
**Testováno s:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}