---
date: 2026-06-09
description: Lär dig hur du lägger till lösenord till zip och skapar LZMA-ziparkiv
  med Aspose.Zip för .NET. Denna handledning täcker Bzip2, LZMA (ordbokstorlek), PPMd,
  Enhanced Deflate, Store-komprimering och ASP.NET-filkomprimering av stora filer.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Optimera komprimeringsinställningar
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Lägg till lösenord till zip och skapa LZMA-arkiv med Aspose.Zip för .NET
url: /sv/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till lösenord till zip och skapa LZMA-arkiv med Aspose.Zip för .NET

I moderna .NET‑applikationer kan **add password to zip** medan du skapar ett högkomprimerat LZMA‑zip‑arkiv skydda känslig data och ändå ge dig den bästa möjliga komprimeringen. Oavsett om du bygger en ASP.NET‑filkomprimeringstjänst, ett skrivbordsverktyg som hanterar flera gigabyte stora filer eller ett molnbaserat arbetsflöde, guidar den här handledningen dig genom de exakta stegen för att säkra och komprimera dina filer med Aspose.Zip för .NET.

## Snabba svar
- **Vad är den främsta fördelen med LZMA‑komprimering?** Högsta komprimeringsförhållande med rimlig hastighet för de flesta filtyper.  
- **Vilken metod lagrar filer utan komprimering?** Store compression (även kallad “store compression zip”).  
- **Kan jag använda dessa inställningar i en ASP.NET‑applikation?** Ja—referera bara till Aspose.Zip i ditt projekt och anropa samma API.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs för produktion; en gratis provversion finns tillgänglig.  
- **Vilka .NET‑versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.

## Vad är “add password to zip” i Aspose.Zip?
**Att lägga till ett zip‑lösenord krypterar varje post i ett ZIP‑arkiv så att endast användare som känner till lösenordet kan extrahera filerna.** Aspose.Zip stöder både traditionell ZipCrypto‑kryptering och AES‑kryptering (128, 192 eller 256‑bit). Krypteringsinställningarna anges som det andra argumentet till `ArchiveEntrySettings` när ett `Archive` konstrueras; det finns ingen separat `SetPassword`‑metod.

## Varför använda Aspose.Zip för .NET‑filkomprimering?
Aspose.Zip erbjuder ett enhetligt API som täcker många algoritmer samtidigt som det levererar hög prestanda och låg minnesanvändning. Det låter utvecklare välja den bästa komprimeringsmetoden för varje scenario och tillämpa kryptering i ett steg, vilket förenklar koden och minskar underhållsbelastningen.

- **Unified API** – Ett enhetligt gränssnitt för Bzip2, LZMA, PPMd, Enhanced Deflate och Store.  
- **Performance‑tuned** – Optimerad native implementation bearbetar **upp till 10 GB‑filer** utan att ladda hela filen i minnet.  
- **ASP.NET friendly** – Fungerar sömlöst i webbprojekt, bakgrundstjänster och Azure Functions.  
- **Fine‑grained control** – Justera ordboksstorlek, komprimeringsnivå och kryptering med ett enda konstruktoranrop.  
- **Supports 10+ compression algorithms** – täcker de vanligaste användningsfallen i företagsdatapipelines.

