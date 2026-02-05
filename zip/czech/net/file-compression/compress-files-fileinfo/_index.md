---
date: 2026-02-05
description: Naučte se, jak v C# zipovat více souborů a vytvořit zip archiv v .NET
  pomocí Aspose.Zip. Tento krok‑za‑krokem průvodce ukazuje kompresi souborů pomocí
  FileInfo v projektech ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak zipovat více souborů v C# pomocí Aspose.Zip pro .NET
url: /cs/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zipovat více souborů v C# pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **zipovat více souborů v C#** programově, Aspose.Zip pro .NET vám poskytuje čisté, vysoce výkonné API, které funguje v jakékoli .NET aplikaci (včetně ASP.NET). V tomto tutoriálu si projdeme kompresi souborů pomocí třídy `FileInfo`, ukážeme vám, jak **přidat soubory do zipu**, a vysvětlíme, proč je tento přístup ideální pro moderní .NET projekty. Pojďme na to!

## Rychlé odpovědi
- **Jaký je nejjednodušší způsob, jak vytvořit zip archiv?** Použijte třídu `Archive` z Aspose.Zip spolu s objekty `FileInfo`.  
- **Mohu přidat více souborů najednou?** Ano – stačí vytvořit `FileInfo` pro každý soubor a zavolat `CreateEntry`.  
- **Potřebuji speciální licenci pro ASP.NET?** Pro produkční nasazení je vyžadována komerční licence Aspose.Zip; pro hodnocení stačí bezplatná zkušební verze.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Je API thread‑safe?** Ano, pokud každý vlákno pracuje se svou vlastní instancí `Archive`.  
- **Jak zipovat soubory v C# bez načítání do paměti?** Použijte objekty `FileInfo` – streamují data přímo.  

## Jak zipovat více souborů v C#
Zip archiv slouží k seskupení jednoho nebo více souborů do jednoho komprimovaného kontejneru. Tím se šetří úložný prostor, zrychlují se přenosy po síti a zjednodušuje distribuce. Ať už dodáváte logy, exportujete reporty nebo balíte assety pro klienta, znalost **jak zipovat soubory v C#** programově je cenná dovednost pro každého .NET vývojáře.

## Proč použít Aspose.Zip pro přidání souborů do zipu?
- **Žádné externí závislosti** – čistá .NET implementace.  
- **Plná kontrola nad úrovní komprese a kódováním** (ASCII, UTF‑8, atd.).  
- **Podpora velkých souborů** (> 4 GB) a ochrany heslem.  
- **Konzistentní API napříč .NET Framework, .NET Core a .NET 5+**.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte:

