---
date: 2025-12-10
description: Leer hoe u bestanden zonder compressie kunt opslaan met Aspose.Zip voor
  .NET. Deze gids laat u zien hoe u een ongecomprimeerde zip maakt, bestanden opslaat
  in een zip en archieven efficiënt beheert.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe bestanden ongecomprimeerd opslaan met Aspose.Zip voor .NET
url: /nl/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe bestanden ongecomprimeerd opslaan met Aspose.Zip voor .NET

In moderne .NET-ontwikkeling kan **hoe bestanden op te slaan** efficiënt een groot verschil maken in prestaties en opslagkosten. Wanneer je bestanden exact ongewijzigd moet houden—zonder enige compressie—biedt Aspose.Zip voor .NET een schone, eenvoudige API. In deze tutorial lopen we de stappen door om een ongecomprimeerd ZIP‑archief te maken, bestanden naar ZIP op te slaan en de oplossing in je applicatie te integreren.

## Snelle antwoorden
- **Wat betekent “uncompressed zip”?** Het is een ZIP‑archief waarbij elk item wordt opgeslagen met de “store”‑methode, waardoor de oorspronkelijke bytes van het bestand onaangetast blijven.  
- **Waarom compressie vermijden?** Om het archiveren te versnellen, de oorspronkelijke bestandsgroottes te behouden voor verdere verwerking, of te voldoen aan regelgeving die gegevenswijziging verbiedt.  
- **Welke Aspose.Zip‑klasse regelt dit?** `ArchiveEntrySettings` gecombineerd met `StoreCompressionSettings`.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework, .NET Core, .NET 5/6/7 en later.

## Wat betekent het opslaan van meerdere bestanden zonder compressie?
Het opslaan van meerdere bestanden zonder compressie betekent dat elk bestand wordt toegevoegd aan een ZIP‑container met de *store*‑compressiemethode. De bestanden blijven byte‑voor‑byte identiek aan de originelen, wat ideaal is wanneer je snel wilt archiveren of de gegevens ongewijzigd moet houden.

## Waarom Aspose.Zip gebruiken voor ongecomprimeerde archieven?
- **Snelheid:** Er worden geen CPU‑intensieve compressie‑algoritmen uitgevoerd.  
- **Voorspelbare grootte:** De archiefgrootte is gelijk aan de som van de originele bestanden plus minimale ZIP‑overhead.  
- **Compatibiliteit:** Het resulterende ZIP‑bestand werkt met elke standaard unzip‑tool.  
- **Flexibiliteit:** Je kunt nog steeds gecomprimeerde en ongecomprimeerde items in hetzelfde archief combineren indien nodig.

## Voorvereisten
- **Aspose.Zip for .NET** – geïntegreerd in je project. Zie de officiële [documentatie](https://reference.aspose.com/zip/net/) voor installatiestappen.  
- **.NET‑ontwikkelomgeving** – Visual Studio, VS Code, of elke IDE die je verkiest.  
- **Documentdirectory** – een map op je computer met de bestanden die je wilt archiveren (bijv. “Your Document Directory”).

## Namespaces importeren
Voordat je code schrijft, importeer je de benodigde namespaces zodat de compiler weet waar de Aspose‑klassen zich bevinden.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Stap 1: Documentdirectory instellen
Definieer het pad waar je bronbestanden zich bevinden. Vervang de placeholder door de daadwerkelijke map op je systeem.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: ZIP‑archief maken zonder compressie
De kern van de tutorial – we maken een `Archive`‑instantie geconfigureerd met `StoreCompressionSettings`. Dit vertelt Aspose.Zip om elk item te *store* (d.w.z. niet te comprimeren).

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Pro tip:** Als je **bestanden naar zip wilt opslaan** terwijl je sommige comprimeert en andere ongecomprimeerd laat, maak dan aparte `ArchiveEntrySettings`‑instanties voor elk bestand en voeg ze toe aan dezelfde `Archive`.

## Veelvoorkomende problemen en oplossingen
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Bestand niet gevonden** | Onjuist `dataDir`‑pad of ontbrekende bestandsextensie. | Controleer het pad en zorg dat de bestanden bestaan. Gebruik `Path.Combine` voor veiligere samenvoeging. |
| **Toegang geweigerd** | Het proces heeft geen toestemming om de bronbestanden te lezen of de ZIP te schrijven. | Voer de applicatie uit met de juiste rechten of kies een map met schrijfrechten. |
| **Onverwachte bestandsgrootte in ZIP** | Het archief is gemaakt met standaardcompressie. | Zorg ervoor dat `new StoreCompressionSettings()` wordt doorgegeven aan `ArchiveEntrySettings`. |

## Veelgestelde vragen

**Q: Kan ik specifieke bestandstypen comprimeren terwijl ik andere ongecomprimeerd opsla?**  
A: Ja, je kunt verschillende `ArchiveEntrySettings` voor elk bestand maken en gecomprimeerde en ongecomprimeerde items in hetzelfde archief combineren.

**Q: Is Aspose.Zip for .NET compatibel met .NET Core en .NET 5/6?**  
A: Absoluut. De bibliotheek ondersteunt .NET Framework, .NET Core, .NET Standard en de nieuwste .NET‑versies.

**Q: Hoe moet ik uitzonderingen afhandelen tijdens het archiveringsproces?**  
A: Plaats de archiveringscode in een `try‑catch`‑blok en log de details van de uitzondering. Dit zorgt voor een nette foutafhandeling en makkelijker debuggen.

**Q: Ondersteunt Aspose.Zip multi‑threaded archiveren?**  
A: Ja, je kunt meerdere bestanden parallel verwerken en aan het archief toevoegen, maar onthoud dat het `Archive`‑object zelf niet thread‑safe is; synchroniseer de toegang bij het toevoegen van items.

**Q: Kan ik Aspose.Zip integreren in een bestaand project zonder grote code‑wijzigingen?**  
A: Zeker. De API is ontworpen voor eenvoudige drop‑in gebruik. Raadpleeg de officiële [documentatie](https://reference.aspose.com/zip/net/) voor migratie‑advies.

---

**Laatst bijgewerkt:** 2025-12-10  
**Getest met:** Aspose.Zip for .NET 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}