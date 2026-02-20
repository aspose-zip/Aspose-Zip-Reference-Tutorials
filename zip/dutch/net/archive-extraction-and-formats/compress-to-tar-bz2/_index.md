---
date: 2026-02-20
description: Leer hoe je tar kunt comprimeren en een TarBz2-archief kunt maken in
  .NET met Aspose.Zip. Deze stapsgewijze handleiding laat zien hoe je bestanden aan
  tar kunt toevoegen en efficiënt tarbz2‑bestanden kunt genereren.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe tar te comprimeren en TarBz2 te maken met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

ose"

Then closing shortcodes.

Finally backtop button shortcode.

Make sure to keep all markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tar te comprimeren en TarBz2 te maken met Aspose.Zip voor .NET

## Introductie

Welkom bij onze uitgebreide gids over **hoe tar te comprimeren** en bestanden toe te voegen aan een tar‑archief, en vervolgens een TarBz2‑bestand te maken met Aspose.Zip voor .NET. Of u nu een back‑up‑hulpmiddel bouwt, implementatiepakketten levert, of gewoon een compact archief nodig heeft voor distributie, deze tutorial leidt u stap voor stap met duidelijke uitleg, praktische tips en voorbeelden.

Voordat we beginnen, laten we ervoor zorgen dat u alles heeft wat u nodig heeft.

## Snelle Antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten
- **Heb ik een licentie nodig?** Een tijdelijke licentie is vereist voor productie; een gratis proefversie is beschikbaar
- **Kan ik meerdere bestanden comprimeren?** Ja – voeg zoveel entries toe als u wilt aan het Tar‑archief
- **Is het compatibel met .NET 6+?** Absoluut, Aspose.Zip ondersteunt .NET Framework en .NET Core/5/6

## Hoe tar te comprimeren

Bestanden toevoegen aan een **tar** (Tape Archive) maakt een enkele ongecomprimeerde container die de mapstructuur en bestandsmetadata behoudt. Wanneer u vervolgens Bzip2‑compressie toepast, ontstaat een **tar.bz2** (TarBz2) archief – ideaal voor efficiënte opslag en overdracht. Aspose.Zip maakt dit proces een één‑regelige bewerking, waarbij zowel tar‑creatie als Bzip2‑compressie onder de motorkap worden afgehandeld.

## Waarom bestanden comprimeren naar TarBz2 met Aspose.Zip?

- **Snelheid & eenvoud** – Eén‑regelige API‑aanroepen behandelen zowel tar‑creatie als Bzip2‑compressie.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS .NET‑runtime.  
- **Fijne controle** – Kies welke bestanden u wilt opnemen, stel aangepaste entry‑namen in en stream direct naar schijf.  
- **Robuuste .NET‑ondersteuning** – Volledig compatibel met **tar archive .net** scenario's, van console‑apps tot webservices.

## Voorwaarden

- **Aspose.Zip for .NET** – Download het nieuwste pakket van de officiële site: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – Een map die de bestanden bevat die u wilt archiveren. In de voorbeelden verwijzen we ernaar met de variabele `dataDir`.

> **Pro tip:** Houd uw bronbestanden in een speciale map om per ongeluk opnemen van ongewenste bestanden te voorkomen.

## Namespaces importeren

Eerst de benodigde namespaces importeren zodat u toegang heeft tot de Tar‑ en Bzip2‑klassen van Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Stap 1: Stel de Document Directory in

Definieer het pad dat naar de map wijst die de bestanden bevat die u wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

> Vervang `"Your Document Directory"` door het absolute of relatieve pad naar uw bronmap.

## Stap 2: Voeg bestanden toe aan tar en maak een TarBz2‑archief

De kern van het proces is het maken van een `TarArchive`, entries toevoegen, en vervolgens wikkelen met een `Bzip2Archive`. De code hieronder demonstreert **hoe tarbz2 te maken** in een schone, disposable‑pattern stijl.

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

- `CreateEntry` voegt elk bestand toe aan de **tar**‑container.  
- `bz2.SetSource(archive)` vertelt het Bzip2‑archief om de volledige tar‑stroom te comprimeren.  
- `bz2.Save(...)` schrijft het uiteindelijke **tar.bz2**‑bestand naar schijf.

**Tip:** Om **bestanden naar tarbz2 te comprimeren** in bulk, herhaal simpelweg `archive.CreateEntry` voor elk bestand dat u nodig heeft.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet gevonden** fout | Verkeerde `dataDir`‑pad of ontbrekende bestandsextensie | Controleer het volledige pad en zorg dat het bestand bestaat. |
| **Leeg archief** | Geen entries toegevoegd vóór `bz2.Save` | Voeg minstens één `CreateEntry`‑aanroep toe. |
| **Toegang geweigerd** | Applicatie heeft geen schrijfrechten voor de uitvoermap | Voer de app uit met de juiste rechten of kies een map met schrijfrechten. |

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met alle .NET‑applicaties?**  
A: Ja. Het werkt met .NET Framework, .NET Core, .NET 5/6 en nieuwere runtimes.

**Q: Kan ik meerdere bestanden tegelijkertijd comprimeren?**  
A: Absoluut. Roep `CreateEntry` aan voor elk bestand voordat u het archief opslaat.

**Q: Waar kan ik aanvullende documentatie vinden?**  
A: Gedetailleerde docs zijn beschikbaar [hier](https://reference.aspose.com/zip/net/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Zip?**  
A: U kunt er een aanvragen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, download een proefversie [hier](https://releases.aspose.com/).

## Conclusie

U heeft nu geleerd hoe u **bestanden aan tar kunt toevoegen**, ze in een Bzip2‑stroom kunt wikkelen, en een **TarBz2**‑archief kunt produceren met Aspose.Zip voor .NET. Deze techniek is snel, betrouwbaar en werkt op alle moderne .NET‑platformen. Voel u vrij om te experimenteren met grotere bestandssets, aangepaste entry‑namen, of de code te integreren in uw eigen back‑up‑ of implementatie‑pijplijnen.

Als u tegen uitdagingen aanloopt, staat de Aspose.Zip‑community klaar om te helpen – ga gewoon naar het [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}