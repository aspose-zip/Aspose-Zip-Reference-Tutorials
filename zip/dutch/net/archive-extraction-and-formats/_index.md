---
date: 2026-06-19
description: Leer hoe u Tar Files comprimeert, targz archives maakt en wachtwoord-beveiligde
  zip files extraheert met Aspose.Zip voor .NET – waardoor opslag efficiëntie en beveiliging
  worden verbeterd.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Archive Extraction en Formats
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe Tar Files comprimeren met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tar‑bestanden comprimeren met Aspose.Zip voor .NET

## Introductie

In deze gids ontdek je **hoe tar te comprimeren** bestanden met Aspose.Zip voor .NET, leer je TarGz‑archieven te maken, en zie je hoe je zip‑archieven met wachtwoordbeveiliging kunt uitpakken. Efficiënt archiefbeheer is een kernvaardigheid voor moderne .NET‑ontwikkelaars—of je nu een back‑upservice, een cloud‑storage‑client, of een gegevensverwerkings‑pipeline bouwt, het beheersen van deze formaten verlaagt opslagkosten, versnelt overdrachten en houdt gevoelige gegevens veilig.

## Snelle antwoorden
- **Wat is TarBz2?** Een gecomprimeerd archief dat TAR‑verpakking combineert met BZIP2‑compressie voor hoge compressieverhoudingen.  
- **Waarom Aspose.Zip voor .NET kiezen?** Het biedt een enkele, vloeiende API voor het maken en uitpakken van veel archiefformaten zonder externe afhankelijkheden.  
- **Kan ik een TarGz‑archief maken?** Ja – Aspose.Zip ondersteunt TarGz, TarLz, TarXz, TarZ en meer.  
- **Hoe pak ik een zip‑archief met wachtwoordbeveiliging uit?** Gebruik de `Password`‑eigenschap op het `ArchiveEntry`‑object bij het uitpakken.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar voor evaluatie.

## Wat is Tar‑compressie?
Tar (Tape Archive) is een containerformaat dat meerdere bestanden en mappen bundelt in één stroom zonder compressie. Wanneer je een compressie‑algoritme zoals BZIP2, GZip, LZMA of XZ toepast, is het resultaat een **tar‑gebaseerd archief** zoals `.tar.bz2`, `.tar.gz`, `.tar.lz`, enz. Deze formaten worden breed ondersteund op Linux, macOS en Windows, waardoor ze ideaal zijn voor cross‑platform gegevensuitwisseling.

## Waarom Aspose.Zip voor .NET gebruiken om deze formaten te verwerken?
Aspose.Zip biedt een **geïntegreerde, afhankelijkheidsvrije API** die meer dan 50 archief‑ en compressieformaten ondersteunt, inclusief TarBz2, TarGz, TarLz, TarXz en TarZ. Het draait op Windows, Linux en macOS, en de op streams gebaseerde architectuur houdt het geheugenverbruik onder 10 MB, zelfs voor archieven van enkele honderden megabytes. Wachtwoordbeveiliging is ingebouwd, waardoor per‑item encryptie mogelijk is zonder extra bibliotheken.

## Voorvereisten
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, of .NET 5–10.  
- Aspose.Zip for .NET NuGet‑pakket geïnstalleerd (`Install-Package Aspose.Zip`).  
- Basiskennis van C# bestands‑I/O en het .NET‑project‑systeem.

## Stapsgewijze handleiding

### Hoe tar‑bestanden comprimeren – Direct antwoord
`Archive` vertegenwoordigt een archiefbestand en biedt methoden om items toe te voegen en op te slaan.  
Maak een `Archive`‑instantie, voeg de bestanden toe die je wilt bundelen, stel `CompressionType.BZip2` in, en roep `Save` aan met `ArchiveFormat.TarBz2`. De bibliotheek schrijft de TAR‑container en comprimeert deze in één enkele streaming‑passage, zodat je nooit het volledige archief in het geheugen laadt.

### Stap 1: Kies het gewenste archiefformaat
Decide which tar‑based format best matches your compression‑speed trade‑off:

- **TarBz2** – Hoogste compressieverhouding (≈30 % kleiner dan TarGz) maar langzamer.  
- **TarGz** – Goede balans tussen snelheid en grootte; ideaal voor de meeste cloud‑storage‑scenario's.  
- **TarLz / TarXz** – Zeer hoge compressie met matige snelheid, nuttig voor archiefopslag.  
- **TarZ** – Legacy‑formaat voor compatibiliteit met oudere Unix‑tools.

### Stap 2: Maak een nieuwe `Archive`‑instantie
`Archive` is het object op het hoogste niveau dat een enkel archiefbestand in het geheugen vertegenwoordigt.  

De `Archive`‑klasse beheert de inpak‑ en compressieworkflow en biedt methoden om items toe te voegen en het uiteindelijke bestand te schrijven.

### Stap 3: Voeg bestanden en mappen toe
Je kunt een volledige mapstructuur toevoegen met `AddAll` of individuele bestanden met `AddFile`. Het behouden van de oorspronkelijke maphiërarchie is zo eenvoudig als het doorgeven van het basispad van de map.

### Stap 4: Stel het gewenste compressietype in
`CompressionType` somt de ondersteunde algoritmen op.  

`CompressionType` definieert het algoritme (BZip2, GZip, LZMA, XZ, enz.) dat tijdens het opslaan op de TAR‑stroom wordt toegepast.

