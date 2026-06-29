---
date: 2026-06-29
description: Leer hoe je een xar-archief kunt extraheren en een xar-bestand kunt decomprimeren
  naar een map met Aspose.Zip voor .NET. Volg deze stapsgewijze handleiding.
keywords:
- extract xar archive
- how to extract xar
- decompress xar file
- aspose zip decompress
linktitle: Decomprimeer Xar naar map
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract xar archive and decompress xar file to a folder
    using Aspose.Zip for .NET. Follow this step‑by‑step guide.
  headline: How to Extract Xar Archive to Folder Using Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip is regularly updated to ensure compatibility with the
      latest .NET framework versions. Refer to the [documentation](https://reference.aspose.com/zip/net/)
      for specific details.
    question: Is Aspose.Zip compatible with the latest .NET framework versions?
  - answer: Absolutely! You can download a free trial version from [here](https://releases.aspose.com/).
    question: Can I try Aspose.Zip before making a purchase?
  - answer: For any queries or assistance, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: How can I get support for Aspose.Zip?
  - answer: Yes, temporary licenses can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.Zip?
  - answer: You can purchase Aspose.Zip for .NET [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een Xar-archief naar een map te extraheren met Aspose.Zip voor .NET
url: /nl/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Xar-archief naar een map te extraheren met Aspose.Zip voor .NET

Als je een .NET‑ontwikkelaar bent die **xar‑archief**‑bestanden snel en betrouwbaar moet **extraheren**, biedt Aspose.Zip voor .NET een nette, high‑performance API die het hele proces afhandelt zonder externe tools. In deze tutorial lopen we stap voor stap door het decomprimeren van een Xar‑archief naar een map, leggen we uit waarom deze methode tijd bespaart, en geven we kant‑klaar code. Aan het einde begrijp je wanneer je deze aanpak moet gebruiken, hoe je deze in je project integreert, en hoe je veelvoorkomende valkuilen vermijdt.

## Snelle antwoorden
- **Wat doet de bibliotheek?** Het leest en extraheert Xar‑archieven zonder externe tools.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten.  
- **Kan ik naar een aangepaste map extraheren?** Ja—geef gewoon het doelpad op in `ExtractToDirectory`.

## Wat betekent “how to extract xar”?
Een Xar‑archief extraheren betekent dat je het gecomprimeerde pakket leest en de interne bestanden naar een map op schijf schrijft. Dit is handig wanneer je XAR‑pakketten ontvangt van macOS‑installateurs, back‑up‑hulpmiddelen of tools van derden en de inhoud in een .NET‑applicatie moet verwerken.

## Waarom Aspose.Zip voor deze taak gebruiken?
- **Geen externe afhankelijkheden** – pure .NET, geen native binaries.  
- **Stream‑gebaseerde API** – werkt met bestanden, geheugen‑streams of netwerk‑streams.  
- **Robuuste foutafhandeling** – gedetailleerde uitzonderingen helpen bij het oplossen van corrupte archieven.  
- **Volledige .NET‑compatibiliteit** – werkt op Windows-, Linux- en macOS-runtime.  
- **Brede formaatondersteuning** – Aspose.Zip kan uit meer dan 30 archieftypen (ZIP, TAR, XAR, 7z, enz.) extraheren en verwerkt bestanden tot 2 GB zonder het volledige archief in het geheugen te laden, waardoor je voorspelbare prestaties krijgt, zelfs op bescheiden servers.

## Vereisten
Voordat we beginnen, zorg dat je het volgende hebt:

- **Aspose.Zip for .NET** – geïntegreerd in je project. Je kunt het downloaden van [hier](https://releases.aspose.com/zip/net/).  
- **Document Directory** – een map in je oplossing waar het voorbeeld‑`.xar`‑bestand en de uitgepakte output zich bevinden.

## Namespaces importeren
In je .NET‑project, voeg de benodigde namespaces toe om toegang te krijgen tot de functionaliteit van Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Stap 1: Definieer je Document Directory
```csharp
string dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het absolute of relatieve pad dat `sample.xar` bevat en waar je de output‑map wilt laten aanmaken. Het later gebruiken van `Path.Combine` helpt pad‑scheidingstekens tussen besturingssystemen te vermijden.

## Stap 2: Decompress Xar-archief
De `XarArchive`‑klasse is het toegangspunt van Aspose.Zip voor het lezen van XAR‑containers en het blootleggen van hun items. Het biedt methoden om bestanden te enumereren en ze naar schijf te extraheren.

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Dit fragment opent het Xar‑bestand, maakt een `XarArchive`‑instantie aan, en extraheert **de volledige decompress xar archive** naar `DecompressXar_out`. De bewerking is volledig stream‑gebaseerd, zodat hij efficiënt werkt, zelfs bij grote pakketten.

## Hoe een xar-archief naar een map te extraheren?
`XarArchive.Open` opent een XAR‑archief en retourneert een `XarArchive`‑instantie. `ExtractToDirectory` extraheert de inhoud van het archief naar een opgegeven map.  
Laad het XAR‑bestand met `XarArchive.Open("sample.xar")` en roep `archive.ExtractToDirectory("DecompressXar_out")` aan. De API maakt automatisch de doelmap aan, behoudt de oorspronkelijke mapstructuur, en schrijft elk item met gebufferde streams, zodat je met slechts twee methoden een getrouwe kopie van het originele pakket krijgt.

### Stap 3: Voer de code uit
Bouw en voer je applicatie uit. Na uitvoering vind je een nieuwe map genaamd `DecompressXar_out` in je documentdirectory, met alle bestanden die in het oorspronkelijke `.xar`‑archief waren verpakt.

## Veelvoorkomende problemen & tips
- **Bestand niet gevonden** – Zorg ervoor dat het pad in `File.OpenRead` correct naar `sample.xar` verwijst. Gebruik `Path.Combine` voor veiliger padbeheer.  
- **Toegang geweigerd** – Voer de applicatie uit met voldoende bestandsysteem‑rechten, vooral bij het schrijven naar beschermde mappen.  
- **Corrupt archief** – Aspose.Zip gooit `InvalidDataException`; controleer of het bron‑`.xar`‑bestand intact is.  
- **Grote archieven** – Als je werkt met archieven groter dan 1 GB, overweeg dan de buffergrootte te verhogen via `ArchiveOptions` om de doorvoersnelheid te verbeteren.

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met de nieuwste .NET-frameworkversies?**  
A: Ja, Aspose.Zip wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworkversies te garanderen. Zie de [documentatie](https://reference.aspose.com/zip/net/) voor specifieke details.

**Q: Kan ik Aspose.Zip uitproberen voordat ik een aankoop doe?**  
A: Absoluut! Je kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Zip?**  
A: Voor vragen of hulp kun je het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) bezoeken.

**Q: Zijn tijdelijke licenties beschikbaar voor Aspose.Zip?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar via [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik Aspose.Zip voor .NET kopen?**  
A: Je kunt Aspose.Zip voor .NET aanschaffen [hier](https://purchase.aspose.com/buy).

**Q: Kan ik alleen specifieke bestanden uit een Xar-archief extraheren?**  
A: Ja—gebruik `archive.Entries` om items te enumereren en roep `ExtractToFile` aan voor geselecteerde items.

**Q: Ondersteunt de bibliotheek wachtwoord‑beveiligde Xar‑bestanden?**  
A: Momenteel ondersteunen Xar‑archieven geen encryptie; als je een beveiligd bestand tegenkomt, moet je het eerst ontsleutelen voordat je Aspose.Zip gebruikt.

**Laatst bijgewerkt:** 2026-06-29  
**Getest met:** Aspose.Zip 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe bestanden te decomprimeren met Aspose.Zip voor .NET](/zip/net/file-decompression/)
- [Hoe zip naar map te extraheren met Aspose.Zip voor .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [Tar-archief maken en bestanden aan tar toevoegen met Aspose.Zip voor .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}