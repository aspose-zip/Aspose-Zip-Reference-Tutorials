---
title: Proteggi i tuoi file crittografia AES con Aspose.Zip
linktitle: Proteggi con password con AES
second_title: Aspose.Zip .NET API per la compressione e l'archiviazione dei file
description: Scopri come migliorare la sicurezza dei tuoi file utilizzando Aspose.Zip per .NET con crittografia AES. Segui la nostra guida passo passo per una protezione ottimale.
weight: 11
url: /it/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proteggi i tuoi file crittografia AES con Aspose.Zip


## introduzione

Proteggere i tuoi file sensibili è fondamentale nell'era digitale di oggi e Aspose.Zip per .NET fornisce una soluzione solida per proteggere con password i tuoi archivi utilizzando Advanced Encryption Standard (AES). In questo tutorial esploreremo come implementare la crittografia AES con tre lunghezze di chiave: 128 bit, 192 bit e 256 bit, garantendo il massimo livello di sicurezza per i tuoi file compressi.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Zip per .NET: assicurati di avere la libreria Aspose.Zip integrata nel tuo progetto .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/zip/net/).

- Directory dei documenti: dispone di una directory in cui si trovano i file di origine.

## Importa spazi dei nomi

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Passaggio 1: proteggere con password con AES-128

```csharp
//ExStart:Protezione password con AES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES128
```

In questo passaggio creiamo un file zip e lo proteggiamo con la crittografia AES-128. La password "p@s$" garantisce la sicurezza del tuo archivio.

## Passaggio 2: proteggere con password con AES-192

```csharp
//ExStart:Protezione password con AES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES192
```

Questo passaggio dimostra come implementare la crittografia AES-192 per una maggiore sicurezza. Per coerenza viene utilizzata la stessa password "p@s$".

## Passaggio 3: proteggere con password con AES-256

```csharp
//ExStart:Proteggi password con AES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: PasswordProtectWithAES256
```

In questo passaggio finale, implementiamo il livello di crittografia più elevato, AES-256, fornendo un ulteriore livello di sicurezza per i tuoi file compressi.

## Conclusione

In questo tutorial, abbiamo coperto i passaggi essenziali per proteggere con password i tuoi archivi utilizzando la crittografia AES in Aspose.Zip per .NET. Sia che tu scelga la crittografia a 128 bit, 192 bit o 256 bit, i tuoi file saranno protetti da accessi non autorizzati.

## Domande frequenti

### Posso utilizzare Aspose.Zip per .NET con altri linguaggi di programmazione?
Aspose.Zip è progettato principalmente per le applicazioni .NET, garantendo un'integrazione perfetta e prestazioni ottimali.

### Il metodo di crittografia AES è sicuro per i dati sensibili?
Sì, la crittografia AES è ampiamente riconosciuta come un metodo sicuro e robusto per proteggere le informazioni sensibili.

### Posso cambiare la password per un archivio già crittografato?
No, la password per un archivio crittografato non può essere modificata una volta impostata. Dovrai creare un nuovo archivio crittografato con una password diversa.

### Esistono limitazioni sui tipi di file che possono essere crittografati utilizzando Aspose.Zip?
Aspose.Zip supporta la crittografia di vari tipi di file, garantendo flessibilità nella protezione di diversi tipi di dati.

### Cosa succede se dimentico la password per un archivio crittografato?
Sfortunatamente, non è possibile recuperare la password di un archivio crittografato. È fondamentale conservare la password in un luogo sicuro.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
