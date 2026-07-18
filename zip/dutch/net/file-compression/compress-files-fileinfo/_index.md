---
date: 2026-07-18
description: Leer hoe je een map toevoegt aan een zip en bestanden toevoegt aan een
  zip met Aspose.Zip voor .NET. Deze stapsgewijze gids laat zien hoe je bestanden
  comprimeert met FileInfo in ASP.NET-projecten.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Bestanden comprimeren met FileInfo
og_description: Map toevoegen aan zip met Aspose.Zip voor .NET. Leer hoe je een zip‑archief
  maakt, bestanden toevoegt aan een zip en mappen efficiënt comprimeert in ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Map toevoegen aan zip – Bestanden comprimeren met Aspose.Zip voor .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Map toevoegen aan zip met Aspose.Zip voor .NET – Bestanden comprimeren met
  FileInfo
url: /nl/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Map toevoegen aan zip met Aspose.Zip voor .NET

## Inleiding

Als je programmatisch **add folder to zip** moet toevoegen, biedt Aspose.Zip voor .NET een schone, high‑performance API die werkt in elke .NET (inclusief ASP.NET) applicatie. In deze tutorial lopen we door het comprimeren van bestanden met de `FileInfo`‑klasse, laten we zien hoe je **add files to zip** kunt doen, en leggen we uit waarom deze aanpak ideaal is voor moderne .NET‑projecten. We behandelen ook de exacte stappen om **add folder to zip** uit te voeren zodat je volledige mappen in één bewerking kunt bundelen. Laten we beginnen!

## Snelle antwoorden
- **Wat is de gemakkelijkste manier om een zip‑archief te maken?** Gebruik de `Archive`‑klasse van Aspose.Zip samen met `FileInfo`‑objecten.  
- **Kan ik meerdere bestanden tegelijk toevoegen?** Ja – maak gewoon een `FileInfo` voor elk bestand en roep `CreateEntry` aan.  
- **Heb ik een speciale licentie nodig voor ASP.NET?** Een commerciële Aspose.Zip‑licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10.  
- **Is de API thread‑safe?** Ja, zolang elke thread werkt met zijn eigen `Archive`‑instantie.

## Wat is een zip‑archief en waarom er een maken?
Een zip‑archief bundelt één of meer bestanden in één gecomprimeerde container. Dit vermindert opslagruimte, versnelt netwerkoverdrachten en vereenvoudigt distributie. Of je nu logbestanden levert, rapporten exporteert of assets voor een klant verpakt, het weten **how to create zip archive** bestanden programmatisch is een waardevolle vaardigheid voor elke .NET‑ontwikkelaar.

## Waarom Aspose.Zip gebruiken om bestanden aan zip toe te voegen?
Aspose.Zip biedt een pure‑.NET‑oplossing die externe afhankelijkheden elimineert en ontwikkelaars fijnmazige controle geeft over compressie, codering en beveiliging. Het ondersteunt grote bestanden, wachtwoordbeveiliging en werkt consistent over alle ondersteunde .NET‑versies, waardoor het een betrouwbare keuze is voor zowel legacy‑ als moderne applicaties.  

- **Geen externe afhankelijkheden** – pure .NET‑implementatie.  
- **Volledige controle over compressieniveau en codering** (ASCII, UTF‑8, enz.).  
- **Ondersteunt bestanden groter dan 4 GB** en wachtwoordbeveiliging.  
- **Consistente API over 50+ .NET‑versies** – van .NET Framework 2.0 tot .NET 10.  

## Vereisten

Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

