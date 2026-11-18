---
date: 2026-11-18
description: Naučte se, jak vytvořit tar archivy a komprimovat je do TarZ pomocí Aspose.Zip
  pro .NET – podrobný návod krok za krokem pro efektivní práci se soubory v .NET.
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: Komprese do TarZ
og_description: Naučte se, jak vytvořit tar archivy a komprimovat je do TarZ pomocí
  Aspose.Zip pro .NET. Tento návod vás provede přidáváním souborů, adresářů a efektivní
  kompresí.
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: Jak vytvořit tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Jak vytvořit tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a komprese do TarZ pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **add files to tar** a poté archiv komprimovat do formátu TarZ, Aspose.Zip pro .NET celý proces usnadní. V tomto tutoriálu vás provedeme všemi kroky – od nastavení projektu po vytvoření tar archivu, přidání souborů a nakonec uložení komprimovaného .tar.z souboru. Na konci budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolné .NET aplikace, ať už pracujete s několika konfiguračními soubory nebo s celým stromem adresářů.

## Rychlé odpovědi
- **Která knihovna zajišťuje tvorbu tar?** Aspose.Zip pro .NET  
- **Kolik řádků kódu?** Přibližně 15 řádků (bez komentářů)  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkci.  
- **Podporované verze .NET?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10  
- **Mohu komprimovat složky, ne jen soubory?** Ano – můžete přidat celé adresáře pomocí smyčky.

## Co je **add files to tar**?
**Add files to tar** je proces seskupení vybraných souborů do jediného, nekomprimovaného tar kontejneru při zachování hierarchie adresářů a metadat. Formát tar vytváří deterministický, platformově nezávislý balíček, na který mohou následně efektivně působit kompresní algoritmy, což ho činí ideálním pro distribuci napříč platformami.

## Jak vytvořit tar archivy pomocí Aspose.Zip pro .NET?

Třída `TarArchive` představuje tar kontejner, který může obsahovat více souborových položek. Načtěte zdrojový adresář, vytvořte instanci `TarArchive`, přidejte každý soubor (nebo celý podadresář) a nakonec zavolejte `Save` s příznakem komprese TarZ. Proces je přímočarý, vyžaduje jen několik řádků kódu a funguje konzistentně na všech podporovaných .NET runtimech, včetně .NET Framework a .NET Core.

Třída `TarArchive` je jádrový objekt Aspose.Zip, který představuje tar kontejner, který můžete naplnit položkami. Použitím této třídy můžete generovat tar soubory kompletně v paměti, streamovat je přímo do odpovědi nebo je zapisovat na disk bez dočasných zip souborů.

## Proč přidat soubory do tar před kompresí do TarZ?

Vytvoření tar kontejneru nejprve odděluje balení od komprese, což přináší tři měřitelné výhody. Oddělením těchto fází získáte předvídatelný, opakovatelný archiv, který lze komprimovat nezávisle, což usnadňuje měření kompresních poměrů a opětovné použití stejného tar souboru pro různé kompresní algoritmy.

1. **Přenositelnost** – Soubor `.tar` lze rozbalit na libovolném Unix‑like systému bez dalších knihoven.  
2. **Rychlost** – Vytvoření tar je v podstatě operace kopírování proudu; následná Z‑komprese se pak soustředí výhradně na zmenšení velikosti, typicky snižuje **30‑70 %** původních dat.  
3. **Kompatibilita** – Mnoho starších nástrojů (např. `tar`, `gzip`) očekává `.tar` před aplikací gzip‑stylu komprese, což přesně představuje rozšíření `.tar.z`.

### Proč je to důležité pro vývojáře .NET
Použití tar kontejneru vám umožní udržet .NET kód jednoduchý a deterministický. Můžete generovat archiv v paměti, streamovat jej přímo do odpovědi nebo jej uložit na disk bez nutnosti dočasných zip souborů. Tento vzor je zvláště užitečný pro build pipeline, agregaci logů nebo když potřebujete odeslat sadu konfiguračních souborů na Linux‑based službu.

## Požadavky

