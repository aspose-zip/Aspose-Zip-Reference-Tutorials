---
title: Creazione di sette file zip - Aspose.Zip per .NET Tutorial
linktitle: SevenZip con vari metodi di compressione
second_title: Aspose.Zip .NET API per la compressione e l'archiviazione dei file
description: Impara a creare file Seven Zip con Aspose.Zip per .NET utilizzando diversi metodi di compressione. Semplici passaggi per LZMA2, BZip2 e Store (nessuna compressione).
type: docs
weight: 12
url: /it/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## introduzione

Nell'ambito dello sviluppo .NET, la gestione e la compressione dei file è un'attività comune. Aspose.Zip per .NET fornisce una potente soluzione per lavorare con archivi compressi, offrendo una varietà di metodi di compressione. In questo tutorial esploreremo come utilizzare Aspose.Zip per .NET per creare file Seven Zip con diversi metodi di compressione.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere quanto segue:

- Una conoscenza di base della programmazione C#.
- Visual Studio installato sul tuo computer.
-  Aspose.Zip per la libreria .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/zip/net/).

## Importa spazi dei nomi

Inizia importando gli spazi dei nomi necessari nel tuo progetto C#. Utilizza il seguente snippet di codice per iniziare:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Compressione LZMA2

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## Compressione BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Memorizza, nessuna compressione

```csharp
//Conservare, nessuna compressione
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Conclusione

In questo tutorial, abbiamo esplorato la versatilità di Aspose.Zip per .NET nella creazione di file Seven Zip con vari metodi di compressione. Sia che tu abbia bisogno di rapporti di compressione elevati o che preferisca nessuna compressione, Aspose.Zip offre la flessibilità per soddisfare le tue esigenze.

## Domande frequenti

### Posso utilizzare Aspose.Zip per .NET con qualsiasi tipo di file?
Sì, Aspose.Zip per .NET supporta un'ampia gamma di tipi di file, consentendoti di comprimere e decomprimere vari formati.

### È disponibile una prova gratuita per Aspose.Zip per .NET?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione per Aspose.Zip per .NET?
 La documentazione è disponibile[Qui](https://reference.aspose.com/zip/net/).

### Come posso ottenere licenze temporanee per Aspose.Zip per .NET?
 È possibile ottenere licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso ottenere supporto per Aspose.Zip per .NET?
 Puoi cercare supporto su[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).
