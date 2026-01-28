---
date: 2026-01-28
description: Scopri come estrarre archivi con password, comprimere file in TarBz2,
  creare archivi TarGz usando Aspose.Zip per .NET. Aumenta l'efficienza di archiviazione
  e la sicurezza.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Estrai archivio con password e comprimi in TarBz2 (.NET)
url: /it/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai archivio con password e comprimi in TarBz2 (.NET)

In questa guida scoprirai **come estrarre un archivio con password** e imparerai anche a **comprimere file in TarBz2** usando Aspose.Zip per .NET. Che tu stia costruendo un servizio di backup, un client di cloud‑storage o una pipeline di elaborazione dati, queste tecniche ti permettono di ridurre l’ingombro di archiviazione, velocizzare i trasferimenti e mantenere i dati sensibili protetti.

## Risposte rapide
- **Cos'è TarBz2?** Un archivio compresso che combina l'impacchettamento TAR con la compressione BZIP2 per rapporti di compressione elevati.  
- **Perché scegliere Aspose.Zip per .NET?** Fornisce un'unica API fluida per molti formati di archivio senza dipendenze native.  
- **Posso creare un archivio TarGz?** Sì – Aspose.Zip supporta TarGz, TarLz, TarXz, TarZ e altri.  
- **Come estrarre un archivio protetto da password?** Imposta la proprietà `Password` su ogni `ArchiveEntry` prima dell'estrazione.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale per la produzione; è disponibile una prova gratuita per la valutazione.

## Come estrarre un archivio con password usando Aspose.Zip per .NET
Estrarre un archivio **protetto da password** è semplice. Apri l'archivio, individua la voce di cui hai bisogno, assegna la sua password e poi chiama `Extract`. Questo approccio funziona per TarBz2, TarGz e altri formati supportati.

## Cosa significa realmente “comprimere file in TarBz2”?
Comprimere file in TarBz2 significa prima raggruppare più file e directory in un unico contenitore **TAR** e poi applicare la compressione **BZIP2**. Il risultato è un file `.tar.bz2` sia facile da trasportare che altamente compresso.

