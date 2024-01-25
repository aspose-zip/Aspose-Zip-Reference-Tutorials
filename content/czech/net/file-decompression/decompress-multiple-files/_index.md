---
title: Dekomprese více souborů pomocí Aspose.Zip pro .NET
linktitle: Dekomprese více souborů
second_title: Aspose.Zip .NET API pro kompresi a archivaci souborů
description: Naučte se, jak dekomprimovat více souborů pomocí Aspose.Zip pro .NET. Postupujte podle našeho podrobného průvodce pro efektivní správu souborů.
type: docs
weight: 11
url: /cs/net/file-decompression/decompress-multiple-files/
---
## Úvod

Vítejte v našem komplexním návodu na dekompresi více souborů pomocí Aspose.Zip pro .NET! Pokud hledáte efektivní zpracování komprimovaných souborů obsahujících více položek, jste na správném místě. V této příručce vás provedeme procesem krok za krokem pomocí Aspose.Zip pro .NET.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Zip for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Zip pro .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/zip/net/).

- Adresář dokumentů: Nastavte adresář, kde jsou uloženy vaše dokumenty. Ten použijete jako základní adresář v kódu.

Nyní začneme s průvodcem krok za krokem.

## Importovat jmenné prostory

Ve svém projektu .NET začněte importováním potřebných jmenných prostorů pro Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Komprimace více souborů

Chcete-li dekomprimovat více souborů, potřebujete nejprve komprimovaný soubor s více položkami. Pojďme si jeden vytvořit:

```csharp
string dataDir = "Your Document Directory";

// Spusťte metodu komprese
CompressMultipleFiles.Run();
```

## Krok 2: Dekomprimujte soubory

Nyní dekomprimujeme soubory krok za krokem:

### Krok 2.1: Otevření komprimovaného souboru

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Krok 2.2: Výpis záznamů a sledování průběhu

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Krok 2.3: Vyjmutí prvního záznamu

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Číst a zapisovat data z dekomprimovaného streamu do extrahovaného souboru.
    }
}
```

### Krok 2.4: Vyjmutí druhého záznamu

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

A tady to máte! Úspěšně jste dekomprimovali několik souborů pomocí Aspose.Zip pro .NET.

## Závěr

tomto tutoriálu jsme probrali základní kroky k dekomprimaci více souborů pomocí Aspose.Zip pro .NET. Podle tohoto průvodce můžete snadno efektivně spravovat komprimované soubory.

## FAQ

### Q1: Mohu používat Aspose.Zip pro .NET v komerčních i osobních projektech?

 A1: Ano, Aspose.Zip for .NET lze použít v komerčních i osobních projektech. Podrobnosti o licencích viz[Licenční informace společnosti Aspose](https://purchase.aspose.com/buy).

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Zip pro .NET?

 A2: Ano, můžete prozkoumat bezplatnou zkušební verzi Aspose.Zip pro .NET[tady](https://releases.aspose.com/zip/net).

### Q3: Kde najdu další podporu pro Aspose.Zip pro .NET?

 A3: Navštivte[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) za podporu komunity a diskuze.

### Q4: Jak mohu zakoupit dočasnou licenci pro Aspose.Zip pro .NET?

 A4: Získejte dočasnou licenci pro Aspose.Zip pro .NET[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Existují nějaké specifické systémové požadavky pro používání Aspose.Zip pro .NET?

 A5: Viz[dokumentace](https://reference.aspose.com/zip/net/) pro podrobné systémové požadavky.