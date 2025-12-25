---
date: 2025-12-25
description: Leer hoe u 7z‑bestanden maakt met Aspose.Zip voor .NET, met zeven zip‑compressiemethoden
  zoals LZMA2, BZip2 en Store. Perfect voor scenario’s waarbij u een map comprimeert
  naar 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe 7z-bestanden te maken – Aspose.Zip voor .NET tutorial
url: /nl/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe 7z-bestanden maken – Aspose.Zip voor .NET Handleiding

## Introductie

Als je **how to create 7z** archieven programmatisch wilt maken in een .NET‑applicatie, ben je op de juiste plek. Aspose.Zip voor .NET maakt het eenvoudig om Seven Zip‑archieven te genereren met elk van de ondersteunde compressie‑algoritmen, of je nu **compress folder to 7z** wilt voor distributie of gewoon een betrouwbare **seven zip archive .net**‑oplossing nodig hebt. In deze handleiding lopen we drie populaire compressiemethoden door—LZMA2, BZip2 en Store (geen compressie)—en laten we je precies zien hoe je een 7z‑bestand maakt met slechts een paar regels C#‑code.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip voor .NET biedt de meest volledige set Seven Zip‑functies.  
- **Welke compressiemethode geeft de beste ratio?** LZMA2 levert meestal de hoogste compressie voor gemengde data.  
- **Kan ik een 7z maken zonder enige compressie?** Ja—gebruik de Store‑methode (geen compressie).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productiegebruik.  
- **Is dit compatibel met .NET 6/7?** Absoluut—Aspose.Zip ondersteunt .NET Framework, .NET Core en .NET 5+.

## Wat zijn de Seven Zip‑compressiemethoden?

Seven Zip ondersteunt verschillende algoritmen, elk geoptimaliseerd voor verschillende scenario's:

* **LZMA2** – hoge compressieverhouding, ideaal voor grote gemengde bestanden.  
* **BZip2** – solide compressie maar trager dan LZMA2; nuttig wanneer compatibiliteit met oudere tools vereist is.  
* **Store** – geen compressie; perfect wanneer je alleen archivering nodig hebt zonder verkleining (bijv. bij het behouden van originele bestands‑timestamps).

Het begrijpen van deze **seven zip compression methods** helpt je de juiste instelling voor je project te kiezen.

## Voorvereisten

- Basiskennis van C# en Visual Studio.  
- De Aspose.Zip voor .NET‑bibliotheek geïnstalleerd. Haal deze op van de officiële downloadpagina **[here](https://releases.aspose.com/zip/net/)**.  
- Een map (`dataDir`) met de bestanden die je wilt archiveren.

## Namespaces importeren

Voeg eerst de benodigde namespaces toe aan je C#‑bestand:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Deze klassen geven je toegang tot de compressie‑instellingen en archiefafhandeling.

## LZMA2‑compressie – Hoe een 7z met maximale ratio maken

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2 werkt het beste wanneer de bronbestanden groter zijn dan 1 MB. Voor veel kleine bestanden kan BZip2 sneller zijn.

## BZip2‑compressie – Een evenwichtige keuze

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 biedt solide compressie terwijl het een redelijke snelheid behoudt, waardoor het een goede fallback is wanneer LZMA2 niet wordt ondersteund door de doelomgeving.

## Store (geen compressie) – Wanneer grootte niet uitmaakt

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Gebruik de Store‑methode als je simpelweg bestanden wilt bundelen zonder hun grootte te wijzigen—perfect voor het behouden van originele timestamps of wanneer het archief on‑the‑fly wordt uitgepakt.

## Veelvoorkomende gebruikssituaties

| Scenario | Recommended Method |
|----------|--------------------|
| Grote installaties distribueren | LZMA2 |
| Logbestanden delen met legacy‑tools | BZip2 |
| Bestanden verpakken voor snelle extractie | Store (no compression) |
| Moet **compress folder to 7z** on the fly in a web service | LZMA2 (for best ratio) |

## Problemen oplossen & Tips

- **Ontbrekende bestanden in het archief?** Controleer of `dataDir` naar de juiste map wijst en of het proces leesrechten heeft.  
- **Archief kan niet worden geopend in oudere 7‑Zip‑versies?** Blijf bij BZip2 of Store, aangezien LZMA2 mogelijk nieuwere decompressiebibliotheken vereist.  
- **Prestatieknelpunt?** Overweeg voor enorme datasets het archief te streamen in plaats van alle items in het geheugen te laden.

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET gebruiken met elk type bestand?**  
A: Ja, Aspose.Zip ondersteunt een breed scala aan bestandsformaten, waardoor je vrijwel elk bestandstype kunt comprimeren en decomprimeren.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Zip voor .NET?**  
A: Ja, je kunt een gratis proefversie verkrijgen **[here](https://releases.aspose.com/)**.

**Q: Waar kan ik documentatie vinden voor Aspose.Zip voor .NET?**  
A: De volledige API‑referentie is beschikbaar **[here](https://reference.aspose.com/zip/net/)**.

**Q: Hoe kan ik tijdelijke licenties krijgen voor Aspose.Zip voor .NET?**  
A: Tijdelijke licenties kunnen worden verkregen **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?**  
A: Je kunt ondersteuning zoeken op het **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose  

---