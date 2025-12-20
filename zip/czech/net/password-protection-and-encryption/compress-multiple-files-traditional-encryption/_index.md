---
date: 2025-12-20
description: Naučte se, jak chránit zip archiv heslem pomocí Aspose.Zip pro .NET s
  tradičním šifrováním. Tento průvodce ukazuje, jak šifrovat zip soubory a efektivně
  přidávat soubory do zipu.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Zabezpečte zip archiv heslem pomocí Aspose.Zip .NET
url: /cs/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zabezpečení zip archivu heslem pomocí Aspose.Zip .NET

## Úvod

Vítejte v tomto podrobném tutoriálu o **tom, jak zabezpečit zip archiv heslem** pomocí tradičního šifrování s Aspose.Zip pro .NET. Aspose.Zip je výkonná knihovna, která vývojářům umožňuje snadno vytvářet, číst a manipulovat se zip archivy. V tomto průvodci vás provedeme kompresí několika souborů, jejich přidáním do zipu a zabezpečením archivu heslem – vše při zachování čistého a udržovatelného kódu.

## Rychlé odpovědi
- **Co znamená „zabezpečit zip archiv heslem“?** Znamená to šifrování zip souboru tak, aby jeho obsah mohl být otevřen pouze po zadání správného hesla.  
- **Která knihovna to v .NET řeší?** Aspose.Zip pro .NET poskytuje vestavěnou podporu pro tradiční šifrování.  
- **Potřebuji licenci pro produkční nasazení?** Ano, pro produkční použití je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Mohu to spustit na Linuxu?** Samozřejmě—Aspose.Zip je multiplatformní a funguje na Windows, Linuxu i macOS.  
- **Kolik souborů mohu přidat?** Můžete přidat libovolný počet souborů; příklad ukazuje tři, ale přístup je škálovatelný.

## Co je „zabezpečit zip archiv heslem“?

Zip archiv chráněný heslem používá šifrování (v tomto případě tradiční PKZIP šifrování) k zakódování dat souborů uvnitř archivu. Když se uživatel pokusí archiv rozbalit, musí zadat správné heslo, aby mohl dešifrovat obsah.

## Proč použít Aspose.Zip pro tento úkol?

- **Jednoduché API** – Jedna řádka kódu pro povolení šifrování.  
- **Žádné externí závislosti** – Čistý .NET, žádné nativní DLL.  
- **Multiplatformní** – Funguje s .NET Framework, .NET Core a .NET 5/6+.  
- **Optimalizovaný výkon** – Efektivně zpracovává velké soubory.

## Požadavky

Než začneme, ujistěte se, že máte následující:

- **Aspose.Zip pro .NET** – Stáhněte jej z oficiální stránky [zde](https://releases.aspose.com/zip/net/).  
- **Složka se soubory** – Nahraďte `"Your Document Directory"` ve vzorovém kódu skutečnou cestou, která obsahuje soubory, jež chcete zkomprimovat.

## Importování jmenných prostorů

Začněte importováním požadovaných jmenných prostorů, abyste mohli pracovat s třídami Aspose.Zip:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Jak zašifrovat zip tradičním šifrováním

### Krok 1: Nastavení zip souboru (Zabezpečení zip archivu heslem)

Vytvořte zip soubor a nakonfigurujte nastavení tradičního šifrování. Heslo `"p@s$"` je pouze příklad—nahraďte jej silným heslem pro reálné projekty.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Přidání souborů do zip archivu

Nyní přidejte každý soubor, který chcete zahrnout. Metoda `CreateEntry` přijímá název souboru uvnitř zipu a stream (`source1`, `source2`, `source3`), který odkazuje na skutečná data souboru.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Uložení zip souboru (komprese souborů s heslem)

Nakonec archiv uložte na disk. Tento krok zapíše zašifrovaný zip soubor na místo, které jste dříve určili.

```csharp
archive.Save(zipFile);
```

> **Tip:** Vždy uzavírejte streamy (`using` bloky), aby se rychle uvolnily souborové handle, zejména při práci s velkými soubory.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Chyba nesprávného hesla** | Neshoda hesla nebo překlep v `TraditionalEncryptionSettings` | Ověřte řetězec hesla a zajistěte, že stejné heslo je použito při rozbalování. |
| **Soubor nebyl přidán** | Zdrojový stream (`sourceX`) je null nebo byl uvolněn | Otevřete zdrojové streamy pomocí `File.OpenRead` před jejich předáním do `CreateEntry`. |
| **Zpomalení výkonu u velkých souborů** | Použití výchozí úrovně komprese u mnoha velkých položek | Zvažte nastavení `CompressionLevel` v `ArchiveEntrySettings` pro rychlejší zpracování. |

## Často kladené otázky

**Q: Mohu to použít jak ve Windows, tak v Linux prostředí?**  
A: Ano, Aspose.Zip pro .NET je plně multiplatformní a funguje na Windows, Linuxu i macOS.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Samozřejmě—můžete si vyzkoušet bezplatnou zkušební verzi Aspose.Zip pro .NET [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu, pokud narazím na problémy?**  
A: Navštivte oficiální [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) pro komunitní pomoc a oficiální podporu.

**Q: Jsou dočasné licence možností pro hodnocení?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu kompletní dokumentaci API?**  
A: Podrobný referenční materiál je k dispozici [zde](https://reference.aspose.com/zip/net/).

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}