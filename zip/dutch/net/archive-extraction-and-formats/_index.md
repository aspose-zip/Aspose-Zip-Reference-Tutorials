---
date: 2026-10-25
description: Leer hoe u het zip-wachtwoord kunt extraheren en het compressie-algoritme
  kunt instellen bij het comprimeren van tar-bestanden met Aspose.Zip voor .NET, waardoor
  de opslag efficiëntie en beveiliging worden verhoogd.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Archiefextractie en -formaten
og_description: Leer hoe u het zip-wachtwoord kunt extraheren en het compressie-algoritme
  kunt instellen bij het comprimeren van tar-bestanden met Aspose.Zip voor .NET, waardoor
  de opslag efficiëntie en beveiliging worden verhoogd.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Zip-wachtwoord extraheren en tar-bestanden comprimeren met Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Zip-wachtwoord extraheren en tar-bestanden comprimeren met Aspose.Zip
url: /nl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zip-wachtwoord extraheren en tar-bestanden comprimeren met Aspose.Zip

## Inleiding

In deze gids ontdek je **extract zip password**-technieken, leer je hoe je een compressie‑algoritme instelt bij het maken van tar‑gebaseerde archieven, en zie je hoe je TarGz, TarBz2 en andere formaten bouwt met Aspose.Zip voor .NET. Of je nu een back‑upservice, een cloud‑storage‑client of een data‑verwerkings‑pipeline bouwt, het beheersen van deze bewerkingen verlaagt de opslagkosten, versnelt overdrachten en beveiligt gevoelige bestanden.

## Snelle antwoorden
- **Wat is TarBz2?** Een gecomprimeerd archief dat TAR-verpakking combineert met BZIP2-compressie voor hoge compressieverhoudingen.  
- **Waarom kiezen voor Aspose.Zip voor .NET?** Het ondersteunt meer dan 50 archief‑ en compressieformaten, draait op Windows, Linux en macOS, en houdt het geheugenverbruik onder 10 MB voor archieven van meerdere honderden megabytes.  
- **Kan ik een TarGz‑archief maken?** Ja – Aspose.Zip biedt TarGz, TarLz, TarXz, TarZ en meer.  
- **Hoe extraheer ik een met wachtwoord beveiligd zip‑archief?** Stel de `Password`‑eigenschap in op elke `ArchiveEntry` voordat je `Extract` aanroept.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar voor evaluatie.

## Wat is tar-compressie?

Tar-compressie combineert de TAR‑container met een compressie‑algoritme zoals BZIP2, GZIP, LZMA of XZ. Het resultaat is één bestand (bijv. `.tar.gz`, `.tar.bz2`) dat kan worden uitgepakt op Linux, macOS en Windows. Het behoudt de oorspronkelijke maphiërarchie, maakt willekeurige‑toegangsextractie mogelijk, en wordt breed ondersteund door command‑line‑tools en programmeerbibliotheken, waardoor het ideaal is voor cross‑platform distributie en archiefopslag.

## Waarom Aspose.Zip voor .NET gebruiken om deze formaten te verwerken?

Aspose.Zip biedt een eenduidige, afhankelijkheids‑vrije API die **50+** archief‑ en compressieformaten ondersteunt, inclusief alle belangrijke tar‑gebaseerde types. De streaming‑architectuur verwerkt archieven groter dan 10 GB terwijl het RAM‑gebruik onder 10 MB blijft, waardoor het ideaal is voor high‑throughput server‑workloads.  

**Direct answer:** Je gebruikt Aspose.Zip omdat het je in staat stelt tar‑gebaseerde archieven en met wachtwoord beveiligde zip‑bestanden te maken, comprimeren en extraheren met één vloeiende API, zonder externe tools, terwijl je multi‑gigabyte archieven verwerkt in een geheugen‑efficiënte streaming‑modus.

