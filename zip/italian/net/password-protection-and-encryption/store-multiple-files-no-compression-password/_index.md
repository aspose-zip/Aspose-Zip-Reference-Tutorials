---
title: Aspose.Zip per .NET - Tutorial sull'archiviazione sicura dei file
linktitle: Archivia più file senza compressione con password
second_title: Aspose.Zip .NET API per la compressione e l'archiviazione dei file
description: Scopri come utilizzare Aspose.Zip per .NET per archiviare in modo sicuro più file senza compressione. Semplici passaggi per la protezione tramite password. Sblocca la potenza della gestione dei file!
type: docs
weight: 13
url: /it/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

Nel mondo dello sviluppo .NET, la gestione e la manipolazione dei file è un compito comune. Aspose.Zip per .NET è una potente libreria che fornisce agli sviluppatori la capacità di comprimere, decomprimere e manipolare gli archivi zip senza problemi. In questo tutorial approfondiremo uno scenario specifico: archiviare più file senza compressione e proteggerli con una password. Alla fine di questa guida avrai le conoscenze necessarie per implementare questa funzionalità utilizzando Aspose.Zip per .NET.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

-  Libreria Aspose.Zip per .NET: assicurati di avere la libreria Aspose.Zip per .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/zip/net/).

-  Directory dei documenti: prepara una directory in cui si trovano i file di origine. Nell'esempio fornito, la variabile`dataDir` rappresenta la directory dei documenti.

## Importa spazi dei nomi

Per iniziare, importiamo gli spazi dei nomi necessari per il nostro codice:

```csharp
// Il percorso della directory delle risorse.
string dataDir = "Your Document Directory"

// Importa spazi dei nomi Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Passaggio 1: apri il file zip

```csharp
//ExStart: memorizza più file senza compressione con password
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Questo passaggio prevede la creazione di un nuovo file zip utilizzando`FileStream`. Il file verrà denominato "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip".

## Passaggio 2: aprire il file sorgente

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Qui apriamo il primo file sorgente, "alice29.txt", che verrà archiviato nell'archivio zip.

## Passaggio 3: crea un archivio

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 In questo passaggio creiamo un'istanza del file`Archive` classe, specificando le impostazioni di compressione e crittografia. Noi usiamo il`StoreCompressionSettings` per archiviare file senza compressione e`AesEcryptionSettings` applicare la crittografia AES con una password ("p@s$").

## Passaggio 4: crea una voce di archivio e salva

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Questo passaggio finale prevede la creazione di una voce nell'archivio per "alice29.txt" e il salvataggio dell'archivio, completando il processo di archiviazione di un file senza compressione e con protezione tramite password.

Concludi il tuo tutorial riassumendo i punti chiave e incoraggiando i lettori a esplorare ulteriori possibilità con Aspose.Zip per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare Aspose.Zip per .NET per archiviare più file senza compressione e proteggerli con una password. Mentre continui il tuo viaggio con lo sviluppo .NET, sfrutta le funzionalità di Aspose.Zip per semplificare le attività di gestione dei file e migliorare la sicurezza delle tue applicazioni.

---

### Domande frequenti

### Posso utilizzare Aspose.Zip per .NET con altri metodi di crittografia?
 Sì, Aspose.Zip supporta vari metodi di crittografia. Controlla la documentazione[Qui](https://reference.aspose.com/zip/net/) per dettagli.

### Dove posso ottenere supporto per Aspose.Zip per .NET?
 Visitare il[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per il supporto e le discussioni della comunità.

### È disponibile una prova gratuita per Aspose.Zip per .NET?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Zip per .NET?
 Richiedi una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare Aspose.Zip per .NET?
 È possibile acquistare Aspose.Zip per .NET[Qui](https://purchase.aspose.com/buy).
