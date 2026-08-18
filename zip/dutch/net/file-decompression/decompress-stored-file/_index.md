---
date: 2026-06-14
description: Leer hoe je een zip zonder compressie maakt en meerdere zip‑bestanden
  extraheert met Aspose.Zip voor .NET. Deze gids behandelt hoe je een zip opent, een
  zip‑entry leest, en de C#‑stappen voor het extraheren van zip.
keywords:
- create zip without compression
- extract multiple zip files
- c# extract zip
- aspose zip extract
- zip archive store method
linktitle: Decomprimeren van een opgeslagen bestand
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  headline: Create Zip Without Compression & Decompress Files – Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  name: Create Zip Without Compression & Decompress Files – Aspose.Zip
  steps:
  - name: '1: Opening the Zip File'
    text: The `Archive` object represents the opened ZIP and gives you access to each
      entry via the `Entries` collection.
  - name: '2: Creating Extracted Files'
    text: Here we **read zip entry** 0, copy its bytes to a new file, and close the
      streams automatically thanks to the `using` statements.
  - name: '3: Repeating the Process for Another File'
    text: By iterating over `archive.Entries`, you can **extract multiple zip files**
      (or multiple entries) with just a few lines of code.
  type: HowTo
- questions:
  - answer: It stores files in a ZIP using the *store* method, leaving the data unchanged.
    question: What does “create zip without compression” mean?
  - answer: Aspose.Zip for .NET provides a clean API for the *store* method and extraction.
    question: Which library supports this in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license to run the sample?
  - answer: Yes – the tutorial demonstrates how to **extract multiple zip files**
      in a loop.
    question: Can I extract several files at once?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Maak zip zonder compressie & decompress bestanden – Aspose.Zip
url: /nl/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Decomprimeren van een opgeslagen bestand met Aspose.Zip voor .NET

## Inleiding

In moderne .NET-toepassingen is **create zip without compression** een handige techniek wanneer je razendsnelle archivering nodig hebt en je geeft niet om de bestandsgrootte. Aspose.Zip voor .NET stelt je in staat dergelijke “store‑method” archieven te genereren en later **extract multiple zip files** met slechts een paar regels C#. In deze tutorial lopen we stap voor stap door het openen van een ZIP, het lezen van een zip entry, en het uitvoeren van een **C# extract zip** operatie.

## Snelle antwoorden
- **Wat betekent “create zip without compression”?** Het slaat bestanden op in een ZIP met de *store* methode, waardoor de gegevens ongewijzigd blijven.  
- **Welke bibliotheek ondersteunt dit in .NET?** Aspose.Zip voor .NET biedt een duidelijke API voor de *store* methode en extractie.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik meerdere bestanden tegelijk extraheren?** Ja – de tutorial laat zien hoe je **extract multiple zip files** in een lus kunt uitvoeren.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10.

## Wat is “create zip without compression”?

De `store` compressiemethode vertelt het ZIP-formaat om elke datacompressiestap over te slaan. **create zip without compression** produceert daardoor een groter archief, maar de bewerking is bijna onmiddellijk en de oorspronkelijke bytes blijven ongewijzigd – perfect voor al gecomprimeerde media (JPEG, MP3) of wanneer je deterministische bestandsinhoud nodig hebt.

## Waarom Aspose.Zip voor .NET gebruiken?

Aspose.Zip geeft ontwikkelaars precieze controle over compressie, een vloeiende API voor het lezen en schrijven van entries, en cross‑platform compatibiliteit over alle .NET‑versies. Het verwerkt grote archieven efficiënt, houdt het geheugenverbruik laag, en ondersteunt meer dan 50 formaten, waardoor het ideaal is voor zowel eenvoudige als complexe archiveringstaken.

