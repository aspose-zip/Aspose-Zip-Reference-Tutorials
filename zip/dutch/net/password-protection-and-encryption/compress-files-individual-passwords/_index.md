---
date: 2026-03-02
description: Leer hoe u een met wachtwoord beveiligd zip‑archief maakt en bestanden
  comprimeert met wachtwoorden in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Maak een wachtwoordbeveiligd ZIP-archief in .NET met Aspose.Zip
url: /nl/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een met wachtwoord beveiligd ZIP‑archief in .NET met Aspose.Zip

## Inleiding

Wanneer u gevoelige gegevens moet delen, is een **met wachtwoord beveiligd zip‑archief** een van de eenvoudigste maar meest effectieve manieren om informatie veilig te houden. In .NET‑toepassingen maakt Aspose.Zip het eenvoudig om **bestanden met wachtwoorden te comprimeren**, waarbij elk bestand zijn eigen encryptiesleutel krijgt. In deze tutorial leert u precies hoe u zo’n archief maakt, waarom het belangrijk is en waar u het kunt toepassen in real‑world projecten.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip voor .NET biedt ingebouwde ondersteuning voor wachtwoorden per bestand en meerdere encryptiemethoden.  
- **Hoeveel regels code?** Ongeveer 30 regels, inclusief setup en het opslaan van het archief.  
- **Kan elk bestand een ander wachtwoord hebben?** Ja – u kunt een uniek wachtwoord toewijzen aan elke entry.  
- **Welke encryptiemethoden zijn beschikbaar?** Traditionele ZipCrypto, AES‑128 en AES‑256.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.

## Wat is een met wachtwoord beschermd zip‑archief?
Een met wachtwoord beschermd zip‑archief is een gecomprimeerd bestand (ZIP) dat een wachtwoord vereist om de inhoud te extraheren. Het wachtwoord kan het gehele archief of individuele entries beschermen, en moderne algoritmen zoals AES‑128/256 bieden sterke encryptie.

## Waarom bestanden met wachtwoorden comprimeren met Aspose.Zip?
- **Granulaire beveiliging** – wijs een afzonderlijk wachtwoord per bestand toe, ideaal voor multi‑tenant scenario’s.  
- **Meerdere encryptienormen** – kies tussen legacy ZipCrypto en sterke AES.  
- **Geen externe tools** – alles wordt programmatisch afgehandeld binnen uw .NET‑codebase.  
- **Prestaties** – snelle compressie met Deflate terwijl de archiefgrootte klein blijft.

## Vereisten

Voordat u begint, zorg ervoor dat u het volgende heeft:

- **Aspose.Zip voor .NET** – installeer de bibliotheek in uw project. Gedetailleerde documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/).  
- **Download het nieuwste pakket** als u dat nog niet heeft gedaan, via [deze link](https://releases.aspose.com/zip/net/).  
- Een map met de bestanden die u wilt comprimeren.

## Namespaces importeren

Voeg de benodigde namespaces toe aan de bovenkant van uw C#‑bestand:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Stap 1: Het pad van de resource‑directory instellen

Verwijs de code naar de map die de bronbestanden bevat:

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Bestanden comprimeren met individuele wachtwoorden

Nu maken we een **met wachtwoord beschermd zip‑archief** waarbij elk bestand zijn eigen wachtwoord en encryptiemethode gebruikt. Het voorbeeld gebruikt drie voorbeeldbestanden (`alice29.txt`, `asyoulik.txt` en `fields.c`) met verschillende wachtwoorden.

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

### Hoe het werkt
- **CreateEntry** voegt een bestand toe aan het archief.  
- Het vierde argument (`ArchiveEntrySettings`) stelt u in staat zowel compressie (`DeflateCompressionSettings`) als encryptie (`TraditionalEncryptionSettings` of `AesEcryptionSettings`) te specificeren.  
- Door voor elke entry een andere wachtwoord‑string door te geven, krijgt u een **met wachtwoord beschermd zip‑archief** waarbij elk bestand alleen met zijn eigen sleutel kan worden ontgrendeld.

## Veelvoorkomende problemen & foutoplossing

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Extraction fails with “Wrong password” | Password mismatch or wrong encryption method | Verify the exact password string and ensure you used the same `EncryptionMethod` when extracting. |
| Archive size is larger than expected | Using AES‑256 on small text files can add overhead | For small files, AES‑128 may be sufficient and yields a smaller archive. |
| Runtime exception on `archive.Save` | Missing write permission on the target folder | Ensure the application has write access to `dataDir` or use a different output path. |

## Veelgestelde vragen (FAQ)

### Kan ik verschillende encryptiemethoden per bestand gebruiken?
Ja, Aspose.Zip voor .NET stelt u in staat om encryptiemethoden te mixen — traditionele ZipCrypto, AES‑128 en AES‑256 — op bestandsniveau.

### Is er een proefversie beschikbaar?
Ja, u kunt de gratis proefversie van Aspose.Zip voor .NET [hier](https://releases.aspose.com/) verkrijgen.

### Hoe kan ik ondersteuning krijgen als ik problemen ondervind?
Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) voor hulp van de community en Aspose‑ondersteuning.

### Waar vind ik gedetailleerde documentatie voor Aspose.Zip voor .NET?
De documentatie is beschikbaar [hier](https://reference.aspose.com/zip/net/).

### Kan ik een tijdelijke licentie aanschaffen voor testdoeleinden?
Ja, u kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-02  
**Getest met:** Aspose.Zip voor .NET (latest release)  
**Auteur:** Aspose  

---