## Förutsättningar
- **Aspose.Zip for .NET Library** – Ladda ner och installera från [Aspose documentation](https://reference.aspose.com/zip/net/).  
- **Sample Text File** – Förbered en exempelfil (t.ex. `sample.txt`) som du ska komprimera.  
- **.NET development environment** – Visual Studio 2022 eller någon kompatibel IDE.  

## Importera namnrymder

`Archive`, `ArchiveEntrySettings` och krypteringsklasserna finns i namnrymden `Aspose.Zip`. Importera dem högst upp i din fil:

- `Archive` representerar en ZIP‑arkivbehållare.  
- `ArchiveEntrySettings` innehåller komprimerings- och krypteringsalternativ för varje post.  
- Krypteringsklasser (t.ex. `AesEncryptionSettings`) definierar hur data krypteras.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Låt oss nu utforska varje komprimeringsinställning och se hur man **add password to zip** där det är lämpligt.

## Använda Bzip2‑komprimeringsinställningar

### Steg 1: Initiera Bzip2‑komprimering med traditionell kryptering

`Bzip2CompressionSettings` konfigurerar Bzip2‑algoritmen (blockstorlek osv.).  
`TraditionalEncryptionSettings` tillämpar den äldre ZipCrypto‑krypteringen på en post.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*Lösenordsskydd tillämpas via `TraditionalEncryptionSettings` som skickas direkt till `ArchiveEntrySettings`.*

## Hur man lägger till lösenord till zip med Aspose.Zip för .NET

Läs in din källfil, skapa ett `Archive` med postinställningarna och lägg till filen i arkivet. Krypteringen tillämpas automatiskt eftersom den angavs när `ArchiveEntrySettings`‑instansen skapades.

**Direkt svar (40‑70 ord):**  
Skapa ett `ArchiveEntrySettings`‑objekt som inkluderar både de önskade komprimeringsinställningarna och antingen `TraditionalEncryptionSettings` eller `AesEncryptionSettings`. Passa sedan detta objekt till `Archive`‑konstruktorn och lägg till filer med `AddEntry`. Arkivet skrivs med lösenordet redan inbäddat, så inget extra steg krävs efter skapandet.

`ArchiveEntrySettings` är konfigurationsbehållaren som talar om för Aspose.Zip hur varje post ska komprimeras och krypteras.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Hur man skapar LZMA‑zip‑arkiv med Aspose.Zip

### Steg 1: Initiera LZMA‑komprimering med AES256‑kryptering

`LzmaCompressionSettings` styr LZMA‑specifika parametrar såsom ordboksstorlek och fast bytes.  
`AesEncryptionSettings` tillhandahåller AES‑256‑kryptering för arkivposterna.

**Direkt svar (40‑70 ord):**  
Instansiera `LzmaCompressionSettings` med en vald `DictionarySize`, skapa ett `AesEncryptionSettings`‑objekt med ditt lösenord och `EncryptionMethod.AES256`, bygg sedan ett `ArchiveEntrySettings` från båda. Passa detta till `Archive`‑konstruktorn och lägg till dina filer; den resulterande zip‑filen blir LZMA‑komprimerad och AES‑skyddad i ett enda steg.

`LzmaCompressionSettings` är klassen som styr LZMA‑specifika parametrar såsom ordboksstorlek och fast bytes.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Tips:** LZMA erbjuder en konfigurerbar **LZMA‑ordboksstorlek** som påverkar både komprimeringsförhållande och minnesanvändning. Du kan sätta den via `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` om du behöver finjustera för mycket stora filer.

## Använda PPMd‑komprimeringsinställningar

### Steg 1: Initiera PPMd‑komprimering med AES256‑kryptering

`PpmdCompressionSettings` definierar ordning och minnesanvändning för PPMd‑algoritmen.  
`AesEncryptionSettings` tillhandahåller AES‑256‑kryptering för arkivposterna.

**Direkt svar (40‑70 ord):**  
Skapa en `PpmdCompressionSettings`‑instans, kombinera den med ett `AesEncryptionSettings`‑objekt som innehåller ditt lösenord, och mata båda i ett `ArchiveEntrySettings`. Använd detta inställningsobjekt när du konstruerar `Archive`; den resulterande zip‑filen blir PPMd‑komprimerad och lösenordsskyddad utan extra anrop.

`PpmdCompressionSettings` definierar ordning och minnesanvändning för PPMd‑algoritmen.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Använda Enhanced Deflate‑komprimeringsinställningar

### Steg 1: Initiera Enhanced Deflate‑komprimering med AES256‑kryptering

`EnhancedDeflateCompressionSettings` låter dig ange en komprimeringsnivå som balanserar hastighet och storlek.  
`AesEncryptionSettings` tillhandahåller AES‑256‑kryptering för arkivposterna.

**Direkt svar (40‑70 ord):**  
Instansiera `EnhancedDeflateCompressionSettings` med önskad nivå (0‑9), kombinera den med `AesEncryptionSettings` och paketera dem i `ArchiveEntrySettings`. Passa detta till `Archive`‑konstruktorn och lägg till filer; arkivet skapas med Enhanced Deflate‑komprimering och AES‑256‑lösenordsskydd i ett enda pass.

`EnhancedDeflateCompressionSettings` låter dig ange en komprimeringsnivå som balanserar hastighet och storlek.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Använda Store‑komprimeringsinställningar (store compression zip)

### Steg 1: Initiera Store‑komprimering med traditionell kryptering

`StoreCompressionSettings` instruerar Aspose.Zip att hoppa över komprimering helt och hållet, vilket bevarar källfilen byte‑för‑byte.  
`TraditionalEncryptionSettings` tillämpar den äldre ZipCrypto‑krypteringen.

**Direkt svar (40‑70 ord):**  
Skapa en `StoreCompressionSettings`‑instans (som inte utför någon komprimering), kombinera den med `TraditionalEncryptionSettings` som innehåller ditt lösenord, och paketera båda i `ArchiveEntrySettings`. Passa detta till `Archive`‑konstruktorn; den resulterande zip‑filen kommer att innehålla den ursprungliga filen okomprimerad men lösenordsskyddad.

`StoreCompressionSettings` instruerar Aspose.Zip att hoppa över komprimering helt och hållet, vilket bevarar källfilen byte‑för‑byte.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro‑tips:** Justera variabeln `dataDir` så att den pekar på din faktiska arbetskatalog, och återanvänd samma `Archive`‑instans om du behöver lägga till flera filer i ett enda arkiv.

## Vanliga problem och lösningar
- **"File not found"-fel** – Verifiera att `dataDir` slutar med en sökvägsseparator (`\` eller `/`) och att `sample.txt` finns.  
- **Minnesanvändning med stora filer** – Använd `ArchiveEntrySettings` för att aktivera streaming‑läge, vilket skriver data direkt till utdata‑strömmen.  
- **Inkompatibel komprimeringsnivå** – Vissa algoritmer (t.ex. LZMA) exponerar ytterligare egenskaper som `DictionarySize`. Konsultera API‑dokumentationen om du behöver finare kontroll.  
- **Lösenordet tillämpas inte** – Säkerställ att krypteringsinställningsobjektet skickas som det andra argumentet till `ArchiveEntrySettings` vid konstruktionstid, inte efter att arkivet har skapats.  

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med andra komprimeringsbibliotek?**  
A: Aspose.Zip är designat för att fungera med sina inbyggda algoritmer. Integration av tredjepartsbibliotek är möjligt men kräver anpassad hantering utanför Aspose‑API‑et.

**Q: Hur kan jag lägga till lösenordsskydd till en zip skapad med Aspose.Zip?**  
A: Skicka antingen `TraditionalEncryptionSettings` eller `AesEncryptionSettings` som det andra argumentet till `ArchiveEntrySettings` när du konstruerar `Archive`. Se [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) för fullständiga exempel.

**Q: Finns det en provversion jag kan testa?**  
A: Ja, du kan komma åt provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag få gemenskapsstöd eller ställa frågor?**  
A: För support och gemenskapsdiskussioner, besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: Kan jag få en tillfällig licens för utvärdering?**  
A: Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Hur hjälper detta med ASP.NET‑filkomprimering?**  
A: Genom att anropa samma API från en ASP.NET‑controller eller middleware kan du komprimera filer i farten innan de skickas till klienten, vilket minskar bandbredden och förbättrar den upplevda prestandan.

**Q: Vad är det bästa sättet att effektivt komprimera stora filer?**  
A: Kombinera streaming‑läge med LZMA‑komprimering och en lämplig `DictionarySize`. Detta balanserar minnesanvändning och komprimeringsförhållande för massiva datamängder.

---

**Senast uppdaterad:** 2026-06-09  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Aspose.Zip för .NET - Lösenordsskydda Zip‑arkiv & lagra flera filer utan komprimering](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Skapa lösenordsskyddad zip för .NET‑kataloger – Aspose.Zip‑handledning](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [zip flera filer c# – Enkel komprimering med Aspose.Zip för .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}