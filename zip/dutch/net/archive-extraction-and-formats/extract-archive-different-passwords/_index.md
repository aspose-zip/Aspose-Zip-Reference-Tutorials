---
date: 2025-12-01
description: Leer hoe je zip-bestanden met wachtwoord kunt uitpakken met Aspose.Zip
  voor .NET, en efficiënt meerdere wachtwoordbeveiligde items verwerkt.
language: nl
linktitle: Extracting Archive Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe zip-bestand met wachtwoord uitpakken met Aspise.Zip voor .NET
url: /net/archive-extraction-and-formats/extract-archive-different-passwords/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe zip met wachtwoord uitpakken met Aspose.Zip voor .NET

In moderne .NET‑toepassingen is het beschermen van gevoelige gegevens in ZIP‑archieven een veelvoorkomende eis. Deze tutorial laat **zien hoe zip met wachtwoord uit te pakken** wanneer elk item een ander wachtwoord gebruikt, zodat je fijnmazige controle over de beveiliging hebt en het uitpakproces eenvoudig blijft.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip voor .NET.  
- **Kan ik items uitpakken die verschillende wachtwoorden hebben?** Ja — elk item kan worden geopend met zijn eigen wachtwoord.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist; een gratis proefversie is beschikbaar.  
- **Ondersteunde platformen?** .NET Framework, .NET Core, .NET 5/6+.  
- **Typische implementatietijd?** Ongeveer 10 minuten voor een basisscenario.

## Voorvereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- **Aspose.Zip voor .NET** geïnstalleerd in je project. Je kunt de officiële documentatie vinden [hier](https://reference.aspose.com/zip/net/).  
- Een .NET‑ontwikkelomgeving (Visual Studio, Rider of VS Code) gericht op .NET 5 of hoger.  
- Een ZIP‑bestand dat items bevat die versleuteld zijn met **verschillende wachtwoorden** (het voorbeeldbestand hier is `different_password.zip`).

## Namespaces importeren

Importeer eerst de namespaces die nodig zijn voor het werken met archieven:

```csharp
using Aspose.Zip;
using System.IO;
```

Deze twee `using`‑statements geven je toegang tot de `Archive`‑klasse en standaard I/O‑hulpmiddelen.

## Stap 1: Definieer de werkmap

Stel de map in waar het ZIP‑bestand zich bevindt en waar de uitgepakte bestanden worden weggeschreven:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gebruik `Path.Combine` voor platform‑onafhankelijke padopbouw als je Linux/macOS wilt ondersteunen.

## Stap 2: Archiefitems met verschillende wachtwoorden uitpakken

Hieronder lopen we stap voor stap door hoe je het archief opent en elk item met zijn eigen wachtwoord uitpakt.

### Stap 2.1: Het Zip‑bestand openen

```csharp
using (FileStream zipFile = File.Open(dataDir + "\\different_password.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
        // Continue to the next steps...
    }
}
```

Het `Archive`‑object vertegenwoordigt de ZIP‑container. Het plaatsen van `FileStream` en `Archive` in `using`‑blokken zorgt ervoor dat alle resources direct worden vrijgegeven.

### Stap 2.2: Het eerste item uitpakken (Wachtwoord = “first_pass”)

```csharp
archive.Entries[0].Extract(dataDir + "alice29_extracted_pass_out.txt", "first_pass");
```

Hier **pakken we meerdere zip‑items uit** door ze via de `Entries`‑collectie aan te roepen. Het eerste item wordt ontsleuteld met het wachtwoord `"first_pass"`.

### Stap 2.3: Het tweede item uitpakken (Wachtwoord = “second_pass”)

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_pass_out.txt", "second_pass");
```

Het tweede item gebruikt een ander wachtwoord, waarmee **wachtwoord‑beveiligde zip‑extractie** voor elk individueel bestand wordt gedemonstreerd.

## Waarom deze aanpak belangrijk is

- **Granulaire beveiliging:** Elk bestand kan zijn eigen wachtwoord hebben, waardoor het risico bij een gecompromitteerd wachtwoord wordt verminderd.  
- **Flexibiliteit:** Je kunt programmatisch bepalen welk wachtwoord moet worden toegepast op basis van bedrijfslogica (bijv. gebruikersrollen).  
- **Prestaties:** Aspose.Zip verwerkt items in‑memory, waardoor je de hele archief niet eerst hoeft uit te pakken.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| *“Invalid password”‑exception* | Verkeerd wachtwoord opgegeven of het item is niet werkelijk versleuteld. | Controleer de wachtwoord‑string en zorg dat het item wachtwoord‑beveiligd is. |
| *Bestand niet gevonden* | Pad `dataDir` is onjuist. | Gebruik `Path.Combine(dataDir, "different_password.zip")` en controleer de map. |
| *Grote archieven veroorzaken hoog geheugenverbruik* | Standaard worden alle items in het geheugen geladen. | Stream elk item afzonderlijk of gebruik `Archive.ExtractToDirectory` met een wachtwoord‑callback (indien ondersteund). |

## Veelgestelde vragen

**Q1: Kan ik Aspose.Zip gebruiken in zowel .NET Core‑ als .NET Framework‑projecten?**  
A1: Ja, Aspose.Zip ondersteunt .NET Framework, .NET Core en .NET 5/6+, waardoor je flexibiliteit hebt over verschillende platformen.

**Q2: Waar vind ik extra ondersteuning of community‑discussies over Aspose.Zip?**  
A2: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) om met de community in contact te komen, vragen te stellen en ervaringen te delen.

**Q3: Is er een gratis proefversie beschikbaar voor Aspose.Zip?**  
A3: Ja, je kunt de gratis proefversie van Aspose.Zip [hier](https://releases.aspose.com/) verkrijgen.

**Q4: Hoe kan ik een tijdelijke licentie voor Aspose.Zip verkrijgen?**  
A4: Voor een tijdelijke licentie, bezoek [deze link](https://purchase.aspose.com/temporary-license/).

**Q5: Waar kan ik Aspose.Zip aanschaffen?**  
A5: Om Aspose.Zip te kopen, ga naar de [aankooppagina](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-01  
**Getest met:** Aspose.Zip voor .NET 24.11 (latest at time of writing)  
**Auteur:** Aspose  

---