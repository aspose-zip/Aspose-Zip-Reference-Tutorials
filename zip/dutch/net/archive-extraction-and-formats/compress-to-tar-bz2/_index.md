---
date: 2026-10-31
description: Leer hoe u een tar-archief maakt en comprimeert tot een TarBz2‑bestand
  in .NET met Aspose.Zip. Een stapsgewijze handleiding toont het maken van tar, Bzip2‑compressie
  en best‑practice‑tips.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Comprimeren naar TarBz2
og_description: Leer hoe u een tar-archief maakt en comprimeert tot een TarBz2‑bestand
  met Aspose.Zip voor .NET. Een stapsgewijze handleiding behandelt het maken van tar,
  Bzip2‑compressie en best‑practice‑tips.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Maak een tar-archief en comprimeer naar TarBz2 met .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: Hoe een tar-archief maken en comprimeren naar TarBz2 met .NET
url: /nl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een tar-archief te maken en te comprimeren naar TarBz2 met .NET

In deze tutorial leer je **hoe je tar-archief** bestanden maakt en ze vervolgens comprimeert tot een compact **TarBz2**-pakket met behulp van de **Aspose.Zip**-bibliotheek voor .NET. Of je nu een back‑up hulpprogramma bouwt, deployment‑bundels voorbereidt, of een lichtgewicht distributieformaat nodig hebt, de onderstaande stappen leiden je door het toevoegen van bestanden aan een tar‑container, het toepassen van Bzip2‑compressie, en het schrijven van het uiteindelijke `.tar.bz2`‑bestand.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten  
- **Heb ik een licentie nodig?** Een tijdelijke licentie is vereist voor productie; een gratis proefversie is beschikbaar  
- **Kan ik meerdere bestanden comprimeren?** Ja – voeg zoveel entries toe als je wilt aan het tar‑archief  
- **Is het compatibel met .NET 6+?** Absoluut, Aspose.Zip ondersteunt .NET Framework en .NET Core/5/6  

## Wat is een TarBz2‑archief?

Een TarBz2‑bestand combineert de traditionele **tar**‑container (die de mapstructuur en bestandsmetadata behoudt) met **Bzip2**‑compressie, resulterend in een sterk gecomprimeerd `.tar.bz2`‑pakket. Dit formaat is populair op Unix‑achtige systemen omdat het een goede balans biedt tussen compressieverhouding en decompressiesnelheid.

## Waarom bestanden comprimeren naar TarBz2 met Aspose.Zip?

Aspose.Zip kan een TarBz2‑archief genereren met **twee API‑aanroepen** terwijl het streams efficiënt verwerkt. Het ondersteunt **meer dan 50 archief‑ en compressieformaten**, verwerkt bestanden tot **2 GB** zonder het volledige archief in het geheugen te laden, en draait op Windows, Linux en macOS .NET‑runtime‑omgevingen. De bibliotheek biedt ook fijne controle over entry‑namen, tijdstempels en compressieniveaus, waardoor het ideaal is voor zowel console‑hulpmiddelen als webservices.

## Vereisten

- **Aspose.Zip for .NET** – download het nieuwste pakket van de officiële site: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Documentmap** – een map die de bestanden bevat die je wilt archiveren. In de voorbeelden verwijzen we ernaar met de variabele `dataDir`.

> **Pro tip:** Houd je bronbestanden in een aparte map om per ongeluk opnemen van ongewenste bestanden te voorkomen.

## Namespaces importeren

Importeer eerst de benodigde namespaces zodat je toegang hebt tot de Tar- en Bzip2‑klassen van Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Stap 1: stel de documentmap in

Definieer het pad dat naar de map wijst die de bestanden bevat die je wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

> Vervang `"Your Document Directory"` door het absolute of relatieve pad naar je bronmap.

## Stap 2: voeg bestanden toe aan tar en maak een TarBz2‑archief

