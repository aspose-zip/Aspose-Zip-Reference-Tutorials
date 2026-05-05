---
date: 2026-05-05
description: Leer hoe je bestanden comprimeert met een wachtwoord en ZIP‑archieven
  versleutelt met Aspose.Zip voor .NET, inclusief 7z‑wachtwoordbeveiliging en per‑bestand
  zip‑wachtwoord in C#.
keywords:
- compress files with password
- how to encrypt zip
- aes 256 zip encryption
- encrypt zip entries
- per file zip password
linktitle: Invoeren met verschillende wachtwoorden
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe bestanden comprimeren met wachtwoord en ZIP‑items versleutelen met verschillende
  wachtwoorden met Aspose.Zip voor .NET
url: /nl/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe bestanden comprimeren met wachtwoord en ZIP‑items versleutelen met verschillende wachtwoorden met Aspose.Zip voor .NET

## Introductie

Als je **bestanden wilt comprimeren met wachtwoord** en elk item een eigen wachtwoord wilt geven, ben je hier aan het juiste adres. In deze tutorial lopen we stap voor stap door hoe je een 7‑zip‑archief maakt waarbij elk bestand wordt beschermd met een uniek wachtwoord, met behulp van de Aspose.Zip‑bibliotheek voor .NET. Aan het einde begrijp je waarom encryptie per item belangrijk is, hoe je het instelt en hoe je het resultaat in je eigen projecten kunt verifiëren.

## Snelle antwoorden
- **Wat betekent “encrypt zip”?** Het betekent het toepassen van wachtwoord‑gebaseerde bescherming (AES of ZipCrypto) op de inhoud van een ZIP/7z‑archief.  
- **Kan elk item een ander wachtwoord hebben?** Ja—Aspose.Zip stelt je in staat om verschillende wachtwoorden per bestand toe te wijzen.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework, .NET Core en .NET 5/6 versies.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Welk compressieformaat wordt in het voorbeeld gebruikt?** Het voorbeeld maakt een 7z‑archief met AES‑256‑encryptie.

## Wat betekent “how to encrypt zip” met Aspose.Zip?

Een ZIP‑ (of 7z‑) bestand versleutelen betekent dat je de items beveiligt zodat ze niet geopend kunnen worden zonder het juiste wachtwoord. Aspose.Zip voor .NET ondersteunt zowel klassieke ZipCrypto als sterkere AES‑encryptie, en stelt je in staat om encryptie‑instellingen per item op te geven, waardoor je fijne controle over de beveiliging hebt.

## Waarom bestanden comprimeren met wachtwoord?

- **Beveiligingssegmentatie:** Als één wachtwoord wordt gecompromitteerd, blijven de andere bestanden beschermd.  
- **Regelgeving naleving:** Bepaalde sectoren verplichten aparte inloggegevens voor verschillende datacategorieën.  
- **Gebruiker‑specifieke distributie:** Een enkel archief kan naar veel gebruikers worden verzonden, waarbij elke gebruiker alleen de bestanden kan ontgrendelen die hij mag zien.

## Waarom AES 256 zip‑encryptie gebruiken?

AES‑256 is de huidige industriestandaard voor sterke symmetrische encryptie. Vergeleken met ZipCrypto weerstaat het moderne brute‑force‑aanvallen en is het volledig compatibel met 7‑Zip en andere hedendaagse extractors. Wanneer je **aes 256 zip encryptie** nodig hebt, maakt Aspose.Zip de configuratie eenvoudig.

## Voorvereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- **Aspose.Zip for .NET** geïnstalleerd – zie de officiële [documentation](https://reference.aspose.com/zip/net/) voor download‑ en installatie‑instructies.  
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

Voer het programma uit en probeer vervolgens `archive.7z` te openen met een tool zoals 7‑Zip. Het zal je om een wachtwoord voor elk item vragen, waarmee wordt bevestigd dat de wachtwoorden inderdaad verschillend zijn.

## Zip‑items versleutelen met per‑bestand zip‑wachtwoord – best practices

Wanneer je **zip‑items versleutelt** met een per‑bestand wachtwoord, houd dan de volgende tips in gedachten:

1. **Gebruik sterke, unieke wachtwoorden** – vermijd veelvoorkomende woorden en hergebruik.  
2. **Bewaar wachtwoorden veilig** – overweeg een wachtwoordmanager of een veilige kluis als je ze moet distribueren.  
3. **Test met meerdere tools** – zorg ervoor dat zowel 7‑Zip als WinRAR het archief kunnen lezen, aangezien sommige oudere tools AES‑256 mogelijk niet ondersteunen.  
4. **Documenteer de wachtwoord‑bestand mapping** – een eenvoudige CSV (bestand, wachtwoord) helpt beheerders bij te houden welk wachtwoord bij welk item hoort.

## Zip‑archief wachtwoordbeveiliging – veelvoorkomende valkuilen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Onjuiste wachtwoordfout** | Wachtwoordreeks bevat vreemde spaties of onzichtbare tekens. | Trim de wachtwoordreeksen (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archief opent niet in oudere tools** | Sommige oudere ZIP‑tools ondersteunen de AES‑256‑encryptie die door 7z wordt gebruikt niet. | Gebruik een moderne extractor (7‑Zip 19.00+). |
| **Bestand niet toegevoegd aan archief** | Bronbestandspad is onjuist of bestand bestaat niet. | Controleer `dataDir` en de bestandsnamen, of gebruik `Path.Combine(dataDir, "data1.bin")`. |

## Veelgestelde vragen

### Q1: Is Aspose.Zip voor .NET compatibel met alle .NET‑versies?

A1: Ja, Aspose.Zip voor .NET is ontworpen om naadloos te integreren met alle versies van het .NET‑framework.

### Q2: Kan ik Aspose.Zip voor .NET gebruiken in mijn commerciële projecten?

A2: Absoluut! Aspose.Zip voor .NET biedt commerciële licenties, en je kunt meer informatie vinden over hoe je kunt kopen [hier](https://purchase.aspose.com/buy).

### Q3: Is er een gratis proefversie beschikbaar?

A3: Ja, je kunt de functies van Aspose.Zip voor .NET verkennen met een gratis proefversie. Begin [hier](https://releases.aspose.com/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?

A4: Voor vragen of hulp, bezoek het [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Kan ik Aspose.Zip voor .NET gebruiken zonder een permanente licentie?

A5: Ja, je kunt een tijdelijke licentie verkrijgen voor je kortetermijnbehoeften. Meer details vind je [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie

Je hebt zojuist geleerd **hoe bestanden te comprimeren met wachtwoord** en ZIP‑archieven te versleutelen met per‑item wachtwoorden met behulp van Aspose.Zip voor .NET. Deze techniek geeft je de flexibiliteit om elk bestand afzonderlijk te beschermen, voldoet aan strengere beveiligingseisen en vereenvoudigt gebruikersspecifieke distributie. Voel je vrij om te experimenteren met andere compressie‑instellingen, grotere bestandssets, of deze logica te integreren in een webservice die beveiligde archieven on‑the‑fly genereert.

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}