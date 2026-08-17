---
date: 2026-06-09
description: Scopri come aggiungere una password allo zip e creare archivi zip LZMA
  utilizzando Aspose.Zip per .NET. Questo tutorial copre Bzip2, LZMA (dimensione del
  dizionario), PPMd, Enhanced Deflate, Store compression e la compressione di file
  di grandi dimensioni in ASP.NET.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Ottimizzare le impostazioni di compressione
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aggiungere una password allo zip e creare un archivio LZMA con Aspose.Zip per
  .NET
url: /it/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una password a zip e creare un archivio LZMA con Aspose.Zip per .NET

Nelle moderne applicazioni .NET, **add password to zip** durante la creazione di un archivio zip LZMA ad alto rapporto di compressione può proteggere i dati sensibili e offrire comunque la migliore compressione possibile. Che tu stia costruendo un servizio di compressione file ASP.NET, un'utilità desktop che gestisce file multi‑gigabyte, o un flusso di lavoro basato su cloud, questo tutorial ti guida passo passo per proteggere e comprimere i tuoi file con Aspose.Zip per .NET.

## Risposte rapide
- **Qual è il beneficio principale della compressione LZMA?** Rapporto di compressione più alto con velocità ragionevole per la maggior parte dei tipi di file.  
- **Quale metodo memorizza i file senza compressione?** Store compression (chiamata anche “store compression zip”).  
- **Posso usare queste impostazioni in un'applicazione ASP.NET?** Sì—basta fare riferimento ad Aspose.Zip nel tuo progetto e chiamare la stessa API.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza commerciale per la produzione; è disponibile una versione di prova gratuita.  
- **Quali versioni .NET sono supportate?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.

## Cos'è “add password to zip” in Aspose.Zip?
**Aggiungere una password a zip cripta ogni voce all'interno di un archivio ZIP in modo che solo gli utenti che conoscono la password possano estrarre i file.** Aspose.Zip supporta sia la crittografia tradizionale ZipCrypto sia la crittografia AES (128, 192 o 256‑bit). Le impostazioni di crittografia vengono fornite come secondo argomento a `ArchiveEntrySettings` durante la costruzione di un `Archive`; non esiste un metodo separato `SetPassword`.

## Perché usare Aspose.Zip per la compressione di file .NET?
Aspose.Zip fornisce un'API unica e coerente che copre molti algoritmi offrendo alte prestazioni e basso utilizzo di memoria. Consente agli sviluppatori di scegliere il metodo di compressione migliore per ogni scenario e di applicare la crittografia in un unico passaggio, semplificando il codice e riducendo l'onere di manutenzione.

- **Unified API** – Un'interfaccia coerente per Bzip2, LZMA, PPMd, Enhanced Deflate e Store.  
- **Performance‑tuned** – L'implementazione nativa ottimizzata elabora **fino a file da 10 GB** senza caricare l'intero file in memoria.  
- **ASP.NET friendly** – Funziona senza problemi nei progetti web, nei servizi in background e nelle Azure Functions.  
- **Fine‑grained control** – Regola la dimensione del dizionario, il livello di compressione e la crittografia con una singola chiamata al costruttore.  
- **Supports 10+ compression algorithms** – copre i casi d'uso più comuni nei flussi di dati aziendali.

