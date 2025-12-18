---
date: 2025-12-18
description: Leer hoe u zip‑bestanden kunt versleutelen met verschillende wachtwoorden
  met Aspose.Zip voor .NET. Deze gids laat zien hoe u bestanden kunt comprimeren met
  wachtwoorden en een 7z‑archief kunt maken in C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe ZIP-bestanden te versleutelen met verschillende wachtwoorden in Aspose.Zip
  voor .NET
url: /nl/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe ZIP‑bestanden te versleutelen met verschillende wachtwoorden in Aspose.Zip voor .NET

## Introductie

Als je **hoe zip te versleutelen** archieven moet maken waarbij elk item zijn eigen wachtwoord krijgt, ben je hier op het juiste adres. In deze tutorial lopen we stap voor stap door hoe je een 7‑zip‑archief maakt waarin elk bestand wordt beschermd met een uniek wachtwoord, met behulp van de Aspose.Zip‑bibliotheek voor .NET. Aan het einde begrijp je waarom versleuteling per item belangrijk is, hoe je het instelt, en hoe je het resultaat in je eigen projecten kunt verifiëren.

## Snelle antwoorden
- **Wat betekent “encrypt zip”?** Het betekent dat je wachtwoord‑gebaseerde bescherming (AES of ZipCrypto) toepast op de inhoud van een ZIP/7z‑archief.  
- **Kan elk item een ander wachtwoord hebben?** Ja—Aspose.Zip laat je verschillende wachtwoorden per bestand toewijzen.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework, .NET Core en .NET 5/6‑versies.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar.  
- **Welk compressieformaat wordt in het voorbeeld gebruikt?** Het voorbeeld maakt een 7z‑archief met AES‑256‑versleuteling.

## Wat is “how to encrypt zip” met Aspose.Zip?

Een ZIP (of 7z) versleutelen betekent dat je de items beveiligt zodat ze niet geopend kunnen worden zonder het juiste wachtwoord. Aspose.Zip voor .NET ondersteunt zowel klassieke ZipCrypto als sterkere AES‑versleuteling, en stelt je in staat om versleutelingsinstellingen per item op te geven, waardoor je fijne controle over de beveiliging krijgt.

## Waarom verschillende wachtwoorden per item gebruiken?

- **Beveiligingssegmentatie:** Als één wachtwoord wordt gecompromitteerd, blijven de andere bestanden beschermd.  
- **Regelgevende naleving:** Sommige sectoren vereisen aparte inloggegevens voor verschillende datacategorieën.  
- **Gebruikersspecifieke toegang:** Je kunt één archief distribueren naar meerdere gebruikers, waarbij elke gebruiker alleen de bestanden kan openen waarvoor hij of zij geautoriseerd is.

## Voorvereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- **Aspose.Zip voor .NET** geïnstalleerd – zie de officiële [documentatie](https://reference.aspose.com/zip/net/) voor download‑ en installatie‑instructies.  
- Een map op je computer waar je de bronbestanden bewaart (de “Document Directory”).  
- Basiskennis van C# en Visual Studio (of je favoriete .NET‑IDE).

## Namespaces importeren

We beginnen met het importeren van de namespaces die de benodigde klassen bevatten.

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

Dit is het kernstuk van de tutorial. We openen een nieuw 7z‑bestand, maken drie `FileInfo`‑objecten, en voegen elk toe als een item met zijn eigen AES‑wachtwoord.

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
- Binnen `SevenZipEntrySettings` geven we twee instellingenobjecten op: één voor compressie (`SevenZipStoreCompressionSettings`) en één voor versleuteling (`SevenZipAESEncryptionSettings`).  
- Elke aanroep levert een **anders wachtwoord** (`"test1"`, `"test2"`, `"test3"`), waardoor per‑item bescherming wordt bereikt.

## Stap 3: Verificatie

Nadat het archief is opgeslagen, kun je een eenvoudige bevestigingsmelding weergeven.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Voer het programma uit en probeer vervolgens `archive.7z` te openen met een tool zoals 7‑Zip. Er wordt voor elk item om een wachtwoord gevraagd, wat bevestigt dat de wachtwoorden inderdaad verschillend zijn.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Foutmelding onjuist wachtwoord** | Het wachtwoord bevat onbedoelde spaties of onzichtbare tekens. | Trim de wachtwoord‑strings (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archief kan niet worden geopend in oudere tools** | Sommige legacy ZIP‑tools ondersteunen geen AES‑256‑versleuteling die door 7z wordt gebruikt. | Gebruik een moderne extractor (7‑Zip 19.00+). |
| **Bestand niet toegevoegd aan archief** | Het pad naar het bronbestand is onjuist of het bestand bestaat niet. | Controleer `dataDir` en de bestandsnamen, of gebruik `Path.Combine(dataDir, "data1.bin")`. |

## Veelgestelde vragen

### Q1: Is Aspose.Zip voor .NET compatibel met alle versies van .NET?

A1: Ja, Aspose.Zip voor .NET is ontworpen om naadloos te integreren met alle versies van het .NET‑framework.

### Q2: Kan ik Aspose.Zip voor .NET gebruiken in mijn commerciële projecten?

A2: Absoluut! Aspose.Zip voor .NET biedt commerciële licenties, en je kunt meer informatie vinden over aanschaf [hier](https://purchase.aspose.com/buy).

### Q3: Is er een gratis proefversie beschikbaar?

A3: Ja, je kunt de functies van Aspose.Zip voor .NET uitproberen met een gratis proefversie. Begin [hier](https://releases.aspose.com/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?

A4: Voor vragen of hulp, bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37).

### Q5: Kan ik Aspose.Zip voor .NET gebruiken zonder een permanente licentie?

A5: Ja, je kunt een tijdelijke licentie verkrijgen voor kortetermijnbehoeften. Meer details vind je [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie

Je hebt zojuist geleerd **hoe zip te versleutelen** met per‑item wachtwoorden met behulp van Aspose.Zip voor .NET. Deze techniek geeft je de flexibiliteit om elk bestand afzonderlijk te beschermen, waardoor je aan strengere beveiligingsvereisten voldoet en gebruikersspecifieke distributie vereenvoudigt. Voel je vrij om te experimenteren met andere compressie‑instellingen, grotere bestandssets, of om deze logica te integreren in een webservice die veilig archieven on‑the‑fly genereert.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}