## Vereisten
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, of .NET 5–10.  
- Aspose.Zip for .NET NuGet‑pakket (`Install-Package Aspose.Zip`).  
- Basiskennis van C# bestands‑I/O en het .NET‑project‑systeem.

## Stapsgewijze handleiding

### Hoe tar‑bestanden comprimeren – direct antwoord
Maak een `Archive`‑instantie, voeg de bestanden toe die je wilt bundelen, stel `CompressionType.BZip2` (of een ander algoritme) in, en roep `Save` aan met `ArchiveFormat.TarBz2`. De bibliotheek schrijft de TAR‑container en comprimeert deze in één streaming‑pass, zodat je nooit het volledige archief in het geheugen laadt.

### Stap 1: Kies het gewenste archiefformaat
Decide which tar‑based format best matches your compression‑speed trade‑off:

- **TarBz2** – Hoogste compressieverhouding (≈30 % kleiner dan TarGz) maar trager.  
- **TarGz** – Goede balans tussen snelheid en grootte; ideaal voor de meeste cloud‑storage‑scenario's.  
- **TarLz / TarXz** – Zeer hoge compressie met matige snelheid, nuttig voor archiefopslag.  
- **TarZ** – Legacy‑formaat voor compatibiliteit met oudere Unix‑tools.

### Stap 2: Maak een nieuwe `Archive`‑instantie
`Archive` vertegenwoordigt één archiefbestand en biedt methoden om items toe te voegen en het archief op te slaan.  

De `Archive`‑klasse beheert de verpakkings‑ en compressieworkflow, en stelt methoden beschikbaar om items toe te voegen en het uiteindelijke bestand te schrijven.

### Stap 3: Voeg bestanden en mappen toe
Je kunt een volledige mapboom toevoegen met `AddAll` of individuele bestanden met `AddFile`.  

`AddAll` voegt een volledige mapboom toe aan het archief, waarbij de structuur behouden blijft.  
`AddFile` voegt één enkel bestand toe aan het archief. Het behouden van de oorspronkelijke maphiërarchie is zo eenvoudig als het doorgeven van het basismap‑pad.

### Stap 4: Stel het gewenste compressietype in
`CompressionType`‑enum geeft het compressie‑algoritme aan dat op de TAR‑stroom wordt toegepast.  

`CompressionType` somt de ondersteunde algoritmen op (BZip2, GZip, LZMA, XZ, enz.) die tijdens het opslaan worden toegepast.

### Stap 5: Sla het archief op
`ArchiveFormat`‑enum selecteert de container‑ en compressiecombinatie voor het uitvoerbestand.  

Het aanroepen van `Save` schrijft het archief naar schijf met het geselecteerde formaat.

### Stap 6: Archieven extraheren met wachtwoorden
`ArchiveEntry` vertegenwoordigt één bestand‑ of map‑item binnen een archief.  

Om een met wachtwoord beveiligde zip te extraheren, open je het archief, zoek je elke `ArchiveEntry`, wijs je de `Password`‑eigenschap toe, en roep je `Extract` aan. De `Password`‑eigenschap stelt het decryptiewachtwoord in voor een zip‑item. Dit per‑item‑wachtwoordmodel stelt je in staat individuele bestanden binnen één zip te beveiligen.

### Stap 7: Verifieer het resultaat
Na het extraheren, vergelijk je bestandsgroottes en SHA‑256‑controlesommen om te bevestigen dat de archief‑ronde‑trip de gegevensintegriteit heeft behouden.

## Veelvoorkomende gebruikssituaties
- **Backup‑hulpmiddelen** – Sla dagelijkse back-ups op als `.tar.bz2` om de opslagkosten tot 30 % te verlagen.  
- **Cross‑platform gegevensuitwisseling** – Tar‑gebaseerde formaten worden van nature begrepen door Linux-, macOS- en Windows‑tools.  
- **Beveiligde distributie** – Wijs wachtwoorden toe aan gevoelige items, waardoor aan compliance‑eisen wordt voldaan zonder extra encryptietools.

