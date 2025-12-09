---
date: 2025-12-01
description: Scopri come comprimere file tar.lz in .NET con Aspose.Zip e creare facilmente
  archivi tar.lz.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come comprimere tar.lz con Aspose.Zip per .NET
url: /it/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come comprimere tar.lz con Aspose.Zip per .NET

Nello sviluppo .NET moderno, impacchettare i file in modo efficiente può migliorare notevolmente le dimensioni di distribuzione e i tempi di trasferimento in rete. **Come comprimere tar.lz** è una necessità comune quando serve un archivio TAR leggero, compresso con LZ. In questo tutorial percorreremo un chiaro esempio **di compressione tar.lz** passo‑passo usando la libreria Aspose.Zip, così potrai creare rapidamente un archivio tar.lz nelle tue applicazioni.

## Risposte rapide
- **Quale libreria devo usare?** Aspose.Zip for .NET.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per un esempio base.  
- **Ho bisogno di una licenza?** Una prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso comprimere più file contemporaneamente?** Sì – basta aggiungere più voci prima di salvare.

## Cos'è la compressione tar.lz?
`tar.lz` è un archivio TAR compresso usando l'algoritmo LZMA (spesso indicato semplicemente come **LZ**). Combina la semplicità del raggruppamento di file di TAR con l'elevato rapporto di compressione di LZ, rendendolo ideale per file di backup, distribuzione di pacchetti o qualsiasi scenario in cui la larghezza di banda è importante.

## Perché usare Aspose.Zip per .NET?
Aspose.Zip astrae i dettagli a basso livello della creazione di archivi, fornendoti un'API pulita e orientata agli oggetti. Ottieni:

* **Zero dipendenze esterne** – implementazione pura .NET.  
* **Supporto cross‑platform** – funziona su Windows, Linux e macOS.  
* **Compressione LZ integrata** – non è necessario installare strumenti nativi aggiuntivi.  
* **Gestione robusta degli errori** – le eccezioni sono descrittive, facilitando il debug.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Libreria Aspose.Zip for .NET** – scaricala da [qui](https://releases.aspose.com/zip/net/).  
- Una cartella che contiene i file da archiviare. Il percorso di questa cartella sarà memorizzato nella variabile `dataDir` (la imposterai al Passo 3).

## Importare gli spazi dei nomi
Aggiungi gli spazi dei nomi necessari affinché il compilatore sappia dove trovare le classi che utilizzeremo.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Come creare un archivio tar.lz – Guida passo‑passo

### Passo 1: Comprimere un singolo file
Il primo esempio mostra lo scenario più basilare – aggiungere un file a un archivio TAR e poi salvarlo come file **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Spiegazione**

- `new TarArchive()` crea un contenitore TAR vuoto.  
- `CreateEntry` aggiunge il file `alice29.txt` dalla tua `dataDir`.  
- `SaveLzipped` scrive l'archivio su disco e applica la compressione LZ, producendo `archive.tar.lz`.

### Passo 2: Comprimere più file in un unico archivio
Spesso avrai bisogno di raggruppare diversi file insieme. Basta chiamare `CreateEntry` per ogni file prima di salvare.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Spiegazione**

- Il codice segue lo stesso schema del Passo 1, ma aggiunge una seconda voce (`lcet10.txt`).  
- Puoi ripetere `CreateEntry` quante volte è necessario; la libreria gestisce automaticamente la struttura interna del TAR.

### Passo 3: Specificare la directory dei documenti
Sostituisci il segnaposto con il percorso reale dove risiedono i tuoi file sorgente. Questo percorso è usato dagli esempi sopra.

```csharp
string dataDir = "Your Document Directory";
```

**Spiegazione**

- Imposta `dataDir` a un percorso di cartella completamente qualificato, ad esempio `@\"C:\\MyFiles\\\"`.  
- Mantenere la directory in una variabile rende il codice riutilizzabile e più facile da mantenere.

## Problemi comuni e risoluzione
| Sintomo | Probabile causa | Correzione |
|---------|-----------------|------------|
| `FileNotFoundException` durante l'esecuzione del campione | `dataDir` punta a una cartella inesistente o il nome del file è scritto male | Verifica il percorso e i nomi dei file; usa `Path.Combine` per sicurezza. |
| Il file di output è **0 KB** | `archive.SaveLzipped` è stato chiamato prima di aggiungere voci | Assicurati che almeno una chiamata a `CreateEntry` preceda `SaveLzipped`. |
| La compressione sembra lenta | File di grandi dimensioni con dimensione buffer predefinita | Considera di elaborare i file a blocchi o usare I/O asincrono se le prestazioni sono critiche. |

## Conclusione
Ora sai **come comprimere file tar.lz** usando Aspose.Zip per .NET, sia che tu stia gestendo un singolo documento sia una collezione di file. Questo **esempio di compressione tar.lz** dimostra un modo pulito e pronto per la produzione di creare archivi leggeri che possono essere facilmente trasferiti o archiviati.

## Domande frequenti

**D:** Posso comprimere file di qualsiasi dimensione usando Aspose.Zip per .NET?  
**R:** Sì, la libreria gestisce sia file piccoli che molto grandi; basta assicurarsi di avere memoria e spazio su disco sufficienti per la struttura temporanea del TAR.

**D:** Il codice è compatibile con l'ultima versione di Aspose.Zip?  
**R:** Il campione è mirato alla versione corrente; mantieni sempre il pacchetto NuGet aggiornato per correzioni di bug e nuove funzionalità.

**D:** Ci sono considerazioni di licenza?  
**R:** È necessaria una licenza commerciale per l'uso in produzione. Vedi i dettagli di licenza sul [sito Aspose](https://purchase.aspose.com/buy).

**D:** Posso usarlo in un progetto commerciale?  
**R:** Assolutamente – una volta ottenuta una licenza valida, puoi incorporare la libreria in qualsiasi applicazione commerciale.

**D:** Dove posso ottenere supporto se incontro problemi?  
**R:** Visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per supporto della community e assistenza ufficiale.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-01  
**Testato con:** Aspose.Zip for .NET (latest release)  
**Autore:** Aspose