1. **Aspose.Zip pro .NET** nainstalovaný. Stáhněte si nejnovější balíček ze [stránky ke stažení Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Složku na vašem počítači obsahující soubory, které chcete komprimovat (např. `alice29.txt` a `fields.c`).  

## Import jmenných prostorů

V libovolném C# souboru, kde budete pracovat se zip archivy, přidejte následující `using` direktivy:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `Archive`, možnostem ukládání a standardním I/O utilitám.

## Průvodce krok za krokem

### Krok 1: Nastavte adresář s dokumenty

Nejprve definujte složku, která obsahuje zdrojové soubory. Nahraďte zástupný text absolutní nebo relativní cestou ve vašem systému:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Použijte `Path.Combine` pro tvorbu cest platformově nezávislým způsobem.

### Krok 2: Otevřete zip soubor pro zápis

Vytvořte `FileStream`, který ukazuje na výstupní zip soubor. Proud je otevřen v režimu **Create**, který přepíše jakýkoli existující soubor se stejným názvem:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Krok 3: Připravte objekty `FileInfo` pro každý zdrojový soubor

`FileInfo` poskytuje Aspose.Zip přímý přístup k fyzickým souborům na disku. Vytvořte jednu instanci pro každý soubor, který chcete komprimovat:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Proč používat `FileInfo`?** Zabraňuje načtení celého souboru do paměti, což je zvláště užitečné u velkých souborů.

### Krok 4: Vytvořte archiv a přidejte položky

Instancujte objekt `Archive` a poté zavolejte `CreateEntry` pro každý `FileInfo`. První argument je název, pod kterým bude soubor v zipu, druhý argument je zdrojový `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 5: Uložte zip archiv s požadovaným kódováním

Nakonec archiv uložte do `FileStream`, který jste otevřeli dříve. Zde používáme ASCII kódování pro názvy položek, ale můžete přepnout na UTF‑8, pokud vaše názvy souborů obsahují ne‑ASCII znaky:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Po opuštění `using` bloků se proudy automaticky uzavřou a zip soubor je připraven k použití.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Prázdný zip soubor** | `FileInfo` ukazuje na neexistující cestu | Ověřte `dataDir` a názvy souborů; použijte `File.Exists` k kontrole před vytvořením položek. |
| **Nesprávné kódování názvu souboru** | Použití výchozího kódování u ne‑ASCII názvů | Nastavte `Encoding = Encoding.UTF8` v `ArchiveSaveOptions`. |
| **OutOfMemoryException u velkých souborů** | Načítání celého souboru do paměti | `FileInfo` streamuje soubor; ujistěte se, že nikde jinde soubor nečtete do pole bajtů. |
| **Přístup odmítnut** | Aplikace nemá právo zápisu do výstupní složky | Spusťte aplikaci s odpovídajícími právy nebo zvolte zapisovatelný adresář. |

## Často kladené otázky

**Q: Mohu přidat ochranu heslem k zip archivu?**  
A: Ano. Po vytvoření `Archive` nastavte `archive.Password = "yourPassword"` před voláním `Save`.

**Q: Je možné aktualizovat existující zip soubor?**  
A: Aspose.Zip podporuje otevření existujícího archivu pomocí `Archive.Open` a následné přidání nových položek.

**Q: Jak komprimovat soubory v ASP.NET MVC kontroleru?**  
A: Stejný kód funguje; jen zajistěte, aby výstupní proud byl vrácen jako `FileResult` klientovi.

**Q: Podporuje Aspose.Zip šifrovací algoritmy?**  
A: Podporuje standardní ZipCrypto a AES‑256 šifrování.

**Q: Co když potřebuji komprimovat složku rekurzivně?**  
A: Projděte `Directory.GetFiles` (a podadresáře) a vytvořte `FileInfo` pro každý soubor, poté je přidejte do archivu.

## Stávající sekce FAQ (zůstává beze změny)

### FAQ's

#### Q1: Je Aspose.Zip kompatibilní se všemi typy souborů?

A1: Aspose.Zip podporuje širokou škálu typů souborů, což zajišťuje univerzálnost při kompresi.

#### Q2: Mohu používat Aspose.Zip v komerčních projektech?

A2: Rozhodně! Navštivte naši [stránku nákupu](https://purchase.aspose.com/buy) a prozkoumejte licenční možnosti.

#### Q3: Jak získám podporu pro Aspose.Zip?

A3: Připojte se k naší komunitě na [fóru Aspose.Zip](https://forum.aspose.com/c/zip/37) pro pomoc a diskuze.

#### Q4: Je k dispozici bezplatná zkušební verze?

A4: Ano, můžete si stáhnout [bezplatnou zkušební verzi zde](https://releases.aspose.com/).

#### Q5: Jak získám dočasnou licenci pro Aspose.Zip?

A5: Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) pro informace o získání dočasné licence.

## Závěr

Nyní víte, **jak zipovat více souborů v C#** pomocí Aspose.Zip pro .NET, **jak přidat soubory do zipu** a proč je tato metoda ideální pro ASP.NET i další .NET aplikace. Experimentujte s různými úrovněmi komprese, kódováními a šifrovacími možnostmi, abyste archiv přizpůsobili přesně svým potřebám. Šťastné komprimování!

---

**Poslední aktualizace:** 2026-02-05  
**Testováno s:** Aspose.Zip pro .NET 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}