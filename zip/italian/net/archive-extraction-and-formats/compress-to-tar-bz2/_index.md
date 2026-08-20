---
date: 2026-08-07
description: Scopri come aggiungere file a tar e generare un archivio TarBz2 in .NET
  usando Aspose.Zip. Guida passo‑passo mostra la creazione di tar, compressione Bzip2
  e consigli di best‑practice.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Compressione in TarBz2
og_description: Aggiungi file a tar e genera un archivio TarBz2 in .NET usando Aspose.Zip.
  Questa guida copre la creazione di tar, compressione Bzip2 e suggerimenti per la
  risoluzione dei problemi.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Aggiungere file a tar e creare un archivio TarBz2 con Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Aggiungere file a tar e creare un archivio TarBz2 con Aspose.Zip
url: /it/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere file a tar e creare un archivio TarBz2 con Aspose.Zip

In questo tutorial scoprirai **come aggiungere file a tar** archivi e trasformarli in un compatto file **TarBz2** usando la libreria **Aspose.Zip** per .NET. Che tu stia creando un'utilità di backup, pubblicando pacchetti di distribuzione, o abbia bisogno di un bundle leggero per la distribuzione, i passaggi seguenti ti guideranno nell'aggiungere file a un contenitore tar, applicare la compressione Bzip2 e produrre un archivio pronto da condividere.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.Zip for .NET  
- **Quanto tempo richiede l'implementazione?** About 5‑10 minutes  
- **È necessaria una licenza?** A temporary license is required for production; a free trial is available  
- **Posso comprimere più file?** Yes – add as many entries as you like to the tar archive  
- **È compatibile con .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## Cos'è un archivio TarBz2?

Un file TarBz2 combina il tradizionale contenitore **tar** (che preserva la struttura delle directory e i metadati dei file) con la compressione **Bzip2**, risultando in un pacchetto altamente compresso `.tar.bz2`. Questo formato è popolare sui sistemi Unix‑like perché offre un buon equilibrio tra rapporto di compressione e velocità di decompressione.

## Perché comprimere file in TarBz2 con Aspose.Zip?

Aspose.Zip può generare un archivio TarBz2 in **due chiamate API** gestendo i flussi in modo efficiente. Supporta **oltre 50 formati di archivio e compressione**, elabora file fino a **2 GB** senza caricare l'intero archivio in memoria, e funziona su runtime .NET per Windows, Linux e macOS. La libreria offre anche un controllo dettagliato su nomi delle voci, timestamp e livelli di compressione, rendendola ideale sia per utility da console sia per servizi web.

## Prerequisiti

- **Aspose.Zip for .NET** – scarica l'ultimo pacchetto dal sito ufficiale: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – una cartella che contiene i file che desideri archiviare. Negli esempi lo riferiamo con la variabile `dataDir`.

> **Consiglio:** Mantieni i tuoi file sorgente in una cartella dedicata per evitare l'inclusione accidentale di file indesiderati.

## Importare gli spazi dei nomi

Per prima cosa, importa gli spazi dei nomi necessari così da poter accedere alle classi Tar e Bzip2 di Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Passo 1: impostare la directory dei documenti

Definisci il percorso che punta alla cartella contenente i file che desideri archiviare.

```csharp
string dataDir = "Your Document Directory";
```

> Sostituisci `"Your Document Directory"` con il percorso assoluto o relativo della tua cartella sorgente.

## Passo 2: aggiungere file a tar e creare un archivio TarBz2

`TarArchive` rappresenta un contenitore tar in memoria che può contenere più voci di file.  
`Bzip2Archive` comprime un flusso usando l'algoritmo Bzip2.  
Il metodo `CreateEntry` aggiunge un file all'archivio tar come una nuova voce.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **aggiunge file a tar** – puoi chiamare questo metodo per ogni file necessario nell'archivio.  
- `bz2.SetSource(archive)` indica all'archivio Bzip2 di comprimere l'intero flusso tar.  
- `bz2.Save(...)` scrive il file finale **TarBz2** su disco.

**Suggerimento:** Per **aggiungere file a tar** in blocco, ripeti semplicemente `archive.CreateEntry` per ogni file prima di chiamare `bz2.Save`.

## Come aggiungere file a tar?

Carica la directory sorgente, crea un'istanza `TarArchive`, aggiungi ogni file con `CreateEntry`, quindi avvolgi il flusso tar in un `Bzip2Archive` e chiama `Save`. Questo modello a due passaggi aggiunge un numero qualsiasi di file e produce un file `.tar.bz2` in un unico flusso fluido, eliminando la necessità di file temporanei o strumenti esterni.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Errore file non trovato** | Percorso `dataDir` errato o estensione del file mancante | Verifica il percorso completo e assicurati che il file esista. |
| **Archivio vuoto** | Nessuna voce aggiunta prima di `bz2.Save` | Aggiungi almeno una chiamata `CreateEntry`. |
| **Permesso negato** | L'applicazione non ha i permessi di scrittura sulla cartella di destinazione | Esegui l'app con i diritti appropriati o scegli una directory scrivibile. |

## Domande frequenti

**Q: Aspose.Zip è compatibile con tutte le applicazioni .NET?**  
A: Sì. Funziona con .NET Framework, .NET Core, .NET 5/6 e runtime più recenti.

**Q: Posso comprimere più file simultaneamente?**  
A: Assolutamente. Chiama `CreateEntry` per ogni file prima di salvare l'archivio.

**Q: Dove posso trovare documentazione aggiuntiva?**  
A: Documenti dettagliati sono disponibili nella **riferimento API .NET di Aspose.Zip**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Zip?**  
A: Puoi **richiedere una licenza temporanea** qui: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: È disponibile una versione di prova gratuita?**  
A: Sì, **scarica una versione di prova dalle release di Aspose**: [download a trial version](https://releases.aspose.com/).

## Conclusione

Ora sai **come aggiungere file a tar**, comprimere il flusso tar con Bzip2 e generare un archivio **TarBz2** usando Aspose.Zip per .NET. L'approccio è veloce, efficiente in termini di memoria e funziona su tutte le piattaforme .NET moderne. Sentiti libero di sperimentare con insiemi di file più grandi, nomi di voci personalizzati, o integrare il codice nei tuoi propri pipeline di backup o distribuzione.

Se incontri delle difficoltà, la community di Aspose.Zip è pronta ad aiutarti—basta andare al **forum di supporto Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Ultimo aggiornamento:** 2026-08-07  
**Testato con:** Aspose.Zip for .NET (latest release)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea archivio tar e aggiungi file a tar con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aggiungi file a tar e crea archivio tarxz con Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Aggiungi file a tar e comprimi in TarZ con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}