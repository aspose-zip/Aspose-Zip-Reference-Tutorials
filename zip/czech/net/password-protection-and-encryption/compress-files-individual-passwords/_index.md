---
date: 2026-03-02
description: Naučte se, jak vytvořit zip archiv chráněný heslem a komprimovat soubory
  s hesly v .NET pomocí Aspose.Zip. Postupujte podle našeho krok‑za‑krokem průvodce.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte ZIP archiv chráněný heslem v .NET s Aspose.Zip
url: /cs/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření chráněného ZIP archivu heslem v .NET s Aspose.Zip

## Úvod

Když potřebujete sdílet citlivá data, **chráněný zip archiv heslem** je jedním z nejjednodušších, ale zároveň nejúčinnějších způsobů, jak udržet informace v bezpečí. V .NET aplikacích Aspose.Zip usnadňuje **kompresi souborů s hesly**, přičemž každému souboru přiřadí vlastní šifrovací klíč. V tomto tutoriálu se naučíte, jak takový archiv vytvořit, proč je to důležité a kde jej můžete použít v reálných projektech.

## Rychlé odpovědi
- **Jakou knihovnu použít?** Aspose.Zip pro .NET poskytuje vestavěnou podporu pro hesla na úrovni souboru a více šifrovacích metod.  
- **Kolik řádků kódu?** Přibližně 30 řádků, včetně nastavení a uložení archivu.  
- **Může mít každý soubor jiné heslo?** Ano – můžete přiřadit unikátní heslo ke každému záznamu.  
- **Jaké šifrovací metody jsou k dispozici?** Tradiční ZipCrypto, AES‑128 a AES‑256.  
- **Potřebuji licenci pro produkci?** Pro produkční použití je vyžadována komerční licence; k dispozici je bezplatná zkušební verze.

## Co je to chráněný zip archiv heslem?
Chráněný zip archiv heslem je komprimovaný soubor (ZIP), který vyžaduje heslo pro rozbalení jeho obsahu. Heslo může chránit celý archiv nebo jednotlivé položky a moderní algoritmy jako AES‑128/256 poskytují silné šifrování.

## Proč komprimovat soubory s hesly pomocí Aspose.Zip?
- **Granulární zabezpečení** – přiřaďte odlišné heslo ke každému souboru, ideální pro multi‑tenant scénáře.  
- **Více šifrovacích standardů** – vyberte si mezi starším ZipCrypto a silným AES.  
- **Žádné externí nástroje** – vše je zpracováno programově přímo ve vašem .NET kódu.  
- **Výkon** – rychlá komprese pomocí Deflate při zachování malé velikosti archivu.

## Předpoklady

Než začnete, ujistěte se, že máte:

- **Aspose.Zip pro .NET** – nainstalujte knihovnu do svého projektu. Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).  
- **Stáhněte nejnovější balíček**, pokud jste tak ještě neučinili, z [tohoto odkazu](https://releases.aspose.com/zip/net/).  
- Složku obsahující soubory, které chcete komprimovat.

## Import Namespaces

Přidejte požadované jmenné prostory na začátek svého C# souboru:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Krok 1: Nastavte cestu ke zdrojovému adresáři

Ukážete kódu, kde se nachází složka se vstupními soubory:

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Komprimujte soubory s individuálními hesly

Nyní vytvoříme **chráněný zip archiv heslem**, kde každý soubor používá vlastní heslo a šifrovací metodu. Příklad používá tři ukázkové soubory (`alice29.txt`, `asyoulik.txt` a `fields.c`) s různými hesly.

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

### Jak to funguje
- **CreateEntry** přidá soubor do archivu.  
- Čtvrtý argument (`ArchiveEntrySettings`) vám umožní specifikovat jak kompresi (`DeflateCompressionSettings`), tak šifrování (`TraditionalEncryptionSettings` nebo `AesEcryptionSettings`).  
- Předáním odlišného řetězce hesla pro každý záznam získáte **chráněný zip archiv heslem**, kde je každý soubor odemčen jen svým vlastním klíčem.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Rozbalení selže s chybou “Wrong password” | Nesprávné heslo nebo špatná šifrovací metoda | Ověřte přesný řetězec hesla a ujistěte se, že při rozbalování používáte stejný `EncryptionMethod`. |
| Velikost archivu je větší, než se očekávalo | Použití AES‑256 na malých textových souborech může přidat režii | Pro malé soubory může být dostačující AES‑128, což vede k menšímu archivu. |
| Výjimka při `archive.Save` | Chybějící oprávnění k zápisu do cílové složky | Zajistěte, aby aplikace měla právo zápisu do `dataDir`, nebo použijte jinou výstupní cestu. |

## Často kladené otázky (FAQ)

### Mohu použít různé šifrovací metody pro každý soubor?
Ano, Aspose.Zip pro .NET umožňuje kombinovat šifrovací metody – tradiční ZipCrypto, AES‑128 i AES‑256 – na úrovni jednotlivých souborů.

### Je k dispozici zkušební verze?
Ano, bezplatnou zkušební verzi Aspose.Zip pro .NET získáte [zde](https://releases.aspose.com/).

### Jak získám podporu, pokud narazím na problémy?
Navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) a požádejte o pomoc komunitu i oficiální podporu Aspose.

### Kde najdu podrobnou dokumentaci k Aspose.Zip pro .NET?
Dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).

### Mohu zakoupit dočasnou licenci pro testování?
Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-03-02  
**Testováno s:** Aspose.Zip pro .NET (nejnovější verze)  
**Autor:** Aspose  

---