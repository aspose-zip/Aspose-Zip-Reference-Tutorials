---
date: 2025-11-29
description: Leer hoe u bestanden aan een tar‑archief kunt toevoegen en ze kunt comprimeren
  tot TarZ met Aspose.Zip voor .NET – een stapsgewijze gids voor efficiënte .NET‑bestandshandeling.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Bestanden toevoegen aan tar en comprimeren naar TarZ met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestanden toevoegen aan tar en comprimeren naar TarZ met Aspose.Zip for .NET

## Inleiding

Als je **bestanden moet toevoegen aan tar** en vervolgens het archief moet comprimeren naar het TarZ‑formaat, maakt Aspose.Zip for .NET het hele proces moeiteloos. In deze tutorial lopen we elke stap door — van het opzetten van je project tot het maken van een tar‑archief, bestanden toevoegen en uiteindelijk een gecomprimeerd .tar.z‑bestand opslaan. Aan het einde heb je een herbruikbare snippet die je in elke .NET‑applicatie kunt gebruiken.

## Snelle antwoorden
- **Welke bibliotheek behandelt het maken van tar?** Aspose.Zip for .NET  
- **Hoeveel regels code?** Ongeveer 15 regels (exclusief commentaar)  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Kan ik mappen comprimeren, niet alleen bestanden?** Ja – je kunt volledige mappen toevoegen met een lus.

## Wat is **bestanden toevoegen aan tar**?
Bestanden toevoegen aan een tar‑archief bundelt ze in één enkel, niet‑gecomprimeerd container dat de mapstructuur en bestandsmetadata behoudt. Tar is een klassiek Unix‑formaat en dient als basis voor veel compressieworkflows, inclusief het TarZ‑formaat dat in deze gids wordt gebruikt.

## Waarom bestanden toevoegen aan tar vóór compressie naar TarZ?
- **Portabiliteit** – Een tar‑archief werkt op verschillende platforms zonder zorgen over individuele bestandsafhandeling.  
- **Snelheid** – Het maken van de tar‑container is snel; de daaropvolgende Z‑compressie richt zich uitsluitend op het verkleinen van de grootte.  
- **Compatibiliteit** – Veel legacy‑tools verwachten een `.tar` voordat gzip‑achtige compressie wordt toegepast, wat precies is wat `.tar.z` levert.

## Voorvereisten

Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- **Aspose.Zip for .NET** geïnstalleerd. Download het van de officiële site [hier](https://releases.aspose.com/zip/net/).  
- Een map op je computer die de bestanden bevat die je wilt archiveren. Vervang het tijdelijke pad door je eigen map.

## Importeer namespaces

Voeg de benodigde `using`‑statements toe aan de bovenkant van je C#‑bestand:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Stapsgewijze handleiding

### Stap 1: Definieer je documentdirectory

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gebruik `Path.Combine` als je paden dynamisch moet opbouwen; het voorkomt ontbrekende pad‑scheidingstekens op verschillende besturingssystemen.

### Stap 2: Maak een Tar‑archief en voeg bestanden toe

#### 2.1: Maak de Tar‑archief‑instantie

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Voeg bestanden toe aan het archief  

Binnen het `using`‑blok, voeg elk bestand toe dat je wilt opnemen:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Je kunt `CreateEntry` herhalen voor zoveel bestanden als nodig, of door een map itereren om ze programmatisch toe te voegen.

#### 2.3: Sla het gecomprimeerde TarZ‑bestand op  

Na het toevoegen van alle items, comprimeer je het tar‑archief naar het `.tar.z`‑formaat:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Het resulterende `archive.tar.z`‑bestand zal zich bevinden in dezelfde map die je hebt opgegeven in `dataDir`.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet gevonden** | Verkeerd pad of ontbrekende bestandsextensie | Controleer of `dataDir` eindigt met een pad‑scheidingsteken en of de bestandsnamen correct zijn. |
| **Toegang geweigerd** | Onvoldoende rechten op de doelmap | Voer de applicatie uit met de juiste rechten of kies een schrijfbare map. |
| **Gecomprimeerd bestand is groter dan verwacht** | Originele bestanden zijn al gecomprimeerd (bijv. afbeeldingen, video’s) | TarZ werkt het beste op tekst‑ of logbestanden; overweeg al gecomprimeerde bestanden ongewijzigd te laten. |

## Veelgestelde vragen

**V: Kan ik volledige mappen comprimeren met Aspose.Zip for .NET?**  
A: Absoluut. Gebruik een `Directory.GetFiles`‑lus en roep `CreateEntry` aan voor elk bestand, waarbij je de relatieve paden behoudt.

**V: Is er een proefversie beschikbaar voor Aspose.Zip for .NET?**  
A: Ja, je kunt de mogelijkheden van Aspose.Zip for .NET verkennen door de gratis proefversie te downloaden [hier](https://releases.aspose.com/).

**V: Waar kan ik uitgebreide documentatie vinden voor Aspose.Zip for .NET?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/), met gedetailleerde inzichten in de functies en het gebruik van de bibliotheek.

**V: Hoe kan ik ondersteuning krijgen voor Aspose.Zip for .NET?**  
A: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) om hulp te zoeken, je ervaringen te delen en contact te maken met de community.

**V: Kan ik een tijdelijke licentie verkrijgen voor Aspose.Zip for .NET?**  
A: Ja, als je een tijdelijke licentie nodig hebt, kun je er een verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie

Je hebt nu geleerd hoe je **bestanden kunt toevoegen aan tar** en het resultaat kunt comprimeren naar een TarZ‑archief met Aspose.Zip for .NET. Deze aanpak levert een schoon, draagbaar pakket op dat eenvoudig kan worden overgebracht, opgeslagen of verder verwerkt. Voel je vrij om de code‑fragment aan te passen voor batch‑verwerking van mappen, te integreren in build‑pijplijnen, of te combineren met andere Aspose‑componenten voor uitgebreidere document‑workflows.

---

**Laatst bijgewerkt:** 2025-11-29  
**Getest met:** Aspose.Zip for .NET 24.11  
**Auteur:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}