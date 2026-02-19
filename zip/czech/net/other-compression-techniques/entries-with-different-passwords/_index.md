---
date: 2025-12-18
description: Naučte se, jak šifrovat zip soubory různými hesly pomocí Aspose.Zip pro
  .NET. Tento průvodce vám ukáže, jak komprimovat soubory s hesly a vytvořit archiv
  7z v C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak šifrovat soubory ZIP s různými hesly v Aspose.Zip pro .NET
url: /cs/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak šifrovat soubory ZIP s různými hesly v Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **jak šifrovat zip** archivy a při tom přiřadit každému záznamu vlastní heslo, jste na správném místě. V tomto tutoriálu projdeme přesné kroky k vytvoření 7‑zip archivu, kde je každý soubor chráněn unikátním heslem, pomocí knihovny Aspose.Zip pro .NET. Na konci pochopíte, proč je šifrování na úrovni záznamu důležité, jak to nastavit a jak výsledek ověřit ve svých projektech.

## Rychlé odpovědi
- **Co znamená „encrypt zip“?** Znamená to aplikovat ochranu založenou na hesle (AES nebo ZipCrypto) na obsah ZIP/7z archivu.  
- **Může mít každý záznam jiné heslo?** Ano — Aspose.Zip vám umožňuje přiřadit odlišná hesla ke každému souboru.  
- **Jaké verze .NET jsou podporovány?** Všechny moderní .NET Framework, .NET Core a .NET 5/6 verze.  
- **Potřebuji licenci pro produkci?** Pro produkční použití je vyžadována komerční licence; k dispozici je bezplatná zkušební verze.  
- **Jaký kompresní formát se používá v příkladu?** Vzor vytváří 7z archiv s AES‑256 šifrováním.

## Co je „how to encrypt zip“ s Aspose.Zip?

Šifrování souboru ZIP (nebo 7z) znamená zabezpečit jeho položky tak, aby nebyly otevřeny bez správného hesla. Aspose.Zip pro .NET podporuje jak klasický ZipCrypto, tak silnější AES šifrování a umožňuje specifikovat nastavení šifrování pro každý záznam zvlášť, což poskytuje detailní kontrolu nad bezpečností.

## Proč používat různá hesla pro každý záznam?

- **Segmentace zabezpečení:** Pokud je jedno heslo kompromitováno, ostatní soubory zůstávají chráněny.  
- **Soulad s předpisy:** Některá odvětví vyžadují oddělené přihlašovací údaje pro různé kategorie dat.  
- **Uživatelsky specifický přístup:** Můžete distribuovat jeden archiv více uživatelům, přičemž každý odemkne jen soubory, ke kterým má oprávnění.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalovaný — viz oficiální [documentation](https://reference.aspose.com/zip/net/) pro stažení a instrukce instalace.  
- Složku na vašem počítači, kde budete uchovávat zdrojové soubory (tzv. „Document Directory“).  
- Základní znalosti C# a Visual Studio (nebo vašeho preferovaného .NET IDE).

## Import Namespaces

Začínáme načtením jmenných prostorů, které obsahují potřebné třídy.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Nastavte svůj Document Directory

Definujte cestu, která obsahuje soubory, jež chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte záznamy s různými hesly

Zde je jádro tutoriálu. Otevřeme nový 7z soubor, vytvoříme tři objekty `FileInfo` a přidáme každý jako záznam s vlastním AES heslem.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Jak to funguje

- `SevenZipArchive` je kontejner pro 7‑z archiv.  
- `CreateEntry` přijímá název záznamu, zdrojový soubor, příznak pro přepsání a objekt `SevenZipEntrySettings`.  
- V rámci `SevenZipEntrySettings` poskytujeme dva objekty nastavení: jeden pro kompresi (`SevenZipStoreCompressionSettings`) a jeden pro šifrování (`SevenZipAESEncryptionSettings`).  
- Každé volání předává **jiné heslo** (`"test1"`, `"test2"`, `"test3"`), čímž dosahuje ochrany na úrovni jednotlivých záznamů.

## Krok 3: Ověření

Po uložení archivu můžete vypsat jednoduchou potvrzovací zprávu.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Spusťte program a poté zkuste otevřít `archive.7z` pomocí nástroje jako 7‑Zip. Budete vyzváni k zadání hesla pro každý záznam, což potvrdí, že hesla jsou skutečně odlišná.

## Časté problémy a řešení

| Problém | Důvod | Oprava |
|-------|--------|-----|
| **Chyba nesprávného hesla** | Řetězec hesla obsahuje nadbytečné mezery nebo neviditelné znaky. | Ořízněte řetězce hesel (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archiv se neotevírá ve starších nástrojích** | Některé starší ZIP nástroje nepodporují AES‑256 šifrování používané v 7z. | Použijte moderní extraktor (7‑Zip 19.00+). |
| **Soubor nebyl přidán do archivu** | Cesta ke zdrojovému souboru je špatná nebo soubor neexistuje. | Ověřte `dataDir` a názvy souborů, nebo použijte `Path.Combine(dataDir, "data1.bin")`. |

## Často kladené otázky

### Q1: Je Aspose.Zip pro .NET kompatibilní se všemi verzemi .NET?

A1: Ano, Aspose.Zip pro .NET je navržen tak, aby se bez problémů integroval se všemi verzemi .NET frameworku.

### Q2: Mohu používat Aspose.Zip pro .NET ve svých komerčních projektech?

A2: Rozhodně! Aspose.Zip pro .NET nabízí komerční licence a více informací o nákupu najdete [zde](https://purchase.aspose.com/buy).

### Q3: Je k dispozici bezplatná zkušební verze?

A3: Ano, můžete si vyzkoušet funkce Aspose.Zip pro .NET pomocí bezplatné zkušební verze. Začněte [zde](https://releases.aspose.com/).

### Q4: Jak mohu získat podporu pro Aspose.Zip pro .NET?

A4: Pro jakékoli dotazy nebo pomoc navštivte [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Můžu používat Aspose.Zip pro .NET bez trvalé licence?

A5: Ano, můžete získat dočasnou licenci pro krátkodobé potřeby. Více podrobností najdete [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Právě jste se naučili **jak šifrovat zip** archivy s hesly na úrovni jednotlivých záznamů pomocí Aspose.Zip pro .NET. Tato technika vám poskytuje flexibilitu chránit každý soubor samostatně, což splňuje přísnější bezpečnostní požadavky a usnadňuje distribuci specifickou pro jednotlivé uživatele. Nebojte se experimentovat s dalšími nastaveními komprese, většími sadami souborů nebo integrovat tuto logiku do webové služby, která generuje zabezpečené archivy za běhu.

---

**Poslední aktualizace:** 2025-12-18  
**Testováno s:** Aspose.Zip pro .NET 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}