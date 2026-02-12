---
date: 2026-02-12
description: Leer hoe u een map kunt zippen met Aspose.Zip voor .NET, maak zip‑archieven
  efficiënt in .NET en verklein de opslagruimte in uw .NET‑toepassingen.
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map zippen met Aspose.Zip voor .NET
url: /nl/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een map zippen met Aspose.Zip voor .NET

In deze tutorial ontdek je **hoe een map zippen** snel en betrouwbaar met Aspose.Zip voor .NET. Of je nu een desktop‑utility, een cloud‑gebaseerde service of een geautomatiseerd back‑up‑script bouwt, het comprimeren van een map naar een ZIP‑archief kan de opslagbehoefte drastisch verkleinen en netwerk‑overdrachten versnellen. We lopen elke stap door, leggen uit waarom elke regel belangrijk is, en wijzen op veelvoorkomende valkuilen zodat je de techniek met vertrouwen kunt toepassen.

## Snelle antwoorden
- **Wat doet Aspose.Zip?** Het biedt een eenvoudige .NET API voor het maken en uitpakken van ZIP‑archieven zonder externe afhankelijkheden.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een basismapcompressie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6+.  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik meerdere mappen tegelijk comprimeren?** Absoluut—gebruik de `CreateEntries`‑methode op een `DirectoryInfo`‑collectie om **meerdere mappen te zippen** in één uitvoering.

## Wat is “hoe een map zippen”?

Een map comprimeren betekent dat je elk bestand en elke submap in een opgegeven directory neemt en deze verpakt in één ZIP‑archief. Dit verkleint de totale grootte, behoudt de oorspronkelijke hiërarchie en maakt het gemakkelijker om de gegevens te verplaatsen of op te slaan.

## Waarom Aspose.Zip voor deze taak gebruiken?

- **Snelheid & efficiëntie:** Geoptimaliseerde algoritmen verwerken grote mappen snel.  
- **Pure .NET:** Geen native binaries of tools van derden nodig.  
- **Rijke functionaliteit:** Ondersteunt wachtwoordbeveiliging (`add password zip`), streaming en het instellen van een aangepast compressieniveau (`set compression level`).  
- **Consistente API:** Werkt hetzelfde op .NET Framework, .NET Core en .NET 5/6, waardoor het ideaal is voor **create zip archive .net** scenario's.  

## Vereisten

- **Aspose.Zip for .NET** – download het [hier](https://releases.aspose.com/zip/net/).  
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

Hieronder staat een eenvoudig voorbeeld dat laat zien hoe je **een map zippen** inhoud. Hetzelfde patroon kan worden uitgebreid naar **meerdere bestanden zippen .net** of om aangepaste archiefstructuren te maken.

### Stap 1: Initialiseert uw documentdirectory

Stel de variabele `dataDir` in op het pad van de directory die je wilt comprimeren.

```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Maak output‑ZIP‑bestanden

Open twee `FileStream`‑objecten voor de output‑ZIP‑bestanden. Dit laat zien hoe je meer dan één archief kunt genereren vanuit dezelfde bron—handig voor versie‑back‑ups.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Stap 3: De directory comprimeren

Gebruik de `Archive`‑klasse om elke entry uit de doelmap toe te voegen. Het voorbeeld gebruikt een voorbeeldmap genaamd **CanterburyCorpus**, maar je kunt elke directory aanwijzen.

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

> **Pro tip:** Als je een **create zip archive .net** met een specifiek compressieniveau nodig hebt, stel dan `archive.CompressionLevel` in vóór het aanroepen van `Save`.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Leeg ZIP‑bestand | `dataDir` wijst naar een verkeerde map of er ontbreekt een slash aan het einde | Controleer het pad en zorg dat de map bestanden bevat |
| `UnauthorizedAccessException` | Applicatie heeft geen bestandsysteem‑rechten | Voer Visual Studio uit als administrator of geef lees‑/schrijfrechten |
| Groot geheugenverbruik bij enorme directories | Alle entries in één keer in het geheugen laden | Gebruik `Archive.CreateEntryFromFile` in een lus om bestanden individueel te streamen |

## Veelgestelde vragen (aanvullend)

**V: Kan ik een wachtwoord toevoegen aan het ZIP‑archief?**  
A: Ja. Stel `archive.Password = "yourPassword";` in vóór het aanroepen van `Save`.

**V: Hoe neem ik alleen bepaalde bestandstypen op?**  
A: Filter de `DirectoryInfo`‑collectie met `GetFiles("*.txt")` of iets dergelijks vóór het aanroepen van `CreateEntries`.

**V: Is er een manier om een bestaand ZIP‑archief bij te werken zonder het opnieuw te maken?**  
A: Aspose.Zip ondersteunt incrementele updates via `Archive.UpdateEntry`.

## Veelgestelde vragen

### V1: Kan ik Aspose.Zip voor .NET gebruiken in zowel commerciële als persoonlijke projecten?

A1: Ja, Aspose.Zip voor .NET is gelicentieerd voor zowel commercieel als persoonlijk gebruik.

### V2: Is er een gratis proefversie beschikbaar?

A2: Ja, je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/zip/net).

### V3: Hoe krijg ik ondersteuning voor Aspose.Zip voor .NET?

A3: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor community‑ondersteuning of overweeg het aanschaffen van een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor toegewijde assistentie.

### V4: Zijn er andere voorbeelden en tutorials beschikbaar?

A4: Ja, de [documentatie](https://reference.aspose.com/zip/net/) bevat uitgebreide voorbeelden en tutorials.

### V5: Kan ik Aspose.Zip voor .NET kopen?

A5: Zeker, je kunt een aankoop doen [hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-02-12  
**Getest met:** Aspose.Zip 24.11 for .NET  
**Auteur:** Aspose