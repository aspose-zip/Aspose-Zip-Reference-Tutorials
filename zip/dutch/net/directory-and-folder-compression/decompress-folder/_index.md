---
date: 2026-04-09
description: Leer hoe u een map comprimeert naar een zip‑bestand en een zip‑bestand
  uitpakt naar een map met Aspose.Zip voor .NET. Deze gids behandelt het programmatic
  maken van zip‑mappen en het verwerken van zip‑archieven in .NET.
keywords:
- compress directory to zip
- zip folder programmatically
- extract zip to directory
- extract zip archive .net
linktitle: Map uitpakken
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map zippen – Map comprimeren met Aspose.Zip
url: /nl/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een map zippen – Directory comprimeren met Aspose.Zip voor .NET

Als je op zoek bent naar een duidelijke **compress directory to zip**‑oplossing in een .NET‑applicatie, ben je hier op de juiste plek. In deze tutorial lopen we het volledige werkproces door—eerst **compress directory to zip**, daarna laten we je de exacte stappen zien om **extract zip to directory** uit te voeren (ook wel hoe je een map unzippt). Aan het einde heb je een herbruikbaar, programmatisch patroon voor zip‑map‑bewerkingen dat werkt op .NET Framework, .NET Core en .NET 5/6+.

## Snelle antwoorden
- **Wat betekent “compress directory to zip”?** Het betekent dat de inhoud van een map wordt omgezet in één .zip‑bestand.  
- **Hoe extraheer ik zip naar directory?** Gebruik de `Archive.ExtractToDirectory`‑methode zoals in de gids weergegeven.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework-, .NET Core- en .NET 5/6+-versies.  
- **Is een licentie vereist voor productie?** Ja, een commerciële Aspose.Zip‑licentie is nodig voor niet‑trial gebruik.  
- **Kan ik dit automatiseren in CI/CD‑pipelines?** Absoluut—voeg gewoon dezelfde code toe aan je buildscripts.

## Wat is “compress directory to zip”?
**Compress directory to zip** betekent simpelweg dat elk bestand en elke submap in een directory worden genomen en in één enkel gecomprimeerd archief worden verpakt. Dit verkleint de opslaggrootte, versnelt overdrachten en creëert een draagbaar pakket voor implementatie.

## Waarom Aspose.Zip voor .NET gebruiken?
Aspose.Zip biedt een **pure‑managed** API die geen native DLL’s vereist, ondersteunt enorme archieven en handelt randgevallen af zoals **zip‑archief wachtwoordbeveiliging** en Unicode‑bestandsnamen automatisch. Het is bovendien geoptimaliseerd voor prestaties, waardoor het ideaal is wanneer je een map programmatically moet zippen in scenario’s met hoge doorvoer.

## Vereisten
- **Aspose.Zip for .NET** bibliotheek geïnstalleerd (download het [hier](https://releases.aspose.com/zip/net/)).  
- Een map op schijf die je wilt archiveren – stel het pad in de `dataDir`‑variabele in.  
- .NET‑ontwikkelomgeving (Visual Studio, VS Code of een andere IDE naar keuze).

## Namespaces importeren
Eerst de benodigde namespaces in scope brengen:

```csharp
using Aspose.Zip;
using System.IO;
```

## compress directory to zip – Stapsgewijze handleiding

### Stap 1: Map programmatically zippen
We maken een zip‑bestand aan van de directory die je later wilt decomprimeren. De helper `CompressDirectory.Run()` doet het zware werk.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Het `CompressDirectory`‑voorbeeld verpakt elk bestand in `dataDir` in `CompressDirectory_out.zip`. Voel je vrij om de uitvoerbestandsnaam te hernoemen volgens je eigen naamgevingsconventies.

### Stap 2: zip naar directory extraheren – Hoe map te unzippen in .NET

#### Stap 2.1: Open het zip‑bestand
Open het gegenereerde archief met een `FileStream`. Dit maakt het bestand klaar voor lezen.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Stap 2.2: Maak een Archive‑instantie
Instantieer het `Archive`‑object, dat de zip‑container vertegenwoordigt.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Stap 2.3: zip‑archief extraheren .net
Trek tenslotte de inhoud naar een nieuwe map. Dit is de **extract zip to directory**‑stap.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Waarom dit belangrijk is
- **Consistentie:** Het gebruik van dezelfde bibliotheek voor zowel comprimeren als extraheren garandeert compatibele archiefformaten.  
- **Prestaties:** Aspose.Zip streamt data efficiënt, zodat zelfs multi‑gigabyte‑archieven met een lage geheugendruk worden verwerkt.  
- **Beveiliging:** Ingebouwde ondersteuning voor wachtwoordbeveiliging betekent dat je het zip‑archief kunt beveiligen zonder extra code.

## Veelvoorkomende gebruikssituaties
- **Geautomatiseerde back-ups** – zip elke nacht een log‑map en sla deze op in cloudopslag.  
- **Implementatiepakketten** – bundel statische web‑assets voordat je ze naar een server publiceert.  
- **Gegevensuitwisseling** – stuur een verzameling bestanden tussen services als één enkel archief.

## Veelvoorkomende problemen & oplossingen
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` bij het extraheren | Doelmap is alleen‑lezen of in gebruik | Zorg dat het bestemmingspad schrijfbaar is en niet vergrendeld |
| Lege uitvoermap na extractie | Verkeerd bron‑zip‑pad | Controleer dat `dataDir + "CompressDirectory_out.zip"` naar het juiste bestand wijst |
| Grote bestanden veroorzaken OutOfMemoryException | Standaard buffer‑grootte gebruiken bij zeer grote archieven | Gebruik `ArchiveOptions` om de buffer‑grootte te verhogen of stream bestanden in delen |

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET met elk type bestand gebruiken?**  
A: Ja, Aspose.Zip ondersteunt alle bestandstypen—tekst, binair, afbeeldingen, PDF’s, wat je maar wilt.

**Q: Is Aspose.Zip geschikt voor grootschalige applicaties?**  
A: Absoluut. Het is ontworpen voor high‑performance zip‑compressie‑scenario’s in .NET, en verwerkt multi‑gigabyte‑archieven met een lage geheugendruk.

**Q: Waar vind ik uitgebreide documentatie voor Aspose.Zip voor .NET?**  
A: Bekijk de gedetailleerde docs [hier](https://reference.aspose.com/zip/net/).

**Q: Kan ik Aspose.Zip eerst uitproberen voordat ik het koop?**  
A: Ja, een gratis proefversie is beschikbaar op de [Aspose.Zip downloadpagina](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?**  
A: Bezoek het [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) voor community‑hulp en officiële ondersteuning.

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}