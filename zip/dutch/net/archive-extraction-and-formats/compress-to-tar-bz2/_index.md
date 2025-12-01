---
date: 2025-11-29
description: Leer hoe u bestanden toevoegt aan tar en bestanden comprimeert naar tarbz2‑formaat
  in .NET met Aspose.Zip. Deze stapsgewijze handleiding laat zien hoe u tarbz2‑archieven
  efficiënt maakt.
language: nl
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Bestanden toevoegen aan tar en comprimeren naar TarBz2 met Aspose.Zip voor
  .NET
url: /net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestanden toevoegen aan tar en comprimeren naar TarBz2 met Aspose.Zip voor .NET

## Introductie

Welkom bij onze uitgebreide gids over **hoe bestanden toe te voegen aan tar** en ze te comprimeren naar het TarBz2‑formaat met Aspose.Zip voor .NET. Of u nu een back‑up‑utility bouwt, implementatie‑pakketten levert, of simpelweg een compacte archief nodig heeft voor distributie, deze tutorial leidt u stap voor stap met duidelijke uitleg en praktijkgerichte tips.

Voordat we beginnen, zorgen we ervoor dat u alles heeft wat u nodig heeft.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten
- **Heb ik een licentie nodig?** Een tijdelijke licentie is vereist voor productie; een gratis proefversie is beschikbaar
- **Kan ik meerdere bestanden comprimeren?** Ja – voeg zoveel entries toe als u wilt aan het Tar‑archief
- **Is het compatibel met .NET 6+?** Absoluut, Aspose.Zip ondersteunt .NET Framework en .NET Core/5/6

## Wat betekent “bestanden toevoegen aan tar”?
Het toevoegen van bestanden aan een **tar** (Tape Archive) creëert een enkele ongecomprimeerde container die de mapstructuur en bestandsmetadata behoudt. Wanneer u vervolgens Bzip2‑compressie toepast, ontstaat er een **tar.bz2** (TarBz2)‑archief – ideaal voor efficiënte opslag en overdracht.

## Waarom bestanden comprimeren naar TarBz2 met Aspose.Zip?
- **Snelheid & Eenvoud** – Eén‑regelige API‑aanroepen behandelen zowel het maken van tar als Bzip2‑compressie.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS .NET‑runtimes.  
- **Fijnmazige controle** – Kies welke bestanden moeten worden opgenomen, stel aangepaste entry‑namen in en stream direct naar schijf.

## Voorvereisten

- **Aspose.Zip for .NET** – Download het nieuwste pakket van de officiële site: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – Een map die de bestanden bevat die u wilt archiveren. In de voorbeelden verwijzen we ernaar met de variabele `dataDir`.

> **Pro tip:** Houd uw bronbestanden in een speciale map om per ongeluk opnemen van ongewenste bestanden te voorkomen.

## Import Namespaces

Importeer eerst de benodigde namespaces zodat u toegang heeft tot de Tar‑ en Bzip2‑klassen van Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Stap 1: Stel de Document Directory in

Definieer het pad dat naar de map wijst waarin de bestanden staan die u wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

> Vervang `"Your Document Directory"` door het absolute of relatieve pad naar uw bronmap.

## Stap 2: Voeg bestanden toe aan tar en maak een TarBz2‑archief

De kern van het proces is het maken van een `TarArchive`, entries toevoegen, en vervolgens inpakken met een `Bzip2Archive`. De code hieronder laat **hoe u tarbz2 maakt** in een nette, disposable‑pattern stijl zien.

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

**Tip:** Om **bestanden in bulk naar tarbz2 te comprimeren**, herhaal simpelweg `archive.CreateEntry` voor elk bestand dat u nodig heeft.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **File not found**‑fout | Verkeerd `dataDir`‑pad of ontbrekende bestandsextensie | Controleer het volledige pad en zorg dat het bestand bestaat. |
| **Leeg archief** | Geen entries toegevoegd vóór `bz2.Save` | Voeg minstens één `CreateEntry`‑aanroep toe. |
| **Permission denied** | Applicatie mist schrijfrechten voor de doelmap | Voer de app uit met de juiste rechten of kies een schrijfbare map. |

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met alle .NET‑applicaties?**  
A: Ja. Het werkt met .NET Framework, .NET Core, .NET 5/6 en nieuwere runtimes.

**Q: Kan ik meerdere bestanden gelijktijdig comprimeren?**  
A: Absoluut. Roep `CreateEntry` aan voor elk bestand voordat u het archief opslaat.

**Q: Waar vind ik extra documentatie?**  
A: Gedetailleerde docs zijn beschikbaar [hier](https://reference.aspose.com/zip/net/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Zip?**  
A: U kunt er een aanvragen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, download een proefversie [hier](https://releases.aspose.com/).

## Conclusie

U heeft nu geleerd hoe u **bestanden toevoegt aan tar**, deze in een Bzip2‑stroom verpakt, en een **TarBz2**‑archief produceert met Aspose.Zip voor .NET. Deze techniek is snel, betrouwbaar en werkt op alle moderne .NET‑platforms. Voel u vrij om te experimenteren met grotere bestandssets, aangepaste entry‑namen, of de code te integreren in uw eigen back‑up‑ of implementatie‑pijplijnen.

Als u tegen uitdagingen aanloopt, staat de Aspose.Zip‑community klaar om te helpen – ga gewoon naar het [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}