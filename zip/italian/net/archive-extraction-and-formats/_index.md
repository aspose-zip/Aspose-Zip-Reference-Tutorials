---
date: 2026-02-20
description: Impara a comprimere file tarbz2, a creare archivi targz e a estrarre
  archivi .NET con estrazione di zip protetta da password usando Aspose.Zip per .NET.
  Migliora l’efficienza di archiviazione e la sicurezza.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come comprimere file TarBz2 con Aspose.Zip per .NET
url: /it/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come comprimere file TarBz2 con Aspose.Zip per .NET

## Introduzione

In questa guida, imparerai **come comprimere file tarbz2** con Aspose.Zip per .NET scoprendo anche come creare archivi TarGz e eseguire l'estrazione di archivi .net di file zip protetti da password. La gestione efficiente dei file è una pietra miliare dello sviluppo .NET moderno, e padroneggiare questi formati ti permette di ridurre i costi di archiviazione, velocizzare il trasferimento dei dati e mantenere le informazioni sensibili al sicuro. Che tu stia costruendo un servizio di backup, un client di cloud‑storage o una pipeline di elaborazione dati, le tecniche trattate qui renderanno le tue attività di gestione dei file più fluide e affidabili.

## Risposte rapide
- **Cos'è TarBz2?** Un archivio compresso che combina l'impacchettamento TAR con la compressione BZIP2 per rapporti di compressione elevati.  
- **Perché scegliere Aspose.Zip per .NET?** Offre un'API unica e fluida per creare ed estrarre molti formati di archivio senza dipendenze esterne.  
- **Posso creare un archivio TarGz?** Sì – Aspose.Zip supporta TarGz, TarLz, TarXz, TarZ e altro.  
- **Come estraggo un archivio zip protetto da password?** Usa la proprietà `Password` sull'oggetto `ArchiveEntry` durante l'estrazione.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale per la produzione; è disponibile una prova gratuita per la valutazione.

## Come comprimere file TarBz2
Comprimere file in TarBz2 significa prima raggruppare più file e directory in un unico contenitore **TAR** e poi applicare la compressione **BZIP2**. Il risultato è un unico file `.tar.bz2` che è sia facile da trasportare sia altamente compresso.

## Perché usare Aspose.Zip per .NET per gestire questi formati?
- **Unified API** – Una libreria, molti formati (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Funziona su Windows, Linux e macOS senza ulteriori dipendenze.  
- **Password support** – Proteggi e estrai archivi in modo sicuro con password per voce.  
- **Performance‑focused** – L'elaborazione basata su stream riduce al minimo l'utilizzo di memoria.

## Prerequisiti
- .NET 6.0 o versioni successive (o .NET Core 3.1+ / .NET Framework 4.5+).  
- Pacchetto NuGet Aspose.Zip per .NET installato (`Install-Package Aspose.Zip`).  
- Conoscenza di base di C# e I/O di file.

## Guida passo‑passo

### Passo 1: Scegli il formato di archivio di cui hai bisogno
Decidi se **TarBz2**, **TarGz**, **TarLz**, **TarXz** o **TarZ** è il più adatto al tuo rapporto di compressione e ai requisiti di compatibilità.  
- **TarBz2** – Compressione migliore, elaborazione più lenta.  
- **TarGz** – Buon equilibrio tra velocità e dimensione (copia la keyword secondaria *how to create targz*).  
- **TarZ** – Formato legacy, utile per la compatibilità con strumenti Unix più vecchi.

### Passo 2: Crea una nuova istanza `Archive`
Istanzia la classe `Archive` e puntala al percorso del file di output. Questo oggetto gestirà il processo di impacchettamento e compressione.

### Passo 3: Aggiungi file e cartelle
Usa i metodi `AddAll` o `AddFile` per includere i file che desideri comprimere. Puoi preservare la struttura delle directory aggiungendo una cartella base.

### Passo 4: Imposta il tipo di compressione desiderato
Specifica l'algoritmo di compressione (`CompressionType.BZip2`, `CompressionType.GZip`, ecc.) al momento del salvataggio dell'archivio. È qui che effettui realmente **comprimere file in TarBz2** o qualsiasi altro formato.

### Passo 5: Salva l'archivio
Chiama `Save` con l'enumerazione di formato appropriata (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, ecc.). La libreria scrive il contenitore TAR e applica la compressione scelta in un'unica passata.

### Passo 6: Estrarre archivi con password
Se hai bisogno di **estrarre voci di archivio con password diverse** (keyword secondaria *password protected zip extraction*), apri l'archivio, individua ogni voce, assegna la sua password e poi estrai.

### Passo 7: Verifica il risultato
Dopo l'estrazione, confronta le dimensioni dei file e i checksum per assicurarti che l'archivio sia stato creato e decompresso correttamente.

## Casi d'uso comuni
- **Backup utilities** – Conserva i backup giornalieri come `.tar.bz2` per ridurre i costi di archiviazione.  
- **Cross‑platform data exchange** – I formati basati su Tar sono universalmente compresi su Linux, macOS e Windows.  
- **Secure distribution** – Proteggi le singole voci con password per ambienti guidati da conformità.

## Risoluzione dei problemi e consigli
- **Large archives** – Usa le API di streaming (`Archive.CreateEntryFromFile`) per evitare di caricare interi file in memoria.  
- **Password mismatches** – Assicurati che la password impostata su ogni `ArchiveEntry` corrisponda a quella usata durante l'estrazione; altrimenti otterrai `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 non supporta livelli di compressione personalizzati; se ti serve un controllo più fine, considera TarLz o TarXz.

## Domande frequenti

**Q: Come creo un archivio TarGz?**  
A: Imposta il tipo di compressione a `CompressionType.GZip` e il formato a `ArchiveFormat.TarGz` quando chiami `Save`.

**Q: Posso estrarre un archivio protetto da password senza conoscere la password?**  
A: No. Ogni voce deve essere fornita con la password corretta; altrimenti l'estrazione fallirà.

**Q: Aspose.Zip supporta l'estrazione di archivi con password diverse per voce?**  
A: Sì. Puoi assegnare una password a ciascun `ArchiveEntry` individualmente prima dell'estrazione.

**Q: Quale formato offre la migliore compressione?**  
A: TarBz2 fornisce tipicamente il più alto rapporto di compressione, seguito da TarLz e TarXz. TarGz offre un buon equilibrio velocità‑dimensione.

**Q: Esiste un limite al numero di file che posso aggiungere a un archivio TAR?**  
A: Praticamente no, ma archivi estremamente grandi possono trarre vantaggio dallo splitting in più parti per una gestione più semplice.

## Tutorial di estrazione di archivi e formati
### [Compressione di file in TarBz2 con Aspose.Zip per .NET](./compress-to-tar-bz2/)
### [Compressione in TarGz con Aspose.Zip per .NET](./compress-to-tar-gz/)
### [Compressione in TarLz con Aspose.Zip per .NET](./compress-to-tar-lz/)
### [Compressione in TarXz con Aspose.Zip per .NET](./compress-to-tar-xz/)
### [Compressione in TarZ con Aspose.Zip per .NET](./compress-to-tar-z/)
### [Estrazione di voci di archivio con password diverse in Aspose.Zip per .NET](./extract-archive-different-passwords/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-02-20  
**Testato con:** Aspose.Zip per .NET 24.11  
**Autore:** Aspose