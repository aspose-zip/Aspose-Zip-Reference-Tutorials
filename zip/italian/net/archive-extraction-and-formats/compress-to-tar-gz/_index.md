---
date: 2026-02-20
description: Impara come creare un archivio tar, aggiungere file al tar e comprimere
  in tar.gz usando Aspose.Zip per .NET – un modo veloce e multipiattaforma per creare
  archivi TarGz.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea archivio tar e aggiungi file al tar con Aspose.Zip per .NET
url: /it/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea archivio tar e aggiungi file a tar con Aspose.Zip per .NET

## Introduzione

Nelle moderne applicazioni .NET, **creare un archivio tar** e **aggiungere file a tar** in modo rapido e affidabile è una necessità comune—sia che tu stia impacchettando log, preparando dati per l'archiviazione cloud o costruendo bundle di distribuzione. Aspose.Zip per .NET ti offre un'API pulita e ad alte prestazioni per **add files to tar**, per poi comprimere l'archivio nel formato ampiamente usato **tar.gz**. In questa guida percorreremo l'intero processo, dalla configurazione del progetto alla produzione di un `archive.tar.gz` pronto per la distribuzione.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.Zip per .NET  
- **Come aggiungere file a tar?** Usa `TarArchive.CreateEntry` per ogni file.  
- **Posso comprimere direttamente in tar.gz?** Sì—chiama `SaveGzipped`.  
- **Ho bisogno di una licenza per la produzione?** È necessaria una licenza Aspose valida per l'uso non‑trial.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cosa significa “add files to tar”?
Aggiungere file a un archivio tar significa raggruppare più file in un unico contenitore non compresso. Il formato tar preserva le strutture delle directory e i metadati dei file, rendendolo ideale per l'archiviazione prima di una compressione opzionale (ad es., gzip) per **creare un archivio tar.gz**.

## Perché usare Aspose.Zip per comprimere file in tar.gz?
- **Nessun tool esterno** – tutto gira all'interno del tuo codice .NET.  
- **Alta performance** – l'API basata su stream gestisce file di grandi dimensioni in modo efficiente.  
- **Tar cross‑platform** – funziona su Windows, Linux e macOS senza modifiche.  
- **Set di funzionalità ricco** – supporta crittografia, protezione con password e attributi personalizzati per le voci.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Esperienza di base nello sviluppo .NET.  
- Visual Studio (o qualsiasi IDE preferito).  
- Aspose.Zip per .NET installato – vedi la documentazione ufficiale [qui](https://reference.aspose.com/zip/net/).  
- La libreria Aspose.Zip scaricata da [questo link](https://releases.aspose.com/zip/net/).

## Importa gli spazi dei nomi

Nel tuo progetto .NET, importa gli spazi dei nomi che espongono le classi relative a tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Come aggiungere file a tar usando Aspose.Zip per .NET

### Passo 1: Imposta la tua directory dei documenti

Per prima cosa, indica al codice la cartella che contiene i file da archiviare.

```csharp
string dataDir = "Your Document Directory";
```

> **Suggerimento:** Usa `Path.Combine` quando costruisci i percorsi per evitare problemi con i separatori specifici della piattaforma.

### Passo 2: Crea un archivio TarGz

Ora creeremo l'archivio tar, aggiungeremo le voci e lo comprimeremo in un unico flusso fluido.

#### 2.1 Inizializza il TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Aggiungi file – il nucleo di “add files to tar”

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Ogni chiamata a `CreateEntry` richiede il **nome della voce** (come il file apparirà all'interno del tar) e il **percorso del file sorgente** sul disco. Puoi chiamare `CreateEntry` ripetutamente per **add multiple files tar** in un unico archivio.

#### 2.3 Salva come Tar Gzippato (come comprimere tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` scrive il contenuto del tar in uno stream gzip, fornendoti un compatto file `archive.tar.gz` pronto per la distribuzione.

## Casi d'uso comuni

| Scenario | Perché “add files to tar” è utile |
|----------|-----------------------------------|
| **Aggregazione log** | Raggruppa i log giornalieri in un unico archivio prima di caricarli nello storage cloud. |
| **Pacchetti di distribuzione** | Crea bundle tar.gz portabili per server Linux a partire da una pipeline di build Windows. |
| **Backup dei dati** | Preserva la gerarchia delle cartelle e i metadati mantenendo ridotto il peso del backup. |

## Problemi comuni e soluzioni

- **Errore file non trovato** – Assicurati che `dataDir` termini con il separatore di percorso appropriato o usa `Path.Combine`.  
- **File di grandi dimensioni causano pressione sulla memoria** – Usa overload basati su stream (`CreateEntry` con uno `Stream`) per evitare di caricare interi file in memoria.  
- **L'output gzip è corrotto** – Verifica che l'archivio sia chiuso (`using` block) prima di chiamare `SaveGzipped`.  

## Domande frequenti

**D: Aspose.Zip per .NET è compatibile con tutte le applicazioni .NET?**  
R: Sì, funziona con progetti .NET Framework, .NET Core e .NET 5/6/7.

**D: Come posso ottenere una licenza temporanea per Aspose.Zip per .NET?**  
R: Visita la [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/) per richiedere una licenza di prova.

**D: Esistono limitazioni di dimensione dei file?**  
R: La libreria è ottimizzata per file di grandi dimensioni; non c'è un limite rigido oltre la memoria di sistema disponibile.

**D: Dove posso ottenere supporto?**  
R: Usa il forum di supporto gestito dalla community [qui](https://forum.aspose.com/c/zip/37) per ricevere aiuto da ingegneri Aspose e altri sviluppatori.

**D: Posso provare Aspose.Zip per .NET gratuitamente?**  
R: Assolutamente—scarica la versione di prova gratuita dalla [pagina dei rilasci Aspose Zip](https://releases.aspose.com/zip/net).

## Conclusione

Ora sai **come creare un archivio tar**, aggiungere file al suo interno e comprimerlo in **tar.gz** usando Aspose.Zip per .NET. Questo approccio elimina dipendenze esterne, ti offre un controllo granulare sul contenuto dell'archivio e scala a grandi set di dati. Sentiti libero di esplorare ulteriori funzionalità di Aspose.Zip come la crittografia, gli attributi personalizzati delle voci e le API di streaming per migliorare ulteriormente il tuo flusso di lavoro di archiviazione.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose