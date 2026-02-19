---
date: 2026-02-07
description: Leer hoe je een map zipt in .NET door een directory te comprimeren naar
  een zip‑bestand en deze weer uit te pakken. Deze gids laat zien hoe je een map zipt
  met Aspose.Zip voor .NET.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map zippen – Directory comprimeren met Aspose.Zip
url: /nl/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Map zippen - Map comprimeren met Aspose.Zip voor .NET

Als je op zoek bent naar een duidelijke **how to zip folder**‑oplossing in een .NET‑applicatie, ben je hier op de juiste plek. In deze tutorial lopen we het volledige proces door—eerst **map comprimeren naar zip**, daarna laten we je de exacte stappen zien om **zip uitpakken naar map** uit te voeren (ook wel hoe je de map uitpakt genoemd). Aan het einde heb je een herbruikbaar, programmatisch patroon voor zip‑folder‑bewerkingen dat werkt op .NET Framework, .NET Core en .NET5/6+.

## Snelle antwoorden
- **Wat betekent “directory comprimeren naar zip”?** Het betekent de inhoud van een kaart omzetten naar één.zip‑bestand.
- **Hoe extraheer ik een zip naar een kaart?** Gebruik de `Archive.ExtractToDirectory`‑methode zoals in de gids wordt getoond.
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework, .NET Core en .NET5/6+ versies.
- **Is een licentie vereist voor productie?** Ja, een logische Aspose.Zip‑licentie is nodig voor gebruik buiten de proefversie.
- **Kan ik dit automatiseren in CI/CD‑pipelines?** Absoluut – voeg dezelfde code toe aan je build‑scripts.

## Wat is "map zippen"?
**Hoe een map te zippen** betekent dat je elk bestand en elke submap binnen een map pakt en dit in één samengeperst archief stopt. Dit verkleinde de opslaggrootte, snelle overdracht en onmogelijk een draagbaar pakket voor implementatie.

## Waarom Aspose.Zip gebruiken voor .NET?
Aspose.Zip biedt een **puur beheerde** API die geen native DLL’s vereist, ondersteunt enorme archieven, en handelt randgevallen af ​​zoals **zip-archiefwachtwoordbeveiliging** en Unicode-bestandsnamen automatisch. Het is horizontaal identiek voor prestaties, waardoor het ideaal is wanneer je zip‑folder‑bewerkingen programmatisch moet uitvoeren in scenario’s met hoge doorvoer.

## Vereisten
- **Aspose.Zip voor .NET**‑bibliotheek vereist (download [hier](https://releases.aspose.com/zip/net/)).
- Een kaart op de schijf die je wilt archiveren – stel het pad in de `dataDir`‑variabele in.
- .NET‑ontwikkelomgeving (Visual Studio, VSCode of een andere IDE naar keuze).

## Naamruimten importeren
Importeer eerst de naamruimten:

```csharp
using Aspose.Zip;
using System.IO;
```

## Stap-voor-stap handleiding

### Stap 1: Directory comprimeren naar Zip (zip-map programmatisch)
We maken een zip‑bestand van de directory die je later wilt uitpakken. De helper `CompressDirectory.Run()` doet het zware werk.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Het `CompressDirectory`‑voorbeeld pakt elk bestand in `dataDir` en stopt het in `CompressDirectory_out.zip`. Hernoem het uitvoerbestand gerust naar uw naamgevingsconventies.

### Stap 2: Decomprimeer de map – Hoe de map uit te pakken in .NET

#### Stap 2.1: Open het zipbestand
Open het vervaardigde archief met een `FileStream`. Dit maakt het bestand klaar om te lezen.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Stap 2.2: Archiefinstantie maken
Instantieer het `Archive`-object, dat de zip-container vertegenwoordigt.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Stap 2.3: Uitpakken naar map
Trek tenslotte de inhoud uit naar een nieuwe kaart. Dit is de **zip uitpakken naar map**‑stap.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Waarom dit ertoe doet
- **Consistentie:** Het gebruik van dezelfde bibliotheek voor zowel comprimeren als uitpakken identieke compatibele archiefformaten.
- **Prestaties:** Aspose.Zip streamt gegevens efficiënt, zodat zelfs archieven van meerdere gigabytes met een lage geheugendruk kunnen worden verwerkt.
- **Beveiliging:** verbetering ondersteuning voor wachtwoordbeveiliging betekent dat je het zip-archief kunt gebruiken zonder extra code.

## Veelvoorkomende gebruiksscenario's
- **Geautomatiseerde back-ups** – zip elke nacht een log‑map en sla deze op in cloud‑opslag.
- **Implementatiepakketten** – bundel statische web‑assets voordat je naar een server publiceert.
- **Gegevensuitwisseling** – stuur een verzameling bestanden tussen services als één enkel archief.

## Veelvoorkomende problemen en oplossingen
| Symptoom | Waarschijnlijke oorzaak | Repareren |
|---------|--------------|-----|
| `UnauthorizedAccessException` bij het uitpakken | Doelmap is alleen‑lezen of in gebruik | Zorg ervoor dat het bestemmingspad schrijfbaar is en niet beveiligd |
| Lege uitvoermap na uitpakken | Verkeerd bron‑zip‑pad | Controleer of `dataDir + "CompressDirectory_out.zip"` naar het juiste bestand wijst |
| Grote bestanden die OutOfMemoryException veroorzaken | Standaard buffer‑grootte wordt gebruikt bij zeer grote archieven | Gebruik `ArchiveOptions` om de buffer stukken‑grootte te verhogen van streambestanden in |

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET met elk type bestand gebruiken?**
A: Ja, Aspose.Zip ondersteunt alle bestandstypen—tekst, binair, afbeeldingen, PDF’s, wat je maar wilt.

**Vraag: Is Aspose.Zip geschikt voor variabele applicaties?**
A: Absoluut. Het is ontworpen voor krachtige zip-compressie.NET-scenario’s en kan multi-gigabyte archieven verwerken met een lage geheugendruk.

**Q: Waar vind ik uitgebreide documentatie voor Aspose.Zip voor .NET?**
A: Bekijk de gedetailleerde documenten [hier](https://reference.aspose.com/zip/net/).

**Q: Kan ik Aspose.Zip eerst uitproberen voordat ik koop?**
A: Ja, er is een gratis proefversie beschikbaar op de [Aspose.Zip downloadpagina](https://releases.aspose.com/).

**V: Hoe krijg ik ondersteuning voor Aspose.Zip voor .NET?**
A: Bezoek het [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) voor community‑hulp en officiële assistentie.

---

**Laatst bijgewerkt:** 2026-02-07
**Getest met:** Aspose.Zip 24.11 voor .NET
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}