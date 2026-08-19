---
date: 2026-07-18
description: Scopri come aggiungere una cartella a ZIP e aggiungere file a ZIP usando
  Aspose.Zip per .NET. Questa guida passo‑passo mostra come comprimere i file con
  FileInfo nei progetti ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Comprimi file usando FileInfo
og_description: Aggiungi una cartella a ZIP usando Aspose.Zip per .NET. Scopri come
  creare un archivio ZIP, aggiungere file a ZIP e comprimere le cartelle in modo efficiente
  in ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Aggiungi cartella a ZIP – Comprimi file con Aspose.Zip per .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Aggiungi cartella a ZIP usando Aspose.Zip per .NET – Comprimi file con FileInfo
url: /it/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una cartella a Zip usando Aspose.Zip per .NET

## Introduzione

Se devi **aggiungere una cartella a zip** in modo programmatico, Aspose.Zip per .NET offre un'API pulita e ad alte prestazioni che funziona in qualsiasi applicazione .NET (inclusi ASP.NET). In questo tutorial vedremo come comprimere file con la classe `FileInfo`, ti mostreremo come **aggiungere file a zip** e spiegheremo perché questo approccio è ideale per i progetti .NET moderni. Copriremo anche i passaggi esatti per **aggiungere una cartella a zip** così potrai raggruppare intere directory in un'unica operazione. Iniziamo!

## Risposte rapide
- **Qual è il modo più semplice per creare un archivio zip?** Usa la classe `Archive` di Aspose.Zip insieme agli oggetti `FileInfo`.  
- **Posso aggiungere più file contemporaneamente?** Sì – basta creare un `FileInfo` per ogni file e chiamare `CreateEntry`.  
- **È necessaria una licenza speciale per ASP.NET?** È richiesta una licenza commerciale di Aspose.Zip per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Quali versioni .NET sono supportate?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.  
- **L'API è thread‑safe?** Sì, purché ogni thread lavori con la propria istanza di `Archive`.

## Cos'è un archivio Zip e perché crearne uno?
Un archivio zip raggruppa uno o più file in un unico contenitore compresso. Questo riduce lo spazio di archiviazione, velocizza i trasferimenti di rete e semplifica la distribuzione. Che tu stia consegnando log, esportando report o impacchettando risorse per un cliente, sapere **come creare file di archivio zip** programmaticamente è una competenza preziosa per qualsiasi sviluppatore .NET.

## Perché usare Aspose.Zip per aggiungere file a Zip?
Aspose.Zip fornisce una soluzione puramente .NET che elimina dipendenze esterne offrendo agli sviluppatori un controllo granulare su compressione, codifica e sicurezza. Supporta file di grandi dimensioni, protezione con password e funziona in modo coerente su tutte le versioni .NET supportate, rendendolo una scelta affidabile sia per applicazioni legacy sia per quelle moderne.  

