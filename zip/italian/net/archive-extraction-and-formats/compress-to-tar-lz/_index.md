---
date: 2026-07-04
description: Scopri come comprimere più file tar usando Aspose.Zip per .NET e creare
  archivi tar.lz in modo efficiente.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Compressione in TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come comprimere più file tar con Aspose.Zip per .NET
url: /it/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come comprimere più file tar con Aspose.Zip per .NET

Nello sviluppo .NET moderno, impacchettare i file in modo efficiente può migliorare notevolmente le dimensioni del deployment e i tempi di trasferimento in rete. **Compress multiple files tar** è una necessità frequente quando hai bisogno di un archivio TAR leggero, compresso LZ, per backup, distribuzione o caricamenti su cloud. In questo tutorial vedremo passo‑passo un **esempio di compressione tar.lz** usando la libreria Aspose.Zip, così potrai creare rapidamente un **archivio tar.lz** nelle tue applicazioni.

## Risposte rapide
- **Quale libreria devo usare?** Aspose.Zip per .NET.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per un esempio base.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso comprimere più file contemporaneamente?** Sì – basta aggiungere più voci prima di salvare.

## Come comprimere più file tar con Aspose.Zip per .NET?
Carica i file di origine, crea un'istanza di `TarArchive`, aggiungi ogni file con `CreateEntry` e termina chiamando `SaveLzipped`. La libreria gestisce internamente la struttura TAR e la compressione LZ, così ottieni un unico file `*.tar.lz` in poche righe di codice. Questo approccio funziona su Windows, Linux e macOS senza dipendenze native.

## Cos'è la compressione tar.lz?
`tar.lz` è un archivio TAR compresso usando l'algoritmo LZMA (spesso indicato semplicemente come **LZ**). Combina la semplicità del raggruppamento dei file di TAR con l'elevato rapporto di compressione di LZ, rendendolo ideale per file di backup, distribuzione di pacchetti o qualsiasi scenario in cui la larghezza di banda è importante.

## Perché usare Aspose.Zip per .NET?
Aspose.Zip offre una soluzione pure‑managed, cross‑platform che crea archivi TAR, ZIP e basati su LZ senza strumenti esterni, supporta oltre 30 formati di archivio e fornisce fino al 30 % di compressione migliore su file di grandi dimensioni, offrendo eccezioni dettagliate per una gestione robusta degli errori. Inoltre si integra perfettamente con i framework di logging .NET e fornisce eventi di avanzamento dettagliati.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Aspose.Zip for .NET** library – download it from [qui](https://releases.aspose.com/zip/net/).  
- Una cartella che contiene i file che desideri archiviare. Il percorso di questa cartella sarà memorizzato nella variabile `dataDir` (lo imposterai al Passo 3).

## Importa gli spazi dei nomi
Aggiungi gli spazi dei nomi richiesti in modo che il compilatore sappia dove trovare le classi che utilizzeremo.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Come creare un archivio tar.lz – Guida passo‑passo

### Passo 1: Comprimere un singolo file
Il primo esempio mostra lo scenario più basilare – aggiungere un file a un archivio TAR e poi salvarlo come file **tar.lz**.

La classe `TarArchive` rappresenta un contenitore TAR che può contenere più file in un unico archivio.  

**Spiegazione**

- `new TarArchive()` crea un contenitore TAR vuoto.  
- `CreateEntry` aggiunge il file `alice29.txt` dalla tua `dataDir`.  
- `SaveLzipped` scrive l'archivio su disco e applica la compressione LZ, producendo `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Passo 2: Comprimere più file in un unico archivio
Spesso avrai bisogno di raggruppare diversi file insieme. Basta chiamare `CreateEntry` per ogni file prima di salvare. Questo dimostra **add files to tar lz** e, in modo efficace, **compress multiple files tar**.

**Spiegazione**

- Il codice segue lo stesso schema del Passo 1, ma aggiunge una seconda voce (`lcet10.txt`).  
- Puoi ripetere `CreateEntry` quante volte è necessario; la libreria gestisce automaticamente la struttura interna TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Passo 3: Specificare la directory dei documenti
Sostituisci il segnaposto con il percorso reale dove risiedono i tuoi file di origine. Questo percorso è usato dagli esempi sopra.

**Spiegazione**

- Imposta `dataDir` su un percorso di cartella completamente qualificato, ad esempio `@"C:\MyFiles\"`.  
- Mantenere la directory in una variabile rende il codice riutilizzabile e più facile da mantenere.

```csharp
string dataDir = "Your Document Directory";
```

## Problemi comuni e risoluzione
| Sintomo | Probabile causa | Soluzione |
|---------|----------------|-----------|
| `FileNotFoundException` durante l'esecuzione del campione | `dataDir` punta a una cartella inesistente o il nome del file è scritto in modo errato | Verifica il percorso e i nomi dei file; usa `Path.Combine` per sicurezza. |
| Il file di output è **0 KB** | `archive.SaveLzipped` è stato chiamato prima di aggiungere voci | Assicurati che almeno una chiamata a `CreateEntry` preceda `SaveLzipped`. |
| La compressione sembra lenta | File di grandi dimensioni con dimensione predefinita del buffer | Considera di elaborare i file a blocchi o di usare I/O asincrono se le prestazioni sono critiche. |

## Conclusione
Ora sai **come comprimere tar.lz** file usando Aspose.Zip per .NET, sia che tu stia gestendo un singolo documento sia una collezione di file. Questo **esempio di compressione tar.lz** dimostra un modo pulito e pronto per la produzione di **creare archivi tar lz** che possono essere facilmente trasferiti o archiviati. Puoi comprimere file in tar.lz usando la stessa API chiamando `SaveLzipped` dopo aver aggiunto tutte le voci desiderate.

## Domande frequenti

**D:** Posso comprimere file di qualsiasi dimensione usando Aspose.Zip per .NET?  
**R:** Sì, la libreria gestisce sia file piccoli che molto grandi; basta assicurarsi di avere sufficiente memoria e spazio su disco per la struttura temporanea TAR.

**D:** Il codice è compatibile con l'ultima versione di Aspose.Zip?  
**R:** Il campione è mirato alla versione corrente; mantieni sempre il pacchetto NuGet aggiornato per correzioni di bug e nuove funzionalità.

**D:** Ci sono considerazioni di licenza?  
**R:** È necessaria una licenza commerciale per l'uso in produzione. Vedi i dettagli di licenza sul [sito Aspose](https://purchase.aspose.com/buy).

**D:** Posso usare questo in un progetto commerciale?  
**R:** Assolutamente – una volta in possesso di una licenza valida, puoi incorporare la libreria in qualsiasi applicazione commerciale.

**D:** Dove posso ottenere supporto se incontro problemi?  
**R:** Visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per supporto della community e assistenza ufficiale.

---

**Last Updated:** 2026-07-04  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea archivio tar e aggiungi file a tar con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Come comprimere tar e creare TarBz2 con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aggiungi file a tar e crea archivio tarxz con Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}