---
date: 2025-12-14
description: Naučte se, jak dekomprimovat zip v C# a extrahovat jeden soubor zip pomocí
  Aspose.Zip pro .NET ve vašich projektech C#.
linktitle: Decompressing a Single File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Rozbalit zip v C# – Extrahovat jeden soubor pomocí Aspose.Zip
url: /cs/net/file-decompression/decompress-single-file/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozbalení zip c# – Extrahování jednoho souboru pomocí Aspose.Zip

## Úvod

Pokud potřebujete **decompress zip c#** soubory a vytáhnout jen jeden záznam, Aspose.Zip pro .NET to provede jednoduše. V tomto tutoriálu projdeme kompletním, reálným příkladem, který ukazuje, jak extrahovat jeden soubor ze ZIP archivu, sledovat průběh a zpracovat výsledek čistým a udržovatelným způsobem. Na konci budete jistí při přidávání rozbalování zip souborů do jakékoli C# aplikace.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Rozbalování ZIP archivu a extrahování jednoho souboru pomocí Aspose.Zip pro .NET.  
- **Jaké primární klíčové slovo je cílem?** decompress zip c#  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Je podporován .NET Core?** Ano – stejný kód běží na .NET Framework i .NET Core.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut proní nastavení.

## Požadavky

Před ponořením se do tutoriálu se ujistěte, že máte následující požadavky připravené:

- Aspose.Zip pro .NET knihovna: Stáhněte a nainstalujte knihovnu z [Aspose.Zip for .NET Documentation](https://reference.aspose.com/zip/net/).
- Vývojové prostředí: Mějte připravené funkční .NET vývojové prostředí, včetně Visual Studio nebo jiného kompatibilního IDE.
- Základní znalost C#: Seznamte se se základy programování v C#.

Nyní si pojďme vyzkoušet kód!

## Importování jmenných prostorů

Začněte importováním potřebných jmenných prostorů pro zahájení vaší cesty s Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## Postupný průvodce rozbalením zip c#

### Krok 1: Nastavte adresář dokumentů

Začněte určením adresáře, kde jsou uloženy vaše dokumenty. Nahraďte `"Your Document Directory"` skutečnou cestou.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte komprimovaný soubor (ukázkové nastavení)

Následující volání vytvoří ukázkový ZIP soubor, který později rozbalíme. To odráží typický scénář, kdy již máte ZIP archiv.

```csharp
CompressSingleFile.Run();
```

### Krok 3: Rozbalte soubor – Extrahujte jeden ZIP soubor

Nyní se ponořme do jádra věci – extrahování jednoho záznamu. Níže uvedený kód otevře ZIP archiv, připojí obslužnou rutinu pro průběh a extrahuje první záznam do textového souboru.

```csharp
// ExStart: DecompressSingleFile
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

Tento úryvek **extrahuje jeden zip záznam** a zároveň vypisuje průběh v reálném čase (např. „30 % rozbaleno“). Index (`Entries[0]`) můžete upravit tak, aby cílil na jakýkoli jiný soubor v archivu.

## Proč použít Aspose.Zip pro rozbalování souborů v C#?

- **Žádné externí závislosti** – čistá .NET knihovna.  
- **Podporuje velké archivy** pomocí streamování, takže využití paměti zůstává nízké.  
- **Vestavěné události průběhu** usnadňují poskytování zpětné vazby v UI.  
- **Funguje napříč .NET Framework, .NET Core a .NET 5/6**.

## Časté problémy a tipy

- **Oddělovače cest** – použijte `Path.Combine` pro bezpečnost napříč platformami.  
- **ZIPy chráněné heslem** – nastavte `archive.Password` před extrahováním.  
- **Více záznamů** – projděte `archive.Entries` a porovnejte podle `FileName`.  

## Často kladené otázky

### Q1: Mohu komprimovat více souborů pomocí Aspose.Zip pro .NET?

A1: Ano, Aspose.Zip pro .NET podporuje kompresi více souborů. Podívejte se do dokumentace pro podrobné instrukce.

### Q2: Je Aspose.Zip kompatibilní s .NET Core?

A2: Rozhodně! Aspose.Zip se bez problémů integruje jak s .NET Framework, tak s .NET Core.

### Q3: Jak mohu pracovat se soubory komprimovanými a chráněnými heslem?

A3: Aspose.Zip poskytuje metody pro práci s archivy chráněnými heslem. Proveďte konzultaci s dokumentací pro návod.

### Q4: Existují nějaké licenční úvahy při používání Aspose.Zip?

A4: Prohlédněte si informace o licencování na [Aspose website](https://purchase.aspose.com/buy).

### Q5: Kde mohu získat pomoc, pokud narazím na problémy?

A5: Navštivte [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) pro podporu komunity.

## Závěr

Gratulujeme! Úspěšně jste prošli složitostmi **decompress zip c#** a extrahovali jeden soubor pomocí Aspose.Zip pro .NET. Začleňte tento vzor do svých aplikací pro zjednodušení práce se soubory, zlepšení uživatelského zážitku a udržení čistoty kódu.

---

**Poslední aktualizace:** 2025-12-14  
**Testováno s:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}