- **Zero dipendenze esterne** – implementazione pura .NET.  
- **Controllo completo sul livello di compressione e sulla codifica** (ASCII, UTF‑8, ecc.).  
- **Supporta file più grandi di 4 GB** e protezione con password.  
- **API coerente su oltre 50 versioni .NET** – da .NET Framework 2.0 fino a .NET 10.  

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.Zip for .NET** installato. Scarica il pacchetto più recente dalla [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Una cartella sul tuo computer contenente i file che desideri comprimere (ad esempio `alice29.txt` e `fields.c`).  

## Importare gli spazi dei nomi

In qualsiasi file C# in cui lavorerai con archivi zip, aggiungi le seguenti istruzioni `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Questi spazi dei nomi ti danno accesso alla classe `Archive`, alle opzioni di salvataggio e alle utility I/O standard.

## Guida passo‑passo

### Passo 1: Configurare la directory del documento

Per prima cosa, definisci la cartella che contiene i file sorgente. Sostituisci il segnaposto con il percorso assoluto o relativo sul tuo sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Suggerimento:** Usa `Path.Combine` per costruire i percorsi in modo cross‑platform.

### Passo 2: Aprire un file Zip per la scrittura

Crea un `FileStream` che punti al file zip di output. Lo stream è aperto in modalità **Create**, che sovrascrive eventuali file esistenti con lo stesso nome:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Passo 3: Preparare gli oggetti `FileInfo` per ogni file sorgente

`FileInfo` fornisce ad Aspose.Zip l'accesso diretto ai file fisici su disco. Crea un'istanza per ogni file che desideri comprimere:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Perché usare `FileInfo`?** Evita di caricare l'intero file in memoria, il che è particolarmente utile per file di grandi dimensioni.

### Passo 4: Creare l'archivio e aggiungere le voci

La classe `Archive` è l'oggetto centrale di Aspose.Zip che rappresenta un contenitore zip in memoria. Istanzia un oggetto `Archive`, quindi chiama `CreateEntry` per ciascun `FileInfo`. Il primo argomento è il nome che il file avrà all'interno dello zip, il secondo argomento è il `FileInfo` sorgente:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Il metodo `CreateEntry` aggiunge una nuova voce file all'archivio, collegando il nome della voce al `FileInfo` sorgente in modo che i dati vengano trasmessi direttamente dal disco al momento del salvataggio dell'archivio.

### Passo 5: Salvare l'archivio Zip con la codifica desiderata

Infine, persisti l'archivio nello `FileStream` aperto in precedenza. Qui usiamo la codifica ASCII per i nomi delle voci, ma puoi passare a UTF‑8 se i tuoi nomi file contengono caratteri non ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando i blocchi `using` terminano, gli stream vengono chiusi automaticamente e il file zip è pronto per l'uso.

## Come aggiungere una cartella a Zip usando Aspose.Zip?

Carica la directory di destinazione, elenca tutti i file e aggiungi ciascuno con un percorso relativo che includa il nome della cartella. Questo approccio ti consente di **aggiungere una cartella a zip** senza elencare manualmente ogni file. Mantenendo la gerarchia delle cartelle nei nomi delle voci, l'archivio risultante può essere estratto con la struttura di directory originale intatta, cosa essenziale in molti scenari di distribuzione.

1. Usa `DirectoryInfo` per puntare alla cartella che desideri comprimere.  
2. Chiama `GetFiles("*", SearchOption.AllDirectories)` per recuperare tutti i file in modo ricorsivo.  
3. Per ogni file, crea un `FileInfo` e chiama `CreateEntry` con un percorso tipo `"MyFolder/Report.pdf"`.  

Poiché l'API lavora con `FileInfo`, ogni file viene trasmesso direttamente dal disco, mantenendo basso l'uso di memoria anche per cartelle contenenti centinaia di megabyte.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **File zip vuoto** | `FileInfo` punta a un percorso inesistente | Verifica `dataDir` e i nomi dei file; usa `File.Exists` per controllare prima di creare le voci. |
| **Codifica del nome file errata** | Uso della codifica predefinita con nomi non ASCII | Imposta `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException su file grandi** | Caricamento dell'intero file in memoria | `FileInfo` trasmette il file; assicurati di non leggere il file in un array di byte altrove. |
| **Permesso negato** | L'applicazione non ha i permessi di scrittura per la cartella di output | Esegui l'app con i diritti appropriati o scegli una directory scrivibile. |

## Domande frequenti

**D: Posso aggiungere un'intera cartella a un archivio zip con una singola chiamata?**  
R: Non esiste un metodo a chiamata singola, ma enumerare i file con `DirectoryInfo` e aggiungerli uno per uno tramite `CreateEntry` ottiene lo stesso risultato in modo efficiente.

**D: Aspose.Zip supporta la protezione con password?**  
R: Sì, puoi impostare una password sull'oggetto `Archive` prima del salvataggio per crittografare l'intero archivio.

**D: Quanto grande può essere un file zip gestito da Aspose.Zip?**  
R: La libreria elabora file più grandi di 4 GB e può creare archivi superiori a 10 GB senza caricare l'intero archivio in memoria.

**D: L'API è compatibile con .NET 6 e .NET 8?**  
R: Assolutamente. Aspose.Zip supporta .NET 5 fino a .NET 10, coprendo tutte le versioni LTS attuali.

**D: Quali livelli di compressione sono disponibili?**  
R: Puoi scegliere `CompressionLevel.NoCompression`, `Fast`, `Normal` o `Maximum` per bilanciare velocità e dimensione.

## Ulteriori risorse

- Scarica il pacchetto più recente di Aspose.Zip: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Acquista una licenza per l'uso in produzione: [purchase page](https://purchase.aspose.com/buy)  
- Ottieni supporto dalla community: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Prova Aspose.Zip gratuitamente: [free trial here](https://releases.aspose.com/)  
- Ottieni una licenza temporanea per la valutazione: [this link](https://purchase.aspose.com/temporary-license/)

## Conclusione

Ora sai **come aggiungere una cartella a zip** e **come creare file di archivio zip** usando Aspose.Zip per .NET, come **aggiungere file a zip**, e perché questo metodo è ideale per ASP.NET e altre applicazioni .NET. Sperimenta con diversi livelli di compressione, codifiche e opzioni di crittografia per adattare l'archivio alle tue esigenze specifiche. Buona compressione!

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Effortless Compression with Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Archive .NET – File Compression with Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}