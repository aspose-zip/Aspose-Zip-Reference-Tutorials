---
date: 2026-07-04
description: Naučte se, jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET
  a efektivně vytvářet archivy tar.lz.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Komprese do TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET

V moderním vývoji .NET může efektivní balení souborů dramaticky zlepšit velikost nasazení a dobu přenosu po síti. **Compress multiple files tar** je častý požadavek, když potřebujete lehký, LZ‑komprimovaný TAR archiv pro zálohy, distribuci nebo nahrávání do cloudu. V tomto tutoriálu projdeme jasný, krok‑za‑krokem **tar.lz compression example** pomocí knihovny Aspose.Zip, abyste mohli rychle vytvořit **tar.lz archiv** ve svých aplikacích.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip pro .NET.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní příklad.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mohu komprimovat více souborů najednou?** Ano – stačí přidat více položek před uložením.

## Jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET?
Načtěte své zdrojové soubory, vytvořte instanci `TarArchive`, přidejte každý soubor pomocí `CreateEntry` a dokončete voláním `SaveLzipped`. Knihovna interně spravuje strukturu TAR a LZ kompresi, takže získáte jediný soubor `*.tar.lz` během několika řádků kódu. Tento přístup funguje na Windows, Linuxu i macOS bez jakýchkoli nativních závislostí.

## Co je komprese tar.lz?
`tar.lz` je archiv TAR, který byl komprimován pomocí algoritmu LZMA (často označovaného jednoduše jako **LZ**). Kombinuje jednoduchost seskupování souborů v TAR s vysokým kompresním poměrem LZ, což je ideální pro záložní soubory, distribuci balíčků nebo jakýkoli scénář, kde je důležitá šířka pásma.

## Proč použít Aspose.Zip pro .NET?
Aspose.Zip poskytuje čistě spravované, multiplatformní řešení, které vytváří archivy TAR, ZIP i LZ‑založené bez externích nástrojů, podporuje více než 30 formátů archivů a dosahuje až o 30 % lepší komprese u velkých souborů, přičemž nabízí podrobné výjimky pro robustní zpracování chyb. Také se bez problémů integruje s .NET logovacími frameworky a poskytuje podrobné události postupu.

## Požadavky
Než začnete, ujistěte se, že máte:

- **Aspose.Zip pro .NET** knihovna – stáhněte ji z [zde](https://releases.aspose.com/zip/net/).  
- Složka, která obsahuje soubory, které chcete archivovat. Cesta k této složce bude uložena v proměnné `dataDir` (nastavíte ji ve Kroku 3).

## Importovat jmenné prostory
Přidejte požadované jmenné prostory, aby kompilátor věděl, kde najít třídy, které budeme používat.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak vytvořit tar.lz archiv – krok za krokem průvodce

### Krok 1: Komprimovat jeden soubor
První příklad ukazuje nejzákladnější scénář – přidání jednoho souboru do TAR archivu a následné uložení jako **tar.lz** soubor.

Třída `TarArchive` představuje TAR kontejner, který může v jednom archivu obsahovat více souborů.  

**Vysvětlení**

- `new TarArchive()` vytvoří prázdný TAR kontejner.  
- `CreateEntry` přidá soubor `alice29.txt` z vašeho `dataDir`.  
- `SaveLzipped` zapíše archiv na disk a použije LZ kompresi, čímž vytvoří `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Krok 2: Komprimovat více souborů v jednom archivu
Často budete potřebovat seskupit několik souborů dohromady. Stačí před uložením zavolat `CreateEntry` pro každý soubor. Tento příklad ukazuje **add files to tar lz** a efektivně **compress multiple files tar**.

**Vysvětlení**

- Kód následuje stejný vzor jako v Kroku 1, ale přidá druhou položku (`lcet10.txt`).  
- Můžete opakovat `CreateEntry` tolikrát, kolik potřebujete; knihovna automaticky spravuje vnitřní strukturu TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Krok 3: Zadejte adresář dokumentů
Nahraďte zástupný znak skutečnou cestou, kde se nacházejí vaše zdrojové soubory. Tato cesta je použita v příkladech výše.

**Vysvětlení**

- Nastavte `dataDir` na plně kvalifikovanou cestu ke složce, např. `@\"C:\\MyFiles\\\"`.  
- Uchování adresáře v proměnné činí kód znovupoužitelným a snadněji udržovatelným.

```csharp
string dataDir = "Your Document Directory";
```

## Časté problémy a řešení
| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| `FileNotFoundException` při spuštění vzorku | `dataDir` ukazuje na neexistující složku nebo je název souboru špatně napsán | Ověřte cestu a názvy souborů; použijte `Path.Combine` pro bezpečnost. |
| Výstupní soubor je **0 KB** | `archive.SaveLzipped` byl zavolán před přidáním jakýchkoli položek | Ujistěte se, že před `SaveLzipped` je alespoň jedno volání `CreateEntry`. |
| Komprese se zdá pomalá | Velké soubory s výchozí velikostí bufferu | Zvažte zpracování souborů po částech nebo použití asynchronního I/O, pokud je výkon kritický. |

## Závěr
Nyní víte, **jak komprimovat tar.lz** soubory pomocí Aspose.Zip pro .NET, ať už pracujete s jedním dokumentem nebo s kolekcí souborů. Tento **tar.lz compression example** ukazuje čistý, produkčně připravený způsob, jak **vytvořit tar lz archiv** soubory, které lze snadno přenášet nebo ukládat. Soubor můžete komprimovat do tar.lz pomocí stejného API voláním `SaveLzipped` po přidání všech požadovaných položek.

## Často kladené otázky

**Q:** Mohu komprimovat soubory libovolné velikosti pomocí Aspose.Zip pro .NET?  
**A:** Ano, knihovna zvládne jak malé, tak velmi velké soubory; stačí zajistit dostatek paměti a místa na disku pro dočasnou strukturu TAR.

**Q:** Je kód kompatibilní s nejnovějším vydáním Aspose.Zip?  
**A:** Vzorek cílí na aktuální verzi; vždy udržujte NuGet balíček aktuální pro opravy chyb a nové funkce.

**Q:** Existují licenční úvahy?  
**A:** Pro produkční použití je vyžadována komerční licence. Podrobnosti o licencování najdete na [Aspose webu](https://purchase.aspose.com/buy).

**Q:** Mohu to použít v komerčním projektu?  
**A:** Rozhodně – jakmile máte platnou licenci, můžete knihovnu vložit do jakékoli komerční aplikace.

**Q:** Kde mohu získat pomoc, pokud narazím na problémy?  
**A:** Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) pro komunitní podporu a oficiální asistenci.

---

**Poslední aktualizace:** 2026-07-04  
**Testováno s:** Aspose.Zip pro .NET (nejnovější vydání)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak komprimovat tar a vytvořit TarBz2 pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Přidat soubory do tar a vytvořit tarxz archiv pomocí Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}