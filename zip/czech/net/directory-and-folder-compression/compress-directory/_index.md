---
date: 2026-05-30
description: Naučte se, jak zkomprimovat složku pomocí Aspose.Zip pro .NET, efektivně
  vytvořit zip archiv a snížit využití úložiště ve vašich .NET aplikacích.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Jak zkomprimovat složku
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak zkomprimovat složku pomocí Aspose.Zip pro .NET
url: /cs/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zkomprimovat složku pomocí Aspose.Zip pro .NET

V tomto tutoriálu objevíte **jak zkomprimovat složku** rychle a spolehlivě pomocí Aspose.Zip pro .NET. Ať už vytváříte desktopovou utilitu, cloudovou službu nebo automatizovaný skript pro zálohování, komprese složky do ZIP archivu může dramaticky zmenšit požadavky na úložiště a urychlit přenosy po síti. Provedeme vás každým krokem, vysvětlíme, proč je každý řádek důležitý, a upozorníme na běžné úskalí, abyste techniku mohli použít s jistotou.

## Rychlé odpovědi
- **Co dělá Aspose.Zip?** Poskytuje jednoduché .NET API pro vytváření a rozbalování ZIP archivů bez externích závislostí.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní kompresi složky.  
- **Které verze .NET jsou podporovány?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1 a .NET 5‑10.  
- **Potřebuji licenci pro produkci?** Ano, pro produkční použití je vyžadována komerční licence.  
- **Mohu komprimovat více složek najednou?** Rozhodně—použijte metodu `CreateEntries` na libovolné kolekci `DirectoryInfo` k **zkomprimování více složek** v jednom běhu.  

`CreateEntries` přidá všechny soubory ze složky do archivu.

## Co je „jak zkomprimovat složku“?

Komprese složky znamená vzít každý soubor a podsložku uvnitř daného adresáře a zabalit je do jediného ZIP archivu. Tím se sníží celková velikost, zachová se původní hierarchie a usnadní se přenos nebo ukládání dat. Výsledný ZIP lze otevřít na jakékoli platformě bez speciálního softwaru a zachovává strukturu složky tak, že po rozbalení je původní uspořádání obnoveno přesně tak, jak bylo.

## Proč použít Aspose.Zip pro tento úkol?

Aspose.Zip vám umožní **vytvořit zip archiv** přímo z .NET kódu s konzistentním API napříč všemi podporovanými runtime. Načtěte třídu `Archive`, přidejte položky, nastavte `CompressionLevel`, volitelně přiřaďte heslo a zavolejte `Save`. Knihovna zpracuje složky obsahující tisíce souborů za méně než sekundu na typickém hardwaru a podporuje více než 50 různých kompresních formátů a šifrovacích algoritmů.

## Požadavky

- **Aspose.Zip pro .NET** – stáhněte jej [zde](https://releases.aspose.com/zip/net/) nebo [zde](https://releases.aspose.com/zip/net).  
- **Vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE podporující C#.  
- **Adresář dokumentů** – nahraďte `"Your Document Directory"` v kódu cestou ke složce, kterou chcete komprimovat.  
- **Referenční dokumentace** – konzultujte oficiální dokumentaci [zde](https://reference.aspose.com/zip/net/).

## Importovat jmenné prostory

Začněte importováním potřebných jmenných prostorů. Ty vám poskytují přístup ke klíčovým třídám pro kompresi.

```csharp
using Aspose.Zip;
using System.IO;
```

## Jak zkomprimovat složku pomocí Aspose.Zip

Níže je jednoduchý příklad, který demonstruje **jak zkomprimovat složku**. Stejný vzor lze rozšířit na **zkomprimovat více souborů .net** nebo na vytvoření vlastních struktur archivů.

### Krok 1: Inicializovat váš adresář dokumentů

Nastavte proměnnou `dataDir` na cestu adresáře, který chcete komprimovat.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořit výstupní ZIP soubory

Otevřete dva objekty `FileStream` pro výstupní ZIP soubory. Toto ukazuje, jak můžete z jednoho zdroje vygenerovat více než jeden archiv — užitečné pro verzované zálohy.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Krok 3: Komprimovat adresář

Třída `Archive` představuje ZIP archiv a poskytuje metody pro přidávání položek a uložení souboru. Použijte ji k přidání každé položky z cílové složky. Příklad používá vzorovou složku pojmenovanou **CanterburyCorpus**, ale můžete ji nasměrovat na libovolný adresář.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Tip:** Pokud potřebujete **vytvořit zip archiv .net** s konkrétní úrovní komprese, nastavte `archive.CompressionLevel` před voláním `Save`.

## Časté problémy a řešení

| Symptom | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Prázdný ZIP soubor | `dataDir` ukazuje na špatnou složku nebo chybí koncová lomítko | Ověřte cestu a ujistěte se, že složka obsahuje soubory |
| `UnauthorizedAccessException` | Aplikace nemá oprávnění k souborovému systému | Spusťte Visual Studio jako administrátor nebo udělte práva čtení/zápisu |
| Vysoké využití paměti pro obrovské adresáře | Načítání všech položek najednou do paměti | Použijte `Archive.CreateEntryFromFile` v cyklu pro streamování souborů jednotlivě |

## Často kladené otázky (další)

**Q: Mohu přidat heslo do ZIP archivu?**  
A: Ano. Nastavte `archive.Password = "yourPassword";` před voláním `Save`.

**Q: Jak zahrnout jen určité typy souborů?**  
A: Filtrovat kolekci `DirectoryInfo` pomocí `GetFiles("*.txt")` nebo podobně před voláním `CreateEntries`.

**Q: Existuje způsob, jak aktualizovat existující ZIP bez jeho přetvoření?**  
A: Aspose.Zip podporuje inkrementální aktualizace pomocí `Archive.UpdateEntry`.

## FAQ

### Q1: Mohu použít Aspose.Zip pro .NET jak v komerčních, tak osobních projektech?

A1: Ano, Aspose.Zip pro .NET je licencován pro komerční i osobní použití.

### Q2: Je k dispozici bezplatná zkušební verze?

A2: Ano, můžete si vyzkoušet bezplatnou verzi [zde](https://releases.aspose.com/zip/net).

### Q3: Jak získám podporu pro Aspose.Zip pro .NET?

A3: Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) pro komunitní podporu nebo zvažte zakoupení [dočasné licence](https://purchase.aspose.com/temporary-license/) pro dedikovanou asistenci.

### Q4: Existují další příklady a tutoriály?

A4: Ano, [dokumentace](https://reference.aspose.com/zip/net/) obsahuje komplexní příklady a tutoriály.

### Q5: Mohu zakoupit Aspose.Zip pro .NET?

A5: Samozřejmě, můžete provést nákup [zde](https://purchase.aspose.com/buy).

## Závěr

Nyní máte kompletní, připravený vzor pro **jak zkomprimovat složku** pomocí Aspose.Zip pro .NET. Využitím třídy `Archive` můžete **vytvořit zip archiv**, nastavit vlastní `CompressionLevel`, přidat ochranu heslem a dokonce **zkomprimovat více složek** v jednom průchodu — což je ideální pro automatizaci úloh zálohování složek. Experimentujte s API, přidejte šifrování, rozdělení archivů nebo streamování přímo do cloudového úložiště a získáte robustní řešení pro jakoukoli .NET‑založenou kompresi.

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.Zip 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
