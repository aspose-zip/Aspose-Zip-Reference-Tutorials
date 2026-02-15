---
date: 2026-02-15
description: Naučte se, jak přidávat soubory do tar a komprimovat je do TarZ pomocí
  Aspose.Zip pro .NET – krok za krokem průvodce efektivní manipulací se soubory v
  .NET.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

here](https://purchase.aspose.com/temporary-license/).

Translate.

Next "## Conclusion" -> "## Závěr"

Paragraph translate.

Then horizontal rule "---" keep.

Then "**Last Updated:** 2026-02-15" translate label.

"**Tested With:** Aspose.Zip for .NET 24.11" translate label.

"**Author:** Aspose" translate label.

Then closing shortcodes.

Finally backtop button shortcode unchanged.

Make sure to keep markdown formatting.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a komprese do TarZ pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **přidat soubory do tar** a poté archiv komprimovat do formátu TarZ, Aspose.Zip pro .NET celý proces usnadňuje. V tomto tutoriálu projdeme každý krok – od nastavení projektu po vytvoření tar archivu, přidání souborů a nakonec uložení komprimovaného .tar.z souboru. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do jakékoli .NET aplikace.

## Rychlé odpovědi
- **Která knihovna zajišťuje tvorbu tar?** Aspose.Zip for .NET  
- **Kolik řádků kódu?** Přibližně 15 řádků (bez komentářů)  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkci.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Mohu komprimovat složky, ne jen soubory?** Ano – můžete přidat celé adresáře pomocí smyčky.

## Co je **add files to tar**?

Přidání souborů do tar archivu je zabalení do jediného, nekomprimovaného kontejneru, který zachovává strukturu adresářů a metadata souborů. Tar je klasický Unixový formát a slouží jako základ pro mnoho kompresních workflow, včetně formátu TarZ použitého v tomto průvodci.

## Proč přidávat soubory do tar před kompresí do TarZ?

- **Portabilita** – Tar archiv funguje napříč platformami, aniž byste se museli starat o jednotlivé soubory.  
- **Rychlost** – Vytvoření tar kontejneru je rychlé; následná Z‑komprese se soustředí jen na zmenšení velikosti.  
- **Kompatibilita** – Mnoho starších nástrojů očekává `.tar` před aplikací gzip‑stylu komprese, což přesně poskytuje `.tar.z`.

### Proč je to důležité pro .NET vývojáře
Použití tar kontejneru vám umožní udržet .NET kód jednoduchý a deterministický. Archiv můžete generovat v paměti, streamovat přímo do odpovědi, nebo uložit na disk bez nutnosti pracovat s dočasnými zip soubory. Tento vzor je zvláště užitečný pro build pipeline, agregaci logů nebo když potřebujete doručit sadu konfiguračních souborů Linux‑ové službě.

## Požadavky

Než se pustíme do kódu, ujistěte se, že máte:

- **Aspose.Zip for .NET** nainstalovaný. Stáhněte jej z oficiální stránky [here](https://releases.aspose.com/zip/net/).  
- Složku na vašem počítači, která obsahuje soubory, jež chcete archivovat. Nahraďte zástupnou cestu skutečným adresářem.

## Importování jmenných prostorů

Přidejte požadované `using` direktivy na začátek vašeho C# souboru:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tip:** Použijte `Path.Combine`, pokud potřebujete dynamicky sestavovat cesty; zabráníte tak chybějícím oddělovačům cest na různých OS.

## Průvodce krok za krokem

### Krok 1: Definujte adresář dokumentu

```csharp
string dataDir = "Your Document Directory";
```

> **Proč je tento krok důležitý:** `dataDir` slouží jako základní umístění pro každý soubor, který přidáte. Uložení do jedné proměnné usnadňuje údržbu kódu a jeho opakované použití napříč více archivy.

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

Uvnitř bloku `using` přidejte každý soubor, který chcete zahrnout:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Můžete opakovat `CreateEntry` pro libovolný počet souborů, nebo projít adresář smyčkou a přidávat je programově. Například smyčka `foreach (var file in Directory.GetFiles(dataDir))` vám umožní zpracovat libovolný počet souborů při zachování jejich relativních cest.

#### 2.3: Uložte komprimovaný TarZ soubor  

Po přidání všech položek komprimujte tar archiv do formátu `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Výsledný soubor `archive.tar.z` bude umístěn ve stejné složce, kterou jste zadali v `dataDir`. Nyní můžete tento jediný, komprimovaný balíček doručit jakémukoli systému, který rozumí TarZ.

## Časté problémy a řešení

| Problém | Důvod | Oprava |
|-------|--------|-----|
| **Soubor nenalezen** | Špatná cesta nebo chybějící přípona souboru | Ověřte, že `dataDir` končí oddělovačem cesty a že názvy souborů jsou správné. |
| **Přístup odmítnut** | Nedostatečná oprávnění ve cílové složce | Spusťte aplikaci s odpovídajícími právy nebo vyberte zapisovatelný adresář. |
| **Komprimovaný soubor je větší než očekáváno** | Původní soubory jsou již komprimované (např. obrázky, videa) | TarZ funguje nejlépe na textových nebo log souborech; zvažte ponechání již komprimovaných souborů beze změny. |

### Běžné úskalí, na která si dát pozor
- **Chybějící koncová lomítka** – Pokud `dataDir` nekončí `\` nebo `/`, spojování řetězců vytvoří neplatnou cestu.  
- **Velké adresáře** – Přidání tisíců souborů může spotřebovat paměť; zvažte streamování položek nebo použití přetížení `TarArchive`, které zapisuje přímo do souborového streamu.  
- **Problémy s kódováním** – Názvy souborů mimo ASCII mohou vyžadovat explicitní nastavení kódování; Aspose.Zip ve výchozím nastavení respektuje UTF‑8, ale ověřte to na cílové platformě.

## Často kladené otázky

**Q: Mohu komprimovat celé složky pomocí Aspose.Zip pro .NET?**  
A: Rozhodně. Použijte smyčku `Directory.GetFiles` a pro každý soubor zavolejte `CreateEntry`, přičemž zachováte relativní cesty.

**Q: Je k dispozici zkušební verze pro Aspose.Zip pro .NET?**  
A: Ano, můžete si vyzkoušet možnosti Aspose.Zip pro .NET stažením bezplatné zkušební verze [here](https://releases.aspose.com/).

**Q: Kde najdu komplexní dokumentaci pro Aspose.Zip pro .NET?**  
A: Dokumentace je dostupná [here](https://reference.aspose.com/zip/net/), poskytuje podrobné informace o funkcích a použití knihovny.

**Q: Jak získám podporu pro Aspose.Zip pro .NET?**  
A: Navštivte [Aspose.Zip forum](https://forum.aspose.com/c/zip/37), kde můžete požádat o pomoc, sdílet své zkušenosti a spojit se s komunitou.

**Q: Mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Ano, pokud potřebujete dočasnou licenci, můžete ji získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr

Nyní jste se naučili, jak **přidat soubory do tar** a komprimovat výsledek do TarZ archivu pomocí Aspose.Zip pro .NET. Tento přístup vám poskytuje čistý, přenosný balíček, který lze snadno přenést, uložit nebo dále zpracovat. Klidně upravte úryvek pro dávkové zpracování adresářů, integraci do build pipeline nebo kombinaci s dalšími Aspose komponentami pro bohatší workflow s dokumenty.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}