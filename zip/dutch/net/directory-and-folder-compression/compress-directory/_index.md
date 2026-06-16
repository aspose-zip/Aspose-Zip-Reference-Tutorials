---
date: 2026-05-30
description: Leer hoe u een map zippt met Aspose.Zip voor .NET, maak zip-archieven
  efficiënt en bespaar opslagruimte in uw .NET-toepassingen.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Hoe een map zippen
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map zippen met Aspose.Zip voor .NET
url: /nl/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een map zippen met Aspose.Zip voor .NET

In deze tutorial ontdek je **hoe je een map zipt** snel en betrouwbaar met Aspose.Zip voor .NET. Of je nu een desktop‑hulpmiddel, een cloud‑gebaseerde service of een geautomatiseerd back‑up script bouwt, het comprimeren van een map naar een ZIP‑archief kan de opslagvereisten drastisch verkleinen en netwerkoverdrachten versnellen. We lopen elke stap door, leggen uit waarom elke regel belangrijk is, en wijzen op veelvoorkomende valkuilen zodat je de techniek met vertrouwen kunt toepassen.

## Snelle antwoorden
- **Wat doet Aspose.Zip?** Het biedt een eenvoudige .NET API voor het maken en uitpakken van ZIP‑archieven zonder externe afhankelijkheden.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een eenvoudige mapcompressie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, en .NET 5‑10.  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik meerdere mappen tegelijk comprimeren?** Absoluut—gebruik de `CreateEntries`‑methode op elke `DirectoryInfo`‑collectie om **meerdere mappen te zippen** in één enkele uitvoering.  

`CreateEntries` voegt alle bestanden uit een map toe aan het archief.

## Wat betekent “hoe een map zippen”?

Een map comprimeren betekent dat je elk bestand en elke sub‑map in een opgegeven directory neemt en deze verpakt in één enkel ZIP‑archief. Dit verkleint de totale grootte, behoudt de oorspronkelijke hiërarchie en maakt het gemakkelijker om de gegevens over te dragen of op te slaan. Het resulterende ZIP‑bestand kan op elk platform worden geopend zonder speciale software, en het behoudt de mapstructuur zodat bij het uitpakken de oorspronkelijke indeling exact wordt hersteld.

## Waarom Aspose.Zip voor deze taak gebruiken?

Aspose.Zip stelt je in staat om **zip‑archief**‑bestanden direct vanuit .NET‑code te **maken** met een consistente API voor alle ondersteunde runtimes. Laad de `Archive`‑klasse, voeg items toe, stel `CompressionLevel` in, wijs eventueel een wachtwoord toe, en roep `Save` aan. De bibliotheek verwerkt mappen met duizenden bestanden in minder dan een seconde op standaard hardware, en ondersteunt meer dan 50 verschillende compressieformaten en encryptie‑algoritmen.

## Vereisten

