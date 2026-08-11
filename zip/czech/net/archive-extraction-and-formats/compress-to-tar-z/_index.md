---
date: 2026-05-30
description: Zjistěte, jak přidat soubory do tar a komprimovat je do TarZ pomocí Aspose.Zip
  pro .NET – krok za krokem průvodce pro efektivní práci se soubory v .NET.
keywords:
- add files to tar
- add directory to tar
- compress folders to tar
- compress files .net
linktitle: Komprimace do TarZ
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to add files to tar and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: Add files to tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/) ,
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a komprese do TarZ pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **add files to tar** a poté archiv komprimovat do formátu TarZ, Aspose.Zip pro .NET celý proces zjednoduší. V tomto tutoriálu vás provedeme všemi kroky – od nastavení projektu po vytvoření tar archivu, přidání souborů a nakonec uložení komprimovaného .tar.z souboru. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do jakékoli .NET aplikace, ať už pracujete s několika konfiguračními soubory nebo s celým stromem adresářů.

## Rychlé odpovědi
- **Která knihovna zajišťuje tvorbu tar?** Aspose.Zip for .NET  
- **Kolik řádků kódu?** About 15 lines (excluding comments)  
- **Potřebuji licenci pro testování?** A free trial is available; a license is required for production.  
- **Podporované verze .NET?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **Mohu komprimovat složky, nejen soubory?** Yes – you can add entire directories with a loop.  

## Co je **add files to tar**?
Operace **add files to tar** seskupí vybrané soubory do jednoho, nekomprimovaného tar kontejneru při zachování hierarchie adresářů a metadat.  
Načtení souborů do tar archivu je prvním krokem před jakoukoliv další kompresí, jako je TarZ, protože formát tar poskytuje deterministický, platformně nezávislý balíček, na který kompresní algoritmy mohou efektivně pracovat.

## Proč přidat soubory do tar před kompresí do TarZ?
Vytvoření tar kontejneru nejprve oddělí logiku balení od kroku komprese, což přináší tři měřitelné výhody. Oddělením těchto fází získáte předvídatelný, opakovatelný archiv, který lze komprimovat nezávisle, což usnadňuje měření poměrů komprese a opětovné použití stejného tar pro různé kompresní algoritmy.  
1. **Portabilita** – Soubor `.tar` lze rozbalit na libovolném Unix‑like systému bez dalších knihoven.  
2. **Rychlost** – Vytvoření tar je v podstatě operace kopírování proudu; následná Z‑komprese se pak soustředí výhradně na zmenšení velikosti, typicky snižuje o 30‑70 % původních dat.  
3. **Kompatibilita** – Mnoho starších nástrojů (např. `tar`, `gzip`) očekává `.tar` před aplikací gzip‑stylové komprese, což přesně představuje příponu `.tar.z`.  

### Proč je to důležité pro .NET vývojáře
Použití tar kontejneru vám umožní udržet .NET kód jednoduchý a deterministický. Archiv můžete vytvořit v paměti, streamovat přímo do odpovědi nebo uložit na disk, aniž byste museli pracovat s dočasnými zip soubory. Tento vzor je zvláště užitečný pro build pipeline, agregaci logů nebo když potřebujete odeslat sadu konfiguračních souborů na Linux‑based službu.

## Požadavky

Než se ponoříme do kódu, ujistěte se, že máte:

