---
date: 2026-02-23
description: Naučte se komprimovat více souborů do tar pomocí Aspose.Zip pro .NET
  a efektivně vytvářet archivy tar.lz.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat více souborů do tar pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET

V moderním vývoji v .NET může efektivní balení souborů výrazně zmenšit velikost nasazení a dobu přenosu po síti. **Compress multiple files tar** je častý požadavek, když potřebujete lehký, LZ‑komprimovaný TAR archiv pro zálohy, distribuci nebo nahrávání do cloudu. V tomto tutoriálu vás provedeme jasným, krok‑za‑krokem **tar.lz compression example** pomocí knihovny Aspose.Zip, abyste mohli rychle vytvořit **tar.lz archive** ve svých aplikacích.

## Rychlé odpovědi
- **Jakou knihovnu použít?** Aspose.Zip pro .NET.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní příklad.  
- **Potřebuji licenci?** Pro testování stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mohu komprimovat více souborů najednou?** Ano – stačí přidat více položek před uložením.

## Jak komprimovat více souborů tar
Tato sekce přímo řeší primární klíčové slovo a ukazuje přesné kroky k **compress multiple files tar** pomocí Aspose.Zip. Přístup funguje pro libovolný počet souborů a můžete jej snadno přizpůsobit vlastní struktuře složek.

## Co je tar.lz komprese?
`tar.lz` je archiv TAR, který byl komprimován pomocí algoritmu LZMA (často označovaného jednoduše jako **LZ**). Kombinuje jednoduchost seskupování souborů v TAR s vysokým kompresním poměrem LZ, což je ideální pro záložní soubory, distribuci balíčků nebo jakýkoli scénář, kde záleží na šířce pásma.

## Proč použít Aspose.Zip pro .NET?
Aspose.Zip abstrahuje nízkoúrovňové detaily tvorby archivů a poskytuje čisté, objektově orientované API. Získáte:

* **Zero external dependencies** – čistá implementace v .NET.  
* **Cross‑platform support** – funguje na Windows, Linuxu i macOS.  
* **Built‑in LZ compression** – není nutné instalovat další nativní nástroje.  
* **Strong error handling** – výjimky jsou popisné, což usnadňuje ladění.

## Předpoklady
Než začnete, ujistěte se, že máte:

- **Aspose.Zip for .NET** knihovnu – stáhněte ji [zde](https://releases.aspose.com/zip/net/).  
- Složku, která obsahuje soubory, jež chcete archivovat. Cesta k této složce bude uložena v proměnné `dataDir` (nastavíte ji v kroku 3).

## Import Namespaces
Přidejte potřebné jmenné prostory, aby kompilátor věděl, kde najít třídy, které budeme používat.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak vytvořit tar.lz archiv – Průvodce krok za krokem

### Krok 1: Komprimovat jeden soubor
První příklad ukazuje nejzákladnější scénář – přidání jednoho souboru do TAR archivu a následné uložení jako **tar.lz** soubor.

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
- `SaveLzipped` zapíše archiv na disk a použije LZ kompresi, čímž vznikne `archive.tar.lz`.

### Krok 2: Komprimovat více souborů v jednom archivu
Často budete potřebovat spojit několik souborů dohromady. Stačí zavolat `CreateEntry` pro každý soubor před uložením. Tento příklad ukazuje **add files to tar lz** a efektivně **compress multiple files tar**.

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

- Kód následuje stejný vzor jako v kroku 1, ale přidává druhou položku (`lcet10.txt`).  
- `CreateEntry` můžete opakovat libovolně mnohokrát; knihovna automaticky spravuje vnitřní strukturu TAR.

### Krok 3: Zadejte adresář s dokumenty
Nahraďte zástupný text skutečnou cestou, kde se nacházejí vaše zdrojové soubory. Tato cesta je používána v předchozích příkladech.

```csharp
string dataDir = "Your Document Directory";
```

**Vysvětlení**

- Nastavte `dataDir` na plně kvalifikovanou cestu ke složce, např. `@"C:\MyFiles\"`.  
- Uložení adresáře do proměnné usnadňuje opakované použití kódu a údržbu.

## Časté problémy a řešení
| Symptom | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| `FileNotFoundException` při spuštění ukázky | `dataDir` ukazuje na neexistující složku nebo je špatně napsáno jméno souboru | Ověřte cestu a názvy souborů; pro bezpečnost použijte `Path.Combine`. |
| Výstupní soubor má **0 KB** | `archive.SaveLzipped` byl zavolán před přidáním jakýchkoli položek | Ujistěte se, že před `SaveLzipped` proběhne alespoň jedno volání `CreateEntry`. |
| Komprese se zdá být pomalá | Velké soubory s výchozí velikostí bufferu | Zvažte zpracování souborů po částech nebo použití asynchronního I/O, pokud je výkon kritický. |

## Závěr
Nyní víte, **jak komprimovat tar.lz** soubory pomocí Aspose.Zip pro .NET, ať už pracujete s jedním dokumentem nebo s kolekcí souborů. Tento **tar.lz compression example** ukazuje čistý, připravený pro produkci způsob, jak **create tar lz archive** soubory, které lze snadno přenášet nebo ukládat.

## Často kladené otázky

**Q:** Mohu komprimovat soubory libovolné velikosti pomocí Aspose.Zip pro .NET?  
**A:** Ano, knihovna zvládne jak malé, tak velmi velké soubory; jen se ujistěte, že máte dostatek paměti a místa na disku pro dočasnou strukturu TAR.

**Q:** Je kód kompatibilní s nejnovější verzí Aspose.Zip?  
**A:** Ukázka cílí na aktuální verzi; vždy udržujte NuGet balíček aktuální pro opravy chyb a nové funkce.

**Q:** Existují licenční úvahy?  
**A:** Pro produkční použití je vyžadována komerční licence. Viz podrobnosti o licencování na [Aspose website](https://purchase.aspose.com/buy).

**Q:** Můžu to použít v komerčním projektu?  
**A:** Rozhodně – po získání platné licence můžete knihovnu vložit do jakékoli komerční aplikace.

**Q:** Kde získám pomoc, pokud narazím na problémy?  
**A:** Navštivte [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) pro komunitní podporu a oficiální asistenci.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** Aspose.Zip pro .NET (nejnovější vydání)  
**Autor:** Aspose  

---