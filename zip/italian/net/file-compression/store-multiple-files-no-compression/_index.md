---
date: 2026-02-12
description: Scopri come creare zip non compressi .NET con Aspose.Zip per .NET. Questa
  guida ti mostra come comprimere file senza compressione, memorizzare i file non
  compressi e gestire gli archivi in modo efficiente.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea un file zip non compresso .NET usando Aspose.Zip per .NET
url: /it/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

 but translate surrounding text.

We need to keep code block placeholders unchanged.

Also table content: translate Issue, Why It Happens, Fix headings? Probably keep them in English? The instruction says translate all text content naturally to Italian, but technical terms remain English. Table headings are generic; we can translate them: "Problema", "Perché accade", "Soluzione". But they are part of text. Should we translate? Yes.

But we must keep the pipe separators.

Also the "Last Updated:" line; translate "Ultimo aggiornamento:" maybe.

"Tested With:" -> "Testato con:".

"Author:" -> "Autore:".

Make sure to keep dates unchanged.

Now produce final content.

Let's construct.

Start with shortcodes unchanged.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea zip non compresso .net con Aspose.Zip per .NET

Nello sviluppo moderno in .NET, **creare un zip non compresso .net** può migliorare notevolmente la velocità di archiviazione e mantenere le dimensioni dei file prevedibili. Quando è necessario **zippare file senza compressione** — ad esempio per rispettare normative o per accelerare l'elaborazione a valle — Aspose.Zip per .NET offre un'API pulita e diretta. In questo tutorial vedremo passo passo come creare un archivio ZIP non compresso, aggiungere file e integrare la soluzione nella tua applicazione.

## Risposte rapide
- **Cosa significa “uncompressed zip”?** È un archivio ZIP in cui ogni voce è memorizzata usando il metodo “store”, lasciando intatti i byte originali del file.  
- **Perché evitare la compressione?** Per velocizzare l'archiviazione, preservare le dimensioni originali dei file per l'elaborazione successiva, o soddisfare requisiti normativi che vietano la modifica dei dati.  
- **Quale classe di Aspose.Zip gestisce questo?** `ArchiveEntrySettings` combinata con `StoreCompressionSettings`.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework, .NET Core, .NET 5/6/7 e successive.  

## Cos'è create uncompressed zip .net?
Creare un ZIP non compresso significa aggiungere ogni file a un contenitore ZIP usando il metodo di compressione *store*. I file rimangono byte‑per‑byte identici agli originali, il che è ideale quando si desidera un'archiviazione rapida o mantenere i dati invariati.

## Perché usare Aspose.Zip per file zip senza compressione?
- **Velocità:** Non vengono eseguiti algoritmi di compressione intensivi per la CPU.  
- **Dimensione prevedibile:** La dimensione dell'archivio è pari alla somma dei file originali più un minimo overhead ZIP.  
- **Compatibilità:** Il ZIP risultante funziona con qualsiasi utility di estrazione standard.  
- **Flessibilità:** È ancora possibile mescolare voci compresse e non compresse nello stesso archivio, se necessario.

## Prerequisiti
- **Aspose.Zip per .NET** – integrato nel tuo progetto. Consulta la [documentazione ufficiale](https://reference.aspose.com/zip/net/) per le istruzioni di installazione.  
- **Ambiente di sviluppo .NET** – Visual Studio, VS Code o qualsiasi IDE tu preferisca.  
- **Directory dei documenti** – una cartella sul tuo computer contenente i file da archiviare (ad es. “Your Document Directory”).

## Importare i namespace
Prima di scrivere qualsiasi codice, importa i namespace necessari affinché il compilatore sappia dove trovare le classi Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Passo 1: Impostare la directory dei documenti
Definisci il percorso in cui risiedono i file di origine. Sostituisci il segnaposto con la cartella reale sul tuo sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Creare l'archivio Zip senza compressione
Il cuore del tutorial – creiamo un'istanza di `Archive` configurata con `StoreCompressionSettings`. Questo indica ad Aspose.Zip di *memorizzare* (cioè non comprimere) ogni voce.

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

> **Suggerimento:** Se devi **salvare file in zip** comprimendo alcuni e lasciandone altri non compressi, crea istanze separate di `ArchiveEntrySettings` per ciascun file e aggiungile allo stesso `Archive`.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **File non trovato** | Percorso `dataDir` errato o estensione del file mancante. | Verifica il percorso e assicurati che i file esistano. Usa `Path.Combine` per una concatenazione più sicura. |
| **Accesso negato** | Il processo non ha i permessi per leggere i file di origine o scrivere lo ZIP. | Esegui l'applicazione con i diritti appropriati o scegli una cartella con permessi di scrittura. |
| **Dimensione inattesa del file nello ZIP** | L'archivio è stato creato con compressione predefinita. | Assicurati che venga passato `new StoreCompressionSettings()` a `ArchiveEntrySettings`. |

## Domande frequenti

**D: Posso comprimere tipi di file specifici lasciando altri non compressi?**  
R: Sì, puoi creare diversi `ArchiveEntrySettings` per ciascun file e mescolare voci compresse e non compresse nello stesso archivio.

**D: Aspose.Zip per .NET è compatibile con .NET Core e .NET 5/6?**  
R: Assolutamente. La libreria supporta .NET Framework, .NET Core, .NET Standard e le versioni più recenti di .NET.

**D: Come gestire le eccezioni durante il processo di archiviazione?**  
R: Avvolgi il codice di archiviazione in un blocco `try‑catch` e registra i dettagli dell'eccezione. Questo garantisce un fallimento controllato e una più facile diagnostica.

**D: Aspose.Zip supporta l'archiviazione multithread?**  
R: Sì, puoi elaborare più file in parallelo e aggiungerli all'archivio, ma ricorda che l'oggetto `Archive` di per sé non è thread‑safe; sincronizza l'accesso quando aggiungi voci.

**D: Posso integrare Aspose.Zip in un progetto esistente senza grandi modifiche al codice?**  
R: Certamente. L'API è progettata per un utilizzo semplice tipo “drop‑in”. Consulta la [documentazione ufficiale](https://reference.aspose.com/zip/net/) per le linee guida di migrazione.

---

**Ultimo aggiornamento:** 2026-02-12  
**Testato con:** Aspose.Zip per .NET (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}