## Perché usare Aspose.Zip per .NET per gestire questi formati?
- **API unificata** – Una libreria, molti formati (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Nessuna dipendenza nativa** – Funziona su Windows, Linux e macOS senza configurazioni aggiuntive.  
- **Supporto password** – Proteggi e estrai archivi in modo sicuro con password per voce.  
- **Orientato alle prestazioni** – L'elaborazione basata su stream riduce al minimo l'uso di memoria.

## Prerequisiti
- .NET 6.0 o successivo (o .NET Core 3.1+ / .NET Framework 4.5+).  
- Pacchetto NuGet Aspose.Zip per .NET installato (`Install-Package Aspose.Zip`).  
- Conoscenza di base di C# e I/O file.

## Guida passo‑passo

### Passo 1: Scegli il formato di archivio di cui hai bisogno
Decidi se **TarBz2**, **TarGz**, **TarLz**, **TarXz** o **TarZ** è più adatto al tuo rapporto di compressione e ai requisiti di compatibilità.  
- **TarBz2** – Migliore compressione, elaborazione più lenta.  
- **TarGz** – Buon equilibrio tra velocità e dimensione (copre la keyword secondaria *compress files to targz*).  
- **TarZ** – Formato legacy per vecchi strumenti Unix.

### Passo 2: Crea una nuova istanza `Archive`
Istanzia la classe `Archive` e puntala al percorso del file di output. Questo oggetto gestirà il processo di impacchettamento e compressione.

### Passo 3: Aggiungi file e cartelle
Usa i metodi `AddAll` o `AddFile` per includere i file da comprimere. Conserva la struttura delle directory aggiungendo una cartella base.

### Passo 4: Imposta il tipo di compressione desiderato
Specifica l'algoritmo di compressione (`CompressionType.BZip2`, `CompressionType.GZip`, ecc.) al salvataggio dell'archivio. Qui è dove effettivamente **comprimere file in tarbz2** o in qualsiasi altro formato.

### Passo 5: Salva l'archivio
Chiama `Save` con l'enumerazione di formato appropriata (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, ecc.). La libreria scrive il contenitore TAR e applica la compressione scelta in un'unica passata.

### Passo 6: Estrai archivi con password
Se devi **estrarre voci di archivio con password diverse** (keyword secondario *how to extract password protected archive*), apri l'archivio, individua ogni voce, assegna la sua password e poi estrai.

### Passo 7: Verifica il risultato
Dopo l'estrazione, confronta le dimensioni dei file e i checksum per assicurarti che l'archivio sia stato creato e decompresso correttamente.

## Casi d'uso comuni
- **Utility di backup** – Archivia i backup giornalieri come `.tar.bz2` per ridurre i costi di archiviazione.  
- **Scambio dati cross‑platform** – I formati basati su Tar sono universalmente compresi su Linux, macOS e Windows.  
- **Distribuzione sicura** – Proteggi le singole voci con password per ambienti guidati da conformità.

## Risoluzione dei problemi e consigli
- **Archivi grandi** – Usa le API di streaming (`Archive.CreateEntryFromFile`) per evitare di caricare interi file in memoria.  
- **Password non corrispondenti** – Assicurati che la password impostata su ogni `ArchiveEntry` corrisponda a quella usata durante l'estrazione; altrimenti otterrai `InvalidPasswordException`.  
- **Livello di compressione non supportato** – BZIP2 non supporta livelli di compressione personalizzati; se ti serve un controllo più fine, considera TarLz o TarXz.  
- **Consiglio di prestazioni** – Quando crei un **create tarbz2 archive**, abilita il buffering sullo stream sottostante per migliorare la velocità di scrittura.

## Domande frequenti

**D: Come creo un archivio TarGz?**  
A: Imposta il tipo di compressione a `CompressionType.GZip` e il formato a `ArchiveFormat.TarGz` quando chiami `Save`.

**D: Posso estrarre un archivio protetto da password senza conoscerla?**  
A: No. Ogni voce deve essere fornita con la password corretta; altrimenti l'estrazione fallirà.

**D: Aspose.Zip supporta l'estrazione di archivi con password diverse per voce?**  
A: Sì. Puoi assegnare una password a ogni `ArchiveEntry` individualmente prima dell'estrazione.

**D: Quale formato offre la migliore compressione?**  
A: TarBz2 tipicamente fornisce il più alto rapporto di compressione, seguito da TarLz e TarXz. TarGz offre un buon equilibrio velocità‑dimensione.

**D: Esiste un limite al numero di file che posso aggiungere a un archivio TAR?**  
A: Praticamente no, ma archivi estremamente grandi possono trarre vantaggio dallo splitting in più parti per una gestione più semplice.

## Tutorial di estrazione archivi e formati
### [Compressione file in TarBz2 con Aspose.Zip per .NET](./compress-to-tar-bz2/)
Impara a comprimere file in formato TarBz2 in .NET usando Aspose.Zip. Segui la nostra guida passo‑passo per una compressione efficiente dei file.
### [Compressione in TarGz con Aspose.Zip per .NET](./compress-to-tar-gz/)
Scopri la compressione efficiente dei file in .NET con Aspose.Zip. Comprimi in TarGz senza sforzo.
### [Compressione in TarLz con Aspose.Zip per .NET](./compress-to-tar-lz/)
Comprimi file in .NET con Aspose.Zip. Impara a creare archivi TarLz passo‑passo.
### [Compressione in TarXz con Aspose.Zip per .NET](./compress-to-tar-xz/)
Scopri come comprimere file in formato TarXz in .NET usando Aspose.Zip. Segui la nostra guida passo‑passo per una memorizzazione e trasmissione efficienti dei file.
### [Compressione in TarZ con Aspose.Zip per .NET](./compress-to-tar-z/)
Esplora la compressione passo‑passo in TarZ usando Aspose.Zip per .NET. Gestione file efficiente per i tuoi progetti .NET.
### [Estrazione di voci di archivio con password diverse in Aspose.Zip per .NET](./extract-archive-different-passwords/)
Scopri come estrarre voci di archivio con password diverse in Aspose.Zip per .NET. Aumenta sicurezza e flessibilità nelle tue applicazioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-28  
**Testato con:** Aspose.Zip per .NET 24.11  
**Autore:** Aspose  

---