- **Aspose.Zip for .NET** – download het [hier](https://releases.aspose.com/zip/net/) of [hier](https://releases.aspose.com/zip/net).  
- **Ontwikkelomgeving** – Visual Studio, Rider, of elke IDE die C# ondersteunt.  
- **Documentdirectory** – vervang `"Your Document Directory"` in de code door het pad naar de map die je wilt comprimeren.  
- **Referentiedocumentatie** – raadpleeg de officiële docs [hier](https://reference.aspose.com/zip/net/).

## Namespaces importeren

Begin met het importeren van de benodigde namespaces. Deze geven je toegang tot de kerncompressie‑klassen.

```csharp
using Aspose.Zip;
using System.IO;
```

## Hoe een map zippen met Aspose.Zip

Hieronder staat een eenvoudig voorbeeld dat **hoe je een map zipt** inhoud laat zien. Hetzelfde patroon kan worden uitgebreid naar **meerdere bestanden zippen .net** of om aangepaste archiefstructuren te maken.

### Stap 1: Initialiseert je documentdirectory

Stel de variabele `dataDir` in op het pad van de map die je wilt comprimeren.

```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Maak uitvoer‑ZIP‑bestanden

Open twee `FileStream`‑objecten voor de uitvoer‑ZIP‑bestanden. Dit laat zien hoe je meer dan één archief kunt genereren vanuit dezelfde bron—handig voor versie‑back‑ups.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Stap 3: De map comprimeren

De `Archive`‑klasse vertegenwoordigt een ZIP‑archief en biedt methoden om items toe te voegen en het bestand op te slaan. Gebruik deze om elk item uit de doelmap toe te voegen. Het voorbeeld gebruikt een voorbeeldmap met de naam **CanterburyCorpus**, maar je kunt naar elke directory wijzen.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Pro tip:** Als je een **zip‑archief .net** met een specifiek compressieniveau moet **maken**, stel dan `archive.CompressionLevel` in voordat je `Save` aanroept.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|---------|--------------|-----|
| Leeg ZIP‑bestand | `dataDir` wijst naar de verkeerde map of er ontbreekt een slash aan het einde | Controleer het pad en zorg ervoor dat de map bestanden bevat |
| `UnauthorizedAccessException` | Applicatie heeft geen bestandsysteem‑rechten | Voer Visual Studio uit als administrator of geef lees‑/schrijfrechten |
| Groot geheugenverbruik voor enorme mappen | Alle items in één keer in het geheugen laden | Gebruik `Archive.CreateEntryFromFile` in een lus om bestanden afzonderlijk te streamen |

## Veelgestelde vragen (extra)

**V: Kan ik een wachtwoord toevoegen aan het ZIP‑archief?**  
A: Ja. Stel `archive.Password = "yourPassword";` in voordat je `Save` aanroept.

**V: Hoe neem ik alleen bepaalde bestandstypen op?**  
A: Filter de `DirectoryInfo`‑collectie met `GetFiles("*.txt")` of iets dergelijks voordat je `CreateEntries` aanroept.

**V: Is er een manier om een bestaand ZIP‑archief bij te werken zonder het opnieuw te maken?**  
A: Aspose.Zip ondersteunt incrementele updates via `Archive.UpdateEntry`.

## Veelgestelde vragen

### V1: Kan ik Aspose.Zip voor .NET gebruiken in zowel commerciële als persoonlijke projecten?

A1: Ja, Aspose.Zip voor .NET is gelicentieerd voor zowel commercieel als persoonlijk gebruik.

### V2: Is er een gratis proefversie beschikbaar?

A2: Ja, je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/zip/net).

### V3: Hoe krijg ik ondersteuning voor Aspose.Zip voor .NET?

A3: Bezoek het [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) voor community‑ondersteuning of overweeg het aanschaffen van een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor toegewijde hulp.

### V4: Zijn er andere voorbeelden en tutorials beschikbaar?

A4: Ja, de [documentatie](https://reference.aspose.com/zip/net/) bevat uitgebreide voorbeelden en tutorials.

### V5: Kan ik Aspose.Zip voor .NET aanschaffen?

A5: Zeker, je kunt een aankoop doen [hier](https://purchase.aspose.com/buy).

## Conclusie

Je hebt nu een volledig, productie‑klaar patroon voor **hoe je een map zipt** met Aspose.Zip voor .NET. Door gebruik te maken van de `Archive`‑klasse van de bibliotheek, kun je **zip‑archief**‑bestanden **maken**, een aangepast `CompressionLevel` instellen, wachtwoordbeveiliging toevoegen, en zelfs **meerdere mappen in één keer zippen**—ideaal voor het automatiseren van map‑back‑up taken. Experimenteer met de API om encryptie toe te voegen, archieven te splitsen, of direct naar cloud‑opslag te streamen, en je hebt een robuuste oplossing voor elke .NET‑gebaseerde compressiebehoefte.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [zip meerdere bestanden c# – moeiteloze compressie met Aspose.Zip voor .NET](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip voor .NET - ZIP‑archief beveiligen met wachtwoord & meerdere bestanden opslaan zonder compressie](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Hoe een map zippen – map comprimeren met Aspose.Zip](/zip/net/directory-and-folder-compression/decompress-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}