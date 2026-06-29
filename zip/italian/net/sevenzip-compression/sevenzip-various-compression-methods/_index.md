---
date: 2026-06-29
description: Scopri come comprimere una cartella in 7z con Aspose.Zip per .NET, coprendo
  i metodi di compressione 7-Zip come LZMA2, BZip2 e Store. Perfetto per creare archivi
  7z in modo programmatico.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip con vari metodi di compressione
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come comprimere una cartella in 7z – Tutorial Aspose.Zip per .NET
url: /it/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come comprimere una cartella in 7z – Aspose.Zip per .NET Tutorial

## Introduzione

Se hai bisogno di **compress folder to 7z** archivi in modo programmatico in un'applicazione .NET, sei nel posto giusto. Aspose.Zip per .NET rende semplice generare archivi Seven Zip con uno qualsiasi degli algoritmi di compressione supportati, sia che tu voglia raggruppare un'intera directory per la distribuzione o semplicemente necessiti di una soluzione affidabile **seven zip archive .net**. In questa guida percorreremo tre metodi di compressione popolari—LZMA2, BZip2 e Store (senza compressione)—e ti mostreremo esattamente come produrre un file 7z in poche righe di codice C#.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.Zip per .NET fornisce il set più completo di funzionalità Seven Zip.  
- **Quale metodo di compressione offre il miglior rapporto?** LZMA2 di solito offre la compressione più alta per dati misti.  
- **Posso creare un 7z senza compressione?** Sì—usa il metodo Store (senza compressione).  
- **Ho bisogno di una licenza per lo sviluppo?** È disponibile una versione di prova gratuita; è necessaria una licenza per l'uso in produzione.  
- **È compatibile con .NET 6/7?** Assolutamente—Aspose.Zip supporta .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.

## Quali sono i metodi di compressione Seven Zip?

Seven Zip supporta diversi algoritmi, ciascuno ottimizzato per scenari differenti. **LZMA2** offre il rapporto di compressione più alto (spesso dal 30 % al 40 % più piccolo rispetto a BZip2), **BZip2** fornisce una compressione solida con un più ampio supporto da parte di strumenti legacy, e **Store** archivia semplicemente i file senza ridurli, preservando perfettamente i timestamp originali.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Conoscenza di base di C# e Visual Studio.  
- La libreria Aspose.Zip per .NET installata. Scaricala dalla pagina di download ufficiale **[qui](https://releases.aspose.com/zip/net/)**.  
- Una cartella (`dataDir`) contenente i file che desideri archiviare.

## Importare gli spazi dei nomi

Per prima cosa, aggiungi gli spazi dei nomi richiesti al tuo file C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Queste classi ti danno accesso alle impostazioni di compressione e alla gestione degli archivi.

## Compressione LZMA2 – Come creare un 7z con rapporto massimo

La classe `Archive` rappresenta un archivio 7z che può contenere più file.  
L'algoritmo LZMA2 fornisce il più alto rapporto di compressione tra i metodi supportati. Funziona dividendo l'input in blocchi e applicando una compressione dizionario sofisticata. In Aspose.Zip imposti `CompressionMethod` su `CompressionMethod.Lzma2` sull'oggetto `Archive` prima di aggiungere i file.

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

> **Pro tip:** LZMA2 funziona al meglio quando i file di origine sono più grandi di 1 MB. Per molti file piccoli, BZip2 può essere più veloce.

## Compressione BZip2 – Una scelta equilibrata

La classe `Archive` rappresenta un archivio 7z che può contenere più file.  
BZip2 offre una compressione solida con buona compatibilità per strumenti più vecchi. Utilizza la trasformazione Burrows‑Wheeler e la codifica Huffman per ridurre le dimensioni. In Aspose.Zip selezioni `CompressionMethod.BZip2` quando configuri l'istanza `Archive`, bilanciando velocità e rapporto di compressione per la maggior parte dei file di testo e binari.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 offre una compressione solida mantenendo una velocità ragionevole, rendendolo un buon fallback quando LZMA2 non è supportato dall'ambiente di destinazione.

## Store (Nessuna compressione) – Quando le dimensioni non contano

La classe `Archive` rappresenta un archivio 7z che può contenere più file.  
Il metodo Store crea un archivio senza comprimere i dati. Copia semplicemente i file originali nel contenitore 7z, preservando timestamp e struttura delle directory. Per usarlo in Aspose.Zip, imposta `CompressionMethod.Store` sull'`Archive` prima di aggiungere i file che desideri raggruppare.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Usa il metodo Store se hai semplicemente bisogno di raggruppare file insieme senza alterarne le dimensioni—perfetto per preservare i timestamp originali o quando l'archivio verrà decompresso al volo.

## Come aggiungere file a 7z?

Aggiungi file a un archivio 7z creando un'istanza `Archive`, impostando il `CompressionMethod` desiderato e chiamando `AddAllFiles(dataDir)`. Il metodo scandisce la cartella specificata in modo ricorsivo, preservando la gerarchia delle directory all'interno dell'archivio. Questo approccio ti consente di **compress folder to 7z** con una sola riga di codice dopo la configurazione iniziale.

## Casi d'uso comuni

| Scenario | Metodo consigliato |
|----------|--------------------|
| Distribuire grandi installer | LZMA2 |
| Condividere log con strumenti legacy | BZip2 |
| Imballare file per estrazione rapida | Store (senza compressione) |
| Necessità di **compress folder to 7z** al volo in un servizio web | LZMA2 (per il miglior rapporto) |

## Risoluzione dei problemi e consigli

- **File mancanti nell'archivio?** Verifica che `dataDir` punti alla directory corretta e che il processo abbia i permessi di lettura.  
- **L'archivio non si apre su versioni più vecchie di 7‑Zip?** Rimani su BZip2 o Store, poiché LZMA2 potrebbe richiedere librerie di decompressione più recenti.  
- **Collo di bottiglia delle prestazioni?** Per set di dati massivi, considera lo streaming dell'archivio invece di caricare tutte le voci in memoria.

## Domande frequenti

**D: Posso usare Aspose.Zip per .NET con qualsiasi tipo di file?**  
R: Sì, Aspose.Zip supporta un'ampia gamma di formati di file, consentendoti di comprimere e decomprimere praticamente qualsiasi tipo di file.

**D: È disponibile una versione di prova gratuita per Aspose.Zip per .NET?**  
R: Sì, puoi ottenere una versione di prova gratuita **[qui](https://releases.aspose.com/)**.

**D: Dove posso trovare la documentazione per Aspose.Zip per .NET?**  
R: Il riferimento API completo è disponibile **[qui](https://reference.aspose.com/zip/net/)**.

**D: Come posso ottenere licenze temporanee per Aspose.Zip per .NET?**  
R: Le licenze temporanee possono essere ottenute **[qui](https://purchase.aspose.com/temporary-license/)**.

**D: Dove posso ottenere supporto per Aspose.Zip per .NET?**  
R: Puoi cercare supporto sul **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

**Ultimo aggiornamento:** 2026-06-29  
**Testato con:** Aspose.Zip per .NET 24.12  
**Autore:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [comprimere file c# – Creare archivio 7z con Aspose.Zip per .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Come comprimere una cartella usando Aspose.Zip per .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Come comprimere LZMA in Aspose.Zip per .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}