De `TarArchive`‑klasse vertegenwoordigt een in‑memory tar‑container, terwijl `Bzip2Archive` streams comprimeert met het Bzip2‑algoritme.  
De `CreateEntry`‑methode voegt een nieuw bestand toe aan het tar‑archief.

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

- `CreateEntry` **voegt bestanden toe aan tar** – je kunt deze methode aanroepen voor elk bestand dat je in het archief nodig hebt.  
- `bz2.SetSource(archive)` vertelt het Bzip2‑archief om de volledige tar‑stream te comprimeren.  
- `bz2.Save(...)` schrijft het uiteindelijke **TarBz2**‑bestand naar schijf.

**Tip:** Om **bestanden toe te voegen aan tar** in bulk, herhaal je simpelweg `archive.CreateEntry` voor elk bestand voordat je `bz2.Save` aanroept.

## Hoe bestanden toevoegen aan tar?

Laad de bronmap, maak een `TarArchive`‑instantie, voeg elk bestand toe met `CreateEntry`, wikkel vervolgens de tar‑stream in een `Bzip2Archive` en roep `Save` aan. Dit twee‑stappenpatroon voegt een willekeurig aantal bestanden toe en produceert een `.tar.bz2`‑bestand in één vloeiende stroom, waardoor tijdelijke bestanden of externe tools overbodig zijn.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **File not found** error | Verkeerd `dataDir`‑pad of ontbrekende bestandsextensie | Controleer het volledige pad en zorg dat het bestand bestaat. |
| **Empty archive** | Geen entries toegevoegd vóór `bz2.Save` | Voeg minstens één `CreateEntry`‑aanroep toe. |
| **Permission denied** | Applicatie heeft geen schrijfrechten voor de doelmap | Voer de app uit met de juiste rechten of kies een schrijfbare map. |

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met alle .NET‑applicaties?**  
A: Ja. Het werkt met .NET Framework, .NET Core, .NET 5/6 en nieuwere runtimes.

**Q: Kan ik meerdere bestanden tegelijk comprimeren?**  
A: Absoluut. Roep `CreateEntry` aan voor elk bestand vóór het opslaan van het archief.

**Q: Waar kan ik extra documentatie vinden?**  
A: Gedetailleerde documentatie is beschikbaar in de **Aspose.Zip .NET API-referentie**: [Aspose.Zip .NET API-referentie](https://reference.aspose.com/zip/net/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Zip?**  
A: Je kunt hier **een tijdelijke licentie aanvragen**: [vraag een tijdelijke licentie aan](https://purchase.aspose.com/temporary-license/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, **download een proefversie van Aspose releases**: [download een proefversie](https://releases.aspose.com/).

Je kunt ook [download een proefversie](https://releases.aspose.com/).

## Conclusie

Je weet nu **hoe je een tar‑archief maakt**, de tar‑stream comprimeert met Bzip2, en een **TarBz2**‑archief genereert met Aspose.Zip voor .NET. De aanpak is snel, geheugen‑efficiënt en werkt op alle moderne .NET‑platformen. Voel je vrij om te experimenteren met grotere bestandssets, aangepaste entry‑namen, of de code te integreren in je eigen back‑up‑ of deployment‑pijplijnen.

Als je tegen uitdagingen aanloopt, staat de Aspose.Zip‑community klaar om te helpen—ga gewoon naar het **Aspose.Zip‑ondersteuningsforum**: [Aspose.Zip ondersteuningsforum](https://forum.aspose.com/c/zip/37).

---

**Laatst bijgewerkt:** 2026-10-31  
**Getest met:** Aspose.Zip for .NET (latest release)  
**Auteur:** Aspose  

## Gerelateerde tutorials

- [Maak tar‑archief en voeg bestanden toe aan tar met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Voeg bestanden toe aan tar en maak tarxz‑archief met Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Voeg bestanden toe aan tar en comprimeer naar TarZ met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}