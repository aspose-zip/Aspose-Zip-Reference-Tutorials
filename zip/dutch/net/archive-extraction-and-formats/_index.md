---
date: 2026-02-20
description: Leer hoe u tarbz2‑bestanden comprimeert, hoe u targz‑archieven maakt
  en .NET‑archiefextractie uitvoert met wachtwoordbeveiligde zip‑extractie met Aspose.Zip
  voor .NET. Verhoog de opslag efficiëntie en beveiliging.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe TarBz2‑bestanden comprimeren met Aspose.Zip voor .NET
url: /nl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe TarBz2‑bestanden comprimeren met Aspose.Zip voor .NET

## Inleiding

In deze gids leer je **hoe je tarbz2‑bestanden comprimeert** met Aspose.Zip voor .NET en ontdek je tevens hoe je TarGz‑archieven maakt en .net‑archiefextractie uitvoert van wachtwoord‑beveiligde zip‑bestanden. Efficiënt bestandsbeheer is een hoeksteen van moderne .NET‑ontwikkeling, en het beheersen van deze formaten stelt je in staat opslagkosten te verlagen, gegevensoverdracht te versnellen en gevoelige informatie veilig te houden. Of je nu een backup‑service, een cloud‑storage‑client of een data‑processing‑pipeline bouwt, de hier behandelde technieken maken je bestandsbeheer soepeler en betrouwbaarder.

## Snelle antwoorden
- **Wat is TarBz2?** Een gecomprimeerd archief dat TAR‑verpakking combineert met BZIP2‑compressie voor hoge compressieverhoudingen.  
- **Waarom kiezen voor Aspose.Zip voor .NET?** Het biedt een enkele, vloeiende API voor het maken en extraheren van vele archiefformaten zonder externe afhankelijkheden.  
- **Kan ik een TarGz‑archief maken?** Ja – Aspose.Zip ondersteunt TarGz, TarLz, TarXz, TarZ en meer.  
- **Hoe extraheer ik een wachtwoord‑beveiligd zip‑archief?** Gebruik de `Password`‑eigenschap op het `ArchiveEntry`‑object bij het extraheren.  
- **Heb ik een licentie nodig voor productiegebruik?** Een commerciële licentie is vereist voor productie; een gratis proefversie is beschikbaar voor evaluatie.

## Hoe TarBz2‑bestanden comprimeren
Bestanden comprimeren naar TarBz2 betekent eerst meerdere bestanden en mappen bundelen in één **TAR**‑container en vervolgens **BZIP2**‑compressie toepassen. Het resultaat is één `.tar.bz2`‑bestand dat zowel gemakkelijk te transporteren als sterk gecomprimeerd is.

