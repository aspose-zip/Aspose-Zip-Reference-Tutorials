---
date: 2025-12-20
description: Leer hoe je met wachtwoord beveiligde zip‑archieven maakt in .NET met
  Aspose.Zip. Deze stapsgewijze handleiding laat zien hoe je bestanden comprimeert
  met wachtwoorden, een zip‑entry‑wachtwoord instelt en AES‑encryptie gebruikt.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Maak wachtwoordbeveiligde ZIP‑bestanden in .NET met Aspose.Zip
url: /nl/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak wachtwoordbeveiligde ZIP‑bestanden in .NET met Aspose.Zip

## Introductie

Als je **wachtwoordbeveiligde zip**‑archieven moet maken in een .NET‑applicatie, maakt Aspose.Zip het eenvoudig. Door elk item een uniek wachtwoord toe te wijzen, kun je gevoelige documenten veilig houden en toch profiteren van het gemak van ZIP‑compressie. In deze tutorial leer je hoe je bestanden comprimeert met individuele wachtwoorden, verschillende encryptiemethoden kiest en een zip‑item‑wachtwoord instelt — alles met duidelijke, productie‑klare code.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip voor .NET.  
- **Kan ik per bestand een ander wachtwoord toewijzen?** Ja, elk item kan een eigen wachtwoord hebben.  
- **Welke encryptie‑algoritmen worden ondersteund?** Traditionele ZipCrypto, AES‑128 en AES‑256.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Is dit compatibel met .NET 6+?** Absoluut — de API richt zich op .NET Standard 2.0 en later.

## Wat betekent “wachtwoordbeveiligde zip maken”?
Een wachtwoordbeveiligde zip maken betekent encryptie toevoegen aan één of meer items binnen een ZIP‑archief zodat de inhoud niet kan worden geopend zonder het juiste wachtwoord. Dit is ideaal voor het verzenden van vertrouwelijke bestanden, het opslaan van back‑ups of het voldoen aan gegevensbeschermingsbeleid.

## Waarom Aspose.Zip gebruiken voor wachtwoordbeveiligde archieven?
- **Fijne controle** – stel een uniek wachtwoord per bestand in.  
- **Meerdere encryptie‑opties** – van legacy ZipCrypto tot sterke AES‑128/256.  
- **Geen externe afhankelijkheden** – pure .NET‑bibliotheek, eenvoudig te integreren.  
- **Uitgebreide documentatie** – bevat een **Aspose Zip‑tutorial** voor diepere scenario's.

## Voorvereisten

Voordat je aan de tutorial begint, zorg dat je de volgende zaken hebt:

- Aspose.Zip voor .NET: Zorg ervoor dat je de Aspose.Zip‑bibliotheek hebt geïnstalleerd in je .NET‑project. Je kunt de benodigde documentatie [hier](https://reference.aspose.com/zip/net/) vinden.  
- Download: Als je dat nog niet hebt gedaan, download de Aspose.Zip voor .NET‑bibliotheek via [deze link](https://releases.aspose.com/zip/net/).  
- Documentmap: Bereid een map voor die de bestanden bevat die je wilt comprimeren.

## Import Namespaces

Zorg ervoor dat je in je .NET‑project de benodigde namespaces importeert:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Stap 1: Stel het pad naar de resource‑directory in

Definieer het pad naar de resource‑directory waar je bronbestanden zich bevinden.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Comprimeer bestanden met individuele wachtwoorden

Laten we nu bestanden comprimeren met individuele wachtwoorden. We gebruiken drie voorbeeldbestanden (`alice29.txt`, `asyoulik.txt` en `fields.c`) met verschillende wachtwoorden voor elk. Dit laat zien hoe je **bestanden comprimeert met wachtwoorden** en ook hoe je **zip‑item‑wachtwoord** instelt met verschillende encryptieschema’s, inclusief een **zip‑archief met aes**.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Hoe dit werkt
- **TraditionalEncryptionSettings** gebruikt het oudere ZipCrypto‑algoritme (compatibel met de meeste ZIP‑hulpmiddelen).  
- **AesEcryptionSettings** laat je AES‑128 of AES‑256 kiezen voor sterkere beveiliging.  
- Elke `CreateEntry`‑aanroep krijgt een `ArchiveEntrySettings`‑object waarin we zowel de compressiemethode als de encryptie‑instellingen specificeren, waardoor **zip‑archief‑items met wachtwoord** worden beveiligd.

## Veelvoorkomende problemen en oplossingen

| Issue | Reason | Fix |
|-------|--------|-----|
| “Invalid password” when opening the ZIP | Mismatch tussen het wachtwoord dat in de code wordt gebruikt en het wachtwoord dat in de extractor wordt ingevoerd | Controleer de exacte tekenreeks die wordt doorgegeven aan `TraditionalEncryptionSettings` of `AesEcryptionSettings`. |
| Older extraction tools cannot open AES‑encrypted entries | Niet alle ZIP‑hulpmiddelen ondersteunen AES‑versleuteling | Gebruik de traditionele ZipCrypto‑methode voor maximale compatibiliteit, of adviseer gebruikers een modern hulpmiddel te gebruiken (bijv. 7‑Zip). |
| Large files cause `OutOfMemoryException` | Grote bestanden in het geheugen laden vóór compressie | Stream het bestand direct met `FileStream` zonder het volledige bestand in een `FileInfo`‑object te laden. |

## Veelgestelde vragen (FAQ)

### Kan ik verschillende encryptiemethoden per bestand gebruiken?
Ja, Aspose.Zip voor .NET stelt je in staat verschillende encryptiemethoden per bestand te gebruiken tijdens het comprimeren.

### Is er een proefversie beschikbaar?
Ja, je kunt de gratis proefversie van Aspose.Zip voor .NET [hier](https://releases.aspose.com/) verkrijgen.

### Hoe krijg ik ondersteuning als ik problemen tegenkom?
Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor hulp van de community en Aspose‑ondersteuning.

### Waar vind ik gedetailleerde documentatie voor Aspose.Zip voor .NET?
De documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/).

### Kan ik een tijdelijke licentie aanschaffen voor testdoeleinden?
Ja, je kunt een tijdelijke licentie aanschaffen [hier](https://purchase.aspose.com/temporary-license/).

## Extra snelle FAQ

**V: Ondersteunt de bibliotheek .NET Core en .NET 5/6?**  
**A:** Ja, Aspose.Zip richt zich op .NET Standard, waardoor het compatibel is met .NET Framework, .NET Core en .NET 5/6.

**V: Kan ik een opmerking toevoegen aan elk ZIP‑item?**  
**A:** Hoewel Aspose.Zip zich richt op compressie en encryptie, kun je metadata opslaan in een apart manifest‑bestand binnen het archief.

**V: Is het mogelijk om het hele archief met één wachtwoord te versleutelen?**  
**A:** Je kunt een wachtwoord per item instellen (zoals getoond) of hetzelfde wachtwoord op alle items toepassen voor een eenvoudigere “zip‑archief‑met‑aes” aanpak.

## Conclusie

Je hebt nu geleerd hoe je **wachtwoordbeveiligde zip**‑bestanden in .NET kunt maken met Aspose.Zip. Door individuele wachtwoorden toe te wijzen en de juiste encryptiemethode te kiezen, kun je je gegevens veilig houden zonder in te leveren op het gemak van ZIP‑compressie. Ontdek andere Aspose.Zip‑functies zoals het streamen van grote bestanden, het toevoegen van aangepaste metadata en integratie met cloudopslag voor nog krachtigere scenario's.

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.Zip voor .NET 23.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}