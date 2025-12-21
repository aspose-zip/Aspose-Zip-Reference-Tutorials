---
date: 2025-12-21
description: Leer hoe u wachtwoordbeveiligde zip‑bestanden maakt in .NET, mappen versleutelt
  en het zip‑wachtwoord wijzigt met Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Maak een wachtwoordbeveiligde zip voor .NET-mappen – Aspose.Zip Tutorial
url: /nl/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een wachtwoordbeveiligde zip voor .NET-mappen – Aspose.Zip Tutorial

In deze gids maak je **wachtwoordbeveiligde zip**-archieven voor volledige mappen met behulp van de Aspose.Zip-bibliotheek voor .NET. Of je nu een **map wilt versleutelen**, back‑upbestanden wilt beveiligen, of simpelweg de toegang tot gevoelige gegevens wilt beperken, deze stap‑voor‑stap tutorial laat je precies zien hoe je dit doet met nette C#-code.

## Snelle antwoorden
- **Welke bibliotheek wordt aanbevolen?** Aspose.Zip for .NET  
- **Kan ik een volledige map versleutelen?** Ja – wijs de API gewoon op de map die je wilt zippen.  
- **Wordt het wijzigen van het zip-wachtwoord ondersteund?** Absoluut, gebruik `TraditionalEncryptionSettings`.  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Zip-licentie is vereist voor commercieel gebruik.  
- **Werkt het met .NET Core/5/6?** Ja, de API is volledig compatibel met moderne .NET-runtime.  

## Wat is “create password protected zip”?
Een wachtwoordbeveiligde zip maken betekent dat je bestanden of mappen comprimeert tot een ZIP-archief en daarbij encryptie toepast, zodat het archief alleen kan worden geopend met het juiste wachtwoord. Dit beschermt de inhoud tegen ongeautoriseerde toegang.

## Waarom Aspose.Zip gebruiken voor wachtwoordbeveiliging van mappen in .NET?
Aspose.Zip biedt een eenvoudige, high‑performance API die **c# zip password protection** ondersteunt, traditionele ZipCrypto-encryptie en AES-encryptie. Het verwerkt grote mappen efficiënt en integreert naadloos met elk .NET‑project.

## Vereisten
- Basiskennis van C#-programmeren.  
- Visual Studio (een recente editie).  
- Aspose.Zip for .NET bibliotheek – download deze **[hier](https://releases.aspose.com/zip/net/)**.  
- Een map op de schijf die je wilt beveiligen met een wachtwoord.

## Namespaces importeren
Voeg de benodigde namespaces toe aan je C#‑bestand zodat de compiler weet waar de Aspose.Zip‑klassen te vinden zijn.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Stap 1: Stel het pad naar de resource‑directory in
Definieer het pad dat naar de map wijst die je wilt zippen en beveiligen.

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Beveilig de map met een wachtwoord
Gebruik `TraditionalEncryptionSettings` om het wachtwoord op te geven en het versleutelde archief te maken. Dit is de kern van **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Stap 3: Uitleg van de code
- **Het output‑bestand maken:** `File.Open(..., FileMode.Create)` opent (of maakt) het ZIP‑bestand dat de versleutelde gegevens zal bevatten.  
- **De bronmap selecteren:** `new DirectoryInfo(".\\CanterburyCorpus")` geeft Aspose.Zip aan welke map moet worden gecomprimeerd.  
- **Het wachtwoord toepassen:** `new TraditionalEncryptionSettings("p@s$")` stelt het wachtwoord in dat het archief zal beveiligen.  
- **Items toevoegen & opslaan:** `archive.CreateEntries(corpus)` voegt elk bestand in de map toe, en `archive.Save(zipFile)` schrijft de versleutelde ZIP naar de schijf.

## Hoe het zip‑wachtwoord later wijzigen?
Als je het **zip‑wachtwoord wilt wijzigen**, maak dan simpelweg het archief opnieuw met een nieuwe `TraditionalEncryptionSettings`‑instantie die het nieuwe wachtwoord bevat, en sla het vervolgens opnieuw op.

## Veelvoorkomende problemen & tips
- **Grote mappen:** Aspose.Zip streamt gegevens, waardoor het geheugenverbruik laag blijft, zelfs bij enorme mappen.  
- **Wachtwoordcomplexiteit:** Gebruik een sterk wachtwoord (mix van letters, cijfers, symbolen) om de beveiliging te verbeteren.  
- **Licentiefouten:** Zorg ervoor dat je een geldig licentiebestand hebt toegepast; anders draait de bibliotheek in evaluatiemodus met beperkingen.

## Veelgestelde vragen

### Is Aspose.Zip for .NET geschikt voor grote mappen?
Ja, Aspose.Zip for .NET is ontworpen om grote mappen efficiënt te verwerken, met optimale prestaties.

### Kan ik het wachtwoord wijzigen voor een al beveiligde map?
Ja, je kunt het wachtwoord wijzigen door de `TraditionalEncryptionSettings` in de code dienovereenkomstig aan te passen.

### Zijn er licentievereisten voor het gebruik van Aspose.Zip for .NET?
Ja, een geldige licentie is vereist voor het gebruik van Aspose.Zip for .NET in een productieomgeving. Je kunt een licentie verkrijgen **[hier](https://purchase.aspose.com/buy)**.

### Is er een gratis proefversie beschikbaar voor Aspose.Zip for .NET?
Ja, je kunt een gratis proefversie krijgen **[hier](https://releases.aspose.com/)**.

### Waar kan ik extra ondersteuning vinden voor Aspose.Zip for .NET?
Je kunt het **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** bezoeken voor ondersteuning of vragen.

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.Zip for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}