- **Aspose.Zip for .NET** nainstalovaný. Stáhněte jej z oficiální stránky [zde](https://releases.aspose.com/zip/net/).  
- Složku na vašem počítači, která obsahuje soubory, které chcete archivovat. Nahraďte zástupnou cestu skutečným adresářem.

## Importování jmenných prostorů

Přidejte požadované `using` příkazy na začátek vašeho C# souboru:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Tip:** Použijte `Path.Combine`, pokud potřebujete dynamicky vytvářet cesty; vyhnete se tak chybějícím oddělovačům cest na různých OS.

## Jak přidat soubory do tar pomocí Aspose.Zip pro .NET?

Načtěte zdrojový adresář, vytvořte instanci `TarArchive`, přidejte každý soubor (nebo celý podadresář) a nakonec zavolejte `Save` s příznakem komprese TarZ. Tento end‑to‑end tok vyžaduje jen několik řádků kódu a funguje na všech podporovaných .NET runtimech.

### Definice kotvy
`TarArchive` třída je jádrový objekt Aspose.Zip, který představuje tar kontejner, který můžete naplnit položkami.

### Průvodce krok za krokem

### Krok 1: Definujte adresář dokumentů

```csharp
string dataDir = "Your Document Directory";
```

> **Proč je tento krok důležitý:** `dataDir` slouží jako základní umístění pro každý soubor, který přidáte. Uložení do jediné proměnné usnadňuje údržbu kódu a jeho opětovné použití v několika archivech.

### Krok 2: Vytvořte Tar archiv a přidejte soubory

#### 2.1: Vytvořte instanci Tar archivu

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` zajišťuje, že objekt `TarArchive` je řádně uvolněn, čímž se uvolní souborové handly nebo paměťové buffery.

#### 2.2: Přidejte soubory do archivu  

`CreateEntry` přidá soubor do tar archivu, určuje jeho název a obsahový stream.  

Uvnitř bloku `using` přidejte každý soubor, který chcete zahrnout:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Můžete opakovat `CreateEntry` pro libovolný počet souborů, nebo projít adresář smyčkou a přidávat je programově. Například smyčka `foreach (var file in Directory.GetFiles(dataDir))` vám umožní zpracovat libovolný počet souborů při zachování jejich relativních cest.

#### 2.3: Uložte komprimovaný TarZ soubor  

`Save` zapíše archiv na disk a použije vybraný kompresní formát.  

Po přidání všech položek komprimujte tar archiv do formátu `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Výsledný soubor `archive.tar.z` bude umístěn ve stejné složce, kterou jste zadali v `dataDir`. Nyní můžete tento jediný komprimovaný balíček odeslat na jakýkoli systém, který rozumí TarZ.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Soubor nenalezen** | Špatná cesta nebo chybějící přípona souboru | Ověřte, že `dataDir` končí oddělovačem cesty a názvy souborů jsou správné. |
| **Přístup odepřen** | Nedostatečná oprávnění k cílové složce | Spusťte aplikaci s odpovídajícími právy nebo vyberte zapisovatelný adresář. |
| **Komprimovaný soubor je větší než očekávané** | Původní soubory jsou již komprimované (např. obrázky, videa) | TarZ funguje nejlépe na textových nebo log souborech; zvažte ponechání již komprimovaných souborů beze změny. |

### Běžné úskalí, na která si dát pozor
- **Chybějící koncová lomítko** – Pokud `dataDir` nekončí `\` nebo `/`, spojování řetězců vytvoří neplatnou cestu.  
- **Velké adresáře** – Přidání tisíců souborů může spotřebovat paměť; zvažte streamování položek nebo použití přetížení `TarArchive`, které zapisuje přímo do souborového streamu.  
- **Problémy s kódováním** – Názvy souborů mimo ASCII mohou vyžadovat explicitní nastavení kódování; Aspose.Zip ve výchozím nastavení respektuje UTF-8, ale ověřte to na cílové platformě.

## Často kladené otázky

**Q: Mohu komprimovat celé složky pomocí Aspose.Zip pro .NET?**  
A: Rozhodně. Použijte smyčku `Directory.GetFiles` a zavolejte `CreateEntry` pro každý soubor, přičemž zachováte relativní cesty.

**Q: Je k dispozici zkušební verze pro Aspose.Zip pro .NET?**  
A: Ano, můžete prozkoumat možnosti Aspose.Zip pro .NET stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

**Q: Kde najdu komplexní dokumentaci pro Aspose.Zip pro .NET?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/), poskytuje podrobné informace o funkcích knihovny a jejím použití.

**Q: Jak mohu získat podporu pro Aspose.Zip pro .NET?**  
A: Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37), kde můžete získat pomoc, sdílet zkušenosti a spojit se s komunitou.

**Q: Mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Ano, pokud potřebujete dočasnou licenci, můžete ji získat [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Nyní jste se naučili, jak **add files to tar** a komprimovat výsledek do TarZ archivu pomocí Aspose.Zip pro .NET. Tento přístup vám poskytuje čistý, přenosný balíček, který lze snadno přenést, uložit nebo dále zpracovat. Klidně upravte úryvek pro dávkové zpracování adresářů, integraci do build pipeline nebo kombinaci s dalšími komponentami Aspose pro bohatší workflow dokumentů.

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
