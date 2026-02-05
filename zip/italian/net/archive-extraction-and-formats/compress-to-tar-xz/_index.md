---
date: 2026-02-05
description: Scopri come aggiungere file a un archivio tar e creare archivi tarxz
  in .NET usando Aspose.Zip. Questa guida mostra come comprimere i file in tarxz con
  alta efficienza.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aggiungere file a tar, creare archivio tarxz .NET con Aspose.Zip
url: /it/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere file a tar, creare archivio tarxz .NET con Aspise.Zip

## Introduzione

Se hai bisogno di **aggiungere file a tar** e poi comprimerli in un archivio tarxz usando .NET, Aspose.Zip per .NET rende il processo semplice e affidabile. Che tu stia impacchettando log, file di configurazione o qualsiasi altro asset per l'archiviazione o la trasmissione, comprimere nel formato TarXz ti offre un alto rapporto di compressione mantenendo la struttura familiare di tar. In questo tutorial percorreremo i passaggi esatti—completi di snippet di codice—così potrai integrare la creazione di tarxz nelle tue applicazioni .NET con sicurezza.

## Risposte rapide
- **Qual è la classe principale?** `TarArchive` da `Aspose.Zip.Tar`
- **Come comprimere tarxz?** Usa `SaveXzCompressed` dopo aver aggiunto le voci
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Licenza necessaria?** Sì, una licenza valida di Aspose.Zip per la produzione
- **Tempo tipico di implementazione?** ~5‑10 minuti

## Che cos'è un archivio TarXz?

Un **archivio TarXz** combina il tradizionale contenitore Unix `tar` con la compressione XZ. La parte tar raggruppa più file in un unico flusso, mentre XZ fornisce una compressione forte e senza perdita. Questo formato è popolare per distribuire codice sorgente, backup e grandi set di dati perché mantiene le strutture delle directory e ottiene dimensioni di file più piccole rispetto a tar o zip semplici.

## Perché aggiungere file a tar e comprimere in tarxz con Aspose.Zip?

- **Alto rapporto di compressione** – XZ comprime spesso dal 30 % al 50 % in meno rispetto a gzip.  
- **Compatibilità cross‑platform** – I file TarXz possono essere aperti su Linux, macOS e Windows.  
- **API semplice** – Aspose.Zip astrae i dettagli a basso livello, lasciandoti concentrarti sulla logica di business.  
- **Nessun tool esterno** – Tutto gira all'interno del tuo processo .NET, perfetto per cloud o pipeline CI.  

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Aspose.Zip per .NET** installato (scaricalo dalla documentazione ufficiale di [Aspose.Zip](https://reference.aspose.com/zip/net/)).  
- Una cartella contenente i file che desideri archiviare. Negli esempi qui sotto, questa cartella è referenziata dalla variabile `dataDir`.  
- Una licenza valida di Aspose.Zip (opzionale per la valutazione, obbligatoria per la produzione).

## Importare i namespace

Per prima cosa, importa i namespace che espongono la funzionalità TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Come aggiungere file a tar usando Aspose.Zip

### Passo 1: Inizializzare un `TarArchive`

Crea una nuova istanza di `TarArchive` che conterrà i file da comprimere.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Suggerimento professionale:** L'istruzione `using` garantisce che l'archivio venga correttamente smaltito, rilasciando le risorse non gestite.

### Passo 2: Aggiungere file all'archivio

Aggiungi ogni file che desideri includere. In questo esempio aggiungiamo due file di testo, ma puoi aggiungere quante voci vuoi.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Perché è importante:** Aggiungere le voci prima della compressione permette ad Aspose.Zip di costruire prima il contenitore tar, quindi applicare la compressione XZ in un unico passaggio.

### Passo 3: Salvare l'archivio con compressione XZ

Infine, scrivi l'archivio tar su disco usando la compressione XZ. Il file risultante avrà estensione `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Risultato:** Ora disponi di un file `archive.tar.xz` completamente compresso, pronto per essere trasferito, archiviato o estratto su qualsiasi piattaforma che supporti TarXz.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Eccezione “File not found”** | Percorso `dataDir` errato | Verifica che il percorso della directory termini con una barra rovesciata (`\`) o usa `Path.Combine`. |
| **Elevato utilizzo di memoria** | File molto grandi compressi in memoria | Usa `TarArchive` in modalità streaming (sovraccarico di `SaveXzCompressed` che accetta uno `Stream`). |
| **Licenza non applicata** | File di licenza mancante | Carica la licenza all'avvio dell'applicazione: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Domande frequenti

**D: Aspose.Zip è compatibile con tutti gli ambienti .NET?**  
R: Sì, Aspose.Zip funziona con .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+. Consulta la [documentazione](https://reference.aspose.com/zip/net/) per i dettagli.

**D: Come posso ottenere una licenza temporanea per Aspose.Zip?**  
R: Puoi richiedere una licenza temporanea dalla [pagina di licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/).

**D: Esistono esempi aggiuntivi per altri formati di archivio?**  
R: Assolutamente—esplora l'intero set di esempi nella [riferimento API di Aspose.Zip](https://reference.aspose.com/zip/net/).

**D: Dove posso trovare supporto o discutere problemi?**  
R: Unisciti alla conversazione sul [forum di Aspose.Zip](https://forum.aspose.com/c/zip/37) per supporto della community e risposte ufficiali.

**D: Posso provare Aspose.Zip gratuitamente prima di acquistare?**  
R: Sì, è disponibile una prova gratuita nella [pagina di download di Aspose.Zip](https://releases.aspose.com/zip/net).

## Conclusione

Seguendo i passaggi sopra, ora sai **come aggiungere file a tar** e **creare archivi tarxz** usando Aspose.Zip in .NET. Questo approccio ti fornisce un pacchetto compatto e portabile che può essere integrato senza problemi in qualsiasi flusso di lavoro .NET—sia che tu stia costruendo un'utilità desktop, un servizio web o una pipeline CI/CD automatizzata.

---

**Ultimo aggiornamento:** 2026-02-05  
**Testato con:** Aspose.Zip per .NET 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}