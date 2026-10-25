---
date: 2026-10-25
description: Scopri come estrarre la password zip e impostare compression algorithm
  quando comprimi file tar con Aspose.Zip per .NET, migliorando storage efficiency
  e security.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Estrazione di archivi e formati
og_description: Scopri come estrarre la password zip e impostare compression algorithm
  quando comprimi file tar con Aspose.Zip per .NET, migliorando storage efficiency
  e security.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Estrai la password zip e comprimi i file tar con Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Estrai la password zip e comprimi i file tar con Aspose.Zip
url: /it/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai la password zip e comprimi file tar con Aspose.Zip

## Introduzione

In questa guida scoprirai le tecniche **extract zip password**, imparerai come impostare l'algoritmo di compressione quando crei archivi basati su tar e vedrai come costruire TarGz, TarBz2 e altri formati con Aspose.Zip per .NET. Che tu stia creando un servizio di backup, un client di cloud‑storage o una pipeline di elaborazione dati, padroneggiare queste operazioni riduce i costi di archiviazione, velocizza i trasferimenti e protegge i file sensibili.

## Risposte rapide
- **Cos'è TarBz2?** Un archivio compresso che combina il packaging TAR con la compressione BZIP2 per rapporti di compressione elevati.  
- **Perché scegliere Aspose.Zip per .NET?** Supporta più di 50 formati di archivio e compressione, funziona su Windows, Linux e macOS, e mantiene l'uso della memoria sotto i 10 MB per archivi di diverse centinaia di megabyte.  
- **Posso creare un archivio TarGz?** Sì – Aspose.Zip offre TarGz, TarLz, TarXz, TarZ e altro.  
- **Come estrarre un archivio zip protetto da password?** Imposta la proprietà `Password` su ogni `ArchiveEntry` prima di chiamare `Extract`.  
- **È necessaria una licenza per l'uso in produzione?** È necessaria una licenza commerciale per la produzione; è disponibile una prova gratuita per la valutazione.

## Cos'è la compressione tar?

La compressione tar combina il contenitore TAR con un algoritmo di compressione come BZIP2, GZIP, LZMA o XZ. Il risultato è un unico file (ad es., `.tar.gz`, `.tar.bz2`) che può essere estratto su Linux, macOS e Windows. Preserva la gerarchia originale delle directory, consente l'estrazione ad accesso casuale ed è ampiamente supportato da strumenti da riga di comando e librerie di programmazione, rendendolo ideale per la distribuzione cross‑platform e l'archiviazione.

## Perché usare Aspose.Zip per .NET per gestire questi formati?

Aspose.Zip fornisce un'API unificata, senza dipendenze, che supporta **50+** formati di archivio e compressione, inclusi tutti i principali tipi basati su tar. La sua architettura di streaming elabora archivi più grandi di 10 GB mantenendo l'uso della RAM sotto i 10 MB, rendendola ideale per carichi di lavoro server ad alta velocità.

**Risposta diretta:** Usa Aspose.Zip perché ti consente di creare, comprimere ed estrarre archivi basati su tar e file zip protetti da password con una singola API fluida, senza strumenti esterni, gestendo archivi multi‑gigabyte in modalità streaming a basso consumo di memoria.

## Prerequisiti
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, o .NET 5–10.  
- Pacchetto NuGet Aspose.Zip per .NET (`Install-Package Aspose.Zip`).  
- Familiarità di base con I/O file C# e il sistema di progetto .NET.

## Guida passo‑passo

### Come comprimere file tar – risposta diretta
Crea un'istanza `Archive`, aggiungi i file che desideri raggruppare, imposta `CompressionType.BZip2` (o un altro algoritmo) e chiama `Save` con `ArchiveFormat.TarBz2`. La libreria scrive il contenitore TAR e lo comprime in un unico passaggio di streaming, così non carichi mai l'intero archivio in memoria.

### Passo 1: Scegli il formato di archivio di cui hai bisogno
Decidi quale formato basato su tar corrisponde meglio al tuo compromesso compressione‑velocità:

- **TarBz2** – Rapporto di compressione più alto (≈30 % più piccolo di TarGz) ma più lento.  
- **TarGz** – Buon equilibrio tra velocità e dimensione; ideale per la maggior parte degli scenari di cloud‑storage.  
- **TarLz / TarXz** – Compressione molto alta con velocità moderata, utile per l'archiviazione.  
- **TarZ** – Formato legacy per compatibilità con strumenti Unix più vecchi.

### Passo 2: Crea una nuova istanza `Archive`
`Archive` rappresenta un singolo file di archivio e fornisce metodi per aggiungere voci e salvare l'archivio.

La classe `Archive` gestisce il flusso di lavoro di impacchettamento e compressione, esponendo metodi per aggiungere voci e scrivere il file finale.

### Passo 3: Aggiungi file e cartelle
Puoi aggiungere un intero albero di directory con `AddAll` o aggiungere file individuali con `AddFile`.

`AddAll` aggiunge un intero albero di directory all'archivio, preservandone la struttura.  
`AddFile` aggiunge un singolo file all'archivio. Preservare la gerarchia originale delle cartelle è semplice come passare il percorso della directory di base.

