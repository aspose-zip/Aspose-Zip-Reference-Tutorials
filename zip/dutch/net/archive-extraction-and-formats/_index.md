---
date: 2026-01-28
description: Leer hoe u een archief met wachtwoord kunt uitpakken, bestanden kunt
  comprimeren naar TarBz2 en TarGz-archieven kunt maken met Aspose.Zip voor .NET.
  Verhoog de opslag efficiëntie en beveiliging.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Archief uitpakken met wachtwoord en comprimeren naar TarBz2 (.NET)
url: /nl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Archief uitpakken met wachtwoord en comprimeren naar TarBz2 (.NET)

In deze gids ontdek je **hoe je een archief met wachtwoord kunt uitpakken** en beheer je ook **bestanden comprimeren naar TarBz2** met Aspose.Zip voor .NET. Of je nu een back‑upservice, een cloud‑storage client, of een data‑verwerkingspipeline bouwt, deze technieken laten je opslagruimte verkleinen, overdrachten versnellen en gevoelige gegevens beschermd houden.

## Snelle antwoorden
- **What is TarBz2?** Een gecomprimeerd archief dat TAR-verpakking combineert met BZIP2-compressie voor hoge compressieverhoudingen.  
- **Why choose Aspose.Zip for .NET?** Het biedt een enkele, vloeiende API voor vele archiefformaten zonder native afhankelijkheden.  
- **Can I create a TarGz archive?** Ja – Aspose.Zip ondersteunt TarGz, TarLz, TarXz, TarZ en meer.  
- **How do I extract a password‑protected archive?** Stel de `Password`‑eigenschap in op elke `ArchiveEntry` vóór het uitpakken.  
- **Do I need a license for production use?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar voor evaluatie.

## Hoe een archief met wachtwoord uit te pakken met Aspose.Zip voor .NET
Het uitpakken van een archief dat **password protect zip archive** beschermd is, is eenvoudig. Je opent het archief, zoekt de gewenste entry, wijst het wachtwoord toe, en roept vervolgens `Extract` aan. Deze aanpak werkt voor TarBz2, TarGz en andere ondersteunde formaten.

## Wat betekent “compress files to TarBz2” eigenlijk?
Bestanden comprimeren naar TarBz2 betekent eerst meerdere bestanden en mappen bundelen in één **TAR**‑container en vervolgens **BZIP2**‑compressie toepassen. Het resultaat is een `.tar.bz2`‑bestand dat zowel gemakkelijk te transporteren als sterk gecomprimeerd is.

