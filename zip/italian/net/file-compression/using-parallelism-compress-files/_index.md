---
date: 2025-12-10
description: Impara la compressione di file in parallelo in .NET usando Aspose.Zip.
  Comprimi più file in modo efficiente con la nostra guida passo‑passo.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Compressione di file in parallelo con Aspose.Zip per .NET
url: /it/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compressione di file in parallelo con Aspose.Zip per .NET

## Introduzione

Nel mondo dello sviluppo .NET, la **compressione di file in parallelo** è fondamentale per ottimizzare lo spazio di archiviazione e velocizzare la trasmissione dei dati. Aspose.Zip per .NET offre una soluzione potente, e una delle sue caratteristiche distintive è la capacità di sfruttare il parallelismo per la compressione dei file. In questo tutorial, ti guideremo nell'utilizzo del parallelismo per **comprimere più file** in modo efficiente con Aspose.Zip per .NET.

## Risposte rapide
- **Cos'è la compressione di file in parallelo?** Una tecnica che comprime diversi file simultaneamente, utilizzando più core CPU per ridurre il tempo di elaborazione complessivo.  
- **Quale libreria la supporta in .NET?** Aspose.Zip per .NET offre opzioni di compressione parallela integrate.  
- **Ho bisogno di una licenza?** È disponibile una licenza temporanea per i test; è necessaria una licenza completa per la produzione.  
- **Posso aggiungere file allo zip al volo?** Sì—usa `Archive.CreateEntry` per ogni file che desideri includere.  
- **È compatibile con .NET Core/5/6?** Assolutamente, l'API funziona su tutti i runtime .NET moderni.

## Cos'è la compressione di file in parallelo?
La compressione di file in parallelo consiste nel dividere il carico di lavoro di compressione su più thread o core, consentendo a diversi file (o a parti di un file di grandi dimensioni) di essere compressi contemporaneamente. Questo approccio riduce drasticamente il tempo necessario per creare un **zip archive c#** rispetto alla compressione sequenziale tradizionale.

## Perché usare Aspose.Zip per la compressione in parallelo?
- **Speed:** Sfrutta al massimo le CPU multi‑core.  
- **Scalability:** Gestisce grandi lotti di file senza un aumento proporzionale del tempo di elaborazione.  
- **Simplicity:** L'API di alto livello astrae le complessità del threading.  
- **Flexibility:** Funziona con qualsiasi versione .NET e si integra senza problemi con i codebase esistenti.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Conoscenze di base di C# e sviluppo .NET.  
- Libreria Aspose.Zip per .NET installata. Puoi scaricarla **[qui](https://releases.aspose.com/zip/net/)**.  
- Una buona comprensione dei concetti standard di compressione dei file.

## Importare gli spazi dei nomi

Per prima cosa, importa gli spazi dei nomi necessari nel tuo file C# affinché il compilatore sappia dove trovare le classi che utilizzerai.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Passo 1: Configura la directory dei documenti

Definisci la cartella che contiene i file da comprimere. Questo percorso è memorizzato nella variabile `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Inizializza il processo di compressione

Apri un nuovo file ZIP per la scrittura. L'istruzione `using` garantisce che lo stream del file venga correttamente eliminato al termine dell'operazione.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Passo 3: Leggi e comprimi i file in parallelo

Apri ogni file sorgente che intendi aggiungere all'archivio. In questo esempio lavoriamo con due testi classici, ma puoi **add files to zip** per qualsiasi numero di documenti.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Passo 4: Crea le voci dell'archivio

Crea un'istanza `Archive` e aggiungi ogni file come voce separata. È qui che avviene il passaggio **create zip archive c#**.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Passo 5: Definisci il criterio di parallelismo

Configura la compressione per l'esecuzione in parallelo impostando `ParallelOptions`. Il flag `ParallelCompressInMemory` indica ad Aspose.Zip di utilizzare sempre l'elaborazione parallela.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Passo 6: Salva l'archivio compresso

Infine, scrivi l'archivio su disco con le opzioni desiderate, includendo codifica, commento e le impostazioni di parallelismo definite in precedenza.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

Congratulazioni! Hai appena eseguito la **compressione di file in parallelo** usando Aspose.Zip per .NET, comprimendo in modo efficiente **multiple files** in un unico archivio.

## Problemi comuni e consigli

- **Large Files:** Se riscontri pressione sulla memoria, considera di comprimere i file a blocchi anziché caricare l'intero file in memoria.  
- **Thread Safety:** L'API Aspose.Zip è thread‑safe per la modalità parallela; evita di modificare lo stesso stream da più thread al di fuori della libreria.  
- **Performance Tuning:** Sperimenta con `ParallelOptions.MaxDegreeOfParallelism` se devi limitare l'uso della CPU su server condivisi.  

## FAQ

### Q1: Posso usare Aspose.Zip per .NET con altre librerie .NET?

A1: Sì, Aspose.Zip per .NET è progettato per integrarsi perfettamente con altre librerie .NET.

### Q2: È disponibile una licenza temporanea per scopi di test?

A2: Sì, puoi ottenere una licenza temporanea per i test **[qui](https://purchase.aspose.com/temporary-license/)**.

### Q3: Dove posso trovare supporto aggiuntivo o fare domande?

A3: Visita il **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** per il supporto della community e le discussioni.

### Q4: Sono disponibili esempi o documentazione?

A4: Esplora la **[documentazione Aspose.Zip](https://reference.aspose.com/zip/net/)** per esempi completi e guide dettagliate.

### Q5: Come posso acquistare Aspose.Zip per .NET?

A5: Puoi acquistare Aspose.Zip per .NET **[qui](https://purchase.aspose.com/buy)**.

---

**Ultimo aggiornamento:** 2025-12-10  
**Testato con:** Aspose.Zip 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}