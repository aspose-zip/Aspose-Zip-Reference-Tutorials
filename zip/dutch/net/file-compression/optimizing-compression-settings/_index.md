---
date: 2026-06-09
description: Leer hoe u een wachtwoord toevoegt aan zip en LZMA-ziparchieven maakt
  met Aspose.Zip voor .NET. Deze tutorial behandelt Bzip2, LZMA (woordenboekgrootte),
  PPMd, Enhanced Deflate, Store-compressie en ASP.NET-bestandscompressie van grote
  bestanden.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Compressie-instellingen optimaliseren
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
title: Wachtwoord toevoegen aan zip en LZMA-archief maken met Aspose.Zip voor .NET
url: /nl/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wachtwoord toevoegen aan zip en LZMA-archief maken met Aspose.Zip voor .NET

In moderne .NET-toepassingen kan **add password to zip** tijdens het maken van een high‑ratio LZMA-zip-archief gevoelige gegevens beschermen en toch de best mogelijke compressie bieden. Of je nu een ASP.NET-bestandscompressieservice bouwt, een desktop-hulpmiddel dat multi‑gigabyte bestanden verwerkt, of een cloud‑gebaseerde workflow, deze tutorial leidt je stap voor stap door het beveiligen en comprimeren van je bestanden met Aspose.Zip voor .NET.

## Snelle antwoorden
- **Wat is het belangrijkste voordeel van LZMA-compressie?** Hoogste compressieverhouding met redelijke snelheid voor de meeste bestandstypen.  
- **Welke methode slaat bestanden op zonder compressie?** Store compressie (ook wel “store compression zip” genoemd).  
- **Kan ik deze instellingen gebruiken in een ASP.NET-toepassing?** Ja—verwijs simpelweg naar Aspose.Zip in je project en roep dezelfde API aan.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10.

## Wat is “add password to zip” in Aspose.Zip?
**Het toevoegen van een zip-wachtwoord versleutelt elke entry in een ZIP-archief zodat alleen gebruikers die het wachtwoord kennen de bestanden kunnen uitpakken.** Aspose.Zip ondersteunt zowel traditionele ZipCrypto-encryptie als AES-encryptie (128, 192 of 256‑bit). Encryptie-instellingen worden opgegeven als het tweede argument van `ArchiveEntrySettings` bij het construeren van een `Archive`; er is geen aparte `SetPassword`-methode.

## Waarom Aspose.Zip gebruiken voor .NET-bestandscompressie?
Aspose.Zip biedt een enkele, consistente API die veel algoritmen dekt en tegelijkertijd hoge prestaties en laag geheugenverbruik levert. Het stelt ontwikkelaars in staat om de beste compressiemethode voor elk scenario te kiezen en encryptie in één stap toe te passen, waardoor code wordt vereenvoudigd en onderhoudsbelasting wordt verminderd.

- **Unified API** – Eén consistente interface voor Bzip2, LZMA, PPMd, Enhanced Deflate en Store.  
- **Performance‑tuned** – Geoptimaliseerde native implementatie verwerkt **bestanden tot 10 GB** zonder het volledige bestand in het geheugen te laden.  
- **ASP.NET friendly** – Werkt naadloos in webprojecten, achtergrondservices en Azure Functions.  
- **Fine‑grained control** – Pas dictionary-grootte, compressieniveau en encryptie aan met één constructor‑aanroep.  
- **Supports 10+ compression algorithms** – dekt de meest voorkomende use‑cases in enterprise data pipelines.