## Waarom Aspose.Zip voor .NET gebruiken om deze formaten te verwerken?
- **Unified API** – Eén bibliotheek, vele formaten (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Werkt direct op Windows, Linux en macOS.  
- **Password support** – Beveilig en pak archieven veilig uit met per‑entry wachtwoorden.  
- **Performance‑focused** – Stream‑gebaseerde verwerking minimaliseert geheugengebruik.

## Vereisten
- .NET 6.0 of later (of .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip for .NET NuGet‑pakket geïnstalleerd (`Install-Package Aspose.Zip`).  
- Basiskennis van C# en bestands‑I/O.

## Stapsgewijze handleiding

### Stap 1: Kies het archiefformaat dat je nodig hebt
Bepaal of **TarBz2**, **TarGz**, **TarLz**, **TarXz**, of **TarZ** het beste past bij je compressieverhouding en compatibiliteitseisen.  
- **TarBz2** – Beste compressie, langzamere verwerking.  
- **TarGz** – Goede balans tussen snelheid en grootte (dekt het secundaire trefwoord *compress files to targz*).  
- **TarZ** – Legacy‑formaat voor oudere Unix‑tools.

### Stap 2: Maak een nieuwe `Archive`‑instantie
Instantieer de `Archive`‑klasse en wijs deze naar het uitvoer‑bestandspad. Dit object beheert het inpakken en comprimeren.

### Stap 3: Voeg bestanden en mappen toe
Gebruik de `AddAll`‑ of `AddFile`‑methoden om de bestanden die je wilt comprimeren toe te voegen. Behoud de mapstructuur door een basismap toe te voegen.

### Stap 4: Stel het gewenste compressietype in
Geef het compressie‑algoritme op (`CompressionType.BZip2`, `CompressionType.GZip`, enz.) bij het opslaan van het archief. Hier **compress files to tarbz2** je daadwerkelijk of een ander formaat.

### Stap 5: Sla het archief op
Roep `Save` aan met de juiste format‑enum (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, enz.). De bibliotheek schrijft de TAR‑container en past de gekozen compressie in één stap toe.

### Stap 6: Archieven uitpakken met wachtwoorden
Als je **archive‑entries met verschillende wachtwoorden** moet uitpakken (secundair trefwoord *how to extract password protected archive*), open dan het archief, zoek elke entry, wijs het wachtwoord toe en pak vervolgens uit.

### Stap 7: Controleer het resultaat
Na het uitpakken, vergelijk bestandsgroottes en controlesommen om te bevestigen dat het archief correct is aangemaakt en uitgepakt.

## Veelvoorkomende gebruikssituaties
- **Backup utilities** – Sla dagelijkse back‑ups op als `.tar.bz2` om opslagkosten te minimaliseren.  
- **Cross‑platform data exchange** – Tar‑gebaseerde formaten worden universeel begrepen op Linux, macOS en Windows.  
- **Secure distribution** – Bescherm individuele entries met wachtwoorden voor compliance‑gedreven omgevingen.

## Problemen oplossen & Tips
- **Large archives** – Gebruik streaming‑API’s (`Archive.CreateEntryFromFile`) om te voorkomen dat volledige bestanden in het geheugen worden geladen.  
- **Password mismatches** – Zorg ervoor dat het wachtwoord dat op elke `ArchiveEntry` is ingesteld overeenkomt met het wachtwoord dat tijdens het uitpakken wordt gebruikt; anders krijg je een `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 ondersteunt geen aangepaste compressieniveaus; als je fijnere controle nodig hebt, overweeg dan TarLz of TarXz.  
- **Performance tip** – Bij het maken van een **create tarbz2 archive**, schakel buffering in op de onderliggende stream om de schrijfsnelheid te verbeteren.

## Veelgestelde vragen

**Q: Hoe maak ik een TarGz‑archief?**  
A: Stel het compressietype in op `CompressionType.GZip` en het formaat op `ArchiveFormat.TarGz` bij het aanroepen van `Save`.

**Q: Kan ik een wachtwoord‑beveiligd archief uitpakken zonder het wachtwoord te kennen?**  
A: Nee. Elke entry moet worden voorzien van het juiste wachtwoord; anders mislukt het uitpakken.

**Q: Ondersteunt Aspose.Zip het uitpakken van archieven met verschillende wachtwoorden per entry?**  
A: Ja. Je kunt elk `ArchiveEntry` afzonderlijk een wachtwoord toewijzen vóór het uitpakken.

**Q: Welk formaat biedt de beste compressie?**  
A: TarBz2 levert doorgaans de hoogste compressieverhouding, gevolgd door TarLz en TarXz. TarGz biedt een goede balans tussen snelheid en grootte.

**Q: Is er een limiet aan het aantal bestanden dat ik aan een TAR‑archief kan toevoegen?**  
A: Praktisch gezien niet, maar zeer grote archieven kunnen baat hebben bij het splitsen in meerdere delen voor gemakkelijker beheer.

## Archiefuitpak- en Formaat‑handleidingen
### [Bestanden comprimeren naar TarBz2 met Aspose.Zip voor .NET](./compress-to-tar-bz2/)
Leer hoe je bestanden naar TarBz2‑formaat kunt comprimeren in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte bestandscompressie.
### [Comprimeren naar TarGz met Aspose.Zip voor .NET](./compress-to-tar-gz/)
Ontdek efficiënte bestandscompressie in .NET met Aspose.Zip. Comprimeer moeiteloos naar TarGz.
### [Comprimeren naar TarLz met Aspose.Zip voor .NET](./compress-to-tar-lz/)
Moeiteloos bestanden comprimeren in .NET met Aspose.Zip. Leer stap‑voor‑stap TarLz‑archieven te maken.
### [Comprimeren naar TarXz met Aspose.Zip voor .NET](./compress-to-tar-xz/)
Leer hoe je bestanden naar TarXz‑formaat kunt comprimeren in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte opslag en transmissie.
### [Comprimeren naar TarZ met Aspose.Zip voor .NET](./compress-to-tar-z/)
Ontdek stap‑voor‑stap compressie naar TarZ met Aspose.Zip voor .NET. Efficiënte bestandsafhandeling voor je .NET‑projecten.
### [Archief‑entries uitpakken met verschillende wachtwoorden in Aspose.Zip voor .NET](./extract-archive-different-passwords/)
Leer hoe je archief‑entries met verschillende wachtwoorden kunt uitpakken in Aspose.Zip voor .NET. Verhoog de beveiliging en flexibiliteit in je applicaties.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-28  
**Getest met:** Aspose.Zip for .NET 24.11  
**Auteur:** Aspose  

---