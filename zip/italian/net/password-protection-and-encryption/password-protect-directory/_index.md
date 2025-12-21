---
date: 2025-12-21
description: Scopri come creare file zip protetti da password in .NET, crittografare
  cartelle e modificare la password dello zip utilizzando Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea zip protetto da password per directory .NET – Tutorial Aspose.Zip
url: /it/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea zip protetto da password per directory .NET – Tutorial Aspose.Zip

In questa guida **creerai archivi zip protetti da password** per intere directory utilizzando la libreria Aspose.Zip per .NET. Che tu abbia bisogno di **cifrare una cartella**, proteggere file di backup, o semplicemente limitare l'accesso a dati sensibili, questo tutorial passo‑passo ti mostra esattamente come farlo con codice C# pulito.

## Quick Answers
- **Qual è la libreria consigliata?** Aspose.Zip per .NET  
- **Posso cifrare un'intera cartella?** Sì – basta puntare l'API sulla cartella che vuoi comprimere.  
- **È supportata la modifica della password dello zip?** Assolutamente, usa `TraditionalEncryptionSettings`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza valida di Aspose.Zip per uso commerciale.  
- **Funziona con .NET Core/5/6?** Sì, l'API è pienamente compatibile con i runtime .NET moderni.  

## Cos'è “creare zip protetto da password”?
Creare un zip protetto da password significa comprimere file o directory in un archivio ZIP applicando la crittografia in modo che l'archivio possa essere aperto solo con la password corretta. Questo protegge il contenuto da accessi non autorizzati.

## Perché usare Aspose.Zip per proteggere con password una directory .NET?
Aspose.Zip offre un'API semplice e ad alte prestazioni che supporta **c# zip password protection**, la crittografia tradizionale ZipCrypto e la crittografia AES. Gestisce grandi directory in modo efficiente e si integra perfettamente con qualsiasi progetto .NET.

## Prerequisites
Prima di iniziare, assicurati di avere:

- Conoscenza di base della programmazione C#.  
- Visual Studio (qualsiasi edizione recente).  
- Libreria Aspose.Zip per .NET – scaricala **[qui](https://releases.aspose.com/zip/net/)**.  
- Una cartella su disco che desideri proteggere con una password.

## Importa gli spazi dei nomi
Aggiungi gli spazi dei nomi necessari al tuo file C# affinché il compilatore sappia dove trovare le classi Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Passo 1: Imposta il percorso della directory di risorse
Definisci il percorso che punta alla directory che intendi comprimere e proteggere.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Proteggi la directory con password
Usa `TraditionalEncryptionSettings` per specificare la password e creare l'archivio cifrato. Questo è il fulcro della **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Passo 3: Spiegazione del codice
- **Creazione del file di output:** `File.Open(..., FileMode.Create)` apre (o crea) il file ZIP che conterrà i dati cifrati.  
- **Selezione della cartella di origine:** `new DirectoryInfo(".\\CanterburyCorpus")` indica ad Aspose.Zip quale directory comprimere.  
- **Applicazione della password:** `new TraditionalEncryptionSettings("p@s$")` imposta la password che proteggerà l'archivio.  
- **Aggiunta delle voci e salvataggio:** `archive.CreateEntries(corpus)` aggiunge tutti i file nella cartella, e `archive.Save(zipFile)` scrive lo ZIP cifrato su disco.

## Come cambiare la password dello zip in seguito?
Se hai bisogno di **change zip password**, ricrea semplicemente l'archivio con una nuova istanza di `TraditionalEncryptionSettings` contenente la nuova password, quindi salvalo nuovamente.

## Problemi comuni e suggerimenti
- **Cartelle grandi:** Aspose.Zip trasmette i dati in streaming, quindi l'uso della memoria rimane basso anche per directory enormi.  
- **Complessità della password:** Usa una password forte (mix di lettere, numeri, simboli) per migliorare la sicurezza.  
- **Errori di licenza:** Assicurati di aver applicato un file di licenza valido; altrimenti la libreria funziona in modalità di valutazione con limitazioni.

## Domande frequenti

### Aspose.Zip per .NET è adatto a directory di grandi dimensioni?
Sì, Aspose.Zip per .NET è progettato per gestire directory di grandi dimensioni in modo efficiente, offrendo prestazioni ottimali.

### Posso cambiare la password di una directory già protetta?
Sì, puoi modificare la password regolando `TraditionalEncryptionSettings` nel codice di conseguenza.

### Ci sono requisiti di licenza per l'uso di Aspose.Zip per .NET?
Sì, è necessaria una licenza valida per utilizzare Aspose.Zip per .NET in un ambiente di produzione. Puoi ottenere una licenza **[qui](https://purchase.aspose.com/buy)**.

### È disponibile una prova gratuita per Aspose.Zip per .NET?
Sì, puoi accedere a una prova gratuita **[qui](https://releases.aspose.com/)**.

### Dove posso trovare supporto aggiuntivo per Aspose.Zip per .NET?
Puoi visitare il **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** per qualsiasi supporto o domanda.

---

**Ultimo aggiornamento:** 2025-12-21  
**Testato con:** Aspose.Zip per .NET (ultima release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}