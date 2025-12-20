---
date: 2025-12-20
description: Scopri come creare archivi zip protetti da password in .NET usando Aspose.Zip.
  Questa guida passo‑passo mostra come comprimere file con password, impostare la
  password per le voci zip e utilizzare la crittografia AES.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea file ZIP protetti da password in .NET con Aspose.Zip
url: /it/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea file ZIP protetti da password in .NET con Aspose.Zip

## Introduzione

Se hai bisogno di **creare zip protetti da password** in un'applicazione .NET, Aspose.Zip lo rende semplice. Assegnando una password unica a ciascuna voce, puoi tenere al sicuro i documenti sensibili mantenendo la comodità della compressione ZIP. In questo tutorial imparerai a comprimere file con password individuali, scegliere diversi metodi di crittografia e impostare la password di una voce zip — tutto con codice chiaro e pronto per la produzione.

## Risposte rapide
- **Quale libreria devo usare?** Aspose.Zip per .NET.
- **Posso assegnare una password diversa per ogni file?** Sì, ogni voce può avere la propria password.
- **Quali algoritmi di crittografia sono supportati?** ZipCrypto tradizionale, AES‑128 e AES‑256.
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.
- **È compatibile con .NET 6+?** Assolutamente – l'API punta a .NET Standard 2.0 e versioni successive.

## Che cosa significa “creare zip protetto da password”?
Creare un zip protetto da password significa aggiungere crittografia a una o più voci all'interno di un archivio ZIP in modo che il contenuto non possa essere aperto senza la password corretta. È ideale per trasmettere file riservati, archiviare backup o rispettare le politiche di protezione dei dati.

## Perché usare Aspose.Zip per archivi protetti da password?
- **Controllo fine‑grained** – imposta una password distinta per ogni file.
- **Opzioni di crittografia multiple** – dal legacy ZipCrypto a AES‑128/256 più robusti.
- **Nessuna dipendenza esterna** – libreria .NET pura, facile da integrare.
- **Documentazione completa** – include un **aspose zip tutorial** per scenari più avanzati.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.Zip per .NET: verifica di aver installato la libreria Aspose.Zip nel tuo progetto .NET. Puoi trovare la documentazione necessaria [qui](https://reference.aspose.com/zip/net/).

- Download: se non l’hai ancora fatto, scarica la libreria Aspose.Zip per .NET dal [seguente link](https://releases.aspose.com/zip/net/).

- Directory dei documenti: prepara una cartella contenente i file che desideri comprimere.

## Importa gli spazi dei nomi

Nel tuo progetto .NET, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Passo 1: Imposta il percorso della directory delle risorse

Definisci il percorso della directory delle risorse dove si trovano i tuoi file sorgente.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Comprimi i file con password individuali

Ora, comprimiamo i file con password individuali. Useremo tre file di esempio (`alice29.txt`, `asyoulik.txt` e `fields.c`) con password distinte per ciascuno. Questo dimostra come **comprimere file con password** e anche come **impostare la password di una voce zip** usando diversi schemi di crittografia, incluso un **zip archive with aes**.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Come funziona
- **TraditionalEncryptionSettings** utilizza l'algoritmo più vecchio ZipCrypto (compatibile con la maggior parte degli strumenti ZIP).
- **AesEcryptionSettings** ti consente di scegliere AES‑128 o AES‑256 per una sicurezza più forte.
- Ogni chiamata a `CreateEntry` riceve un oggetto `ArchiveEntrySettings` dove specifichiamo sia il metodo di compressione sia le impostazioni di crittografia, proteggendo così le voci dell'archivio zip con password.

## Problemi comuni e soluzioni

| Problema | Motivo | Correzione |
|----------|--------|------------|
| “Invalid password” quando si apre lo ZIP | Discrepanza tra la password usata nel codice e quella inserita nell'estrattore | Verifica la stringa esatta passata a `TraditionalEncryptionSettings` o `AesEcryptionSettings`. |
| Gli strumenti di estrazione più vecchi non aprono voci criptate con AES | Non tutti gli utility ZIP supportano la crittografia AES | Usa il metodo tradizionale ZipCrypto per la massima compatibilità, o consiglia agli utenti di utilizzare uno strumento moderno (es. 7‑Zip). |
| File di grandi dimensioni causano `OutOfMemoryException` | Caricamento di file enormi in memoria prima della compressione | Esegui lo streaming del file direttamente con `FileStream` senza caricare l'intero file in un oggetto `FileInfo`. |

## Domande frequenti (FAQ)

### Posso usare metodi di crittografia diversi per ogni file?
Sì, Aspose.Zip per .NET consente di utilizzare metodi di crittografia diversi per ciascun file durante la compressione.

### È disponibile una versione di prova?
Sì, puoi accedere alla prova gratuita di Aspose.Zip per .NET [qui](https://releases.aspose.com/).

### Come posso ottenere supporto se incontro problemi?
Visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per assistenza dalla community e dal supporto Aspose.

### Dove posso trovare la documentazione dettagliata per Aspose.Zip per .NET?
La documentazione è disponibile [qui](https://reference.aspose.com/zip/net/).

### Posso acquistare una licenza temporanea per scopi di test?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## FAQ rapide aggiuntive

**D: La libreria supporta .NET Core e .NET 5/6?**  
R: Sì, Aspose.Zip punta a .NET Standard, rendendola compatibile con .NET Framework, .NET Core e .NET 5/6.

**D: Posso aggiungere un commento a ogni voce ZIP?**  
R: Sebbene Aspose.Zip si concentri su compressione e crittografia, puoi memorizzare metadati in un file manifesto separato all'interno dell'archivio.

**D: È possibile crittografare l'intero archivio con una singola password?**  
R: Puoi impostare una password su ogni voce individualmente (come mostrato) oppure applicare la stessa password a tutte le voci per un approccio più semplice di “zip archive with aes”.

## Conclusione

Ora hai imparato a **creare zip protetti da password** in .NET usando Aspose.Zip. Assegnando password individuali e scegliendo il metodo di crittografia appropriato, puoi mantenere i tuoi dati al sicuro senza rinunciare alla comodità della compressione ZIP. Esplora altre funzionalità di Aspose.Zip come lo streaming di file di grandi dimensioni, l'aggiunta di metadati personalizzati e l'integrazione con lo storage cloud per scenari ancora più potenti.

---

**Ultimo aggiornamento:** 2025-12-20  
**Testato con:** Aspose.Zip per .NET 23.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}