---
date: 2026-05-30
description: Scopri come creare zip senza compressione in .NET con Aspose.Zip per
  .NET. Questa guida ti mostra come zip file senza compressione, memorizzare file
  non compressi e gestire gli archive in modo efficiente.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Memorizzazione di più file senza compressione
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea zip senza compressione in .NET usando Aspose.Zip
url: /it/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea zip senza compressione in .NET usando Aspose.Zip

Nello sviluppo moderno .NET, **creare un zip senza compressione** può migliorare drasticamente la velocità di archiviazione e mantenere le dimensioni dei file prevedibili. Quando è necessario **zippare file senza compressione** — ad esempio, per rispettare normative, velocizzare l'elaborazione a valle o garantire che la sequenza originale di byte rimanga intatta — Aspose.Zip per .NET offre un'API pulita e semplice. In questo tutorial illustreremo i passaggi esatti per creare un archivio ZIP non compresso, aggiungere file e integrare la soluzione nella tua applicazione.

## Risposte rapide
- **Cosa significa “zip non compresso”?** È un archivio ZIP in cui ogni voce è memorizzata usando il metodo “store”, lasciando intatti i byte originali del file.  
- **Perché evitare la compressione?** Per velocizzare l'archiviazione, preservare le dimensioni originali dei file per l'elaborazione a valle, o soddisfare i requisiti normativi che vietano la modifica dei dati.  
- **Quale classe di Aspose.Zip gestisce questo?** `ArchiveEntrySettings` combined with `StoreCompressionSettings`.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  

## Cos'è lo zip senza compressione?
**Zip senza compressione** è un archivio ZIP in cui ogni voce di file utilizza il metodo *store*, il che significa che i dati vengono copiati alla lettera nell'archivio senza alcun algoritmo di compressione applicato. Questo produce un archivio la cui dimensione è essenzialmente la somma dei file originali più qualche byte di overhead ZIP.

## Perché usare Aspose.Zip per file zip senza compressione?
Aspose.Zip è ottimizzato per l'archiviazione ad alte prestazioni, consentendo di memorizzare i file istantaneamente senza l'overhead degli algoritmi di compressione. Garantisce la piena compatibilità ZIP, permette di mescolare voci memorizzate e compresse, e fornisce un'API semplice che astrae le strutture ZIP a basso livello, rendendo l'implementazione veloce e affidabile.

## Prerequisiti
- **Aspose.Zip per .NET** – integrato nel tuo progetto. Consulta la [documentazione](https://reference.aspose.com/zip/net/) ufficiale per i passaggi di installazione.  
- **Ambiente di sviluppo .NET** – Visual Studio, VS Code o qualsiasi IDE tu preferisca.  
- **Directory dei documenti** – una cartella sul tuo computer contenente i file che desideri archiviare (ad esempio, “Your Document Directory”).

## Importa spazi dei nomi
Prima di scrivere qualsiasi codice, importa gli spazi dei nomi richiesti affinché il compilatore sappia dove trovare le classi Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Passo 1: Imposta la directory dei documenti
Definisci il percorso dove risiedono i tuoi file di origine. Sostituisci il segnaposto con la cartella reale sul tuo sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Crea archivio Zip senza compressione
Il cuore del tutorial – creiamo un'istanza `Archive` configurata con `StoreCompressionSettings`. `Archive` rappresenta un contenitore ZIP che può contenere più voci. `StoreCompressionSettings` specifica che una voce deve essere memorizzata senza compressione. Questo indica ad Aspose.Zip di *memorizzare* (cioè, non comprimere) ogni voce.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Consiglio professionale:** Se hai bisogno di **salvare file in zip** comprimendo alcuni e lasciandone altri non compressi, crea istanze separate di `ArchiveEntrySettings` per ogni file e aggiungile allo stesso `Archive`.

## Come creare zip senza compressione in .NET?
Carica i tuoi file di origine, istanzia un oggetto `Archive` e aggiungi ogni file usando `ArchiveEntrySettings` con `new StoreCompressionSettings()`. L'intera operazione richiede solo tre righe di codice e viene eseguita in tempo lineare rispetto alla dimensione totale dei file, offrendoti l'esperienza di archiviazione più veloce possibile.

### Guida passo‑passo
1. **Crea l'archivio** – istanzia `Archive` con uno stream di destinazione o un percorso file.  
2. **Configura le impostazioni della voce** – per ogni file, crea un oggetto `ArchiveEntrySettings` e assegna `new StoreCompressionSettings()` alla sua proprietà `Compression`.  
3. **Aggiungi le voci** – chiama `archive.Add(entrySettings)` per ogni file, quindi finalizza con `archive.Save()`.

## Problemi comuni e soluzioni
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **File non trovato** | Percorso `dataDir` errato o estensione file mancante. | Verifica il percorso e assicurati che i file esistano. Usa `Path.Combine` per una concatenazione più sicura. |
| **Accesso negato** | Il processo non ha i permessi per leggere i file di origine o scrivere lo ZIP. | Esegui l'applicazione con i diritti appropriati o scegli una cartella con accesso in scrittura. |
| **Dimensione file inattesa nello ZIP** | L'archivio è stato creato con compressione predefinita. | Assicurati che `new StoreCompressionSettings()` sia passato a `ArchiveEntrySettings`. |

## Domande frequenti

**D: Posso comprimere tipi di file specifici mentre ne memorizzo altri senza compressione?**  
R: Sì, puoi creare diversi `ArchiveEntrySettings` per ogni file e mescolare voci compresse e non compresse nello stesso archivio.

**D: Aspose.Zip per .NET è compatibile con .NET Core e .NET 5/6?**  
R: Assolutamente. La libreria supporta .NET Framework, .NET Core, .NET Standard e le versioni .NET più recenti.

**D: Come dovrei gestire le eccezioni durante il processo di archiviazione?**  
R: Avvolgi il codice di archiviazione in un blocco `try‑catch` e registra i dettagli dell'eccezione. Questo garantisce un fallimento gestito e una più facile debug.

**D: Aspose.Zip supporta l'archiviazione multithread?**  
R: Sì, puoi elaborare più file in parallelo e aggiungerli all'archivio, ma ricorda che l'oggetto `Archive` non è thread‑safe; sincronizza l'accesso quando aggiungi le voci.

**D: Posso integrare Aspose.Zip in un progetto esistente senza grandi modifiche al codice?**  
R: Assolutamente. L'API è progettata per un utilizzo semplice plug‑and‑play. Consulta la [documentazione](https://reference.aspose.com/zip/net/) ufficiale per le linee guida di migrazione.

---

**Ultimo aggiornamento:** 2026-05-30  
**Testato con:** Aspose.Zip for .NET (latest version at time of writing)  
**Autore:** Aspose


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}