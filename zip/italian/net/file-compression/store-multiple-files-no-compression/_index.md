---
date: 2025-12-10
description: Scopri come archiviare file senza compressione usando Aspose.Zip per
  .NET. Questa guida ti mostra come creare un file zip non compresso, salvare file
  nello zip e gestire gli archivi in modo efficiente.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come archiviare file non compressi con Aspose.Zip per .NET
url: /it/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come archiviare file senza compressione con Aspose.Zip per .NET

Nello sviluppo .NET moderno, **come archiviare file** in modo efficiente può fare una grande differenza in termini di prestazioni e costi di archiviazione. Quando è necessario mantenere i file esattamente così come sono—senza alcuna compressione—Aspose.Zip per .NET offre un'API pulita e semplice. In questo tutorial vedremo i passaggi per creare un archivio ZIP non compresso, salvare file nello ZIP e integrare la soluzione nella tua applicazione.

## Risposte rapide
- **Cosa significa “zip non compresso”?** È un archivio ZIP in cui ogni voce è memorizzata usando il metodo “store”, lasciando intatti i byte originali del file.  
- **Perché evitare la compressione?** Per velocizzare l'archiviazione, preservare le dimensioni originali dei file per l'elaborazione successiva, o soddisfare requisiti normativi che vietano la modifica dei dati.  
- **Quale classe di Aspose.Zip gestisce questo?** `ArchiveEntrySettings` combinata con `StoreCompressionSettings`.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework, .NET Core, .NET 5/6/7 e successive.

## Cos'è l'archiviazione di più file senza compressione?
Archiviare più file senza compressione significa aggiungere ogni file a un contenitore ZIP usando il metodo di compressione *store*. I file rimangono identici byte per byte agli originali, il che è ideale quando si desidera un'archiviazione rapida o è necessario mantenere i dati invariati.

## Perché usare Aspose.Zip per archivi non compressi?
- **Velocità:** Non vengono eseguiti algoritmi di compressione intensivi per la CPU.  
- **Dimensione prevedibile:** La dimensione dell'archivio è pari alla somma dei file originali più un minimo overhead ZIP.  
- **Compatibilità:** Lo ZIP risultante funziona con qualsiasi utility di estrazione standard.  
- **Flessibilità:** È comunque possibile mescolare voci compresse e non compresse nello stesso archivio, se necessario.

## Prerequisiti
- **Aspose.Zip for .NET** – integrato nel tuo progetto. Consulta la [documentazione](https://reference.aspose.com/zip/net/) ufficiale per le istruzioni di installazione.  
- **Ambiente di sviluppo .NET** – Visual Studio, VS Code o qualsiasi IDE tu preferisca.  
- **Directory dei documenti** – una cartella sul tuo computer contenente i file che desideri archiviare (ad esempio, “Your Document Directory”).

## Importa gli spazi dei nomi
Prima di scrivere qualsiasi codice, importa gli spazi dei nomi richiesti in modo che il compilatore sappia dove trovare le classi Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Passo 1: Imposta la directory dei documenti
Definisci il percorso in cui risiedono i tuoi file sorgente. Sostituisci il segnaposto con la cartella effettiva sul tuo sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Crea un archivio Zip senza compressione
Il fulcro del tutorial – creiamo un'istanza `Archive` configurata con `StoreCompressionSettings`. Questo indica ad Aspose.Zip di *memorizzare* (cioè, non comprimere) ogni voce.

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

> **Consiglio professionale:** Se hai bisogno di **salvare file nello zip** comprimendo alcuni e lasciandone altri non compressi, crea istanze separate di `ArchiveEntrySettings` per ogni file e aggiungile allo stesso `Archive`.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|----------|
| **File non trovato** | Percorso `dataDir` errato o estensione del file mancante. | Verifica il percorso e assicurati che i file esistano. Usa `Path.Combine` per una concatenazione più sicura. |
| **Accesso negato** | Il processo non ha i permessi per leggere i file sorgente o scrivere lo ZIP. | Esegui l'applicazione con i diritti appropriati o scegli una cartella con accesso in scrittura. |
| **Dimensione file inattesa nello ZIP** | L'archivio è stato creato con compressione predefinita. | Assicurati che `new StoreCompressionSettings()` sia passato a `ArchiveEntrySettings`. |

## Domande frequenti

**D: Posso comprimere tipi di file specifici mentre ne archivio altri senza compressione?**  
R: Sì, puoi creare diversi `ArchiveEntrySettings` per ogni file e mescolare voci compresse e non compresse nello stesso archivio.

**D: Aspose.Zip per .NET è compatibile con .NET Core e .NET 5/6?**  
R: Assolutamente. La libreria supporta .NET Framework, .NET Core, .NET Standard e le versioni più recenti di .NET.

**D: Come dovrei gestire le eccezioni durante il processo di archiviazione?**  
R: Avvolgi il codice di archiviazione in un blocco `try‑catch` e registra i dettagli dell'eccezione. Questo garantisce un fallimento gestito e una più facile debug.

**D: Aspose.Zip supporta l'archiviazione multithread?**  
R: Sì, puoi elaborare più file in parallelo e aggiungerli all'archivio, ma ricorda che l'oggetto `Archive` non è thread‑safe; sincronizza l'accesso quando aggiungi voci.

**D: Posso integrare Aspose.Zip in un progetto esistente senza grandi modifiche al codice?**  
R: Certamente. L'API è progettata per un utilizzo semplice plug‑and‑play. Consulta la [documentazione](https://reference.aspose.com/zip/net/) ufficiale per le linee guida sulla migrazione.

---

**Ultimo aggiornamento:** 2025-12-10  
**Testato con:** Aspose.Zip for .NET 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}