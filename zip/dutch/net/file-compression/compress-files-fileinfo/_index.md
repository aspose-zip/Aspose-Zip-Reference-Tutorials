---
date: 2026-02-28
description: Leer hoe je een map aan een zip toevoegt en bestanden aan een zip toevoegt
  met Aspose.Zip voor .NET. Deze stapsgewijze handleiding laat zien hoe je bestanden
  comprimeert met FileInfo in ASP.NET‑projecten.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map toevoegen aan een zip met Aspose.Zip voor .NET – Bestanden comprimeren
  met FileInfo
url: /nl/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een map toevoegen aan zip met Aspose.Zip voor .NET

## Introductie

Als je programmatically **een zip‑archief wilt maken**, biedt Aspose.Zip voor .NET een schone, high‑performance API die werkt in elke .NET (inclusief ASP.NET) applicatie. In deze tutorial lopen we het comprimeren van bestanden met de `FileInfo`‑klasse door, laten we zien hoe je **bestanden aan zip kunt toevoegen**, en leggen we uit waarom deze aanpak ideaal is voor moderne .NET‑projecten. We behandelen ook hoe je **een map aan zip kunt toevoegen** zodat je hele mappen in één stap kunt bundelen. Laten we beginnen!

## Snelle antwoorden
- **Wat is de makkelijkste manier om een zip‑archief te maken?** Gebruik de `Archive`‑klasse van Aspose.Zip samen met `FileInfo`‑objecten.  
- **Kan ik meerdere bestanden tegelijk toevoegen?** Ja – maak gewoon een `FileInfo` voor elk bestand en roep `CreateEntry` aan.  
- **Heb ik een speciale licentie nodig voor ASP.NET?** Een commerciële Aspose.Zip‑licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Is de API thread‑safe?** Ja, zolang elke thread met zijn eigen `Archive`‑instantie werkt.

## Wat is een Zip‑archief en waarom er één maken?
Een zip‑archief bundelt één of meer bestanden in één gecomprimeerde container. Dit vermindert de opslagruimte, versnelt netwerkoverdrachten en vereenvoudigt distributie. Of je nu logbestanden levert, rapporten exporteert of assets voor een klant verpakt, weten **hoe je zip‑archief kunt maken** programmatically is een waardevolle vaardigheid voor elke .NET‑ontwikkelaar.

## Waarom Aspose.Zip gebruiken om bestanden aan zip toe te voegen?
- **Geen externe afhankelijkheden** – pure .NET‑implementatie.  
- **Volledige controle over compressieniveau en codering** (ASCII, UTF‑8, enz.).  
- **Ondersteunt grote bestanden** (> 4 GB) en wachtwoordbeveiliging.  
- **Consistente API over .NET Framework, .NET Core en .NET 5+**.

## Voorvereisten

Voordat we in de code duiken, zorg dat je het volgende hebt:

