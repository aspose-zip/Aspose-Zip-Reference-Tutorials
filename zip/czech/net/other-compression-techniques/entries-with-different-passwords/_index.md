---
date: 2026-02-28
description: Naučte se komprimovat soubory s heslem a šifrovat ZIP archivy pomocí
  Aspose.Zip pro .NET, včetně ochrany heslem formátu 7z a hesla pro jednotlivé soubory
  v ZIP v C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat soubory s heslem a šifrovat položky ZIP různými hesly pomocí
  Aspose.Zip pro .NET
url: /cs/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

 preserved with pipes.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat soubory s heslem a šifrovat položky ZIP s různými hesly pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **komprimovat soubory s heslem** a přiřadit každé položce vlastní heslo, jste na správném místě. V tomto tutoriálu vás provedeme přesnými kroky k vytvoření 7‑zip archivu, kde je každý soubor chráněn jedinečným heslem, pomocí knihovny Aspose.Zip pro .NET. Na konci pochopíte, proč je šifrování na úrovni položky důležité, jak jej nastavit a jak výsledek ověřit ve svých projektech.

## Rychlé odpovědi
- **Co znamená „encrypt zip“?** Znamená to aplikaci ochrany založené na hesle (AES nebo ZipCrypto) na obsah ZIP/7z archivu.  
- **Může mít každá položka jiné heslo?** Ano—Aspose.Zip vám umožní přiřadit různá hesla jednotlivým souborům.  
- **Které verze .NET jsou podporovány?** Všechny moderní verze .NET Framework, .NET Core a .NET 5/6.  
- **Potřebuji licenci pro produkční použití?** Pro produkční použití je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Jaký kompresní formát je v příkladu použit?** Vzorek vytváří 7z archiv s AES‑256 šifrováním.

## Jak komprimovat soubory s heslem pomocí Aspose.Zip pro .NET
V této sekci odpovíme přímo na hlavní otázku a připravíme půdu pro následující krok‑za‑krokem průvodce.

## Co je „how to encrypt zip“ s Aspose.Zip?
Šifrování ZIP (nebo 7z) souboru znamená zabezpečení jeho položek tak, aby nebylo možné je otevřít bez správného hesla. Aspose.Zip pro .NET podporuje jak klasické ZipCrypto, tak silnější AES šifrování a umožňuje nastavit šifrovací parametry pro každou položku, což vám poskytuje detailní kontrolu nad zabezpečením.

## Proč používat různá hesla pro každou položku?
- **Segementace zabezpečení:** Pokud je jedno heslo kompromitováno, ostatní soubory zůstávají chráněny.  
- **Soulad s předpisy:** Některá odvětví vyžadují samostatné přihlašovací údaje pro různé kategorie dat.  
- **Uživatelsky specifický přístup:** Můžete distribuovat jeden archiv více uživatelům, přičemž každý odemkne jen soubory, ke kterým má oprávnění.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalovaný – viz oficiální [dokumentace](https://reference.aspose.com/zip/net/) pro stažení a instrukce instalace.  
- Složku ve vašem počítači, kde budete uchovávat zdrojové soubory („Document Directory“).  
- Základní znalost C# a Visual Studio (nebo vašeho preferovaného .NET IDE).

## Importovat jmenné prostory

Začneme načtením jmenných prostorů, které obsahují třídy, jež budeme potřebovat.

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

## Krok 1: Nastavte svůj Document Directory

Definujte cestu, která obsahuje soubory, jež chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte položky s různými hesly

Zde je jádro tutoriálu. Otevřeme nový 7z soubor, vytvoříme tři objekty `FileInfo` a přidáme je jako položky s vlastním AES heslem.

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
- `CreateEntry` přijímá název položky, zdrojový soubor, příznak pro přepsání a objekt `SevenZipEntrySettings`.  
- V rámci `SevenZipEntrySettings` poskytujeme dva objekty nastavení: jeden pro kompresi (`SevenZipStoreCompressionSettings`) a jeden pro šifrování (`SevenZipAESEncryptionSettings`).  
- Každé volání předává **jiné heslo** (`"test1"`, `"test2"`, `"test3"`), čímž dosahuje ochrany na úrovni položky.

## Krok 3: Ověření

Po uložení archivu můžete vypsat jednoduchou potvrzovací zprávu.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Spusťte program a poté zkuste otevřít `archive.7z` nástrojem jako 7‑Zip. Požádá vás o heslo pro každou položku, čímž potvrdí, že hesla jsou skutečně odlišná.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| **Chyba nesprávného hesla** | Řetězec hesla obsahuje nadbytečné mezery nebo neviditelné znaky. | Ořízněte řetězce hesla (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archiv se neotevírá ve starších nástrojích** | Některé starší ZIP nástroje nepodporují AES‑256 šifrování používané v 7z. | Použijte moderní extraktor (7‑Zip 19.00+). |
| **Soubor nebyl přidán do archivu** | Cesta ke zdrojovému souboru je špatná nebo soubor neexistuje. | Ověřte `dataDir` a názvy souborů, nebo použijte `Path.Combine(dataDir, "data1.bin")`. |

## Často kladené otázky

### Q1: Je Aspose.Zip pro .NET kompatibilní se všemi verzemi .NET?

A1: Ano, Aspose.Zip pro .NET je navržen tak, aby se bez problémů integroval se všemi verzemi .NET frameworku.

### Q2: Mohu používat Aspose.Zip pro .NET ve svých komerčních projektech?

A2: Ano! Aspose.Zip pro .NET nabízí komerční licence a více informací o nákupu najdete [zde](https://purchase.aspose.com/buy).

### Q3: Je k dispozici bezplatná zkušební verze?

A3: Ano, můžete prozkoumat funkce Aspose.Zip pro .NET s bezplatnou zkušební verzí. Začněte [zde](https://releases.aspose.com/).

### Q4: Jak mohu získat podporu pro Aspose.Zip pro .NET?

A4: Pro jakékoli dotazy nebo pomoc navštivte [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Mohu používat Aspose.Zip pro .NET bez trvalé licence?

A5: Ano, můžete získat dočasnou licenci pro své krátkodobé potřeby. Více informací najdete [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Právě jste se naučili **jak komprimovat soubory s heslem** a šifrovat ZIP archivy s hesly na úrovni položky pomocí Aspose.Zip pro .NET. Tato technika vám poskytuje flexibilitu chránit každý soubor samostatně, splňovat přísnější bezpečnostní požadavky a zjednodušit distribuci specifickou pro uživatele. Klidně experimentujte s dalšími nastaveními komprese, většími sadami souborů nebo integrujte tuto logiku do webové služby, která za běhu generuje zabezpečené archivy.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}