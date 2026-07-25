---
date: 2026-05-15
description: Leer hoe u met wachtwoord beveiligde zip‑bestanden maakt en bestanden
  comprimeert met wachtwoorden met behulp van Aspose.Zip voor .NET in een paar eenvoudige
  stappen.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Bestanden comprimeren met individuele wachtwoorden
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Maak een met wachtwoord beveiligde ZIP in .NET met Aspose.Zip
url: /nl/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een met wachtwoord beveiligde ZIP in .NET met Aspose.Zip

## Introductie

In deze tutorial leer je hoe je **wachtwoordbeveiligde zip**-bestanden maakt in een .NET-toepassing met behulp van Aspose.Zip. Veilige compressie is essentieel wanneer je vertrouwelijke gegevens moet verzenden of gevoelige documenten moet opslaan zonder ze bloot te stellen aan onbevoegde toegang.

**Aspose.Zip** is een .NET-bibliotheek die het mogelijk maakt ZIP-archieven programmatically te maken, lezen en versleutelen. Het ondersteunt AES‑256 encryptie en laat je een uniek wachtwoord toewijzen aan elk item in het archief.

## Snelle Antwoorden
- **Wat doet Aspose.Zip?** Het maakt en bewerkt ZIP-archieven, inclusief per‑bestand wachtwoordbeveiliging.  
- **Hoeveel wachtwoorden kan ik toewijzen?** Eén uniek wachtwoord per bestand; onbeperkt aantal items.  
- **Welke encryptie-algoritme wordt gebruikt?** AES‑256, biedt 256‑bit beveiliging.  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productie.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vereisten

Voordat je aan de tutorial begint, zorg dat je de volgende vereisten hebt:

- Aspose.Zip voor .NET: Zorg ervoor dat je de Aspose.Zip-bibliotheek hebt geïnstalleerd in je .NET-project. Je kunt de benodigde documentatie vinden [hier](https://reference.aspose.com/zip/net/).

- Download: Als je dit nog niet hebt gedaan, download de Aspose.Zip voor .NET-bibliotheek via [deze link](https://releases.aspose.com/zip/net/).

- Documentmap: Bereid een map voor die de bestanden bevat die je wilt comprimeren.

## Namespaces Importeren

Zorg ervoor dat je in je .NET-project de benodigde namespaces importeert:

`ZipFile` is de primaire klasse van Aspose.Zip voor het maken van ZIP-archieven en het toewijzen van individuele wachtwoorden aan elk item.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Hoe maak je wachtwoordbeveiligde zip-bestanden in .NET?

Laad de doelmap, maak een `ZipFile`-object aan, voeg elk bestand toe met zijn eigen wachtwoord, en roep vervolgens `Save` aan om het archief te schrijven. Dit volledige proces vereist slechts een paar regels code en garandeert dat elk item wordt versleuteld met het door jou opgegeven wachtwoord.

### Stap 1: Stel het pad naar de resource‑directory in

Definieer het pad naar de resource‑directory waar je bestanden zich bevinden.

```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Bestanden comprimeren met individuele wachtwoorden

Laten we nu bestanden comprimeren met individuele wachtwoorden. We gebruiken drie voorbeeldbestanden (`alice29.txt`, `asyoulik.txt` en `fields.c`) met elk een verschillend wachtwoord.

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

## Waarom wachtwoordbeveiliging gebruiken voor ZIP-archieven?

Aspose.Zip ondersteunt **meer dan 30 compressie‑algoritmen** en kan archieven versleutelen met AES‑256, waardoor tot **256‑bit beveiliging** wordt geboden. Het kan archieven van honderden megabytes verwerken zonder het volledige bestand in het geheugen te laden, wat het ideaal maakt voor high‑performance server‑side scenario's. Bovendien helpt wachtwoordbeveiliging te voldoen aan regelgeving zoals GDPR en HIPAA door ervoor te zorgen dat gevoelige gegevens zowel in rust als tijdens verzending versleuteld blijven.

## Conclusie

Gefeliciteerd! Je hebt met succes geleerd hoe je **wachtwoordbeveiligde zip**-bestanden maakt en **bestanden comprimeert met wachtwoorden** met behulp van Aspose.Zip voor .NET. Deze functie voegt een extra beveiligingslaag toe aan je gecomprimeerde bestanden, waardoor vertrouwelijkheid en naleving van gegevensbeschermingsbeleid worden gewaarborgd.

## Veelgestelde Vragen

**V: Kan ik verschillende encryptiemethoden gebruiken voor elk bestand?**  
A: Ja, Aspose.Zip laat je het encryptie‑algoritme (bijv. AES‑256) kiezen voor elk item wanneer je het aan het archief toevoegt.

**V: Is er een proefversie beschikbaar?**  
A: Ja, je kunt de gratis proefversie van Aspose.Zip voor .NET [hier](https://releases.aspose.com/) vinden.

**V: Hoe kan ik ondersteuning krijgen als ik problemen ondervind?**  
A: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor hulp van de community en Aspose‑ondersteuning.

**V: Waar kan ik gedetailleerde documentatie vinden voor Aspose.Zip voor .NET?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/).

**V: Kan ik een tijdelijke licentie aanschaffen voor testdoeleinden?**  
A: Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-05-15  
**Getest met:** Aspose.Zip 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde Tutorials

- [Maak een met wachtwoord beveiligde ZIP met Aspose.Zip voor .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [ZIP-bestanden beveiligen met wachtwoord en AES-encryptie met Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Meerdere bestanden comprimeren met encryptie in Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}