---
date: 2025-12-01
description: Leer hoe u tar.lz‑bestanden kunt comprimeren in .NET met Aspose.Zip en
  eenvoudig een tar.lz‑archief kunt maken.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe tar.lz te comprimeren met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tar.lz te comprimeren met Aspose.Zip voor .NET

In moderne .NET-ontwikkeling kan het efficiënt verpakken van bestanden de implementatiegrootte en netwerktransfertijden aanzienlijk verbeteren. **Hoe tar.lz te comprimeren** is een veelvoorkomende eis wanneer u een lichtgewicht, LZ‑gecomprimeerd TAR‑archief nodig heeft. In deze tutorial lopen we een duidelijk, stap‑voor‑stap **tar.lz compressie‑voorbeeld** door met behulp van de Aspose.Zip‑bibliotheek, zodat u snel een tar.lz‑archief kunt maken in uw eigen toepassingen.

## Snelle antwoorden
- **What library should I use?** Aspose.Zip for .NET.  
- **How long does the implementation take?** Ongeveer 5‑10 minuten voor een basisvoorbeeld.  
- **Do I need a license?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I compress multiple files at once?** Ja – voeg gewoon meer items toe vóór het opslaan.

## Wat is tar.lz compressie?
`tar.lz` is een TAR‑archief dat gecomprimeerd is met het LZMA‑algoritme (vaak simpelweg **LZ** genoemd). Het combineert de eenvoud van het groeperen van bestanden in TAR met de hoge compressieverhouding van LZ, waardoor het ideaal is voor back‑upbestanden, pakketdistributie of elke situatie waarin bandbreedte belangrijk is.

## Waarom Aspose.Zip voor .NET gebruiken?
Aspose.Zip abstraheert de low‑level details van het maken van archieven, waardoor u een schone, object‑georiënteerde API krijgt. U krijgt:

* **Zero external dependencies** – pure .NET-implementatie.  
* **Cross‑platform support** – werkt op Windows, Linux en macOS.  
* **Built‑in LZ compression** – geen extra native tools nodig.  
* **Strong error handling** – uitzonderingen zijn beschrijvend, waardoor debugging makkelijker wordt.

## Vereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:

- **Aspose.Zip for .NET** bibliotheek – download deze van [hier](https://releases.aspose.com/zip/net/).  
- Een map die de bestanden bevat die u wilt archiveren. Het pad naar deze map wordt opgeslagen in de `dataDir` variabele (u stelt deze in stap 3).

## Namespaces importeren
Voeg de benodigde namespaces toe zodat de compiler weet waar de klassen die we gaan gebruiken zich bevinden.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hoe een tar.lz‑archief te maken – Stapsgewijze gids

### Stap 1: Eén bestand comprimeren
Het eerste voorbeeld toont het meest eenvoudige scenario – één bestand toevoegen aan een TAR‑archief en het vervolgens opslaan als een **tar.lz**‑bestand.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Uitleg**

- `new TarArchive()` maakt een lege TAR‑container.  
- `CreateEntry` voegt het bestand `alice29.txt` uit uw `dataDir` toe.  
- `SaveLzipped` schrijft het archief naar schijf en past LZ‑compressie toe, waardoor `archive.tar.lz` ontstaat.

### Stap 2: Meerdere bestanden in één archief comprimeren
Vaak moet u meerdere bestanden bundelen. Roep gewoon `CreateEntry` aan voor elk bestand vóór het opslaan.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Uitleg**

- De code volgt hetzelfde patroon als stap 1, maar voegt een tweede entry (`lcet10.txt`) toe.  
- U kunt `CreateEntry` zo vaak herhalen als nodig; de bibliotheek behandelt de interne TAR‑structuur automatisch.

### Stap 3: Uw documentdirectory opgeven
Vervang de placeholder door het daadwerkelijke pad waar uw bronbestanden zich bevinden. Dit pad wordt gebruikt door de bovenstaande voorbeelden.

```csharp
string dataDir = "Your Document Directory";
```

**Uitleg**

- Stel `dataDir` in op een volledig gekwalificeerd mappad, bijv. `@"C:\\MyFiles\\"`.  
- Het behouden van de directory in een variabele maakt de code herbruikbaar en makkelijker te onderhouden.

## Veelvoorkomende valkuilen & probleemoplossing
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| `FileNotFoundException` bij het uitvoeren van het voorbeeld | `dataDir` wijst naar een niet‑bestaande map of de bestandsnaam is verkeerd gespeld | Controleer het pad en de bestandsnamen; gebruik `Path.Combine` voor de veiligheid. |
| Uitvoerbestand is **0 KB** | `archive.SaveLzipped` werd aangeroepen voordat er entries waren toegevoegd | Zorg ervoor dat er minstens één `CreateEntry`‑aanroep voorafgaat aan `SaveLzipped`. |
| Compressie lijkt traag | Grote bestanden met de standaard buffer‑grootte | Overweeg om bestanden in stukken te verwerken of asynchrone I/O te gebruiken als prestaties cruciaal zijn. |

## Conclusie
U weet nu **hoe tar.lz** bestanden te comprimeren met Aspose.Zip voor .NET, of u nu met één document of een verzameling bestanden werkt. Dit **tar.lz compressie‑voorbeeld** toont een schone, productie‑klare manier om lichtgewicht archieven te maken die gemakkelijk kunnen worden overgedragen of opgeslagen.

## Veelgestelde vragen

**Q:** Kan ik bestanden van elke grootte comprimeren met Aspose.Zip voor .NET?  
**A:** Ja, de bibliotheek verwerkt zowel kleine als zeer grote bestanden; zorg er alleen voor dat u voldoende geheugen en schijfruimte heeft voor de tijdelijke TAR‑structuur.

**Q:** Is de code compatibel met de nieuwste Aspose.Zip‑release?  
**A:** Het voorbeeld is gericht op de huidige versie; houd het NuGet‑pakket altijd up‑to‑date voor bug‑fixes en nieuwe functies.

**Q:** Zijn er licentie‑overwegingen?  
**A:** Een commerciële licentie is vereist voor productiegebruik. Zie de licentie‑details op de [Aspose‑website](https://purchase.aspose.com/buy).

**Q:** Kan ik dit gebruiken in een commercieel project?  
**A:** Absoluut – zodra u een geldige licentie heeft, kunt u de bibliotheek in elke commerciële applicatie integreren.

**Q:** Waar kan ik hulp krijgen als ik problemen ondervind?  
**A:** Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor community‑ondersteuning en officiële assistentie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-01  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---