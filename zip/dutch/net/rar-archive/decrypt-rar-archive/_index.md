---
description: Leer hoe u RAR-bestanden naar een map kunt uitpakken en versleutelde
  RAR-bestanden kunt ontsleutelen met Aspose.Zip voor .NET. Volg de stapsgewijze handleiding
  om een versleuteld RAR‑bestand te lezen en het RAR‑wachtwoord op te geven.
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: RAR uitpakken naar map met Aspose.Zip voor .NET
url: /nl/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extract RAR to Folder with Aspose.Zip for .NET

## Introductie

Als je **extract RAR to folder** wilt en wilt werken met met wachtwoord‑protected archives, maakt Aspose.Zip for .NET het werk moeiteloos. In deze tutorial lopen we de exacte stappen door om een encrypted RAR file te lezen, het RAR‑wachtwoord op te geven, en de inhoud van het archief naar een target directory te extraheren. Of je nu een desktop utility of een server‑side service bouwt, je ziet hoe je de decryptielogica snel en betrouwbaar kunt integreren.

## Snelle antwoorden
- **Wat betekent “extract RAR to folder”?** Het betekent een RAR‑archive openen en elke entry naar een opgegeven directory op disk schrijven.  
- **Welke bibliotheek behandelt de decryptie?** Aspose.Zip for .NET provides built‑in support for encrypted RAR archives.  
- **Heb ik een licentie nodig voor testen?** Een tijdelijke licentie is beschikbaar voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten voor een basic extraction scenario.

## Wat is “extract RAR to folder”?
Een RAR‑archive naar een folder extraheren betekent het decompressen van elk bestand dat in het archief is opgeslagen en deze plaatsen in een directory die je kiest. Wanneer het archief versleuteld is, moet je ook het juiste wachtwoord opgeven voordat extractie kan plaatsvinden.

## Waarom Aspose.Zip gebruiken om versleutelde RAR te extraheren?
Aspose.Zip abstracts the complexities of the RAR format, handling both standard and encrypted archives without external dependencies. Het biedt een clean, object‑oriented API, strong performance, en excellent error handling—perfect voor .NET developers die een reliable solution zoeken voor **how to decrypt RAR** files.

## Voorvereisten

Voordat je aan de tutorial begint, zorg ervoor dat je de volgende voorvereisten hebt:

1. Aspose.Zip for .NET Library: Zorg ervoor dat je de Aspose.Zip library installed in your .NET project. Je kunt deze downloaden van de [Aspose.Zip documentation](https://reference.aspose.com/zip/net/).

2. Document Directory: Maak een directory aan waar je encrypted RAR archive zich bevindt. Vervang "Your Document Directory" in de example code met het actual path to this directory.

## Namespaces importeren

Laten we beginnen met het importeren van de benodigde namespaces om de Aspose.Zip library effectively te gebruiken. Voeg de volgende lines toe aan de top of your .NET file:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Stap 1 – Open het versleutelde RAR‑archive

Open eerst een read‑only stream voor het encrypted RAR file. Dit prepares the file for decryption en extraction.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Stap 2 – Specificeer het RAR‑wachtwoord (how to decrypt RAR)

Maak nu een `RarArchive` instance en vertel Aspose.Zip het password dat het archive beschermt. Vervang `"p@s$"` met het actual password dat je gebruikte toen je de encrypted RAR maakte.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Stap 3 – Inhoud extraheren naar een folder (extract encrypted RAR)

Tot slot, extract every entry naar de folder of your choice. Dit completes the **extract RAR to folder** operation.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

Herhaal deze steps voor each RAR archive die je moet decrypten, ensuring a seamless integration of Aspose.Zip for .NET into your project.

## Veelvoorkomende valkuilen & tips

- **Incorrect password** – Als het password onjuist is, gooit Aspose.Zip een `WrongPasswordException`. Double‑check de string die je pass to `DecryptionPassword`.
- **Large archives** – Voor zeer grote RAR files, consider extracting to a temporary folder first en dan moving files to the final location om te avoid running out of disk space.
- **Path safety** – Always validate `dataDir` en output paths om directory‑traversal vulnerabilities te voorkomen.

## Conclusie

Gefeliciteerd! Je hebt succesvol **extracted a RAR to folder** en geleerd hoe je **read encrypted RAR file** kunt gebruiken met Aspose.Zip for .NET. Deze powerful library vereenvoudigt het complex process of unlocking password‑protected archives, waardoor het een invaluable tool is voor developers die werken met .NET applications.

## Veelgestelde vragen (FAQ's)

### Is Aspose.Zip for .NET compatible with all RAR archive versions?
Aspose.Zip for .NET supports various RAR archive versions, ensuring compatibility with a wide range of files.

### Kan ik Aspose.Zip for .NET gebruiken in commerciële projecten?
Ja, Aspose.Zip for .NET is available for commercial use. Bezoek de [purchase page](https://purchase.aspose.com/buy) voor licensing details.

### Zijn tijdelijke licenties beschikbaar voor testdoeleinden?
Ja, je kunt een temporary license voor testing verkrijgen via [here](https://purchase.aspose.com/temporary-license/).

### Waar kan ik extra support of community discussions vinden?
Bezoek het [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) voor support en community discussions.

### Hoe krijg ik toegang tot de documentatie voor Aspose.Zip for .NET?
De [documentation](https://reference.aspose.com/zip/net/) provides comprehensive information on using Aspose.Zip for .NET.

**Additional Q&A**

**Q:** Hoe kan ik alleen specifieke bestanden uit een versleutelde RAR extraheren?  
**A:** Gebruik `RarArchiveEntry` om de gewenste entry te vinden en roep `ExtractToFile` aan met het decryption password al ingesteld op het archive.

**Q:** Wat als ik de naam van de output folder dynamisch moet wijzigen?  
**A:** Bouw het output path using `Path.Combine` en any runtime variables before calling `ExtractToDirectory`.

**Q:** Ondersteunt Aspose.Zip multi‑volume RAR archives?  
**A:** Ja, de library can open and extract multi‑volume RAR sets as long as all parts are accessible.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}