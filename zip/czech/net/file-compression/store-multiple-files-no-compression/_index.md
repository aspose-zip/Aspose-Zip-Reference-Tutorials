---
date: 2026-05-30
description: Zjistěte, jak vytvořit zip soubor bez komprese v .NET s Aspose.Zip pro
  .NET. Tento průvodce vám ukáže, jak zipovat soubory bez komprese, ukládat soubory
  nekomprimované a efektivně spravovat archivy.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Ukládání více souborů bez komprese
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvoření zip souboru bez komprese v .NET pomocí Aspose.Zip
url: /cs/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření zipu bez komprese v .NET pomocí Aspose.Zip

V moderním vývoji v .NET je **vytváření zipu bez komprese** schopno dramaticky zlepšit rychlost archivace a udržet velikosti souborů předvídatelné. Když potřebujete **zabalit soubory bez komprese** — například kvůli splnění regulatorních pravidel, urychlení následného zpracování nebo zajištění, že původní sekvence bajtů zůstane nedotčena — Aspose.Zip pro .NET poskytuje čisté, přehledné API. V tomto tutoriálu projdeme přesné kroky k vytvoření nekomprimovaného ZIP archivu, přidání souborů a integraci řešení do vaší aplikace.

## Rychlé odpovědi
- **Co znamená „nekomprimovaný zip“?** Jedná se o ZIP archiv, kde je každý záznam uložen pomocí metody „store“, což ponechává původní bajty souboru nedotčeny.  
- **Proč se vyhýbat kompresi?** Pro zrychlení archivace, zachování původních velikostí souborů pro následné zpracování nebo splnění regulatorních požadavků, které zakazují úpravu dat.  
- **Která třída Aspose.Zip to řeší?** `ArchiveEntrySettings` v kombinaci s `StoreCompressionSettings`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10.  

## Co je zip bez komprese?
**Zip bez komprese** je ZIP archiv, kde každý souborový záznam používá metodu *store*, což znamená, že data jsou do archivu zkopírována doslovně bez použití jakéhokoli kompresního algoritmu. Výsledkem je archiv, jehož velikost je v podstatě součtem původních souborů plus několik bajtů režie ZIP.

## Proč použít Aspose.Zip pro zip soubory bez komprese?
Aspose.Zip je optimalizován pro vysoce výkonnou archivaci, což vám umožní okamžitě ukládat soubory bez režie kompresních algoritmů. Zaručuje plnou kompatibilitu se ZIP, umožňuje kombinovat uložené a komprimované položky a poskytuje jednoduché API, které abstrahuje nízkoúrovňové struktury ZIP, což činí implementaci rychlou a spolehlivou.

## Předpoklady
- **Aspose.Zip pro .NET** – integrován do vašeho projektu. Viz oficiální [dokumentace](https://reference.aspose.com/zip/net/) pro kroky instalace.  
- **Vývojové prostředí .NET** – Visual Studio, VS Code nebo jakékoli IDE, které preferujete.  
- **Adresář dokumentů** – složka ve vašem počítači obsahující soubory, které chcete archivovat (např. „Váš adresář dokumentů“).

## Importujte jmenné prostory
Před psaním jakéhokoli kódu importujte požadované jmenné prostory, aby kompilátor věděl, kde najít třídy Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Krok 1: Nastavte adresář dokumentů
Definujte cestu, kde se nacházejí vaše zdrojové soubory. Nahraďte zástupný text skutečnou složkou ve vašem systému.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte ZIP archiv bez komprese
Jádro tutoriálu – vytvoříme instanci `Archive` nakonfigurovanou s `StoreCompressionSettings`. `Archive` představuje ZIP kontejner, který může obsahovat více položek. `StoreCompressionSettings` určuje, že položka má být uložena bez komprese. Tím se Aspose.Zip říká, aby *uložil* (tj. nekomprimoval) každou položku.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Tip:** Pokud potřebujete **uložit soubory do zipu** a přitom některé komprimovat a jiné nekomprimovat, vytvořte samostatné instance `ArchiveEntrySettings` pro každý soubor a přidejte je do stejného `Archive`.

## Jak vytvořit zip bez komprese v .NET?
Načtěte své zdrojové soubory, vytvořte objekt `Archive` a přidejte každý soubor pomocí `ArchiveEntrySettings` s `new StoreCompressionSettings()`. Celá operace vyžaduje pouze tři řádky kódu a běží v lineárním čase vzhledem k celkové velikosti souborů, což vám poskytne nejrychlejší možný zážitek z archivace.

### Postup krok za krokem
1. **Vytvořte archiv** – vytvořte instanci `Archive` s cílovým proudem nebo cestou k souboru.  
2. **Nastavte vlastnosti položky** – pro každý soubor vytvořte objekt `ArchiveEntrySettings` a přiřaďte `new StoreCompressionSettings()` k jeho vlastnosti `Compression`.  
3. **Přidejte položky** – zavolejte `archive.Add(entrySettings)` pro každý soubor a poté dokončete pomocí `archive.Save()`.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Soubor nenalezen** | Nesprávná cesta `dataDir` nebo chybějící přípona souboru. | Ověřte cestu a ujistěte se, že soubory existují. Použijte `Path.Combine` pro bezpečnější spojování. |
| **Přístup odepřen** | Proces nemá oprávnění číst zdrojové soubory nebo zapisovat ZIP. | Spusťte aplikaci s odpovídajícími právy nebo vyberte složku s oprávněním k zápisu. |
| **Neočekávaná velikost souboru v ZIP** | Archiv byl vytvořen s výchozí kompresí. | Ujistěte se, že `new StoreCompressionSettings()` je předáno do `ArchiveEntrySettings`. |

## Často kladené otázky

**Q: Mohu komprimovat konkrétní typy souborů a ostatní ukládat bez komprese?**  
A: Ano, můžete vytvořit různé `ArchiveEntrySettings` pro každý soubor a v jednom archivu kombinovat komprimované i nekomprimované položky.

**Q: Je Aspose.Zip pro .NET kompatibilní s .NET Core a .NET 5/6?**  
A: Rozhodně. Knihovna podporuje .NET Framework, .NET Core, .NET Standard a nejnovější verze .NET.

**Q: Jak mám zacházet s výjimkami během procesu archivace?**  
A: Zabalte kód archivace do bloku `try‑catch` a zaznamenejte podrobnosti výjimky. To zajistí elegantní selhání a usnadní ladění.

**Q: Podporuje Aspose.Zip vícevláknovou archivaci?**  
A: Ano, můžete zpracovávat více souborů paralelně a přidávat je do archivu, ale pamatujte, že objekt `Archive` není vláknově bezpečný; synchronizujte přístup při přidávání položek.

**Q: Můžu integrovat Aspose.Zip do existujícího projektu bez velkých změn kódu?**  
A: Určitě. API je navrženo pro jednoduché vložení. Viz oficiální [dokumentace](https://reference.aspose.com/zip/net/) pro pokyny k migraci.

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.Zip pro .NET (nejnovější verze v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Create Zip Archive .NET – File Compression with Aspose.Zip](/zip/net/file-compression/)
- [zip multiple files c# – Effortless Compression with Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Without Compression & Decompress Files – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}