---
date: 2025-12-05
description: Scopri come creare un archivio zip e aggiungere file allo zip utilizzando
  Aspose.Zip per .NET. Questa guida passo‑passo mostra come comprimere i file con
  FileInfo nei progetti ASP.NET.
language: it
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come creare un archivio Zip usando Aspose.Zip per .NET – Comprimere file con
  FileInfo
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un archivio Zip usando Aspose.Zip per .NET

## Introduzione

Se hai bisogno di **creare un archivio zip** in modo programmatico, Aspose.Zip per .NET ti offre un'API pulita e ad alte prestazioni che funziona in qualsiasi applicazione .NET (inclusi ASP.NET). In questo tutorial vedremo come comprimere file con la classe `FileInfo`, ti mostreremo come **aggiungere file allo zip** e spiegheremo perché questo approccio è ideale per i progetti .NET moderni. Iniziamo!

## Risposte rapide
- **Qual è il modo più semplice per creare un archivio zip?** Usa la classe `Archive` di Aspose.Zip insieme agli oggetti `FileInfo`.  
- **Posso aggiungere più file contemporaneamente?** Sì – basta creare un `FileInfo` per ogni file e chiamare `CreateEntry`.  
- **È necessaria una licenza speciale per ASP.NET?** È richiesta una licenza commerciale di Aspose.Zip per la produzione; una versione di prova gratuita è sufficiente per la valutazione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **L'API è thread‑safe?** Sì, purché ogni thread utilizzi la propria istanza di `Archive`.

## Cos'è un archivio Zip e perché crearne uno?
Un archivio zip raggruppa uno o più file in un unico contenitore compresso. Questo riduce lo spazio di archiviazione, velocizza i trasferimenti di rete e semplifica la distribuzione. Che tu stia consegnando log, esportando report o impacchettando risorse per un cliente, sapere **come creare file zip** in modo programmatico è una competenza preziosa per qualsiasi sviluppatore .NET.

## Perché usare Aspose.Zip per aggiungere file allo Zip?
- **Zero dipendenze esterne** – implementazione pura .NET.  
- **Controllo completo sul livello di compressione e sulla codifica** (ASCII, UTF‑8, ecc.).  
- **Supporta file di grandi dimensioni** (> 4 GB) e protezione con password.  
- **API coerente su .NET Framework, .NET Core e .NET 5+**.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere:

1. **Aspose.Zip per .NET** installato. Scarica il pacchetto più recente dalla [pagina di download di Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Una cartella sul tuo computer contenente i file che desideri comprimere (ad es., `alice29.txt` e `fields.c`).  

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

### Passo 1: Configurare la directory dei documenti

Per prima cosa, definisci la cartella che contiene i file sorgente. Sostituisci il segnaposto con il percorso assoluto o relativo sul tuo sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Consiglio professionale:** Usa `Path.Combine` per costruire i percorsi in modo cross‑platform.

### Passo 2: Aprire un file Zip per la scrittura

Crea un `FileStream` che punta al file zip di output. Lo stream è aperto in modalità **Create**, che sovrascrive eventuali file esistenti con lo stesso nome:

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

Istanzia un oggetto `Archive`, quindi chiama `CreateEntry` per ogni `FileInfo`. Il primo argomento è il nome che il file avrà all'interno dello zip, il secondo è il `FileInfo` di origine:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Passo 5: Salvare l'archivio Zip con la codifica desiderata

Infine, persisti l'archivio nello `FileStream` aperto in precedenza. Qui usiamo la codifica ASCII per i nomi delle voci, ma puoi passare a UTF‑8 se i tuoi nomi di file contengono caratteri non ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando i blocchi `using` terminano, gli stream vengono chiusi automaticamente e il file zip è pronto per l'uso.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **File zip vuoto** | `FileInfo` punta a un percorso inesistente | Verifica `dataDir` e i nomi dei file; usa `File.Exists` per controllare prima di creare le voci. |
| **Codifica del nome file errata** | Uso della codifica predefinita con nomi non ASCII | Imposta `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException su file grandi** | Caricamento dell'intero file in memoria | `FileInfo` trasmette il file; assicurati di non leggere il file in un array di byte altrove. |
| **Accesso negato** | L'applicazione non ha permessi di scrittura nella cartella di output | Esegui l'app con i diritti appropriati o scegli una directory scrivibile. |

## Domande frequenti

**D: Posso aggiungere una protezione con password all'archivio zip?**  
R: Sì. Dopo aver creato l'`Archive`, imposta `archive.Password = "yourPassword"` prima di chiamare `Save`.

**D: È possibile aggiornare un file zip esistente?**  
R: Aspose.Zip supporta l'apertura di un archivio esistente con `Archive.Open` e poi l'aggiunta di nuove voci.

**D: Come comprimere file in un controller ASP.NET MVC?**  
R: Lo stesso codice funziona; basta assicurarsi che lo stream di output venga restituito come `FileResult` al client.

**D: Aspose.Zip supporta algoritmi di crittografia?**  
R: Supporta la crittografia standard ZipCrypto e AES‑256.

**D: Cosa fare se devo comprimere una cartella ricorsivamente?**  
R: Scorri `Directory.GetFiles` (e le sottocartelle) creando un `FileInfo` per ogni file, quindi aggiungili all'archivio.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusione

Ora sai **come creare file zip** usando Aspose.Zip per .NET, **come aggiungere file allo zip** e perché questo metodo è ideale per ASP.NET e altre applicazioni .NET. Sperimenta con diversi livelli di compressione, codifiche e opzioni di crittografia per adattare l'archivio alle tue esigenze precise. Buona compressione!

---

**Ultimo aggiornamento:** 2025-12-05  
**Testato con:** Aspose.Zip per .NET 24.12 (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}