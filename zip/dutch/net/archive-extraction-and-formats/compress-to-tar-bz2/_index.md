---
date: 2026-04-24
description: Leer hoe je tar comprimeert en een TarBz2‑archief maakt in .NET met Aspose.Zip.
  Deze stapsgewijze handleiding laat zien hoe je bestanden aan een tar‑archief toevoegt
  en efficiënt tarbz2‑bestanden genereert.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Comprimeren naar TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe tar te comprimeren en TarBz2 te maken met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tar te comprimeren en TarBz2 te maken met Aspose.Zip voor .NET

## Introductie

In deze tutorial ontdek je **hoe je tar**-archieven kunt comprimeren en ze kunt omzetten in een compact **TarBz2**-bestand met behulp van de **Aspose.Zip**-bibliotheek voor .NET. Of je nu een back‑up hulpprogramma bouwt, implementatiepakketten publiceert, of gewoon een lichtgewicht bundel voor distributie nodig hebt, de onderstaande stappen begeleiden je bij het toevoegen van bestanden aan tar, het toepassen van Bzip2‑compressie en het produceren van een kant‑klaar archief.

Voordat we beginnen, zorg ervoor dat je de vereisten die later in deze gids worden vermeld, hebt, zodat je zonder problemen kunt volgen.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten  
- **Heb ik een licentie nodig?** Een tijdelijke licentie is vereist voor productie; een gratis proefversie is beschikbaar  
- **Kan ik meerdere bestanden comprimeren?** Ja – voeg zoveel items toe als je wilt aan het tar‑archief  
- **Is het compatibel met .NET 6+?** Absoluut, Aspose.Zip ondersteunt .NET Framework en .NET Core/5/6  

## Wat is een TarBz2‑archief?

Een **TarBz2**‑bestand combineert de traditionele **tar**‑container (die de mapstructuur en bestandsmetadata behoudt) met **Bzip2**‑compressie, wat resulteert in een sterk gecomprimeerd `.tar.bz2`‑pakket. Dit formaat is populair op Unix‑achtige systemen omdat het een goede balans biedt tussen compressieverhouding en decompressiesnelheid.

## Waarom bestanden comprimeren naar TarBz2 met Aspose.Zip?

- **Snelheid & Eenvoud** – Eén‑regelige API‑aanroepen behandelen zowel het maken van tar als Bzip2‑compressie.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS .NET‑runtime.  
- **Fijne controle** – Kies welke bestanden je wilt opnemen, stel aangepaste itemnamen in en stream direct naar schijf.  
- **Robuste .NET‑ondersteuning** – Perfect voor **tar archive .net**‑scenario's, van console‑apps tot webservices.  

## Vereisten

- **Aspose.Zip for .NET** – Download het nieuwste pakket van de officiële site: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Documentdirectory** – Een map die de bestanden bevat die je wilt archiveren. In de voorbeelden verwijzen we ernaar met de variabele `dataDir`.

> **Pro tip:** Houd je bronbestanden in een speciale map om per ongeluk opnemen van ongewenste bestanden te voorkomen.

## Namespaces importeren

Importeer eerst de benodigde namespaces zodat je toegang hebt tot de Tar- en Bzip2‑klassen van Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Stap 1: Stel de documentdirectory in

Definieer het pad dat naar de map wijst die de bestanden bevat die je wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

> Vervang `"Your Document Directory"` door het absolute of relatieve pad naar je bronmap.

## Stap 2: Voeg bestanden toe aan tar en maak een TarBz2‑archief

De kern van het proces is het maken van een `TarArchive`, het toevoegen van items, en vervolgens het omhullen met een `Bzip2Archive`. De onderstaande code toont **hoe je tar maakt** en het comprimeert tot een **TarBz2** in een schone, disposable‑patroonstijl.

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
- `bz2.SetSource(archive)` vertelt het Bzip2‑archief om de volledige tar‑stroom te comprimeren.  
- `bz2.Save(...)` schrijft het uiteindelijke **TarBz2**‑bestand naar schijf.

Tip: Om **bestanden toe te voegen aan tar** in bulk, herhaal je eenvoudig `archive.CreateEntry` voor elk bestand voordat je `bz2.Save` aanroept.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet gevonden**-fout | Verkeerd `dataDir`-pad of ontbrekende bestandsextensie | Controleer het volledige pad en zorg ervoor dat het bestand bestaat. |
| **Leeg archief** | Geen items toegevoegd vóór `bz2.Save` | Voeg minstens één `CreateEntry`‑aanroep toe. |
| **Toegang geweigerd** | Applicatie heeft geen schrijfrechten voor de doelmap | Voer de app uit met de juiste rechten of kies een map met schrijfpermissies. |

## Veelgestelde vragen

**Q: Is Aspose.Zip compatibel met alle .NET‑applicaties?**  
A: Ja. Het werkt met .NET Framework, .NET Core, .NET 5/6 en nieuwere runtimes.

**Q: Kan ik meerdere bestanden tegelijk comprimeren?**  
A: Absoluut. Roep `CreateEntry` aan voor elk bestand voordat je het archief opslaat.

**Q: Waar kan ik extra documentatie vinden?**  
A: Gedetailleerde documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/).

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Zip?**  
A: Je kunt er een aanvragen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, download een proefversie [hier](https://releases.aspose.com/).

## Conclusie

Je hebt nu geleerd **hoe je tar comprimeert**, bestanden eraan toevoegt, en het resultaat in een Bzip2‑stroom verpakt om een **TarBz2**‑archief te produceren met Aspose.Zip voor .NET. Deze aanpak is snel, betrouwbaar en werkt op alle moderne .NET‑platformen. Voel je vrij om te experimenteren met grotere bestandssets, aangepaste itemnamen, of de code te integreren in je eigen back‑up‑ of implementatie‑pijplijnen.

Als je tegen problemen aanloopt, staat de Aspose.Zip‑community klaar om te helpen—ga gewoon naar het [Aspose.Zip supportforum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}