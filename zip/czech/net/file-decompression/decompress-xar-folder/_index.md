---
date: 2025-12-17
description: Naučte se, jak extrahovat archivy Xar a rozbalit archiv Xar do složky
  pomocí Aspose.Zip pro .NET. Postupujte podle tohoto průvodce krok po kroku.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak rozbalit soubor Xar do složky pomocí Aspose.Zip pro .NET
url: /cs/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak extrahovat Xar do složky pomocí Aspose.Zip pro .NET

## Úvod

Pokud jste vývojář .NET a hledáte spolehlivý způsob **jak extrahovat xar**, Aspose.Zip pro .NET poskytuje čisté, vysoce výkonné API. V tutoriálu projdeme celý proces dekomprese archivu Xar do složky, vysvětlíme, proč tento přístup šetří čas, a ukážeme vám přesný kód, který potřebujete spustit.

## Rychlé odpovědi
- **Co knihovna dělá?** Čte a archivy Xar bez externích nástrojů.
- **Které verze .NET jsou podporovány?** .NET Framework4.6+, .NETCore3.1+, .NET5/6+.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut.
- **Mohu extrahovat do vlastní složky?** Ano– stačí zadat cílovou cestu v `ExtractToDirectory`.

## Co je to „jak extrahovat xar“?
Extrahování archivu Xar znamená čtení komprimovaného souboru a zápisu jeho vnitřních souborů do adresáře na disku. To je užitečné, když získáte balíčky XAR z instalátorů macOS, zálohy nebo třetí strany a potřebujete zpracovat jejich obsah v aplikaci .NET.

## Proč pro tento úkol používat Aspose.Zip?
- **Žádné externí závislosti** – čistý .NET, žádné nativní binární soubory.
- **API založené na streamu** – funguje se soubory, paměťovými streamy nebo síťovými streamy.
- **Robustní zpracování chyb** – podrobný tip vám pomůže řešit poškozené archivy.
- **Plná kompatibilita s .NET** – funguje na Windows, Linux a macOS runtimech.

## Předpoklady

Než se pustíme dál, vyberete se, že máte následující:

- **Aspose.Zip pro .NET** – integrováno do vašeho projektu. Můžete si jej stáhnout [zde](https://releases.aspose.com/zip/net/).
- **Adresář dokumentů** – složka ve vašem řešení, kde bude umístěn ukázkový soubor `.xar` a extrahovaný výstup.

## Import jmenných prostorů

Ve vašem .NET projektu zahrňte potřebné jmenné prostory pro přístup k funkcionalitě Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Krok 1: Definujte adresář dokumentů

```csharp
string dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou, která obsahuje `sample.xar` a kde chcete vytvořit výstupní složku.

## Krok 2: Dekomprimujte archiv Xar

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Tento úryvek otevře soubor Xar, vytvoří instanci `XarArchive` a extrahuje **celý dekomprimovaný xar archiv** do `DecompressXar_out`. Operace je plně založena na streamech, takže funguje efektivně i u velkých balíčků.

## Krok 3: Spusťte kód

Sestavte a spusťte aplikaci. Po provedení najdete novou složku pojmenovanou `DecompressXar_out` ve vašem adresáři dokumentů, obsahující všechny soubory, které byly zabaleny v původním archivu `.xar`.

## Běžné problémy a tipy

- **bor nenalezen** – `Sou nalezen, že cesta v File.OpenRead` správně ukazuje na `sample.xar`. Pro bezpečnější práci s cestami použijte `Path.Combine`.
- **Přístup odmítnut** – Spusťte aplikaci s dostatečnými oprávněními k souborovému systému, zejména při zápisu do chráněných adresářů.
- **Poškozený archiv** – Aspose.Zip vyhodí `InvalidDataException`; ověřte, že zdrojový soubor `.xar` je nepoškozený.

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní s nejnovějšími verzemi .NET frameworku?**
A: Ano, Aspose.Zip je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi .NET frameworku. Podrobnosti najdete v [dokumentaci](https://reference.aspose.com/zip/net/).

**Q: Mohu vyzkoušet Aspose.Zip před zakoupením?**
A: Rozhodně! Bezplatnou zkušební verzi si můžete stáhnout [zde](https://releases.aspose.com/).

**Q: Jak získám podporu pro Aspose.Zip?**
A: Pro jakékoliv dotazy nebo pomoc navštivte [forum Aspose.Zip] (https://forum.aspose.com/c/zip/37).

**Q: Jsou k dispozici dočasné licence pro Aspose.Zip?**
A: Ano, dočasná licence lze získat [zde](https://purchase.aspose.com/temporary-license/).

**Otázka: Kde mohu zakoupit Aspose.Zip pro .NET?**
A: Aspose.Zip pro .NET si můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Mohu extrahovat jen konkrétní soubory z archivu Xar?**
A: Ano– použijte `archive.Entries` k výčtu položek a zavolejte `ExtractToFile` na vybraných položkách.

**O: Podporuje knihovna soubory Xar chráněné heslem?**
A: V současné době archivy Xar nepodporují šifrování; pokud narazíte na chráněný soubor, budete její muset dešifrovat před použitím Aspose.Zip.

---

**Poslední aktualizace:** 2025-12-17
**Testováno s:** Aspose.Zip 24.11 pro .NET
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}