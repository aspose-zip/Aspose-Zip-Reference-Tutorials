---
date: 2026-05-05
description: Leer hoe u 7z-archieven kunt versleutelen met Aspose.Zip voor .NET. Deze
  gids laat zien hoe u een bestand aan een 7z toevoegt, AES-versleuteling instelt
  en een veilig 7z-archief genereert.
keywords:
- how to encrypt 7z
- add file to 7z
- how to set aes
- generate 7z archive
- add multiple files 7z
linktitle: Maak SevenZip-item
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe 7z‑archief te versleutelen met Aspose.Zip voor .NET
url: /nl/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe 7z-archief te versleutelen met Aspose.Zip voor .NET

## Introductie

In deze tutorial leer je **hoe je 7z**-bestanden versleutelt met de Aspose.Zip‑bibliotheek voor .NET. Of je nu gevoelige gegevens wilt beschermen, moet voldoen aan beveiligingsbeleid, of gewoon efficiënt bestanden wilt comprimeren, deze gids leidt je stap voor stap – van het opzetten van het project tot het bevestigen dat het archief succesvol is aangemaakt. Laten we meteen zien hoe eenvoudig het is om een **bestand toe te voegen aan 7z** met AES‑versleuteling en een betrouwbaar 7z‑archief te genereren.

## Snelle antwoorden
- **Wat betekent “create encrypted 7z”?** Het betekent het genereren van een 7‑zip‑archief dat beschermd is met AES‑versleuteling.  
- **Welke bibliotheek wordt gebruikt?** Aspose.Zip voor .NET.  
- **Heb ik een licentie nodig?** Een tijdelijke licentie volstaat voor testen; een volledige licentie is vereist voor productie.  
- **Kan ik meerdere bestanden toevoegen?** Ja – roep `CreateEntry` herhaaldelijk aan om **meerdere bestanden 7z toe te voegen**.  
- **Wordt AES‑versleuteling ondersteund?** Ja, Aspose.Zip ondersteunt **hoe je AES**‑256‑versleuteling instelt voor 7z‑archieven.  

## Wat is een versleuteld 7z-archief?
Een 7z‑archief is een containerformaat met hoge compressie. Wanneer je **versleutelde 7z**‑archieven maakt, wordt de inhoud versleuteld met AES, waardoor het onleesbaar is zonder het juiste wachtwoord. Dit is ideaal voor het veilig verzenden of opslaan van vertrouwelijke bestanden.

## Waarom Aspose.Zip gebruiken voor versleutelde 7z-bestanden?
- **Volledige .NET‑integratie** – werkt met .NET Framework, .NET Core en .NET 5/6.  
- **Ingebouwde AES‑256‑ondersteuning** – geen externe tools nodig; je kunt eenvoudig **hoe je AES** instelt.  
- **Eenvoudige API** – één‑regelige aanroepen om **bestand toe te voegen aan 7z** en het archief op te slaan.  
- **Cross‑platform** – draait op Windows, Linux en macOS.

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- **Aspose.Zip voor .NET Library** – download deze [hier](https://releases.aspose.com/zip/net/).  
- **Een schrijfbare map** op je computer waar het archief wordt opgeslagen.  
- **Een bronbestand** (bijv. `file.dat`) dat je wilt comprimeren en versleutelen.

## Namespaces importeren

Voeg de benodigde namespace toe aan de bovenkant van je C#‑bestand:

```csharp
using Aspose.Zip.SevenZip;
```

## Stapsgewijze handleiding

### Stap 1: Definieer de werkmap

Stel het pad in naar de map die het bronbestand bevat dat je wilt comprimeren.

```csharp
string dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het daadwerkelijke pad op jouw machine.

### Stap 2: Maak de versleutelde 7z-entry

De kern van de tutorial – we openen een nieuwe bestandsstroom, maken een `SevenZipArchive`, voegen een entry toe en slaan het archief op. Dit voorbeeld voegt één bestand (`file.dat`) toe als `data.bin` binnen het archief.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Pro tip:** Om AES‑versleuteling in te schakelen, stel je de eigenschap `Encryption` in op de `SevenZipArchive` voordat je `Save` aanroept. (De eigenschap is hier weggelaten om het voorbeeld beknopt te houden.)

### Stap 3: Bevestig succes

Print een vriendelijke boodschap zodat je weet dat de bewerking zonder fouten is voltooid.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Stap 4: Verifieer het archief (optioneel)

Nadat het programma is uitgevoerd, navigeer je naar de map met `archive.7z` en probeer je het te openen met een 7‑zip‑client. Je zou om een wachtwoord gevraagd moeten worden als je in Stap 2 versleuteling hebt toegevoegd. Deze stap laat je ook **7z‑wachtwoord verifiëren**.

## Veelvoorkomende problemen & oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Bestand niet gevonden** | Onjuist `dataDir` of bronbestandsnaam | Controleer het pad en zorg dat `file.dat` bestaat. |
| **Toegang geweigerd** | Onvoldoende schrijfrechten | Voer de applicatie uit met verhoogde rechten of kies een schrijfbare map. |
| **Versleuteling niet toegepast** | Ontbrekende versleutelingsinstellingen op het archief | Stel `archive.Encryption = EncryptionAlgorithm.Aes256;` in vóór `Save`. |

## Veelgestelde vragen

**V: Kan ik meer dan één bestand toevoegen aan hetzelfde 7z‑archief?**  
A: Zeker. Roep `archive.CreateEntry` aan voor elk bestand dat je **bestand toe te voegen aan 7z** of **meerdere bestanden 7z toe te voegen** wilt.

**V: Hoe specificeer ik het wachtwoord voor AES‑versleuteling?**  
A: Gebruik de eigenschap `Password` op de `SevenZipArchive` vóór het opslaan, bijvoorbeeld `archive.Password = "YourStrongPassword";`. Hiermee kun je later **7z‑wachtwoord verifiëren** bij het uitpakken.

**V: Ondersteunt Aspose.Zip andere archiefformaten?**  
A: Aspose.Zip richt zich voornamelijk op ZIP‑ en 7z‑formaten. Voor andere formaten kun je beter gespecialiseerde bibliotheken gebruiken.

**V: Is een licentie vereist voor productie?**  
A: Ja. Je kunt een tijdelijke licentie voor evaluatie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik community‑ondersteuning vinden?**  
A: Bezoek het [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) om vragen te stellen en ervaringen te delen.

## Conclusie

Je hebt nu een solide basis om **hoe je 7z**‑archieven versleutelt met Aspose.Zip voor .NET. Door de bovenstaande stappen te volgen, kun je veilig bestanden comprimeren, ze aan een 7z‑container toevoegen en desgewenst AES‑versleuteling inschakelen. Voel je vrij om dit voorbeeld uit te breiden door meer entries toe te voegen, wachtwoorden in te stellen of het te integreren in grotere workflows, zoals geautomatiseerde back‑uppijplijnen.

---

**Laatst bijgewerkt:** 2026-05-05  
**Getest met:** Aspose.Zip voor .NET 24.11  
**Auteur:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}