## Prerequisiti
- **Aspose.Zip for .NET Library** – Scarica e installa dalla [documentazione Aspose](https://reference.aspose.com/zip/net/).  
- **Sample Text File** – Prepara un file di esempio (ad es., `sample.txt`) che comprimerai.  
- **.NET development environment** – Visual Studio 2022 o qualsiasi IDE compatibile.  

## Importare gli spazi dei nomi

Le classi `Archive`, `ArchiveEntrySettings` e le classi di crittografia risiedono nello spazio dei nomi `Aspose.Zip`. Importale all'inizio del tuo file:

- `Archive` rappresenta un contenitore di archivio ZIP.  
- `ArchiveEntrySettings` contiene le opzioni di compressione e crittografia per ogni voce.  
- Le classi di crittografia (ad es., `AesEncryptionSettings`) definiscono come i dati vengono criptati.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora esploriamo ogni impostazione di compressione e vediamo come **add password to zip** dove opportuno.

## Utilizzare le impostazioni di compressione Bzip2

### Passo 1: Inizializzare la compressione Bzip2 con crittografia tradizionale

`Bzip2CompressionSettings` configura l'algoritmo Bzip2 (dimensione del blocco, ecc.).  
`TraditionalEncryptionSettings` applica la crittografia legacy ZipCrypto a una voce.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*La protezione con password viene applicata tramite `TraditionalEncryptionSettings` passato direttamente a `ArchiveEntrySettings`.*

## Come aggiungere una password a zip usando Aspose.Zip per .NET

Carica il tuo file di origine, crea un `Archive` con le impostazioni della voce e aggiungi il file all'archivio. La crittografia viene applicata automaticamente perché è stata fornita al momento della creazione dell'istanza `ArchiveEntrySettings`.

**Risposta diretta (40‑70 parole):**  
Crea un oggetto `ArchiveEntrySettings` che includa sia le impostazioni di compressione desiderate sia `TraditionalEncryptionSettings` o `AesEncryptionSettings`. Quindi passa questo oggetto al costruttore `Archive` e aggiungi i file con `AddEntry`. L'archivio viene scritto con la password già incorporata, quindi non è necessario alcun passaggio aggiuntivo dopo la creazione.

`ArchiveEntrySettings` è il contenitore di configurazione che indica ad Aspose.Zip come ogni voce deve essere compressa e criptata.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Come creare un archivio zip LZMA usando Aspose.Zip

### Passo 1: Inizializzare la compressione LZMA con crittografia AES256

`LzmaCompressionSettings` controlla i parametri specifici di LZMA come la dimensione del dizionario e i fast bytes.  
`AesEncryptionSettings` fornisce crittografia AES‑256 per le voci dell'archivio.

**Risposta diretta (40‑70 parole):**  
Istanzia `LzmaCompressionSettings` con un `DictionarySize` scelto, crea un oggetto `AesEncryptionSettings` con la tua password e `EncryptionMethod.AES256`, quindi costruisci un `ArchiveEntrySettings` da entrambi. Passa questo al costruttore `Archive` e aggiungi i tuoi file; lo zip risultante sarà compresso LZMA e protetto da AES in un'unica operazione.

`LzmaCompressionSettings` è la classe che controlla i parametri specifici di LZMA come la dimensione del dizionario e i fast bytes.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Suggerimento:** LZMA offre una **dimensione del dizionario LZMA** configurabile che influisce sia sul rapporto di compressione sia sull'uso della memoria. Puoi impostarla tramite `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` se devi ottimizzare per file molto grandi.

## Utilizzare le impostazioni di compressione PPMd

### Passo 1: Inizializzare la compressione PPMd con crittografia AES256

`PpmdCompressionSettings` definisce l'ordine e l'uso della memoria per l'algoritmo PPMd.  
`AesEncryptionSettings` fornisce crittografia AES‑256 per le voci dell'archivio.

**Risposta diretta (40‑70 parole):**  
Crea un'istanza `PpmdCompressionSettings`, combinala con un oggetto `AesEncryptionSettings` contenente la tua password e inseriscili entrambi in un `ArchiveEntrySettings`. Usa questo oggetto di impostazioni quando costruisci l'`Archive`; lo zip risultante sarà compresso PPMd e protetto da password senza chiamate aggiuntive.

`PpmdCompressionSettings` definisce l'ordine e l'uso della memoria per l'algoritmo PPMd.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Utilizzare le impostazioni di compressione Enhanced Deflate

### Passo 1: Inizializzare la compressione Enhanced Deflate con crittografia AES256

`EnhancedDeflateCompressionSettings` ti consente di specificare un livello di compressione che bilancia velocità e dimensione.  
`AesEncryptionSettings` fornisce crittografia AES‑256 per le voci dell'archivio.

**Risposta diretta (40‑70 parole):**  
Istanzia `EnhancedDeflateCompressionSettings` con il livello desiderato (0‑9), accoppialo con `AesEncryptionSettings` e avvolgili in `ArchiveEntrySettings`. Passa questo al costruttore `Archive` e aggiungi i file; l'archivio verrà creato con compressione Enhanced Deflate e protezione password AES‑256 in un unico passaggio.

`EnhancedDeflateCompressionSettings` ti consente di specificare un livello di compressione che bilancia velocità e dimensione.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Utilizzare le impostazioni di compressione Store (store compression zip)

### Passo 1: Inizializzare la compressione Store con crittografia tradizionale

`StoreCompressionSettings` indica ad Aspose.Zip di saltare completamente la compressione, preservando il file sorgente byte‑per‑byte.  
`TraditionalEncryptionSettings` applica la crittografia legacy ZipCrypto.

**Risposta diretta (40‑70 parole):**  
Crea un'istanza `StoreCompressionSettings` (che non esegue compressione), combinala con `TraditionalEncryptionSettings` contenente la tua password e avvolgi entrambi in `ArchiveEntrySettings`. Passa questo al costruttore `Archive`; lo zip risultante conterrà il file originale non compresso ma protetto da password.

`StoreCompressionSettings` indica ad Aspose.Zip di saltare completamente la compressione, preservando il file sorgente byte‑per‑byte.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Consiglio professionale:** Regola la variabile `dataDir` per puntare alla tua directory di lavoro effettiva e riutilizza la stessa istanza `Archive` se devi aggiungere più file a un unico archivio.

## Problemi comuni e soluzioni
- **Errori “File not found”** – Verifica che `dataDir` termini con un separatore di percorso (`\` o `/`) e che `sample.txt` esista.  
- **Consumo di memoria con file di grandi dimensioni** – Usa `ArchiveEntrySettings` per abilitare la modalità streaming, che scrive i dati direttamente sullo stream di output.  
- **Livello di compressione incompatibile** – Alcuni algoritmi (ad es., LZMA) espongono proprietà aggiuntive come `DictionarySize`. Consulta la documentazione API se hai bisogno di un controllo più fine.  
- **Password non applicata** – Assicurati che l'oggetto delle impostazioni di crittografia sia passato come secondo argomento a `ArchiveEntrySettings` al momento della costruzione, non dopo la creazione dell'archivio.  

## Domande frequenti

**D: Posso usare Aspose.Zip per .NET con altre librerie di compressione?**  
R: Aspose.Zip è progettato per funzionare con i suoi algoritmi integrati. Integrare librerie di terze parti è possibile ma richiede una gestione personalizzata al di fuori dell'API Aspose.

**D: Come posso aggiungere la protezione con password a uno zip creato con Aspose.Zip?**  
R: Passa `TraditionalEncryptionSettings` o `AesEncryptionSettings` come secondo argomento a `ArchiveEntrySettings` quando costruisci l'`Archive`. Vedi la [documentazione](https://docs.aspose.com/zip/net/password-protecting-archives/) per esempi completi.

**D: Esiste una versione di prova che posso testare?**  
R: Sì, puoi accedere alla versione di prova [qui](https://releases.aspose.com/).

**D: Dove posso ottenere aiuto dalla community o fare domande?**  
R: Per supporto e discussioni della community, visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**D: Posso ottenere una licenza temporanea per la valutazione?**  
R: Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Come aiuta questo nella compressione di file ASP.NET?**  
R: Chiamando la stessa API da un controller o middleware ASP.NET, puoi comprimere i file al volo prima di inviarli al client, riducendo la larghezza di banda e migliorando le prestazioni percepite.

**D: Qual è il modo migliore per comprimere file di grandi dimensioni in modo efficiente?**  
R: Combina la modalità streaming con la compressione LZMA e un `DictionarySize` appropriato. Questo bilancia l'uso della memoria e il rapporto di compressione per dataset massivi.

---

**Ultimo aggiornamento:** 2026-06-09  
**Testato con:** Aspose.Zip 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aspose.Zip per .NET - Proteggere con password l'archivio Zip e memorizzare più file senza compressione](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Creare zip protetto da password per directory .NET – Tutorial Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [zip più file c# – Compressione senza sforzo con Aspose.Zip per .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}