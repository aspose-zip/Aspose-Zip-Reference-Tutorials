---
date: 2026-02-28
description: Leer hoe je bestanden comprimeert met een wachtwoord en ZIP‑archieven
  versleutelt met Aspose.Zip voor .NET, inclusief 7z‑wachtwoordbeveiliging en per‑bestand
  zip‑wachtwoord in C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe bestanden comprimeren met een wachtwoord en ZIP‑items versleutelen met
  verschillende wachtwoorden met Aspose.Zip voor .NET
url: /nl/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

Make sure to keep all code block placeholders unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe bestanden comprimeren met wachtwoord en ZIP‑items versleutelen met verschillende wachtwoorden met Aspose.Zip voor .NET

## Introductie

Als je **bestanden wilt comprimeren met een wachtwoord** en elk item een eigen wachtwoord wilt geven, ben je hier aan het juiste adres. In deze tutorial lopen we stap voor stap door hoe je een 7‑zip‑archief maakt waarbij elk bestand wordt beschermd met een uniek wachtwoord, met behulp van de Aspose.Zip‑bibliotheek voor .NET. Aan het einde begrijp je waarom encryptie per item belangrijk is, hoe je het instelt, en hoe je het resultaat in je eigen projecten kunt verifiëren.

## Snelle antwoorden
- **Wat betekent “encrypt zip”?** Het betekent het toepassen van wachtwoord‑gebaseerde bescherming (AES of ZipCrypto) op de inhoud van een ZIP/7z‑archief.  
- **Kan elk item een ander wachtwoord hebben?** Ja—Aspose.Zip laat je verschillende wachtwoorden per bestand toewijzen.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework, .NET Core en .NET 5/6 versies.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Welk compressieformaat wordt in het voorbeeld gebruikt?** Het voorbeeld maakt een 7z‑archief met AES‑256‑encryptie.

## Hoe bestanden comprimeren met wachtwoord met Aspose.Zip voor .NET
In deze sectie beantwoorden we de hoofdvraag direct en bereiden we de basis voor de stap‑voor‑stap‑gids die volgt.

## Wat is “how to encrypt zip” met Aspose.Zip?
Een ZIP (of 7z) bestand versleutelen betekent dat je de items beveiligt zodat ze niet geopend kunnen worden zonder het juiste wachtwoord. Aspose.Zip voor .NET ondersteunt zowel de klassieke ZipCrypto als sterkere AES‑encryptie, en het laat je encryptie‑instellingen per item specificeren, waardoor je fijnmazige controle over de beveiliging krijgt.

## Waarom verschillende wachtwoorden voor elk item gebruiken?
- **Beveiligingssegmentatie:** Als één wachtwoord wordt gecompromitteerd, blijven de andere bestanden beschermd.  
- **Regelgeving naleving:** Sommige sectoren vereisen aparte inloggegevens voor verschillende datacategorieën.  
- **Gebruikersspecifieke toegang:** Je kunt één archief verspreiden naar meerdere gebruikers, waarbij elke gebruiker alleen de bestanden kan ontgrendelen die hij mag zien.

## Voorvereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- **Aspose.Zip for .NET** geïnstalleerd – zie de officiële [documentatie](https://reference.aspose.com/zip/net/) voor download‑ en installatie‑instructies.  
- Een map op je computer waar je de bronbestanden opslaat (de “Document Directory”).  
- Basiskennis van C# en Visual Studio (of je favoriete .NET‑IDE).

## Namespaces importeren

We beginnen met het importeren van de namespaces die de klassen bevatten die we nodig hebben.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Stel je Document Directory in

Definieer het pad dat de bestanden bevat die je wilt archiveren.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Maak items met verschillende wachtwoorden

Dit is de kern van de tutorial. We openen een nieuw 7z‑bestand, maken drie `FileInfo`‑objecten aan, en voegen elk toe als een item met zijn eigen AES‑wachtwoord.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Hoe dit werkt

- `SevenZipArchive` is de container voor een 7‑z‑archief.  
- `CreateEntry` neemt de itemnaam, bronbestand, een vlag voor overschrijven, en een `SevenZipEntrySettings`‑object.  
- Binnen `SevenZipEntrySettings` geven we twee instellingen‑objecten: één voor compressie (`SevenZipStoreCompressionSettings`) en één voor encryptie (`SevenZipAESEncryptionSettings`).  
- Elke aanroep levert een **anders wachtwoord** (`"test1"`, `"test2"`, `"test3"`), waardoor per‑item bescherming wordt bereikt.

## Stap 3: Verificatie

Nadat het archief is opgeslagen, kun je een eenvoudige bevestigingsmelding weergeven.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Voer het programma uit en probeer vervolgens `archive.7z` te openen met een tool zoals 7‑Zip. Het vraagt je om een wachtwoord voor elk item, waarmee wordt bevestigd dat de wachtwoorden inderdaad verschillend zijn.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Onjuist wachtwoord‑fout** | Wachtwoord‑string bevat vreemde spaties of onzichtbare tekens. | Trim de wachtwoord‑strings (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archief opent niet in oudere tools** | Sommige oudere ZIP‑tools ondersteunen de AES‑256‑encryptie die door 7z wordt gebruikt niet. | Gebruik een moderne extractor (7‑Zip 19.00+). |
| **Bestand niet toegevoegd aan archief** | Bronbestandspad is onjuist of bestand bestaat niet. | Controleer `dataDir` en de bestandsnamen, of gebruik `Path.Combine(dataDir, "data1.bin")`. |

## Veelgestelde vragen

### Q1: Is Aspose.Zip for .NET compatibel met alle versies van .NET?

A1: Ja, Aspose.Zip for .NET is ontworpen om naadloos te integreren met alle versies van het .NET‑framework.

### Q2: Kan ik Aspose.Zip for .NET gebruiken in mijn commerciële projecten?

A2: Absoluut! Aspose.Zip for .NET biedt commerciële licenties, en je kunt meer informatie vinden over hoe je kunt kopen [hier](https://purchase.aspose.com/buy).

### Q3: Is er een gratis proefversie beschikbaar?

A3: Ja, je kunt de functies van Aspose.Zip for .NET verkennen met een gratis proefversie. Begin [hier](https://releases.aspose.com/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Zip for .NET?

A4: Voor vragen of hulp, bezoek het [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Kan ik Aspose.Zip for .NET gebruiken zonder een permanente licentie?

A5: Ja, je kunt een tijdelijke licentie verkrijgen voor je kortetermijnbehoeften. Meer details vind je [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie

Je hebt zojuist geleerd **hoe bestanden te comprimeren met een wachtwoord** en ZIP‑archieven te versleutelen met per‑item wachtwoorden met behulp van Aspose.Zip voor .NET. Deze techniek geeft je de flexibiliteit om elk bestand afzonderlijk te beschermen, voldoet aan strengere beveiligingseisen en vereenvoudigt gebruikersspecifieke distributie. Voel je vrij om te experimenteren met andere compressie‑instellingen, grotere bestandenverzamelingen, of deze logica te integreren in een webservice die beveiligde archieven on‑the‑fly genereert.

---

**Laatst bijgewerkt:** 2026-02-28  
**Getest met:** Aspose.Zip for .NET 24.12 (latest op moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}