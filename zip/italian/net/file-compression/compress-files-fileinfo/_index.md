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

## Domande frequenti

**D: Posso aggiungere la protezione con password all'archivio zip?**  
R: Sì. Dopo aver creato l'`Archive`, imposta `archive.Password = "yourPassword"` prima di chiamare `Save`.

**D: È possibile aggiornare un file zip esistente?**  
R: Aspose.Zip supporta l'apertura di un archivio esistente con `Archive.Open` e quindi l'aggiunta di nuove voci.

**D: Come comprimo i file in un controller ASP.NET MVC?**  
R: Lo stesso codice funziona; basta assicurarsi che lo stream di output venga restituito come `FileResult` al client.

**D: Aspose.Zip supporta algoritmi di crittografia?**  
R: Supporta la crittografia standard ZipCrypto e AES‑256.

**D: Cosa fare se devo comprimere una cartella in modo ricorsivo?**  
R: Scorri `Directory.GetFiles` (e le sottocartelle) creando un `FileInfo` per ogni file, quindi aggiungili all'archivio.

## FAQ aggiuntive

**D: Come creo un archivio zip .net per grandi set di dati?**  
R: Usa gli oggetti `FileInfo` per lo streaming dei dati e imposta `CompressionLevel` in `ArchiveSaveOptions` per ottenere le migliori prestazioni.

**D: Posso usare Aspose.Zip in una Web API .NET Core (zip files asp.net core)?**  
R: Assolutamente sì – la libreria è pienamente compatibile con .NET Core 3.1 e versioni successive.

**D: Esiste un modo per aggiungere una cartella a zip senza scrivere un ciclo personalizzato?**  
R: Aspose.Zip non dispone di un metodo unico “add folder”, ma iterare con `DirectoryInfo` è leggero e ti dà il pieno controllo sui nomi delle voci.

**D: La protezione con password influisce sulla velocità di compressione?**  
R: L'abilitazione della crittografia aggiunge un piccolo overhead, ma l'impatto è minimo nella maggior parte dei casi d'uso.

**D: Quale licenza è necessaria per il deployment commerciale?**  
R: È richiesta una licenza a pagamento di Aspose.Zip per la produzione; una versione di prova gratuita può essere usata per sviluppo e test.

## Sezione FAQ esistente (invariata)

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

Ora sai **come aggiungere una cartella a zip** e **come creare archivi zip** usando Aspose.Zip per .NET, come **aggiungere file a zip**, e perché questo metodo è ideale per ASP.NET e altre applicazioni .NET. Sperimenta con diversi livelli di compressione, codifiche e opzioni di crittografia per adattare l'archivio alle tue esigenze precise. Buona compressione!

---

**Ultimo aggiornamento:** 2026-02-28  
**Testato con:** Aspose.Zip per .NET 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}