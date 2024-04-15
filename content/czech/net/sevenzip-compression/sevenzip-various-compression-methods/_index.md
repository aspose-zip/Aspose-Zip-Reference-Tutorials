---
title: Vytváření sedmi souborů ZIP – výukový program Aspose.Zip pro .NET
linktitle: SevenZip s různými metodami komprese
second_title: Aspose.Zip .NET API pro kompresi a archivaci souborů
description: Naučte se vytvářet soubory Seven Zip pomocí Aspose.Zip pro .NET pomocí různých kompresních metod. Snadné kroky pro LZMA2, BZip2 a Store (bez komprese).
type: docs
weight: 12
url: /cs/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## Úvod

oblasti vývoje .NET je správa a komprimace souborů běžným úkolem. Aspose.Zip for .NET poskytuje výkonné řešení pro práci s komprimovanými archivy a nabízí řadu metod komprese. V tomto tutoriálu prozkoumáme, jak používat Aspose.Zip pro .NET k vytváření souborů Seven Zip s různými metodami komprese.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující:

- Základní znalost programování v C#.
- Visual Studio nainstalované na vašem počítači.
-  Aspose.Zip pro knihovnu .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/zip/net/).

## Importovat jmenné prostory

Začněte importováním potřebných jmenných prostorů do vašeho projektu C#. Chcete-li začít, použijte následující fragment kódu:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Komprese LZMA2

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithRůznými metodami komprese
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## BZip2 komprese

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Sklad, bez komprese

```csharp
//Sklad, žádná komprese
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Závěr

tomto tutoriálu jsme prozkoumali všestrannost Aspose.Zip pro .NET při vytváření souborů Seven Zip různými metodami komprese. Ať už potřebujete vysoké kompresní poměry nebo preferujete žádnou kompresi, Aspose.Zip poskytuje flexibilitu pro splnění vašich požadavků.

## Nejčastější dotazy

### Mohu použít Aspose.Zip pro .NET s jakýmkoli typem souboru?
Ano, Aspose.Zip for .NET podporuje širokou škálu typů souborů, což vám umožňuje komprimovat a dekomprimovat různé formáty.

### Je k dispozici bezplatná zkušební verze pro Aspose.Zip pro .NET?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Kde najdu dokumentaci k Aspose.Zip pro .NET?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/zip/net/).

### Jak mohu získat dočasné licence pro Aspose.Zip pro .NET?
 Je možné získat dočasné licence[tady](https://purchase.aspose.com/temporary-license/).

### Kde mohu získat podporu pro Aspose.Zip pro .NET?
 Podporu můžete hledat na[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37).
