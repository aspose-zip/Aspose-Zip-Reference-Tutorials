---
date: 2026-02-28
description: Impara a comprimere file con password e a crittografare archivi ZIP usando
  Aspose.Zip per .NET, trattando la protezione con password per 7z e la password per
  file ZIP in C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come comprimere file con password e crittografare le voci ZIP con password
  diverse usando Aspose.Zip per .NET
url: /it/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come comprimere file con password e crittografare le voci ZIP con password diverse usando Aspose.Zip per .NET

## Introduzione

Se hai bisogno di **comprimere file con password** e assegnare a ciascuna voce una password propria, sei nel posto giusto. In questo tutorial vedremo passo per passo come creare un archivio 7‑zip in cui ogni file è protetto da una password unica, utilizzando la libreria Aspose.Zip per .NET. Alla fine comprenderai perché la crittografia per voce è importante, come configurarla e come verificare il risultato nei tuoi progetti.

## Risposte rapide
- **Cosa significa “encrypt zip”?** Indica l’applicazione di protezione basata su password (AES o ZipCrypto) ai contenuti di un archivio ZIP/7z.  
- **Ogni voce può avere una password diversa?** Sì—Aspose.Zip consente di assegnare password distinte per file.  
- **Quali versioni di .NET sono supportate?** Tutte le versioni moderne di .NET Framework, .NET Core e .NET 5/6.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per l’uso in produzione; è disponibile una versione di prova gratuita.  
- **Quale formato di compressione viene usato nell’esempio?** Il campione crea un archivio 7z con crittografia AES‑256.

## Come comprimere file con password usando Aspose.Zip per .NET
In questa sezione rispondiamo direttamente alla domanda principale e prepariamo il terreno per la guida passo‑passo che segue.

## Che cosa è “how to encrypt zip” con Aspose.Zip?
Crittografare un file ZIP (o 7z) significa proteggere le sue voci in modo che non possano essere aperte senza la password corretta. Aspose.Zip per .NET supporta sia il classico ZipCrypto sia la crittografia AES più robusta, e permette di specificare le impostazioni di crittografia per voce, offrendo un controllo granulare sulla sicurezza.

## Perché usare password diverse per ogni voce?
- **Segmentazione della sicurezza:** Se una password viene compromessa, gli altri file rimangono protetti.  
- **Conformità normativa:** Alcuni settori richiedono credenziali separate per diverse categorie di dati.  
- **Accesso specifico per utente:** Puoi distribuire un unico archivio a più utenti, ognuno dei quali sblocca solo i file a cui è autorizzato.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Zip per .NET** installato – consulta la [documentazione ufficiale](https://reference.aspose.com/zip/net/) per le istruzioni di download e installazione.  
- Una cartella sul tuo computer dove conservare i file sorgente (la “Document Directory”).  
- Familiarità di base con C# e Visual Studio (o il tuo IDE .NET preferito).

## Importare gli spazi dei nomi

Iniziamo includendo gli spazi dei nomi che contengono le classi necessarie.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passo 1: Impostare la tua Document Directory

Definisci il percorso che contiene i file da archiviare.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Creare voci con password diverse

Ecco il cuore del tutorial. Apriamo un nuovo file 7z, creiamo tre oggetti `FileInfo` e aggiungiamo ciascuno come voce con la propria password AES.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Come funziona

- `SevenZipArchive` è il contenitore per un archivio 7‑z.  
- `CreateEntry` accetta il nome della voce, il file sorgente, un flag per sovrascrivere e un oggetto `SevenZipEntrySettings`.  
- All’interno di `SevenZipEntrySettings` forniamo due oggetti di impostazione: uno per la compressione (`SevenZipStoreCompressionSettings`) e uno per la crittografia (`SevenZipAESEncryptionSettings`).  
- Ogni chiamata fornisce una **password diversa** (`"test1"`, `"test2"`, `"test3"`), ottenendo la protezione per voce.

## Passo 3: Verifica

Dopo aver salvato l’archivio, puoi stampare un semplice messaggio di conferma.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Esegui il programma, quindi prova ad aprire `archive.7z` con uno strumento come 7‑Zip. Ti verrà chiesta una password per ogni voce, confermando che le password sono effettivamente distinte.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Errore di password errata** | La stringa della password contiene spazi superflui o caratteri invisibili. | Rimuovi gli spazi con `new SevenZipAESEncryptionSettings(password.Trim())`. |
| **Archivio non apre in strumenti più vecchi** | Alcuni strumenti ZIP legacy non supportano la crittografia AES‑256 usata da 7z. | Usa un estrattore moderno (7‑Zip 19.00+). |
| **File non aggiunto all'archivio** | Il percorso del file sorgente è errato o il file non esiste. | Verifica `dataDir` e i nomi dei file, oppure usa `Path.Combine(dataDir, "data1.bin")`. |

## Domande frequenti

### Q1: Aspose.Zip per .NET è compatibile con tutte le versioni di .NET?

A1: Sì, Aspose.Zip per .NET è progettato per integrarsi senza problemi con tutte le versioni del framework .NET.

### Q2: Posso usare Aspose.Zip per .NET nei miei progetti commerciali?

A2: Assolutamente! Aspose.Zip per .NET offre licenze commerciali; puoi trovare maggiori informazioni su come acquistare [qui](https://purchase.aspose.com/buy).

### Q3: È disponibile una versione di prova gratuita?

A3: Sì, puoi esplorare le funzionalità di Aspose.Zip per .NET con una prova gratuita. Inizia [qui](https://releases.aspose.com/).

### Q4: Come posso ottenere supporto per Aspose.Zip per .NET?

A4: Per qualsiasi domanda o assistenza, visita il [Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5: Posso usare Aspose.Zip per .NET senza una licenza permanente?

A5: Sì, è possibile ottenere una licenza temporanea per esigenze a breve termine. Trovi maggiori dettagli [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione

Hai appena imparato **come comprimere file con password** e crittografare archivi ZIP con password per voce usando Aspose.Zip per .NET. Questa tecnica ti offre la flessibilità di proteggere ogni file singolarmente, soddisfacendo requisiti di sicurezza più stringenti e semplificando la distribuzione specifica per utente. Sentiti libero di sperimentare altre impostazioni di compressione, set di file più grandi o di integrare questa logica in un servizio web che genera archivi sicuri al volo.

---

**Ultimo aggiornamento:** 2026-02-28  
**Testato con:** Aspose.Zip per .NET 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}