### Stap 5: Sla het archief op
`ArchiveFormat` is een enum‑set (bijv. `TarBz2`, `TarGz`) die de schrijver vertelt welke container en compressie te gebruiken.  

Het aanroepen van `Save` schrijft het archief naar schijf met het geselecteerde formaat.

### Stap 6: Archieven uitpakken met wachtwoorden
`ArchiveEntry` vertegenwoordigt een enkel bestand‑ of map‑item binnen een archief.  

Om een zip‑archief met wachtwoordbeveiliging uit te pakken, open je het archief, zoek je elke `ArchiveEntry`, wijs je de `Password`‑eigenschap toe, en roep je `Extract` aan. Dit per‑item‑wachtwoordmodel stelt je in staat individuele bestanden binnen één zip te beveiligen.

### Stap 7: Verifieer het resultaat
Na het uitpakken, vergelijk je bestandsgroottes en SHA‑256‑controlesommen om te bevestigen dat de archief‑ronde‑trip de gegevensintegriteit heeft behouden.

## Veelvoorkomende gebruikssituaties
- **Backup‑hulpmiddelen** – Sla dagelijkse back‑ups op als `.tar.bz2` om opslagkosten tot 30 % te verlagen.  
- **Cross‑platform gegevensuitwisseling** – Tar‑gebaseerde formaten worden natively begrepen door Linux-, macOS- en Windows‑tools.  
- **Veilige distributie** – Ken wachtwoorden toe aan gevoelige items, waardoor aan compliance‑eisen wordt voldaan zonder extra encryptietools.

## Problemen oplossen & Tips
- **Grote archieven** – Geef de voorkeur aan de streaming‑API (`Archive.CreateEntryFromFile`) om het geheugenverbruik laag te houden.  
- **Wachtwoord‑mismatch** – Het wachtwoord dat op elke `ArchiveEntry` is ingesteld, moet exact overeenkomen; anders wordt `InvalidPasswordException` gegooid.  
- **Compressieniveau** – BZIP2 biedt geen aangepaste niveaus; als je fijnere controle nodig hebt, schakel dan over naar LZMA (`CompressionType.LZMA`) of XZ (`CompressionType.XZ`).  

## Veelgestelde vragen

**Q: Hoe maak ik een TarGz‑archief?**  
A: Stel `CompressionType.GZip` in en gebruik `ArchiveFormat.TarGz` bij het aanroepen van `Save`. Dit produceert een `.tar.gz`‑bestand in één stap.

**Q: Kan ik een archief met wachtwoordbeveiliging uitpakken zonder het wachtwoord te kennen?**  
A: Nee. Elk item moet worden voorzien van het juiste wachtwoord; anders mislukt het uitpakken met een `InvalidPasswordException`.

**Q: Ondersteunt Aspose.Zip het uitpakken van archieven met verschillende wachtwoorden per item?**  
A: Ja. Ken een wachtwoord toe aan elke `ArchiveEntry` afzonderlijk voordat je `Extract` aanroept.

**Q: Welk formaat biedt de beste compressie?**  
A: TarBz2 levert doorgaans de kleinste grootte, gevolgd door TarLz en TarXz. TarGz biedt een snellere, nog steeds effectieve alternatieve.

**Q: Is er een limiet aan het aantal bestanden dat ik aan een TAR‑archief kan toevoegen?**  
A: Praktisch gezien geen, maar zeer grote archieven (>10 GB) kunnen baat hebben bij het splitsen in meerdere delen voor gemakkelijker beheer.

## Archief‑uitpakken en formaten‑tutorials
### [Bestanden comprimeren naar TarBz2 met Aspose.Zip voor .NET](./compress-to-tar-bz2/)
Leer hoe je bestanden naar het TarBz2‑formaat comprimeert in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte bestandscompressie.  
### [Comprimeren naar TarGz met Aspose.Zip voor .NET](./compress-to-tar-gz/)
Ontdek efficiënte bestandscompressie in .NET met Aspose.Zip. Comprimeer moeiteloos naar TarGz.  
### [Comprimeren naar TarLz met Aspose.Zip voor .NET](./compress-to-tar-lz/)
Comprimeer moeiteloos bestanden in .NET met Aspose.Zip. Leer stap‑voor‑stap TarLz‑archieven te maken.  
### [Comprimeren naar TarXz met Aspose.Zip voor .NET](./compress-to-tar-xz/)
Leer hoe je bestanden naar het TarXz‑formaat comprimeert in .NET met Aspose.Zip. Volg onze gids voor efficiënte opslag en verzending.  
### [Comprimeren naar TarZ met Aspose.Zip voor .NET](./compress-to-tar-z/)
Ontdek stapsgewijze compressie naar TarZ met Aspose.Zip voor .NET. Efficiënte bestandsafhandeling voor je .NET‑projecten.  
### [Archief‑items uitpakken met verschillende wachtwoorden in Aspose.Zip voor .NET](./extract-archive-different-passwords/)
Leer hoe je archief‑items met verschillende wachtwoorden uitpakt in Aspose.Zip voor .NET. Verhoog de beveiliging en flexibiliteit in je applicaties.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Gerelateerde tutorials

- [Tar‑archief maken en bestanden toevoegen aan tar met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hoe tar comprimeren en TarBz2 maken met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Bestanden toevoegen aan tar en tarxz‑archief maken met Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}