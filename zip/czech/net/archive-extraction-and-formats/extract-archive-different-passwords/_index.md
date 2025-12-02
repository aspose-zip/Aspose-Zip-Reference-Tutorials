---
date: 2025-12-01
description: Naučte se, jak rozbalit zip s heslem pomocí Aspose.Zip pro .NET a efektivně
  zpracovávat více položek chráněných heslem.
language: cs
linktitle: Extracting Archive Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak rozbalit zip s heslem pomocí Aspise.Zip pro .NET
url: /net/archive-extraction-and-formats/extract-archive-different-passwords/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak extrahovat zip s heslem pomocí Aspose.Zip pro .NET

V moderních aplikacích .NET je ochrana citlivých dat uvnitř ZIP archivů běžnou požadavkem. Tento tutoriál ukazuje **jak extrahovat zip s heslem**, když každý záznam používá jiné heslo, což vám poskytuje detailní kontrolu nad zabezpečením a zároveň udržuje proces extrakce jednoduchý.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip for .NET.
- **Mohu extrahovat záznamy, které mají různá hesla?** Ano — každý záznam může být otevřen svým vlastním heslem.
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.
- **Podporované platformy?** .NET Framework, .NET Core, .NET 5/6+.
- **Typický čas implementace?** Přibližně 10 minut pro základní scénář.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

- **Aspose.Zip for .NET** nainstalovaný ve vašem projektu. Oficiální dokumentaci najdete [zde](https://reference.aspose.com/zip/net/).
- Vývojové prostředí .NET (Visual Studio, Rider nebo VS Code) cílící na .NET 5 nebo novější.
- ZIP soubor, který obsahuje záznamy šifrované **různými hesly** (příklad použitý zde je `different_password.zip`).

## Importujte jmenné prostory

Nejprve importujte jmenné prostory potřebné pro práci s archivy:

```csharp
using Aspose.Zip;
using System.IO;
```

Tyto dva `using` příkazy vám poskytují přístup ke třídě `Archive` a standardním I/O utilitám.

## Krok 1: Definujte pracovní adresář

Nastavte složku, kde se nachází ZIP soubor a kam budou zapsány extrahované soubory:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Použijte `Path.Combine` pro tvorbu cest napříč platformami, pokud potřebujete podporovat Linux/macOS.

## Krok 2: Extrahujte položky archivu s různými hesly

Níže projdeme přesné kroky, jak otevřít archiv a extrahovat každou položku pomocí jejího vlastního hesla.

### Krok 2.1: Otevřete Zip soubor

```csharp
using (FileStream zipFile = File.Open(dataDir + "\\different_password.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
        // Continue to the next steps...
    }
}
```

`Archive` objekt představuje ZIP kontejner. Udržování `FileStream` a `Archive` uvnitř `using` bloků zajišťuje, že všechny prostředky jsou uvolněny okamžitě.

### Krok 2.2: Extrahujte první položku (heslo = “first_pass”)

```csharp
archive.Entries[0].Extract(dataDir + "alice29_extracted_pass_out.txt", "first_pass");
```

Zde **extrahujeme více zip položek** pomocí kolekce `Entries`. První položka je dešifrována heslem `"first_pass"`.

### Krok 2.3: Extrahujte druhou položku (heslo = “second_pass”)

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_pass_out.txt", "second_pass");
```

Druhá položka používá jiné heslo, což demonstruje **extrakci zip chráněnou heslem** pro každý jednotlivý soubor.

## Proč je tento přístup důležitý

- **Granulární zabezpečení:** Každý soubor může mít své vlastní heslo, což snižuje riziko při kompromitaci jediného hesla.
- **Flexibilita:** Můžete programově rozhodnout, které heslo použít na základě obchodní logiky (např. role uživatelů).
- **Výkon:** Aspose.Zip zpracovává položky v paměti, čímž se vyhýbá nutnosti nejprve rozbalit celý archiv.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| *“Invalid password” exception* | Bylo zadáno špatné heslo nebo položka není skutečně zašifrovaná. | Ověřte řetězec hesla a ujistěte se, že je položka chráněna heslem. |
| *File not found* | cesta `dataDir` je nesprávná. | Použijte `Path.Combine(dataDir, "different_password.zip")` a dvojitě zkontrolujte složku. |
| *Large archives cause high memory usage* | Všechny položky jsou ve výchozím nastavení načteny do paměti. | Streamujte každou položku jednotlivě nebo použijte `Archive.ExtractToDirectory` s callbackem pro heslo (pokud je podporováno). |

## Často kladené otázky

**Q1: Mohu používat Aspose.Zip jak v .NET Core, tak v .NET Framework projektech?**  
A1: Ano, Aspose.Zip podporuje .NET Framework, .NET Core a .NET 5/6+, což vám poskytuje flexibilitu napříč platformami.

**Q2: Kde mohu najít další podporu nebo komunitní diskuze související s Aspose.Zip?**  
A2: Navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37), kde můžete komunikovat s komunitou, klást otázky a sdílet zkušenosti.

**Q3: Je k dispozici bezplatná zkušební verze Aspose.Zip?**  
A3: Ano, bezplatnou zkušební verzi Aspose.Zip můžete získat [zde](https://releases.aspose.com/).

**Q4: Jak mohu získat dočasnou licenci pro Aspose.Zip?**  
A4: Pro dočasnou licenci navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/).

**Q5: Kde mohu zakoupit Aspose.Zip?**  
A5: Pro nákup Aspose.Zip navštivte [stránku nákupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-01  
**Testováno s:** Aspose.Zip for .NET 24.11 (latest at time of writing)  
**Autor:** Aspose  

---