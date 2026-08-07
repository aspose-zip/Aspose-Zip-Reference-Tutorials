---
date: 2026-08-07
description: Leer hoe u bestanden aan tar kunt toevoegen en een TarBz2-archief kunt
  genereren in .NET met Aspose.Zip. Stapsgewijze handleiding toont het maken van tar,
  Bzip2-compressie en best‑practice‑tips.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Comprimeren naar TarBz2
og_description: Bestanden toevoegen aan tar en een TarBz2-archief genereren in .NET
  met Aspose.Zip. Deze handleiding behandelt het maken van tar, Bzip2-compressie en
  tips voor probleemoplossing.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Bestanden toevoegen aan tar en een TarBz2-archief maken met Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Bestanden toevoegen aan tar en een TarBz2-archief maken met Aspose.Zip
url: /nl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestanden toevoegen aan tar en een TarBz2-archief maken met Aspose.Zip

In deze tutorial ontdek je **hoe je bestanden aan tar toevoegt** archieven en ze omzet in een compact **TarBz2** bestand met behulp van de **Aspose.Zip** bibliotheek voor .NET. Of je nu een back‑up‑hulpmiddel bouwt, implementatiepakketten publiceert, of een lichtgewicht bundel voor distributie nodig hebt, de onderstaande stappen leiden je door het toevoegen van bestanden aan een tar‑container, het toepassen van Bzip2‑compressie, en het produceren van een kant‑klaar archief.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten  
- **Heb ik een licentie nodig?** Een tijdelijke licentie is vereist voor productie; een gratis proefversie is beschikbaar  
- **Kan ik meerdere bestanden comprimeren?** Ja – voeg zoveel entries toe als je wilt aan het tar‑archief  
- **Is het compatibel met .NET 6+?** Absoluut, Aspose.Zip ondersteunt .NET Framework en .NET Core/5/6  

## Wat is een TarBz2‑archief?

Een TarBz2‑bestand combineert de traditionele **tar**‑container (die de mapstructuur en bestandsmetadata behoudt) met **Bzip2**‑compressie, resulterend in een sterk gecomprimeerd `.tar.bz2`‑pakket. Dit formaat is populair op Unix‑achtige systemen omdat het een goede balans biedt tussen compressieverhouding en decompressiesnelheid.

## Waarom bestanden comprimeren naar TarBz2 met Aspose.Zip?

Aspose.Zip kan een TarBz2‑archief genereren in **twee API‑aanroepen** terwijl het streams efficiënt verwerkt. Het ondersteunt **meer dan 50 archief‑ en compressieformaten**, verwerkt bestanden tot **2 GB** zonder het volledige archief in het geheugen te laden, en draait op Windows, Linux en macOS .NET‑runtime‑omgevingen. De bibliotheek geeft je ook fijnmazige controle over entry‑namen, tijdstempels en compressieniveaus, waardoor het ideaal is voor zowel console‑hulpmiddelen als webservices.

## Vereisten

- **Aspose.Zip for .NET** – download het nieuwste pakket van de officiële site: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – een map die de bestanden bevat die je wilt archiveren. In de voorbeelden verwijzen we ernaar met de variabele `dataDir`.

> **Pro tip:** Bewaar je bronbestanden in een speciale map om per ongeluk opnemen van ongewenste bestanden te voorkomen.

## Namespaces importeren

Importeer eerst de benodigde namespaces zodat je toegang hebt tot de Tar- en Bzip2‑klassen van Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Stap 1: stel de documentdirectory in

Definieer het pad dat naar de map wijst die de bestanden bevat die je wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

> Vervang `"Your Document Directory"` door het absolute of relatieve pad naar je bronmap.

## Stap 2: bestanden toevoegen aan tar en een TarBz2‑archief maken

`TarArchive` vertegenwoordigt een in‑memory tar‑container die meerdere bestandsentries kan bevatten.  
`Bzip2Archive` comprimeert een stream met behulp van het Bzip2‑algoritme.  
De `CreateEntry`‑methode voegt een bestand toe aan het tar‑archief als een nieuwe entry.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **voegt bestanden toe aan tar** – je kunt deze methode aanroepen voor elk bestand dat je nodig hebt in het archief.  
- `bz2.SetSource(archive)` geeft de Bzip2‑archive aan om de volledige tar‑stream te comprimeren.  
- `bz2.Save(...)` schrijft het uiteindelijke **TarBz2**‑bestand naar schijf.

**Tip:** Om **bestanden toe te voegen aan tar** in bulk, herhaal je simpelweg `archive.CreateEntry` voor elk bestand voordat je `bz2.Save` aanroept.

## Hoe bestanden toevoegen aan tar?

Laad de bronmap, maak een `TarArchive`‑instantie, voeg elk bestand toe met `CreateEntry`, wikkel vervolgens de tar‑stream in een `Bzip2Archive` en roep `Save` aan. Dit twee‑stappen‑patroon voegt een willekeurig aantal bestanden toe en produceert een `.tar.bz2`‑bestand in één vloeiende stroom, waardoor tijdelijke bestanden of externe tools overbodig zijn.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet gevonden** fout | Verkeerd `dataDir`‑pad of ontbrekende bestandsextensie | Controleer het volledige pad en zorg dat het bestand bestaat. |
| **Leeg archief** | Geen entries toegevoegd vóór `bz2.Save` | Voeg minstens één `CreateEntry`‑aanroep toe. |
| **Toegang geweigerd** | Applicatie mist schrijfrechten voor de doelmap | Voer de app uit met de juiste rechten of kies een schrijfbare map. |

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met alle .NET‑applicaties?**  
A: Ja. Het werkt met .NET Framework, .NET Core, .NET 5/6 en nieuwere runtimes.

**Q: Kan ik meerdere bestanden tegelijk comprimeren?**  
A: Absoluut. Roep `CreateEntry` aan voor elk bestand voordat je het archief opslaat.

**Q: Waar kan ik extra documentatie vinden?**  
A: Gedetailleerde documentatie is beschikbaar in de **Aspose.Zip .NET API‑referentie**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Zip?**  
A: Je kunt hier **een tijdelijke licentie aanvragen**: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, **download een proefversie van Aspose releases**: [download a trial version](https://releases.aspose.com/).

## Conclusie

Je weet nu **hoe je bestanden aan tar toevoegt**, de tar‑stream comprimeert met Bzip2, en een **TarBz2**‑archief genereert met Aspose.Zip voor .NET. De aanpak is snel, geheugen‑efficiënt en werkt op alle moderne .NET‑platformen. Voel je vrij om te experimenteren met grotere bestandssets, aangepaste entry‑namen, of de code te integreren in je eigen back‑up‑ of implementatie‑pijplijnen.

Als je tegen problemen aanloopt, staat de Aspose.Zip‑community klaar om te helpen—ga gewoon naar het **Aspose.Zip‑ondersteuningsforum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Laatst bijgewerkt:** 2026-08-07  
**Getest met:** Aspose.Zip for .NET (latest release)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Tar‑archief maken en bestanden toevoegen aan tar met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Bestanden toevoegen aan tar en een tarxz‑archief maken met Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Bestanden toevoegen aan tar en comprimeren naar TarZ met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}