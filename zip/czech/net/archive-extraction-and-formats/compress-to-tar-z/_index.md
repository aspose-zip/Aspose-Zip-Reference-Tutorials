---
date: 2025-11-29
description: Naučte se, jak přidávat soubory do tar a komprimovat je do TarZ pomocí
  Aspose.Zip pro .NET – krok za krokem průvodce pro efektivní práci se soubory v .NET.
language: cs
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET
url: /net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a komprese do TarZ pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **přidat soubory do tar** a poté archiv zkomprimovat do formátu TarZ, Aspose.Zip pro .NET celý proces učiní bezproblémovým. V tomto tutoriálu vás provedeme každým krokem – od nastavení projektu po vytvoření tar archivu, přidání souborů a nakonec uložení komprimovaného .tar.z souboru. Na konci budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolné .NET aplikace.

## Rychlé odpovědi
- **Která knihovna zajišťuje tvorbu tar?** Aspose.Zip pro .NET  
- **Kolik řádků kódu?** Přibližně 15 řádků (bez komentářů)  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Mohu komprimovat složky, ne jen soubory?** Ano – můžete přidat celé adresáře pomocí smyčky.

## Co je **add files to tar**?
Přidání souborů do tar archivu je způsob, jak je zabalit do jediného, nekomprimovaného kontejneru, který zachovává strukturu adresářů a metadata souborů. Tar je klasický Unixový formát a slouží jako základ pro mnoho kompresních pracovních toků, včetně formátu TarZ použitého v tomto průvodci.

## Proč přidávat soubory do tar před kompresí do TarZ?
- **Přenositelnost** – Tar archiv funguje napříč platformami, aniž byste se museli starat o jednotlivé soubory.  
- **Rychlost** – Vytvoření tar kontejneru je rychlé; následná Z‑komprese se soustředí jen na zmenšení velikosti.  
- **Kompatibilita** – Mnoho starších nástrojů očekává `.tar` před aplikací gzip‑stylové komprese, což přesně poskytuje `.tar.z`.

## Požadavky

Než se pustíme do kódu, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalovaný. Stáhněte jej z oficiálního webu [here](https://releases.aspose.com/zip/net/).  
- Složku na vašem počítači, která obsahuje soubory, jež chcete archivovat. Nahraďte zástupnou cestu skutečnou cestou k vašemu adresáři.

## Importování jmenných prostorů

Přidejte požadované `using` direktivy na začátek vašeho C# souboru:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Postupný průvodce

### Krok 1: Definujte adresář dokumentu

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Použijte `Path.Combine`, pokud potřebujete dynamicky sestavovat cesty; zabrání tak chybějícím oddělovačům cest na různých OS.

### Krok 2: Vytvořte tar archiv a přidejte soubory

#### 2.1: Vytvořte instanci tar archivu

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Přidejte soubory do archivu  

Uvnitř `using` bloku přidejte každý soubor, který chcete zahrnout:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Můžete opakovat `CreateEntry` pro libovolný počet souborů, nebo projít adresář smyčkou a přidávat je programově.

#### 2.3: Uložte komprimovaný soubor TarZ  

Po přidání všech položek zkomprimujte tar archiv do formátu `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Výsledný soubor `archive.tar.z` bude umístěn ve stejné složce, kterou jste zadali v `dataDir`.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|---------|-------|--------|
| **File not found** | Nesprávná cesta nebo chybějící přípona souboru | Ověřte, že `dataDir` končí oddělovačem cesty a že názvy souborů jsou správné. |
| **Access denied** | Nedostatečná oprávnění k cílové složce | Spusťte aplikaci s potřebnými právy nebo zvolte zapisovatelný adresář. |
| **Compressed file is larger than expected** | Původní soubory jsou již komprimované (např. obrázky, videa) | TarZ funguje nejlépe na textových nebo logových souborech; zvažte ponechání již komprimovaných souborů beze změny. |

## Často kladené otázky

**Q: Mohu komprimovat celé složky pomocí Aspose.Zip pro .NET?**  
A: Rozhodně. Použijte smyčku `Directory.GetFiles` a pro každý soubor zavolejte `CreateEntry`, přičemž zachováte relativní cesty.

**Q: Je k dispozici zkušební verze pro Aspose.Zip pro .NET?**  
A: Ano, můžete si vyzkoušet funkce Aspose.Zip pro .NET stažením bezplatné zkušební verze [here](https://releases.aspose.com/).

**Q: Kde najdu komplexní dokumentaci pro Aspose.Zip pro .NET?**  
A: Dokumentace je dostupná [here](https://reference.aspose.com/zip/net/), poskytuje podrobné informace o funkcích a použití knihovny.

**Q: Jak získám podporu pro Aspose.Zip pro .NET?**  
A: Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37), kde můžete požádat o pomoc, sdílet své zkušenosti a spojit se s komunitou.

**Q: Mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Ano, pokud potřebujete dočasnou licenci, můžete ji získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr

Nyní jste se naučili, jak **přidat soubory do tar** a výsledek zkomprimovat do archivu TarZ pomocí Aspose.Zip pro .NET. Tento přístup vám poskytne čistý, přenosný balíček, který lze snadno přenášet, ukládat nebo dále zpracovávat. Klidně upravte úryvek tak, aby zpracovával adresáře hromadně, integroval jej do build pipeline nebo jej kombinoval s dalšími komponentami Aspose pro bohatší pracovní toky s dokumenty.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-11-29  
**Testováno s:** Aspose.Zip pro .NET 24.11  
**Autor:** Aspose  

---