1. **Aspose.Zip voor .NET** geïnstalleerd. Download het nieuwste pakket van de [Aspose.Zip downloadpagina](https://releases.aspose.com/zip/net/).  
2. Een map op je machine met de bestanden die je wilt comprimeren (bijv. `alice29.txt` en `fields.c`).  

## Namespaces importeren

Voeg in elk C#‑bestand waarin je met zip‑archieven werkt de volgende `using`‑statements toe:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Deze namespaces geven je toegang tot de `Archive`‑klasse, opslaan‑opties en de standaard I/O‑hulpmiddelen.

## Stapsgewijze handleiding

### Stap 1: Stel je documentdirectory in

Definieer eerst de map die de bronbestanden bevat. Vervang de placeholder door het absolute of relatieve pad op jouw systeem:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Gebruik `Path.Combine` om paden platform‑onafhankelijk op te bouwen.

### Stap 2: Open een zip‑bestand voor schrijven

Maak een `FileStream` die naar het output‑zip‑bestand wijst. De stream wordt geopend in **Create**‑modus, waardoor elk bestaand bestand met dezelfde naam wordt overschreven:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Stap 3: Bereid `FileInfo`‑objecten voor elk bronbestand voor

`FileInfo` geeft Aspose.Zip directe toegang tot de fysieke bestanden op schijf. Maak één instantie per bestand dat je wilt comprimeren:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Waarom `FileInfo` gebruiken?** Het voorkomt dat het volledige bestand in het geheugen wordt geladen, wat vooral handig is voor grote bestanden.

### Stap 4: Maak het archief en voeg items toe

Instantieer een `Archive`‑object en roep vervolgens `CreateEntry` aan voor elke `FileInfo`. Het eerste argument is de naam die het bestand in de zip zal hebben, het tweede argument is de bron‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Stap 5: Sla het zip‑archief op met de gewenste codering

Sla tenslotte het archief op in de `FileStream` die je eerder hebt geopend. Hier gebruiken we ASCII‑codering voor de entry‑namen, maar je kunt overschakelen naar UTF‑8 als je bestandsnamen niet‑ASCII‑tekens bevatten:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Wanneer de `using`‑blokken worden verlaten, worden de streams automatisch gesloten en is het zip‑bestand klaar voor gebruik.

## Hoe een map toevoegen aan zip met Aspose.Zip

Als je **een map aan zip wilt toevoegen** in plaats van individuele bestanden, is het proces eenvoudig:

1. **Doorloop de map** met `DirectoryInfo.GetFiles` (en eventueel `GetDirectories` voor recursie).  
2. **Maak een `FileInfo`** voor elk gevonden bestand.  
3. **Roep `CreateEntry`** aan met een relatief pad dat de mapnaam bevat, bijv. `"MyFolder/Report.pdf"`.

Omdat de API werkt met `FileInfo`, hoef je nooit hele bestanden in het geheugen te laden, waardoor het veilig is voor grote mappen. Deze techniek werkt ook voor **zip multiple files asp.net**‑scenario's waarin je een rapportset on‑the‑fly genereert en als één archief wilt leveren.

## Veelvoorkomende problemen & oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Leeg zip‑bestand** | `FileInfo` wijst naar een niet‑bestaand pad | Controleer `dataDir` en bestandsnamen; gebruik `File.Exists` om te controleren voordat je entries maakt. |
| **Onjuiste bestandsnaamacodering** | Standaardcodering gebruiken met niet‑ASCII namen | Stel `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException bij grote bestanden** | Het volledige bestand in het geheugen laden | `FileInfo` streamt het bestand; zorg dat je het bestand niet elders in een byte‑array laadt. |
| **Toegang geweigerd** | Applicatie heeft geen schrijfrechten voor de output‑map | Voer de app uit met de juiste rechten of kies een schrijfbare directory. |

## Veelgestelde vragen

**V: Kan ik wachtwoordbeveiliging toevoegen aan het zip‑archief?**  
A: Ja. Nadat je de `Archive` hebt aangemaakt, stel je `archive.Password = "yourPassword"` in vóór het aanroepen van `Save`.

**V: Is het mogelijk een bestaand zip‑bestand bij te werken?**  
A: Aspose.Zip ondersteunt het openen van een bestaand archief met `Archive.Open` en vervolgens nieuwe entries toevoegen.

**V: Hoe comprimeer ik bestanden in een ASP.NET MVC‑controller?**  
A: Dezelfde code werkt; zorg er alleen voor dat de output‑stream wordt geretourneerd als een `FileResult` naar de client.

**V: Ondersteunt Aspose.Zip encryptie‑algoritmen?**  
A: Het ondersteunt standaard ZipCrypto en AES‑256 encryptie.

**V: Wat als ik een map recursief moet comprimeren?**  
A: Loop door `Directory.GetFiles` (en sub‑mappen) en maak een `FileInfo` voor elk bestand, voeg ze vervolgens toe aan het archief.

## Extra FAQ

**V: Hoe maak ik een zip‑archief .net voor grote datasets?**  
A: Gebruik `FileInfo`‑objecten om data te streamen en stel `CompressionLevel` in `ArchiveSaveOptions` in voor optimale prestaties.

**V: Kan ik Aspose.Zip gebruiken in een .NET Core web‑API (zip files asp.net core)?**  
A: Absoluut – de bibliotheek is volledig compatibel met .NET Core 3.1 en later.

**V: Is er een manier om een map toe te voegen aan zip zonder een eigen lus te schrijven?**  
A: Aspose.Zip heeft geen enkele “add folder”‑methode, maar itereren met `DirectoryInfo` is lichtgewicht en geeft volledige controle over de entry‑namen.

**V: Heeft wachtwoordbeveiliging van zip‑archief invloed op de compressiesnelheid?**  
A: Encryptie voegt een kleine overhead toe, maar de impact is minimaal voor de meeste gebruikssituaties.

**V: Welke licentie is vereist voor commerciële inzet?**  
A: Een betaalde Aspose.Zip‑licentie is vereist voor productie; een gratis proefversie kan worden gebruikt voor ontwikkeling en testen.

## Bestaande FAQ‑sectie (ongewijzigd)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusie

Je weet nu **hoe je een map aan zip kunt toevoegen** en **hoe je zip‑archief kunt maken** met Aspose.Zip voor .NET, hoe je **bestanden aan zip kunt toevoegen**, en waarom deze methode ideaal is voor ASP.NET en andere .NET‑applicaties. Experimenteer met verschillende compressieniveaus, coderingen en encryptie‑opties om het archief precies op jouw behoeften af te stemmen. Veel compressieplezier!

---

**Laatst bijgewerkt:** 2026-02-28  
**Getest met:** Aspose.Zip for .NET 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}