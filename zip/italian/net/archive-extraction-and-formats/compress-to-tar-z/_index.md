---
date: 2025-11-29
description: Scopri come aggiungere file a un archivio tar e comprimerli in TarZ usando
  Aspose.Zip per .NET – una guida passo‑passo per una gestione efficiente dei file
  .NET.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aggiungi file a tar e comprimi in TarZ con Aspose.Zip per .NET
url: /it/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere file a tar e comprimere in TarZ con Aspose.Zip per .NET

## Introduzione

Se hai bisogno di **add files to tar** e poi comprimere l'archivio nel formato TarZ, Aspose.Zip per .NET rende l'intero processo indolore. In questo tutorial percorreremo ogni passaggio—dalla configurazione del progetto alla creazione di un archivio tar, aggiunta dei file e, infine, salvataggio di un file compresso .tar.z. Alla fine avrai uno snippet riutilizzabile da inserire in qualsiasi applicazione .NET.

## Risposte Rapide
- **Quale libreria gestisce la creazione di tar?** Aspose.Zip per .NET  
- **Quante righe di codice?** Circa 15 righe (escluse i commenti)  
- **Ho bisogno di una licenza per i test?** È disponibile una versione di prova gratuita; è necessaria una licenza per la produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Posso comprimere cartelle, non solo file?** Sì – è possibile aggiungere intere directory con un ciclo.

## Cos'è **add files to tar**?
Aggiungere file a un archivio tar li raggruppa in un unico contenitore non compresso che preserva la struttura delle directory e i metadati dei file. Tar è un formato Unix classico e funge da base per molti flussi di lavoro di compressione, incluso il formato TarZ utilizzato in questa guida.

## Perché aggiungere file a tar prima di comprimere in TarZ?
- **Portabilità** – Un archivio tar funziona su più piattaforme senza preoccuparsi della gestione di file singoli.  
- **Velocità** – Creare il contenitore tar è veloce; la successiva compressione Z si concentra solo sulla riduzione delle dimensioni.  
- **Compatibilità** – Molti strumenti legacy si aspettano un `.tar` prima di applicare una compressione in stile gzip, che è esattamente ciò che fornisce `.tar.z`.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere:

- **Aspose.Zip per .NET** installato. Scaricalo dal sito ufficiale [qui](https://releases.aspose.com/zip/net/).  
- Una cartella sul tuo computer che contiene i file da archiviare. Sostituisci il percorso segnaposto con la tua directory reale.

## Importare gli Spazi dei Nomi

Aggiungi le istruzioni `using` richieste all'inizio del tuo file C#:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Guida Passo‑Passo

### Passo 1: Definire la Directory del Documento

```csharp
string dataDir = "Your Document Directory";
```

> **Suggerimento:** Usa `Path.Combine` se devi costruire percorsi dinamicamente; evita la mancanza di separatori di percorso su diversi OS.

### Passo 2: Creare un Archivio Tar e aggiungere file

#### 2.1: Creare l'istanza dell'archivio Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Aggiungere file all'archivio  

All'interno del blocco `using`, aggiungi ogni file che desideri includere:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Puoi ripetere `CreateEntry` per tutti i file necessari, oppure iterare una directory per aggiungerli programmaticamente.

#### 2.3: Salvare il file TarZ compresso  

Dopo aver aggiunto tutte le voci, comprimi l'archivio tar nel formato `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Il file risultante `archive.tar.z` verrà posizionato nella stessa cartella specificata in `dataDir`.

## Problemi Comuni e Soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **File non trovato** | Percorso errato o estensione del file mancante | Verifica che `dataDir` termini con un separatore di percorso e che i nomi dei file siano corretti. |
| **Accesso negato** | Permessi insufficienti sulla cartella di destinazione | Esegui l'applicazione con i diritti appropriati o scegli una directory scrivibile. |
| **Il file compresso è più grande del previsto** | I file originali sono già compressi (es. immagini, video) | TarZ funziona al meglio su file di testo o log; considera di lasciare i file già compressi così come sono. |

## Domande Frequenti

**D: Posso comprimere intere cartelle con Aspose.Zip per .NET?**  
R: Assolutamente. Usa un ciclo `Directory.GetFiles` e chiama `CreateEntry` per ogni file, preservando i percorsi relativi.

**D: È disponibile una versione di prova perose.Zip per .NET?**  
R: Sì, puoi esplorare le funzionalità di Aspose.Zip per .NET scaricando la versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione completa per Aspose.Zip per .NET?**  
R: La documentazione è disponibile [qui](https://reference.aspose.com/zip/net/), fornendo approfondimenti dettagliati sulle caratteristiche e sull'uso della libreria.

**D: Come posso ottenere supporto per Aspose.Zip per .NET?**  
R: Visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per chiedere assistenza, condividere esperienze e connetterti con la community.

**D: Posso ottenere una licenza temporanea per Aspose.Zip per .NET?**  
R: Sì, se ti serve una licenza temporanea, puoi ottenerla [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione

Ora sai come **add files to tar** e comprimere il risultato in un archivio TarZ usando Aspose.Zip per .NET. Questo approccio ti fornisce un pacchetto pulito e portabile, facilmente trasferibile, archiviabile o ulteriormente processato. Sentiti libero di adattare lo snippet per elaborare batch di directory, integrarlo nei pipeline di build o combinarlo con altri componenti Aspose per flussi di lavoro documentali più ricchi.

---

**Ultimo aggiornamento:** 2025-11-29  
**Testato con:** Aspose.Zip per .NET 24.11  
**Autore:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}