## Vereisten
- **Aspose.Zip for .NET Library** – Download en installeer vanaf de [Aspose documentation](https://reference.aspose.com/zip/net/).  
- **Sample Text File** – Bereid een voorbeeldbestand voor (bijv. `sample.txt`) dat je gaat comprimeren.  
- **.NET development environment** – Visual Studio 2022 of een compatibele IDE.  

## Namespaces importeren

De `Archive`, `ArchiveEntrySettings` en encryptie‑klassen bevinden zich in de `Aspose.Zip` namespace. Importeer ze bovenaan je bestand:

- `Archive` vertegenwoordigt een ZIP-archiefcontainer.  
- `ArchiveEntrySettings` bevat compressie‑ en encryptie‑opties voor elke entry.  
- Encryptie‑klassen (bijv. `AesEncryptionSettings`) definiëren hoe gegevens worden versleuteld.

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

Laten we nu elke compressie‑instelling verkennen en zien hoe we **add password to zip** waar nodig kunnen toepassen.

## Bzip2-compressie-instellingen gebruiken

### Stap 1: Bzip2-compressie initialiseren met traditionele encryptie

`Bzip2CompressionSettings` configureert het Bzip2-algoritme (block‑size, etc.).  
`TraditionalEncryptionSettings` past legacy ZipCrypto‑encryptie toe op een entry.

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

*Wachtwoordbeveiliging wordt toegepast via `TraditionalEncryptionSettings` die direct aan `ArchiveEntrySettings` wordt doorgegeven.*

## Hoe wachtwoord toevoegen aan zip met Aspose.Zip voor .NET

Laad je bronbestand, maak een `Archive` met de entry‑instellingen, en voeg het bestand toe aan het archief. De encryptie wordt automatisch toegepast omdat deze werd opgegeven toen de `ArchiveEntrySettings`‑instantie werd gecreëerd.

**Direct answer (40‑70 words):**  
Maak een `ArchiveEntrySettings`‑object dat zowel de gewenste compressie‑instellingen als `TraditionalEncryptionSettings` of `AesEncryptionSettings` bevat. Geef dit object vervolgens door aan de `Archive`‑constructor en voeg bestanden toe met `AddEntry`. Het archief wordt geschreven met het wachtwoord al ingebed, dus er is geen extra stap nodig na het aanmaken.

`ArchiveEntrySettings` is de configuratie‑houder die Aspose.Zip vertelt hoe elke entry moet worden gecomprimeerd en versleuteld.  

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

## Hoe een LZMA-zip-archief maken met Aspose.Zip

### Stap 1: LZMA-compressie initialiseren met AES256-encryptie

`LzmaCompressionSettings` regelt LZMA‑specifieke parameters zoals dictionary‑grootte en fast bytes.  
`AesEncryptionSettings` biedt AES‑256‑encryptie voor de archief‑entries.

**Direct answer (40‑70 words):**  
Instantieer `LzmaCompressionSettings` met een gekozen `DictionarySize`, maak een `AesEncryptionSettings`‑object met je wachtwoord en `EncryptionMethod.AES256`, en bouw vervolgens een `ArchiveEntrySettings` uit beide. Geef dit door aan de `Archive`‑constructor en voeg je bestanden toe; het resulterende zip‑archief wordt LZMA‑gecomprimeerd en AES‑beveiligd in één bewerking.

`LzmaCompressionSettings` is de klasse die LZMA‑specifieke parameters zoals dictionary‑grootte en fast bytes regelt.  

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

> **Tip:** LZMA biedt een configureerbare **LZMA dictionary size** die zowel compressieverhouding als geheugenverbruik beïnvloedt. Je kunt deze instellen via `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` als je zeer grote bestanden fijn moet afstemmen.

## PPMd-compressie-instellingen gebruiken

### Stap 1: PPMd-compressie initialiseren met AES256-encryptie

`PpmdCompressionSettings` definieert de order en het geheugenverbruik voor het PPMd-algoritme.  
`AesEncryptionSettings` biedt AES‑256‑encryptie voor de archief‑entries.

**Direct answer (40‑70 words):**  
Maak een `PpmdCompressionSettings`‑instantie, combineer deze met een `AesEncryptionSettings`‑object dat je wachtwoord bevat, en geef beide door aan `ArchiveEntrySettings`. Gebruik dit instellingenobject bij het construeren van de `Archive`; het resulterende zip‑archief wordt PPMd‑gecomprimeerd en wachtwoordbeveiligd zonder extra aanroepen.

`PpmdCompressionSettings` definieert de order en het geheugenverbruik voor het PPMd-algoritme.  

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

## Enhanced Deflate-compressie-instellingen gebruiken

### Stap 1: Enhanced Deflate-compressie initialiseren met AES256-encryptie

`EnhancedDeflateCompressionSettings` laat je een compressieniveau specificeren dat snelheid en grootte in balans brengt.  
`AesEncryptionSettings` biedt AES‑256‑encryptie voor de archief‑entries.

**Direct answer (40‑70 words):**  
Instantieer `EnhancedDeflateCompressionSettings` met je gewenste niveau (0‑9), combineer dit met `AesEncryptionSettings`, en wikkel ze in `ArchiveEntrySettings`. Geef dit door aan de `Archive`‑constructor en voeg bestanden toe; het archief wordt aangemaakt met Enhanced Deflate-compressie en AES‑256‑wachtwoordbeveiliging in één stap.

`EnhancedDeflateCompressionSettings` laat je een compressieniveau specificeren dat snelheid en grootte in balans brengt.  

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

## Store-compressie-instellingen gebruiken (store compression zip)

### Stap 1: Store-compressie initialiseren met traditionele encryptie

`StoreCompressionSettings` vertelt Aspose.Zip om compressie volledig over te slaan, waardoor het bronbestand byte‑voor‑byte behouden blijft.  
`TraditionalEncryptionSettings` past legacy ZipCrypto‑encryptie toe.

**Direct answer (40‑70 words):**  
Maak een `StoreCompressionSettings`‑instantie (die geen compressie uitvoert), combineer deze met `TraditionalEncryptionSettings` die je wachtwoord bevat, en wikkel beide in `ArchiveEntrySettings`. Geef dit door aan de `Archive`‑constructor; het resulterende zip‑archief bevat het originele bestand oncomprimeerd maar wel wachtwoordbeveiligd.

`StoreCompressionSettings` vertelt Aspose.Zip om compressie volledig over te slaan, waardoor het bronbestand byte‑voor‑byte behouden blijft.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro tip:** Pas de `dataDir`‑variabele aan zodat deze naar je werkelijke werkmap wijst, en hergebruik dezelfde `Archive`‑instantie als je meerdere bestanden aan één archief wilt toevoegen.

## Veelvoorkomende problemen & oplossingen
- **"File not found"-fouten** – Controleer of `dataDir` eindigt met een pad‑scheidingsteken (`\` of `/`) en dat `sample.txt` bestaat.  
- **Geheugengebruik bij grote bestanden** – Gebruik `ArchiveEntrySettings` om streaming‑modus in te schakelen, waardoor data direct naar de output‑stream wordt geschreven.  
- **Incompatibel compressieniveau** – Sommige algoritmen (bijv. LZMA) bieden extra eigenschappen zoals `DictionarySize`. Raadpleeg de API‑documentatie voor fijnere controle.  
- **Wachtwoord niet toegepast** – Zorg ervoor dat het encryptie‑instellingenobject als tweede argument aan `ArchiveEntrySettings` wordt doorgegeven bij de constructie, niet na het aanmaken van het archief.  

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET gebruiken met andere compressiebibliotheken?**  
A: Aspose.Zip is ontworpen om te werken met zijn ingebouwde algoritmen. Integratie van externe bibliotheken is mogelijk, maar vereist aangepaste afhandeling buiten de Aspose API.

**Q: Hoe kan ik wachtwoordbeveiliging toevoegen aan een zip die met Aspose.Zip is gemaakt?**  
A: Geef of `TraditionalEncryptionSettings` of `AesEncryptionSettings` als tweede argument aan `ArchiveEntrySettings` door bij het construeren van de `Archive`. Zie de [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) voor volledige voorbeelden.

**Q: Is er een proefversie die ik kan testen?**  
A: Ja, je kunt de proefversie benaderen [hier](https://releases.aspose.com/).

**Q: Waar kan ik community‑ondersteuning krijgen of vragen stellen?**  
A: Voor ondersteuning en community‑discussies, bezoek het [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: Kan ik een tijdelijke licentie voor evaluatie verkrijgen?**  
A: Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Hoe helpt dit bij ASP.NET-bestandscompressie?**  
A: Door dezelfde API vanuit een ASP.NET‑controller of middleware aan te roepen, kun je bestanden on‑the‑fly comprimeren voordat ze naar de client worden gestuurd, waardoor bandbreedte wordt bespaard en de waargenomen prestaties verbeteren.

**Q: Wat is de beste manier om grote bestanden efficiënt te comprimeren?**  
A: Combineer streaming‑modus met LZMA‑compressie en een geschikte `DictionarySize`. Dit balanceert geheugenverbruik en compressieverhouding voor enorme datasets.

**Laatst bijgewerkt:** 2026-06-09  
**Getest met:** Aspose.Zip 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Zip voor .NET - Zip-archief beveiligen met wachtwoord & meerdere bestanden opslaan zonder compressie](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Wachtwoordbeveiligde zip maken voor .NET-mappen – Aspose.Zip Tutorial](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [Meerdere bestanden zippen c# – Eenvoudige compressie met Aspose.Zip voor .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}