## Probleemoplossing & tips
- **Grote archieven** – Gebruik de streaming‑API (`Archive.CreateEntryFromFile`) om het geheugenverbruik laag te houden.  
- **Wachtwoord‑mismatches** – Het wachtwoord dat op elke `ArchiveEntry` is ingesteld moet exact overeenkomen; anders wordt `InvalidPasswordException` gegooid.  
- **Compressieniveau** – BZIP2 biedt geen aangepaste niveaus; als je fijnere controle nodig hebt, schakel dan over naar LZMA (`CompressionType.LZMA`) of XZ (`CompressionType.XZ`).  

## Veelgestelde vragen

**Q: Hoe maak ik een TarGz‑archief?**  
A: Stel `CompressionType.GZip` in en gebruik `ArchiveFormat.TarGz` bij het aanroepen van `Save`. Dit produceert een `.tar.gz`‑bestand in één stap.

**Q: Kan ik een met wachtwoord beveiligd archief extraheren zonder het wachtwoord te kennen?**  
A: Nee. Elke entry moet worden voorzien van het juiste wachtwoord; anders mislukt de extractie met een `InvalidPasswordException`.

**Q: Ondersteunt Aspose.Zip het extraheren van archieven met verschillende wachtwoorden per entry?**  
A: Ja. Wijs elk `ArchiveEntry` afzonderlijk een wachtwoord toe voordat je `Extract` aanroept.

**Q: Welk formaat levert de beste compressie?**  
A: TarBz2 levert doorgaans de kleinste grootte, gevolgd door TarLz en TarXz. TarGz biedt een snellere, nog steeds effectieve alternatieve.

**Q: Is er een limiet aan het aantal bestanden dat ik kan toevoegen aan een TAR‑archief?**  
A: Praktisch gezien geen, maar extreem grote archieven (>10 GB) kunnen profiteren van opsplitsen in meerdere delen voor gemakkelijker beheer.

## Archiefextractie en format‑tutorials
### [Bestanden comprimeren naar TarBz2 met Aspose.Zip voor .NET](./compress-to-tar-bz2/)
Leer hoe je bestanden comprimeert naar het TarBz2‑formaat in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte bestandscompressie.  
### [Comprimeren naar TarGz met Aspose.Zip voor .NET](./compress-to-tar-gz/)
Ontdek efficiënte bestandscompressie in .NET met Aspose.Zip. Comprimeer moeiteloos naar TarGz.  
### [Comprimeren naar TarLz met Aspose.Zip voor .NET](./compress-to-tar-lz/)
Comprimeer moeiteloos bestanden in .NET met Aspose.Zip. Leer stap‑voor‑stap TarLz‑archieven te maken.  
### [Comprimeren naar TarXz met Aspose.Zip voor .NET](./compress-to-tar-xz/)
Leer bestanden te comprimeren naar het TarXz‑formaat in .NET met Aspose.Zip. Volg onze gids voor efficiënte opslag en transmissie.  
### [Comprimeren naar TarZ met Aspose.Zip voor .NET](./compress-to-tar-z/)
Ontdek stapsgewijze compressie naar TarZ met Aspose.Zip voor .NET. Efficiënte bestandsafhandeling voor je .NET‑projecten.  
### [Archiefitems extraheren met verschillende wachtwoorden in Aspose.Zip voor .NET](./extract-archive-different-passwords/)
Leer hoe je archiefitems met verschillende wachtwoorden kunt extraheren in Aspose.Zip voor .NET. Verhoog de beveiliging en flexibiliteit in je applicaties.

## Gerelateerde tutorials

- [Maak tar‑archief en voeg bestanden toe aan tar met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hoe tar comprimeren en TarBz2 maken met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Bestanden toevoegen aan tar en tarxz‑archief maken met Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Laatst bijgewerkt:** 2026-10-25  
**Getest met:** Aspose.Zip for .NET 24.11  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}