### Passo 4: Imposta il tipo di compressione desiderato
L'enumerazione `CompressionType` specifica l'algoritmo di compressione applicato al flusso TAR.

`CompressionType` elenca gli algoritmi supportati (BZip2, GZip, LZMA, XZ, ecc.) che verranno applicati durante il salvataggio.

### Passo 5: Salva l'archivio
L'enumerazione `ArchiveFormat` seleziona la combinazione di contenitore e compressione per il file di output.

Chiamare `Save` scrive l'archivio su disco usando il formato selezionato.

### Passo 6: Estrarre archivi con password
`ArchiveEntry` rappresenta una singola voce di file o directory all'interno di un archivio.

Per estrarre un zip protetto da password, apri l'archivio, individua ogni `ArchiveEntry`, assegna la sua proprietà `Password` e chiama `Extract`. La proprietà `Password` imposta la password di decrittazione per una voce zip. Questo modello di password per voce ti consente di proteggere file individuali all'interno di un unico zip.

### Passo 7: Verifica il risultato
Dopo l'estrazione, confronta le dimensioni dei file e i checksum SHA‑256 per confermare che il ciclo dell'archivio abbia preservato l'integrità dei dati.

## Casi d'uso comuni
- **Utility di backup** – Archivia i backup giornalieri come `.tar.bz2` per ridurre i costi di archiviazione fino al 30 %.  
- **Scambio dati cross‑platform** – I formati basati su tar sono nativamente compresi da strumenti Linux, macOS e Windows.  
- **Distribuzione sicura** – Assegna password alle voci sensibili, soddisfacendo i requisiti di conformità senza strumenti di crittografia aggiuntivi.

## Risoluzione dei problemi e consigli
- **Archivi di grandi dimensioni** – Usa l'API di streaming (`Archive.CreateEntryFromFile`) per mantenere basso l'uso della memoria.  
- **Password non corrispondenti** – La password impostata su ogni `ArchiveEntry` deve corrispondere esattamente; altrimenti viene sollevata `InvalidPasswordException`.  
- **Livello di compressione** – BZIP2 non espone livelli personalizzati; se hai bisogno di un controllo più fine, passa a LZMA (`CompressionType.LZMA`) o XZ (`CompressionType.XZ`).  

## Domande frequenti

**Q: Come creo un archivio TarGz?**  
A: Imposta `CompressionType.GZip` e usa `ArchiveFormat.TarGz` quando chiami `Save`. Questo produce un file `.tar.gz` in un unico passaggio.

**Q: Posso estrarre un archivio protetto da password senza conoscere la password?**  
A: No. Ogni voce deve essere fornita con la password corretta; altrimenti l'estrazione fallisce con `InvalidPasswordException`.

**Q: Aspose.Zip supporta l'estrazione di archivi con password diverse per voce?**  
A: Sì. Assegna una password a ciascun `ArchiveEntry` individualmente prima di chiamare `Extract`.

**Q: Quale formato offre la migliore compressione?**  
A: TarBz2 di solito produce la dimensione più piccola, seguita da TarLz e TarXz. TarGz offre un'alternativa più veloce, comunque efficace.

**Q: Esiste un limite al numero di file che posso aggiungere a un archivio TAR?**  
A: Praticamente nessuno, ma archivi estremamente grandi (>10 GB) possono trarre beneficio dallo splitting in più parti per una gestione più semplice.

## Tutorial di estrazione archivi e formati
### [Compressione file in TarBz2 con Aspose.Zip per .NET](./compress-to-tar-bz2/)
Scopri come comprimere file nel formato TarBz2 in .NET usando Aspose.Zip. Segui la nostra guida passo‑passo per una compressione efficiente dei file.  
### [Compressione in TarGz con Aspose.Zip per .NET](./compress-to-tar-gz/)
Esplora la compressione efficiente di file in .NET con Aspose.Zip. Comprimi in TarGz senza sforzo.  
### [Compressione in TarLz con Aspose.Zip per .NET](./compress-to-tar-lz/)
Comprimi file in .NET con Aspose.Zip senza sforzo. Impara a creare archivi TarLz passo‑passo.  
### [Compressione in TarXz con Aspose.Zip per .NET](./compress-to-tar-xz/)
Scopri come comprimere file nel formato TarXz in .NET usando Aspose.Zip. Segui la nostra guida per un'efficiente archiviazione e trasmissione.  
### [Compressione in TarZ con Aspose.Zip per .NET](./compress-to-tar-z/)
Esplora la compressione passo‑passo in TarZ usando Aspose.Zip per .NET. Gestione efficiente dei file per i tuoi progetti .NET.  
### [Estrazione di voci di archivio con password diverse in Aspose.Zip per .NET](./extract-archive-different-passwords/)
Scopri come estrarre voci di archivio con password diverse in Aspose.Zip per .NET. Aumenta sicurezza e flessibilità nelle tue applicazioni.

## Tutorial correlati

- [Crea archivio tar e aggiungi file a tar con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Come comprimere tar e creare TarBz2 con Aspose.Zip per .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aggiungi file a tar e crea archivio tarxz con Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Ultimo aggiornamento:** 2026-10-25  
**Testato con:** Aspose.Zip for .NET 24.11  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}