- **Full control** over compressieniveau – kies *store* of *deflate* per entry.  
- **Simple, fluent API** voor het lezen van entries, het openen van zip‑bestanden, en het extraheren van data.  
- **Cross‑platform** ondersteuning voor .NET Framework, .NET Core, en .NET 5+.  
- **Handles large archives** tot 2 GB zonder het volledige bestand in het geheugen te laden.  
- **Quantified claim:** Aspose.Zip ondersteunt **50+ input and output formats** en kan **multi‑hundred‑page archives** verwerken terwijl het geheugenverbruik onder 100 MB blijft.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- **Aspose.Zip for .NET** – download het van de officiële site **[here](https://releases.aspose.com/zip/net/)**.  
- Een werkende **document directory** op je machine waar de voorbeeldbestanden worden gelezen en geschreven.

## Namespaces importeren

Importeer eerst de namespaces die de kernklassen bevatten die we gaan gebruiken:

```csharp
using Aspose.Zip;
using System.IO;
```

## Hoe maak ik een zip‑archief zonder compressie in C#?

`Archive` is de primaire klasse die een ZIP‑archief vertegenwoordigt in Aspose.Zip.

Om een stored‑archief te maken, laad elk bronbestand, instantiate een `Archive`, en voeg elk bestand toe met `CompressionMethod.Store`. Er zijn geen extra compressie‑parameters nodig, en de bibliotheek schrijft de ruwe bytes direct, wat resulteert in een bijna onmiddellijke bewerking terwijl de oorspronkelijke data ongewijzigd blijft.

## Hoe een zip zonder compressie maken

Eerst hebben we een ZIP‑archief nodig dat de **store**‑methode gebruikt (d.w.z. geen compressie). De voorbeeldcode hieronder maakt zo’n archief en wordt door Aspose.Zip geleverd als een hulpfunctie. Het uitvoeren ervan genereert `StoreMultipleFilesWithoutCompression_out.zip` in je document directory.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** De hulpfunctie stelt intern `CompressionMethod.Store` in voor elke entry, waardoor het archief zonder enige datacompressie wordt aangemaakt.

## Hoe kan ik een zip‑bestand openen en meerdere entries extraheren met Aspose.Zip?

`Archive` vertegenwoordigt een geopend ZIP‑bestand en biedt toegang tot de entries via de `Entries`‑collectie.

Open het archief door het bestandspad door te geven aan de `Archive`‑constructor, en itereren vervolgens door `archive.Entries`. Voor elke entry open je de stream met `entry.Open()`, kopieer je de data naar een doelbestand met een gebufferde stream, en sluit je de streams automatisch met `using`. Deze aanpak extrahert efficiënt alle entries zonder het volledige archief in het geheugen te laden.

## Hoe een zip openen en meerdere bestanden extraheren

Nu we een stored ZIP hebben, laten we zien **how to open zip** en de bestanden eruit halen.

### Stap 2.1: Het zip‑bestand openen

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

Het `Archive`‑object vertegenwoordigt de geopende ZIP en geeft je toegang tot elke entry via de `Entries`‑collectie.

### Stap 2.2: Extractie‑bestanden maken

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

Hier **read zip entry** 0, kopiëren we de bytes naar een nieuw bestand, en sluiten we de streams automatisch dankzij de `using`‑statements.

### Stap 2.3: Het proces herhalen voor een ander bestand

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

Door te itereren over `archive.Entries`, kun je **extract multiple zip files** (of meerdere entries) met slechts een paar regels code.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `FileNotFoundException` bij het openen van de ZIP | Verkeerd `dataDir` pad | Controleer of `dataDir` eindigt op een slash of gebruik `Path.Combine`. |
| Uitgepakt bestand is leeg | Buffer niet geleegd | Het `using`‑blok leegt automatisch; zorg ervoor dat je de stream leest tot `bytesRead` 0 is (zoals getoond). |
| Licentie‑exception | Uitvoeren zonder een geldige licentie | Pas een proef‑ of permanente licentie toe vóór implementatie. |

## Veelgestelde vragen

### Q1: Is Aspose.Zip for .NET compatible with all .NET frameworks?

**A:** Ja, Aspose.Zip voor .NET werkt met .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10, waardoor je flexibiliteit over platforms krijgt.

### Q2: Kan ik Aspose.Zip voor .NET gebruiken in zowel commerciële als niet‑commerciële projecten?

**A:** Ja, je kunt het in elk type project gebruiken. Zie de licentie‑details op de **[purchase page](https://purchase.aspose.com/buy)** voor meer informatie.

### Q3: Hoe kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?

**A:** Bezoek het **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** waar de community en Aspose‑engineers vragen beantwoorden.

### Q4: Is er een gratis proefversie beschikbaar voor Aspose.Zip voor .NET?

**A:** Absoluut – je kunt een proefversie downloaden **[here](https://releases.aspose.com/)** en alle functies zonder kosten evalueren.

### Q5: Kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?

**A:** Ja, een tijdelijke licentie is beschikbaar via **[this link](https://purchase.aspose.com/temporary-license/)** voor kortetermijn‑evaluatie.

### Q6: Hoe lees ik een zip entry zonder het hele archief te extraheren?

**A:** Gebruik `archive.Entries[index].Open()` om een stream voor een specifieke entry te verkrijgen, en lees vervolgens alleen de bytes die je nodig hebt – precies zoals getoond in de code‑fragmenten.

### Q7: Wat is de beste manier om **extract multiple zip files** in een lus uit te voeren?

**A:** Iterate over `archive.Entries` met een `foreach`‑lus, open de stream van elke entry, en schrijf deze naar de doel‑locatie. Deze aanpak weerspiegelt het patroon dat wordt getoond in Stappen 2.2 en 2.3.

## Conclusie

Het beheersen van **create zip without compression** en het daaropvolgende extractie‑proces is essentieel voor high‑performance .NET‑applicaties. Aspose.Zip voor .NET biedt je een duidelijke, intuïtieve API om **how to open zip**, elke **zip entry** te lezen, en een **C# extract zip**‑operatie uit te voeren met minimale code. Door deze gids te volgen, heb je geleerd hoe je een stored‑archief genereert, opent, en de inhoud efficiënt extraheert.

---

**Laatst bijgewerkt:** 2026-06-14  
**Getest met:** Aspose.Zip for .NET 24.12  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Zip for .NET - Zip‑archief beveiligen met wachtwoord & meerdere bestanden opslaan zonder compressie](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Zip‑archief maken .NET – Bestandscompressie met Aspose.Zip](/zip/net/file-compression/)
- [Bestanden decomprimeren met Aspose.Zip voor .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}