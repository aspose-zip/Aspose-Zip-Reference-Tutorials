---
date: 2026-03-02
description: Scopri come creare un archivio zip protetto da password e comprimere
  file con password in .NET usando Aspose.Zip. Segui la nostra guida passo‑passo.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crea un archivio ZIP protetto da password in .NET con Aspose.Zip
url: /it/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un archivio ZIP protetto da password in .NET con Aspose.Zip

## Introduzione

Quando devi condividere dati sensibili, un **archivio zip protetto da password** è uno dei modi più semplici ma efficaci per mantenere le informazioni al sicuro. Nelle applicazioni .NET, Aspose.Zip semplifica **la compressione dei file con password**, assegnando a ciascun file la propria chiave di crittografia. In questo tutorial imparerai esattamente come creare un tale archivio, perché è importante e dove puoi applicarlo in progetti reali.

## Risposte rapide
- **Quale libreria devo usare?** Aspose.Zip per .NET fornisce supporto integrato per password per file e più metodi di crittografia.  
- **Quante righe di codice?** Circa 30 righe, inclusa la configurazione e il salvataggio dell'archivio.  
- **Ogni file può avere una password diversa?** Sì – è possibile assegnare una password univoca a ogni voce.  
- **Quali metodi di crittografia sono disponibili?** ZipCrypto tradizionale, AES‑128 e AES‑256.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per l'uso in produzione; è disponibile una versione di prova gratuita.

## Che cos'è un archivio zip protetto da password?
Un archivio zip protetto da password è un file compresso (ZIP) che richiede una password per estrarne il contenuto. La password può proteggere l'intero archivio o le singole voci, e algoritmi moderni come AES‑128/256 offrono una crittografia robusta.

## Perché comprimere i file con password usando Aspose.Zip?
- **Sicurezza granulare** – assegna una password distinta per file, ideale per scenari multi‑tenant.  
- **Molteplici standard di crittografia** – scegli tra ZipCrypto legacy e AES forte.  
- **Nessuno strumento esterno** – tutto è gestito programmaticamente all'interno del tuo codice .NET.  
- **Prestazioni** – compressione veloce con Deflate mantenendo le dimensioni dell'archivio contenute.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Zip per .NET** – installa la libreria nel tuo progetto. Documentazione dettagliata disponibile [qui](https://reference.aspose.com/zip/net/).  
- **Scarica il pacchetto più recente** se non lo hai già fatto, da [questo link](https://releases.aspose.com/zip/net/).  
- Una cartella contenente i file che desideri comprimere.

## Importa gli spazi dei nomi

Aggiungi gli spazi dei nomi richiesti all'inizio del tuo file C#:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Passo 1: Imposta il percorso della directory delle risorse

Indica al codice la cartella che contiene i file di origine:

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Comprimi i file con password individuali

Ora creeremo un **archivio zip protetto da password** in cui ogni file utilizza la propria password e metodo di crittografia. L'esempio utilizza tre file di esempio (`alice29.txt`, `asyoulik.txt` e `fields.c`) con password diverse.

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
- **CreateEntry** aggiunge un file all'archivio.  
- Il quarto argomento (`ArchiveEntrySettings`) consente di specificare sia la compressione (`DeflateCompressionSettings`) sia la crittografia (`TraditionalEncryptionSettings` o `AesEcryptionSettings`).  
- Passando una stringa di password diversa per ogni voce, ottieni un **archivio zip protetto da password** in cui ogni file si sblocca solo con la propria chiave.

## Problemi comuni e risoluzione

| Sintomo | Probabile causa | Soluzione |
|---------|-----------------|-----------|
| L'estrazione fallisce con “Password errata” | Mismatch della password o metodo di crittografia errato | Verifica la stringa della password esatta e assicurati di aver usato lo stesso `EncryptionMethod` durante l'estrazione. |
| La dimensione dell'archivio è più grande del previsto | L'uso di AES‑256 su file di testo piccoli può aggiungere overhead | Per file piccoli, AES‑128 può essere sufficiente e produce un archivio più piccolo. |
| Eccezione runtime su `archive.Save` | Mancanza di permessi di scrittura sulla cartella di destinazione | Assicurati che l'applicazione abbia accesso in scrittura a `dataDir` o utilizza un percorso di output diverso. |

## Domande frequenti (FAQ)

### Posso usare metodi di crittografia diversi per ogni file?
Sì, Aspose.Zip per .NET consente di mescolare i metodi di crittografia — ZipCrypto tradizionale, AES‑128 e AES‑256 — a livello di singolo file.

### È disponibile una versione di prova?
Sì, puoi accedere alla versione di prova gratuita di Aspose.Zip per .NET [qui](https://releases.aspose.com/).

### Come posso ottenere supporto se riscontro problemi?
Visita il [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) per assistenza dalla community e dal supporto Aspose.

### Dove posso trovare la documentazione dettagliata per Aspose.Zip per .NET?
La documentazione è disponibile [qui](https://reference.aspose.com/zip/net/).

### Posso acquistare una licenza temporanea per scopi di test?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-02  
**Testato con:** Aspose.Zip per .NET (ultima release)  
**Autore:** Aspose  

---