1. **Aspose.Zip for .NET** geïnstalleerd. Download het nieuwste pakket vanaf de [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Een map op je computer met de bestanden die je wilt comprimeren (bijv. `alice29.txt` en `fields.c`).  

## Namespaces importeren

In elk C#‑bestand waar je met zip‑archieven werkt, voeg je de volgende `using`‑statements toe:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Stapsgewijze handleiding

### Stap 1: Stel je documentmap in

Definieer eerst de map die de bronbestanden bevat. Vervang de placeholder door het absolute of relatieve pad op jouw systeem:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gebruik `Path.Combine` om paden platformonafhankelijk op te bouwen.

### Stap 2: Open een zip‑bestand voor schrijven

Maak een `FileStream` die naar het uitvoer‑zip‑bestand wijst. De stream wordt geopend in **Create**‑modus, waardoor elk bestaand bestand met dezelfde naam wordt overschreven:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Stap 3: Bereid `FileInfo`‑objecten voor elk bronbestand voor

`FileInfo` geeft Aspose.Zip direct toegang tot de fysieke bestanden op schijf. Maak één instantie per bestand dat je wilt comprimeren:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Waarom `FileInfo` gebruiken?** Het voorkomt dat het volledige bestand in het geheugen wordt geladen, wat vooral handig is voor grote bestanden.

### Stap 4: Maak het archief aan en voeg items toe

De `Archive`‑klasse is het kernobject van Aspose.Zip dat een zip‑container in het geheugen vertegenwoordigt. Instantieer een `Archive`‑object en roep vervolgens `CreateEntry` aan voor elke `FileInfo`. Het eerste argument is de naam die het bestand binnen de zip krijgt, het tweede argument is de bron‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

De `CreateEntry`‑methode voegt een nieuw bestand toe aan het archief, waarbij de entry‑naam wordt gekoppeld aan de bron‑`FileInfo` zodat de gegevens direct van de schijf worden gestreamd wanneer het archief wordt opgeslagen.

### Stap 5: Sla het zip‑archief op met gewenste codering

Sla ten slotte het archief op in de `FileStream` die je eerder hebt geopend. Hier gebruiken we ASCII‑codering voor entry‑namen, maar je kunt overschakelen naar UTF‑8 als je bestandsnamen niet‑ASCII tekens bevatten:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Wanneer de `using`‑blokken worden verlaten, worden de streams automatisch gesloten en is het zip‑bestand klaar voor gebruik.

## Hoe voeg je een map toe aan zip met Aspose.Zip?

Laad de doelmap, doorloop elk bestand en voeg elk toe met een relatief pad dat de mapnaam bevat. Deze aanpak laat je **add folder to zip** uitvoeren zonder handmatig elk bestand te vermelden. Door de maphiërarchie in de entry‑namen te behouden, kan het resulterende archief worden uitgepakt met de oorspronkelijke directory‑structuur intact, wat essentieel is voor veel implementatiescenario's.

1. Gebruik `DirectoryInfo` om naar de map te wijzen die je wilt comprimeren.  
2. Roep `GetFiles("*", SearchOption.AllDirectories)` aan om alle bestanden recursief op te halen.  
3. Voor elk bestand, maak een `FileInfo` en roep `CreateEntry` aan met een pad zoals `"MyFolder/Report.pdf"`.  

## Veelvoorkomende problemen & oplossingen

| Issue | Cause | Fix |
|-------|-------|-----|
| **Leeg zip‑bestand** | `FileInfo` wijst naar een niet‑bestaand pad | Controleer `dataDir` en bestandsnamen; gebruik `File.Exists` om te controleren voordat je entries maakt. |
| **Onjuiste bestandsnaamacodering** | Gebruik van de standaardcodering met niet‑ASCII namen | Stel `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException bij grote bestanden** | Het volledige bestand in het geheugen laden | `FileInfo` streamt het bestand; zorg ervoor dat je het bestand niet elders in een byte‑array laadt. |
| **Toegang geweigerd** | Applicatie heeft geen schrijfrechten voor de uitvoermap | Voer de app uit met de juiste rechten of kies een schrijfbare directory. |

## Veelgestelde vragen

**Q: Kan ik een volledige map in één keer aan een zip‑archief toevoegen?**  
A: Er bestaat geen enkele‑aanroep‑methode, maar het enumereren van bestanden met `DirectoryInfo` en elk toevoegen via `CreateEntry` levert hetzelfde resultaat efficiënt op.

**Q: Ondersteunt Aspose.Zip wachtwoordbeveiliging?**  
A: Ja, je kunt een wachtwoord instellen op het `Archive`‑object voordat je het opslaat om het hele archief te versleutelen.

**Q: Hoe groot een zip‑bestand kan Aspose.Zip aan?**  
A: De bibliotheek verwerkt bestanden groter dan 4 GB en kan archieven maken die groter zijn dan 10 GB zonder het volledige archief in het geheugen te laden.

**Q: Is de API compatibel met .NET 6 en .NET 8?**  
A: Absoluut. Aspose.Zip ondersteunt .NET 5 tot en met .NET 10, wat alle huidige LTS‑releases dekt.

**Q: Welke compressieniveaus zijn beschikbaar?**  
A: Je kunt kiezen uit `CompressionLevel.NoCompression`, `Fast`, `Normal` of `Maximum` om snelheid en grootte in balans te brengen.

## Verdere bronnen

- Download het nieuwste Aspose.Zip‑pakket: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Koop een licentie voor productiegebruik: [purchase page](https://purchase.aspose.com/buy)  
- Krijg hulp van de community: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Probeer Aspose.Zip gratis: [free trial here](https://releases.aspose.com/)  
- Verkrijg een tijdelijke licentie voor evaluatie: [this link](https://purchase.aspose.com/temporary-license/)

## Conclusie

Je weet nu **how to add folder to zip** en **how to create zip archive** bestanden te maken met Aspose.Zip voor .NET, hoe je **add files to zip** uitvoert, en waarom deze methode ideaal is voor ASP.NET en andere .NET‑applicaties. Experimenteer met verschillende compressieniveaus, coderingen en encryptie‑opties om het archief precies op jouw behoeften af te stemmen. Veel zip‑plezier!

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe map zippen met Aspose.Zip voor .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Meerdere bestanden zippen c# – Eenvoudige compressie met Aspose.Zip voor .NET](/zip/net/file-compression/compress-multiple-files/)
- [Zip‑archief maken .NET – Bestandscompressie met Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}