## Waarom Aspose.Zip voor .NET gebruiken om deze formaten te verwerken?
- **Unified API** – Eén bibliotheek, vele formaten (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Werkt direct op Windows, Linux en macOS.  
- **Password support** – Beveilig en extraheer archieven veilig met per‑entry‑wachtwoorden.  
- **Performance‑focused** – Stream‑gebaseerde verwerking minimaliseert het geheugenverbruik.

## Voorvereisten
- .NET 6.0 of later (of .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip voor .NET NuGet‑pakket geïnstalleerd (`Install-Package Aspose.Zip`).  
- Basiskennis van C# en bestands‑I/O.

## Stapsgewijze handleiding

### Stap 1: Kies het archiefformaat dat je nodig hebt
Bepaal of **TarBz2**, **TarGz**, **TarLz**, **TarXz** of **TarZ** het beste past bij je compressieverhouding en compatibiliteitseisen.  
- **TarBz2** – Beste compressie, langzamere verwerking.  
- **TarGz** – Goede balans tussen snelheid en grootte (dekt het secundaire trefwoord *how to create targz*).  
- **TarZ** – Legacy‑formaat, nuttig voor compatibiliteit met oudere Unix‑tools.

### Stap 2: Maak een nieuw `Archive`‑object aan
Instantieer de `Archive`‑klasse en wijs het pad naar het uitvoerbestand toe. Dit object beheert het inpakken en comprimeren.

### Stap 3: Voeg bestanden en mappen toe
Gebruik de methoden `AddAll` of `AddFile` om de bestanden die je wilt comprimeren op te nemen. Je kunt de mapstructuur behouden door een basismap toe te voegen.

### Stap 4: Stel het gewenste compressietype in
Geef het compressie‑algoritme op (`CompressionType.BZip2`, `CompressionType.GZip`, enz.) bij het opslaan van het archief. Hier **compress je bestanden naar TarBz2** of een ander formaat.

### Stap 5: Sla het archief op
Roep `Save` aan met de juiste format‑enum (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, enz.). De bibliotheek schrijft de TAR‑container en past de gekozen compressie in één stap toe.

### Stap 6: Archieven extraheren met wachtwoorden
Als je **archief‑items met verschillende wachtwoorden wilt extraheren** (secundair trefwoord *password protected zip extraction*), open dan het archief, zoek elk item, wijs het wachtwoord toe en extraheer vervolgens.

### Stap 7: Verifieer het resultaat
Na het extraheren, vergelijk je bestandsgroottes en controlesommen om te bevestigen dat het archief correct is aangemaakt en uitgepakt.

## Veelvoorkomende gebruikssituaties
- **Backup‑hulpmiddelen** – Sla dagelijkse back-ups op als `.tar.bz2` om opslagkosten te minimaliseren.  
- **Cross‑platform gegevensuitwisseling** – Tar‑gebaseerde formaten worden universeel begrepen op Linux, macOS en Windows.  
- **Veilige distributie** – Bescherm individuele items met wachtwoorden voor compliance‑gedreven omgevingen.

## Problemen oplossen & Tips
- **Grote archieven** – Gebruik streaming‑API’s (`Archive.CreateEntryFromFile`) om te voorkomen dat volledige bestanden in het geheugen worden geladen.  
- **Wachtwoord‑mismatch** – Zorg ervoor dat het wachtwoord dat op elk `ArchiveEntry` is ingesteld overeenkomt met het wachtwoord dat tijdens het extraheren wordt gebruikt; anders krijg je een `InvalidPasswordException`.  
- **Niet‑ondersteund compressieniveau** – BZIP2 ondersteunt geen aangepaste compressieniveaus; als je fijnmazigere controle nodig hebt, overweeg dan TarLz of TarXz.

## Veelgestelde vragen

**Q: Hoe maak ik een TarGz‑archief?**  
A: Stel het compressietype in op `CompressionType.GZip` en het formaat op `ArchiveFormat.TarGz` bij het aanroepen van `Save`.

**Q: Kan ik een wachtwoord‑beveiligd archief extraheren zonder het wachtwoord te kennen?**  
A: Nee. Elk item moet worden voorzien van het juiste wachtwoord; anders mislukt het extraheren.

**Q: Ondersteunt Aspose.Zip het extraheren van archieven met verschillende wachtwoorden per item?**  
A: Ja. Je kunt elk `ArchiveEntry` afzonderlijk een wachtwoord toewijzen vóór het extraheren.

**Q: Welk formaat biedt de beste compressie?**  
A: TarBz2 levert doorgaans de hoogste compressieverhouding, gevolgd door TarLz en TarXz. TarGz biedt een goede snelheid‑tot‑grootte‑balans.

**Q: Is er een limiet aan het aantal bestanden dat ik kan toevoegen aan een TAR‑archief?**  
A: Praktisch gezien niet, maar zeer grote archieven kunnen baat hebben bij opsplitsen in meerdere delen voor gemakkelijker beheer.

## Archief‑extractie en Formaat‑handleidingen
### [Bestanden comprimeren naar TarBz2 met Aspose.Zip voor .NET](./compress-to-tar-bz2/)
Leer hoe je bestanden comprimeert naar het TarBz2‑formaat in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte bestandscompressie.
### [Comprimeren naar TarGz met Aspose.Zip voor .NET](./compress-to-tar-gz/)
Ontdek efficiënte bestandscompressie in .NET met Aspose.Zip. Comprimeer moeiteloos naar TarGz.
### [Comprimeren naar TarLz met Aspose.Zip voor .NET](./compress-to-tar-lz/)
Comprimeer eenvoudig bestanden in .NET met Aspose.Zip. Leer stap voor stap TarLz‑archieven te maken.
### [Comprimeren naar TarXz met Aspose.Zip voor .NET](./compress-to-tar-xz/)
Leer hoe je bestanden comprimeert naar het TarXz‑formaat in .NET met Aspose.Zip. Volg onze stapsgewijze handleiding voor efficiënte opslag en overdracht van bestanden.
### [Comprimeren naar TarZ met Aspose.Zip voor .NET](./compress-to-tar-z/)
Ontdek stap‑voor‑stap compressie naar TarZ met Aspose.Zip voor .NET. Efficiënt bestandsbeheer voor je .NET‑projecten.
### [Archief‑items extraheren met verschillende wachtwoorden in Aspose.Zip voor .NET](./extract-archive-different-passwords/)
Leer hoe je archief‑items met verschillende wachtwoorden extraheren in Aspose.Zip voor .NET. Verhoog de beveiliging en flexibiliteit in je applicaties.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose