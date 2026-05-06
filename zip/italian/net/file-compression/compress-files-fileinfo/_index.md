---
date: 2026-02-28
description: Scopri come aggiungere una cartella a un file zip e aggiungere file a
  un zip usando Aspose.Zip per .NET. Questa guida passo passo mostra come comprimere
  i file con FileInfo nei progetti ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Come aggiungere una cartella a un archivio zip usando Aspose.Zip per .NET –
  Comprimere file con FileInfo
url: /it/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere una cartella a un file Zip usando Aspose.Zip per .NET

## Introduzione

Se hai bisogno di **creare un archivio zip** in modo programmatico, Aspose.Zip per .NET ti offre un'API pulita e ad alte prestazioni che funziona in qualsiasi applicazione .NET (inclusi ASP.NET). In questo tutorial vedremo come comprimere file con la classe `FileInfo`, ti mostreremo come **aggiungere file a zip** e spiegheremo perché questo approccio è ideale per i progetti .NET moderni. Tratteremo anche come **aggiungere una cartella a zip** così potrai raggruppare intere directory in un unico passaggio. Iniziamo!

## Risposte rapide
- **Qual è il modo più semplice per creare un archivio zip?** Usa la classe `Archive` di Aspose.Zip insieme agli oggetti `FileInfo`.  
- **Posso aggiungere più file contemporaneamente?** Sì – basta creare un `FileInfo` per ogni file e chiamare `CreateEntry`.  
- **È necessaria una licenza speciale per ASP.NET?** È richiesta una licenza commerciale di Aspose.Zip per la produzione; una versione di prova gratuita è sufficiente per la valutazione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **L'API è thread‑safe?** Sì, purché ogni thread utilizzi la propria istanza di `Archive`.

## Cos'è un archivio Zip e perché crearne uno?
Un archivio zip raggruppa uno o più file in un unico contenitore compresso. Questo riduce lo spazio di archiviazione, velocizza i trasferimenti di rete e semplifica la distribuzione. Che tu stia consegnando log, esportando report o impacchettando risorse per un cliente, conoscere **come creare un archivio zip** programmaticamente è una competenza preziosa per qualsiasi sviluppatore .NET.

## Perché usare Aspose.Zip per aggiungere file a Zip?
- **Zero dipendenze esterne** – implementazione pura .NET.  
- **Controllo completo sul livello di compressione e sulla codifica** (ASCII, UTF‑8, ecc.).  
- **Supporta file di grandi dimensioni** (> 4 GB) e protezione con password.  
- **API coerente su .NET Framework, .NET Core e .NET 5+**.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.Zip per .NET** installato. Scarica il pacchetto più recente dalla [pagina di download di Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Una cartella sul tuo computer contenente i file che desideri comprimere (ad esempio `alice29.txt` e `fields.c`).  

## Importare i namespace

In qualsiasi file C# in cui lavorerai con archivi zip, aggiungi le seguenti istruzioni `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Questi namespace ti danno accesso alla classe `Archive`, alle opzioni di salvataggio e alle utility I/O standard.

## Guida passo‑passo

### Passo 1: Configura la directory dei documenti

Per prima cosa, definisci la cartella che contiene i file di origine. Sostituisci il segnaposto con il percorso assoluto o relativo sul tuo sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Suggerimento professionale:** Usa `Path.Combine` per costruire i percorsi in modo cross‑platform.

### Passo 2: Apri un file Zip per la scrittura

Crea un `FileStream` che punti al file zip di destinazione. Lo stream è aperto in modalità **Create**, che sovrascrive eventuali file esistenti con lo stesso nome:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Passo 3: Prepara gli oggetti `FileInfo` per ogni file di origine

`FileInfo` fornisce ad Aspose.Zip l'accesso diretto ai file fisici su disco. Crea un'istanza per ciascun file che desideri comprimere:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Perché usare `FileInfo`?** Evita di caricare l'intero file in memoria, il che è particolarmente utile per file di grandi dimensioni.

### Passo 4: Crea l'archivio e aggiungi le voci

Istanzia un oggetto `Archive`, quindi chiama `CreateEntry` per ogni `FileInfo`. Il primo argomento è il nome che il file avrà all'interno dello zip, il secondo argomento è il `FileInfo` di origine:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Passo 5: Salva l'archivio Zip con la codifica desiderata

Infine, persisti l'archivio nello `FileStream` aperto in precedenza. Qui usiamo la codifica ASCII per i nomi delle voci, ma puoi passare a UTF‑8 se i tuoi nomi file contengono caratteri non ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando i blocchi `using` terminano, gli stream vengono chiusi automaticamente e il file zip è pronto per l'uso.

## Come aggiungere una cartella a Zip usando Aspose.Zip

Se devi **aggiungere una cartella a zip** anziché file individuali, il processo è semplice:

1. **Elenca la cartella** con `DirectoryInfo.GetFiles` (e opzionalmente `GetDirectories` per la ricorsione).  
2. **Crea un `FileInfo`** per ogni file scoperto.  
3. **Chiama `CreateEntry`** con un percorso relativo che includa il nome della cartella, ad esempio `"MyFolder/Report.pdf"`.

Poiché l'API lavora con `FileInfo`, non dovrai mai caricare interi file in memoria, rendendo sicura l'elaborazione di grandi directory. Questa tecnica funziona anche per scenari **zip multiple files asp.net** in cui generi un set di report al volo e devi consegnarlo come unico archivio.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **File zip vuoto** | `FileInfo` punta a un percorso inesistente | Verifica `dataDir` e i nomi dei file; usa `File.Exists` per controllare prima di creare le voci. |
| **Codifica del nome file errata** | Uso della codifica predefinita con nomi non ASCII | Imposta `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException su file grandi** | Caricamento dell'intero file in memoria | `FileInfo` trasmette il file; assicurati di non leggere il file in un array di byte altrove. |
| **Permesso negato** | L'applicazione non ha i permessi di scrittura sulla cartella di destinazione | Esegui l'app con i diritti appropriati o scegli una directory scrivibile. |

### Domande frequenti

#### D1: Aspose.Zip è compatibile con tutti i tipi di file?

R1: Aspose.Zip supporta un'ampia gamma di tipi di file, garantendo versatilità nella compressione.

#### D2: Posso usare Aspose.Zip per progetti commerciali?

R2: Certamente! Visita la nostra [pagina di acquisto](https://purchase.aspose.com/buy) per scoprire le opzioni di licenza.

#### D3: Come posso ottenere supporto per Aspose.Zip?

R3: Unisciti alla nostra community sul [forum di Aspose.Zip](https://forum.aspose.com/c/zip/37) per ricevere assistenza e partecipare alle discussioni.

#### D4: È disponibile una versione di prova gratuita?

R4: Sì, puoi scaricare la tua [versione di prova gratuita qui](https://releases.aspose.com/).

#### D5: Come posso ottenere una licenza temporanea per Aspose.Zip?

R5: Visita [questo link](https://purchase.aspose.com/temporary-license/) per informazioni su come ottenere una licenza temporanea.

## Conclusione

Ora sai **come aggiungere una cartella a zip** e **come creare archivi zip** usando Aspose.Zip per .NET, come **aggiungere file a zip**, e perché questo metodo è ideale per ASP.NET e altre applicazioni .NET. Sperimenta con diversi livelli di compressione, codifiche e opzioni di crittografia per adattare l'archivio alle tue esigenze precise. Buona compressione!

---

**Ultimo aggiornamento:** 2026-02-28  
**Testato con:** Aspose.Zip per .NET 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}