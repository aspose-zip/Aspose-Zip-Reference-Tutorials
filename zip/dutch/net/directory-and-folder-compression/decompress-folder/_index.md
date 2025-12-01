---
date: 2025-12-01
description: Leer hoe u een map comprimeert naar zip en een zip-bestand naar een map
  extraheert met Aspose.Zip voor .NET – een complete gids voor zip-compressie in .NET
  en het maken van zip-archieven in .NET.
language: nl
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Map comprimeren naar zip & decomprimeren – Aspose.Zip voor .NET
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Map comprimeren naar zip & decomprimeren – Aspose.Zip voor .NET

Als je een **compress directory to zip** moet uitvoeren en vervolgens dat archief wilt uitpakken in een .NET‑applicatie, ben je op de juiste plek. In deze tutorial lopen we het volledige proces door—beginnend met het maken van een zip‑archief, daarna laten we je een nette, stap‑voor‑stap unzip zien met Aspose.Zip voor .NET. Aan het einde heb je een herbruikbaar patroon voor zip‑compressie .NET‑projecten en een goed begrip van hoe je .NET‑stijl unzip uitvoert.

## Snelle antwoorden
- **Wat betekent “compress directory to zip”?** Het betekent dat de inhoud van een map wordt omgezet in één .zip‑bestand.  
- **Hoe pak ik een zip uit naar een map?** Gebruik de `Archive.ExtractToDirectory`‑methode zoals in de gids weergegeven.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework, .NET Core en .NET 5/6+ versies.  
- **Is een licentie vereist voor productie?** Ja, een commerciële Aspose.Zip‑licentie is nodig voor niet‑trial gebruik.  
- **Kan ik dit automatiseren in CI/CD‑pipelines?** Absoluut—voeg gewoon dezelfde code toe aan je buildscripts.

## Wat is “compress directory to zip”?
Het comprimeren van een map naar zip bundelt elk bestand en elke submap in één enkel gecomprimeerd archief. Dit verkleint de opslaggrootte, vereenvoudigt overdracht en is een standaardmethode om resources te verpakken voor implementatie.

## Waarom Aspose.Zip voor .NET gebruiken?
Aspose.Zip biedt een **pure‑managed** API die werkt zonder native afhankelijkheden, ondersteunt grote bestanden en levert high‑performance zip‑compressie .NET‑mogelijkheden. Het behandelt ook randgevallen zoals met wachtwoord beveiligde archieven en Unicode‑bestandsnamen direct uit de doos.

## Vereisten
- **Aspose.Zip for .NET** bibliotheek geïnstalleerd (download deze [hier](https://releases.aspose.com/zip/net/)).  
- Een map op schijf die je wilt archiveren – stel het pad in de `dataDir`‑variabele in.  
- .NET‑ontwikkelomgeving (Visual Studio, VS Code, of een andere IDE naar keuze).

## Namespaces importeren
First, bring the required namespaces into scope:

```csharp
using Aspose.Zip;
using System.IO;
```

## Stap 1: Map comprimeren naar zip
We maken een zip‑bestand aan vanuit de map die je later wilt uitpakken. De `CompressDirectory.Run()`‑helper doet het zware werk.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Het `CompressDirectory`‑voorbeeld verpakt elk bestand in `dataDir` naar `CompressDirectory_out.zip`. Voel je vrij om de uitvoerbestandsnaam aan te passen aan je naamgevingsconventies.

## Stap 2: Map uitpakken (Hoe .NET unzippen)

### Stap 2.1: Zip‑bestand openen
Open het gegenereerde archief met een `FileStream`. Dit maakt het bestand klaar voor lezen.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### Stap 2.2: Archive‑instantie maken
Instantieer het `Archive`‑object, dat de zip‑container vertegenwoordigt.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### Stap 2.3: Uitpakken naar map
Extract ten slotte de inhoud naar een nieuwe map. Dit is de **extract zip to directory** stap.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Gefeliciteerd! Je hebt met succes een **directory gecomprimeerd naar zip** en vervolgens de zip **naar een directory uitgepakt** met Aspose.Zip voor .NET. Deze aanpak garandeert gegevensintegriteit terwijl de code beknopt en leesbaar blijft.

## Veelvoorkomende problemen & oplossingen
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` bij uitpakken | Doelmap is alleen‑lezen of in gebruik | Zorg dat het bestemmingspad schrijfbaar is en niet vergrendeld |
| Lege uitvoermap na uitpakken | Verkeerd bron‑zip‑pad | Controleer dubbel `dataDir + "CompressDirectory_out.zip"` wijst naar het juiste bestand |
| Grote bestanden veroorzaken OutOfMemoryException | Standaard buffer‑grootte gebruiken bij zeer grote archieven | Gebruik `ArchiveOptions` om de buffer‑grootte te verhogen of stream bestanden in stukken |

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET gebruiken met elk type bestand?**  
A: Ja, Aspose.Zip ondersteunt alle bestandstypen—tekst, binair, afbeeldingen, PDF’s, wat je maar wilt.

**Q: Is Aspose.Zip geschikt voor grootschalige toepassingen?**  
A: Absoluut. Het is ontworpen voor high‑performance zip‑compressie .NET‑scenario’s en kan multi‑gigabyte archieven verwerken met een lage geheugengebruik.

**Q: Waar kan ik uitgebreide documentatie vinden voor Aspose.Zip voor .NET?**  
A: Bekijk de gedetailleerde documentatie [hier](https://reference.aspose.com/zip/net/).

**Q: Kan ik Aspose.Zip uitproberen voordat ik koop?**  
A: Ja, een gratis proefversie is beschikbaar op de [Aspose.Zip downloadpagina](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?**  
A: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor community‑hulp en officiële ondersteuning.

---

**Laatst bijgewerkt:** 2025-12-01  
**Getest met:** Aspose.Zip 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}