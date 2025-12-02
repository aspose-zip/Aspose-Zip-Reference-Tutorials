---
date: 2025-12-01
description: Naučte se komprimovat soubory tar.lz v .NET pomocí Aspose.Zip a snadno
  vytvořit archiv tar.lz.
language: cs
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat tar.lz pomocí Aspose.Zip pro .NET
url: /net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat tar.lz pomocí Aspose.Zip pro .NET

V moderním vývoji .NET je efektivní balení souborů schopno dramaticky zlepšit velikost nasazení a časy přenosu po síti. **How to compress tar.lz** je běžná požadavek, když potřebujete lehký, LZ‑komprimovaný TAR archiv. V tomto tutoriálu vás provedeme jasným, krok‑za‑krokem **tar.lz compression example** pomocí knihovny Aspose.Zip, abyste mohli rychle vytvořit tar.lz archiv ve svých aplikacích.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip for .NET.
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní příklad.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mohu komprimovat více souborů najednou?** Ano – stačí před uložením přidat další položky.

## Co je komprese tar.lz?
`tar.lz` je archiv TAR, který byl komprimován pomocí algoritmu LZMA (často označovaného jednoduše jako **LZ**). Kombinuje jednoduchost seskupování souborů TAR s vysokým kompresním poměrem LZ, což ho činí ideálním pro záložní soubory, distribuci balíčků nebo jakýkoli scénář, kde záleží na šířce pásma.

## Proč použít Aspose.Zip pro .NET?
Aspose.Zip abstrahuje nízkoúrovňové detaily tvorby archivů a poskytuje čisté, objektově orientované API. Získáte:

* **Zero external dependencies** – čistá implementace v .NET.  
* **Cross‑platform support** – funguje na Windows, Linuxu i macOS.  
* **Built‑in LZ compression** – není potřeba instalovat další nativní nástroje.  
* **Strong error handling** – výjimky jsou popisné, což usnadňuje ladění.

## Předpoklady
Před zahájením se ujistěte, že máte:

- **Aspose.Zip for .NET** library – stáhněte ji z [zde](https://releases.aspose.com/zip/net/).  
- Složku, která obsahuje soubory, jež chcete archivovat. Cesta k této složce bude uložena v proměnné `dataDir` (nastavíte ji v kroku 3).

## Importujte jmenné prostory
Přidejte požadované jmenné prostory, aby kompilátor věděl, kde najít třídy, které budeme používat.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak vytvořit tar.lz archiv – krok‑za‑krokem průvodce

### Krok 1: Komprimovat jeden soubor
První příklad ukazuje nejzákladnější scénář – přidání jednoho souboru do TAR archivu a následné uložení jako soubor **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Vysvětlení**

- `new TarArchive()` vytvoří prázdný TAR kontejner.  
- `CreateEntry` přidá soubor `alice29.txt` z vašeho `dataDir`.  
- `SaveLzipped` zapíše archiv na disk a použije LZ kompresi, čímž vytvoří `archive.tar.lz`.

### Krok 2: Komprimovat více souborů v jednom archivu
Často budete potřebovat seskupit několik souborů dohromady. Stačí před uložením zavolat `CreateEntry` pro každý soubor.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Vysvětlení**

- Kód následuje stejný vzor jako v Kroku 1, ale přidává druhý záznam (`lcet10.txt`).  
- `CreateEntry` můžete opakovat libovolně často; knihovna automaticky spravuje vnitřní strukturu TAR.

### Krok 3: Zadejte adresář dokumentů
Nahraďte zástupný znak skutečnou cestou, kde se nacházejí vaše zdrojové soubory. Tato cesta je používána v příkladech výše.

```csharp
string dataDir = "Your Document Directory";
```

**Vysvětlení**

- Nastavte `dataDir` na plně kvalifikovanou cestu ke složce, např. `@"C:\MyFiles\"`.  
- Uložení adresáře do proměnné činí kód znovupoužitelným a snadněji udržovatelným.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| `FileNotFoundException` při spouštění vzorku | `dataDir` ukazuje na neexistující složku nebo je název souboru špatně napsán | Ověřte cestu a názvy souborů; pro bezpečnost použijte `Path.Combine`. |
| Výstupní soubor má **0 KB** | `archive.SaveLzipped` byl zavolán před přidáním jakýchkoli položek | Ujistěte se, že před `SaveLzipped` je alespoň jedno volání `CreateEntry`. |
| Komprese se zdá pomalá | Velké soubory s výchozí velikostí bufferu | Zvažte zpracování souborů po částech nebo použití asynchronního I/O, pokud je výkon kritický. |

## Závěr
Nyní víte, **jak komprimovat tar.lz** soubory pomocí Aspose.Zip pro .NET, ať už pracujete s jedním dokumentem nebo s kolekcí souborů. Tento **tar.lz compression example** ukazuje čistý, připravený pro produkci způsob, jak vytvořit lehké archivy, které lze snadno přenášet nebo ukládat.

## Často kladené otázky

**Q:** Mohu komprimovat soubory libovolné velikosti pomocí Aspose.Zip pro .NET?  
**A:** Ano, knihovna zvládne jak malé, tak velmi velké soubory; stačí zajistit dostatek paměti a místa na disku pro dočasnou strukturu TAR.

**Q:** Je kód kompatibilní s nejnovějším vydáním Aspose.Zip?  
**A:** Ukázka cílí na aktuální verzi; vždy udržujte NuGet balíček aktuální pro opravy chyb a nové funkce.

**Q:** Existují licenční úvahy?  
**A:** Pro produkční použití je vyžadována komerční licence. Podrobnosti o licencování najdete na [webu Aspose](https://purchase.aspose.com/buy).

**Q:** Mohu to použít v komerčním projektu?  
**A:** Rozhodně – jakmile máte platnou licenci, můžete knihovnu vložit do jakékoli komerční aplikace.

**Q:** Kde mohu získat pomoc, pokud narazím na problémy?  
**A:** Navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pro podporu komunity a oficiální asistenci.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-01  
**Testováno s:** Aspose.Zip for .NET (nejnovější verze)  
**Autor:** Aspose