Než se pustíme do kódu, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalováno. Stáhněte jej z oficiální stránky [here](https://releases.aspose.com/zip/net/).  
- Složku na vašem počítači, která obsahuje soubory, jež chcete archivovat. Nahraďte zástupnou cestu skutečným adresářem.

## Importujte jmenné prostory

Přidejte požadované `using` direktivy na začátek vašeho C# souboru:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Pro tip:** Použijte `Path.Combine`, pokud potřebujete dynamicky sestavovat cesty; tím se vyhnete chybějícím oddělovačům cest na různých OS.

## Jak přidat soubory do tar pomocí Aspose.Zip pro .NET?

Metoda `CreateEntry` přidává novou souborovou položku do tar archivu se zadaným názvem a obsahem proudu. Načtěte zdrojový adresář, vytvořte instanci `TarArchive`, přidejte každý soubor (nebo celý podadresář) a nakonec zavolejte `Save` s příznakem komprese TarZ. Tento workflow zůstává stručný, typicky pod 20 řádků, a funguje na všech podporovaných .NET runtimech, poskytujíc spolehlivý způsob balení a komprese dat.

Metoda `Save` zapisuje archiv na disk a volitelně aplikuje kompresi.

### Definiční kotva
Třída `TarArchive` je jádrový objekt Aspose.Zip, který představuje tar kontejner, který můžete naplnit položkami.

### Průvodce krok za krokem

#### Krok 1: Definujte adresář dokumentu

```csharp
string dataDir = "Your Document Directory";
```

> **Proč je tento krok důležitý:** `dataDir` slouží jako základní umístění pro každý soubor, který přidáte. Uložení jej v jediné proměnné usnadňuje údržbu kódu a jeho opětovné použití v různých archivech.

#### Krok 2: Vytvořte Tar archiv a přidejte soubory

##### 2.1: Vytvořte instanci Tar archivu

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` zajišťuje, že objekt `TarArchive` je řádně uvolněn, čímž se uvolní souborové handly nebo paměťové buffery.

##### 2.2: Přidejte soubory do archivu  

`CreateEntry` přidává soubor do tar archivu, určuje jeho název a obsahový proud.  

Uvnitř bloku `using` přidejte každý soubor, který chcete zahrnout:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Můžete opakovat `CreateEntry` pro libovolný počet souborů, nebo projít adresář smyčkou a přidávat je programově. Například smyčka `foreach (var file in Directory.GetFiles(dataDir))` vám umožní zpracovat libovolný počet souborů při zachování jejich relativních cest.

##### 2.3: Uložte komprimovaný soubor TarZ  

`Save` zapisuje archiv na disk a aplikuje vybraný kompresní formát.  

Po přidání všech položek komprimujte tar archiv do formátu `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Výsledný soubor `archive.tar.z` bude umístěn ve stejné složce, kterou jste zadali v `dataDir`. Nyní můžete tento jediný komprimovaný balíček odeslat na libovolný systém, který rozumí TarZ.

## Časté problémy a řešení

| Problém | Důvod | Oprava |
|-------|--------|-----|
| **Soubor nenalezen** | Špatná cesta nebo chybějící přípona souboru | Ověřte, že `dataDir` končí oddělovačem cesty a názvy souborů jsou správné. |
| **Přístup odmítnut** | Nedostatečná oprávnění ve cílové složce | Spusťte aplikaci s odpovídajícími právy nebo vyberte zapisovatelný adresář. |
| **Komprimovaný soubor je větší než očekáváno** | Původní soubory jsou již komprimované (např. obrázky, videa) | TarZ funguje nejlépe na textových nebo logových souborech; zvažte ponechání již komprimovaných souborů beze změny. |

### Běžné úskalí, na která si dát pozor
- **Chybějící koncová lomítka** – Pokud `dataDir` nekončí `\` nebo `/`, spojování řetězců vytvoří neplatnou cestu.  
- **Velké adresáře** – Přidání tisíců souborů může spotřebovat paměť; zvažte streamování položek nebo použití přetížení `TarArchive`, které zapisuje přímo do souborového proudu.  
- **Problémy s kódováním** – Názvy souborů mimo ASCII mohou vyžadovat explicitní nastavení kódování; Aspose.Zip ve výchozím nastavení respektuje UTF‑8, ale ověřte to na cílové platformě.

## Často kladené otázky

**Q:** Mohu komprimovat celé složky pomocí Aspose.Zip pro .NET?  
**A:** Ano. Použijte smyčku `Directory.GetFiles` a pro každý soubor zavolejte `CreateEntry`, přičemž zachováte relativní cesty.

**Q:** Je k dispozici zkušební verze Aspose.Zip pro .NET?  
**A:** Ano, můžete si vyzkoušet funkce Aspose.Zip pro .NET stažením bezplatné zkušební verze [here](https://releases.aspose.com/).

**Q:** Kde najdu komplexní dokumentaci k Aspose.Zip pro .NET?  
**A:** Dokumentace je k dispozici [here](https://reference.aspose.com/zip/net/), poskytuje podrobné informace o funkcích a použití knihovny.

**Q:** Jak získám podporu pro Aspose.Zip pro .NET?  
**A:** Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37), kde můžete požádat o pomoc, sdílet zkušenosti a spojit se s komunitou.

**Q:** Mohu získat dočasnou licenci pro Aspose.Zip pro .NET?  
**A:** Ano, pokud potřebujete dočasnou licenci, můžete ji získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr

Nyní jste se naučili, jak **add files to tar** a komprimovat výsledek do TarZ archivu pomocí Aspose.Zip pro .NET. Tento přístup vám poskytuje čistý, přenosný balíček, který lze snadno přenést, uložit nebo dále zpracovat. Klidně upravte úryvek pro dávkové zpracování adresářů, integraci do build pipeline nebo kombinaci s dalšími komponentami Aspose pro bohatší workflow dokumentů.

---

**Poslední aktualizace:** 2026-11-18  
**Testováno s:** Aspose.Zip pro .NET 24.11  
**Autor:** Aspose

## Související tutoriály

- [Přidání více souborů do tar a vytvoření tar.gz archivu pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak komprimovat více souborů tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Extrahování archivů a formáty](/zip/net/archive-extraction-and-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}