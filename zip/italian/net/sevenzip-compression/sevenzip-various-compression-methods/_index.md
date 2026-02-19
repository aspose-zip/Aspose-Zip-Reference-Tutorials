---
date: 2025-12-25
description: Scopri come creare file 7z con Aspose.Zip per .NET, coprendo i metodi
  di compressione di 7‑Zip come LZMA2, BZip2 e Store. Perfetto per scenari di compressione
  di cartelle in 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come creare file 7z – Tutorial Aspose.Zip per .NET
url: /it/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare file 7z – Aspose.Zip per .NET Tutorial

## Introduzione

Se hai bisogno di **how to create 7z** archivi programmaticamente in un'applicazione .NET, sei nel posto giusto. Aspose.Zip per .NET rende semplice generare archivi Seven Zip con uno qualsiasi degli algoritmi di compressione supportati, sia che tu voglia **comprimere cartelle in 7z** per la distribuzione o abbia semplicemente bisogno di una soluzione affidabile di **seven zip archive .net**. In questa guida esamineremo tre metodi di compressione popolari — LZMA2, BZip2 e Store (senza compressione) — e ti mostreremo esattamente come produrre un file 7z in poche righe di codice C#.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.Zip per .NET fornisce il set più completo di funzionalità Seven Zip.
- **Quale metodo di compressione offre il miglior rapporto?** LZMA2 di solito fornisce la compressione più alta per dati misti.
- **Posso creare un 7z senza compressione?** Sì — usa il metodo Store (no compression).
- **È necessaria una licenza per lo sviluppo?** È disponibile una versione di prova gratuita; è richiesta una licenza per l'uso in produzione.
- **È compatibile con .NET 6/7?** Assolutamente — Aspose.Zip supporta .NET Framework, .NET Core e .NET 5+.

## Quali sono i sette metodi di compressione zip?

Seven Zip supporta diversi algoritmi, ognuno ottimizzato per scenari diversi:

* **LZMA2** – rapporto di compressione elevato, ideale per file di grandi dimensioni e tipo misto.
* **BZip2** – compressione solida ma più lenta rispetto a LZMA2; utile quando è richiesta la compatibilità con strumenti più vecchi.
* **Store** – nessuna compressione; perfetto quando è necessario solo archiviare senza ridurre le dimensioni (ad esempio, preservando il timestamp originale dei file).

Comprendere questi **sette metodi di compressione zip** ti aiuta a scegliere l'impostazione giusta per il tuo progetto.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Conoscenza di base di C# e Visual Studio.
- La libreria Aspose.Zip per .NET installata. Scaricala dalla pagina ufficiale di download **[qui](https://releases.aspose.com/zip/net/)**.
- Una cartella (`dataDir`) contenente i file che desideri archiviare.

## Importa spazi dei nomi

Per prima cosa, aggiungi gli spazi dei nomi richiesti al tuo file C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Queste classi ti danno accesso alle impostazioni di compressione e alla gestione dell'archivio.

## Compressione LZMA2 – Come creare un 7z con il rapporto massimo

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

> **Suggerimento:** LZMA2 funziona al meglio quando i file di origine sono più grandi di 1MB. Per molti file piccoli, BZip2 può essere più veloce.

## Compressione BZip2: una scelta equilibrata

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 offre una compressione solida mantenendo una velocità ragionevole, rendendola una buona alternativa quando LZMA2 non è supportata dall'ambiente di destinazione.

## Store (senza compressione) – Quando le dimensioni non contano

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Utilizza il metodo Store se hai semplicemente bisogno di raggruppare i file senza modificarne le dimensioni — perfetto per preservare i timestamp originali o quando l'archivio verrà decompresso al volo.

## Casi d'uso comuni

| Scenario | Metodo consigliato |
|----------|--------------------|
| Distribuire grandi installer | LZMA2 |
| Condividere log con strumenti legacy | BZip2 |
| Impacchettare il file per un'estrazione rapida | Memorizza (nessuna compressione) |
| Necessità di **comprimere cartella in 7z** al volo in un servizio web | LZMA2 (per il miglior rapporto) |

## Risoluzione dei problemi e suggerimenti

- **File mancanti nell'archivio?** Verifica che `dataDir` punti alla directory corretta e che il processo abbia i permessi di lettura.
- **L'archivio non si apre su versioni più vecchie di 7‑Zip?** Rimani con BZip2 o Store, poiché LZMA2 potrebbe richiedere librerie di decompressione più recenti.
- **Collo di bottiglia delle prestazioni?** Per set di dati molto grandi, considera lo streaming dell'archivio invece di caricare tutte le voci in memoria.

## Domande frequenti

**D: Posso usare Aspose.Zip per .NET con qualsiasi tipo di file?**
R: Sì, Aspose.Zip supporta un'ampia gamma di formati di file, consentendo di comprimere e decomprimere praticamente qualsiasi tipo di file.

**D: È disponibile una versione di prova gratuita per Aspose.Zip per .NET?**
R: Sì, puoi ottenere una versione di prova gratuita **[qui](https://releases.aspose.com/)**.

**D: Dove posso trovare la documentazione per Aspose.Zip per .NET?**
R: Il riferimento completo dell'API è disponibile **[qui](https://reference.aspose.com/zip/net/)**.

**D: Come posso ottenere la licenza temporanea per Aspose.Zip per .NET?**
R: Le licenze temporanee possono essere ottenute **[qui](https://purchase.aspose.com/temporary-license/)**.

**D: Dove posso ottenere supporto per Aspose.Zip per .NET?**
R: Puoi richiedere supporto sul **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Ultimo aggiornamento:** 25-12-2025
**Testato con:** Aspose.Zip per .NET 24.12
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
