---
date: 2026-06-29
description: Leer hoe u een map kunt comprimeren naar 7z met Aspose.Zip for .NET,
  met uitleg over zeven zip-compressiemethoden zoals LZMA2, BZip2 en Store. Perfect
  voor het programmatically aanmaken van 7z-archieven.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip met verschillende compressiemethoden
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hoe een map comprimeren naar 7z – Aspose.Zip for .NET tutorial
url: /nl/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe map comprimeren naar 7z – Aspose.Zip voor .NET handleiding

## Inleiding

Als u programmatically **compress folder to 7z** archieven in een .NET-applicatie moet maken, bent u hier aan het juiste adres. Aspose.Zip voor .NET maakt het eenvoudig om Seven Zip-archieven te genereren met een van de ondersteunde compressie‑algoritmen, of u nu een volledige map wilt bundelen voor distributie of gewoon een betrouwbare **seven zip archive .net** oplossing nodig heeft. In deze handleiding lopen we drie populaire compressiemethoden door—LZMA2, BZip2 en Store (geen compressie)—en laten we u precies zien hoe u een 7z‑bestand maakt met slechts een paar regels C#‑code.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.Zip for .NET biedt de meest volledige set van Seven Zip‑functies.  
- **Welke compressiemethode geeft de beste compressieverhouding?** LZMA2 levert meestal de hoogste compressie voor gemengde data.  
- **Kan ik een 7z maken zonder enige compressie?** Ja—gebruik de Store (geen compressie) methode.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productiegebruik.  
- **Is dit compatibel met .NET 6/7?** Absoluut—Aspose.Zip ondersteunt .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10.

## Wat zijn de Seven Zip-compressiemethoden?

Seven Zip ondersteunt verschillende algoritmen, elk geoptimaliseerd voor verschillende scenario's. **LZMA2** biedt de hoogste compressieverhouding (vaak 30‑40 % kleiner dan BZip2), **BZip2** levert solide compressie met bredere ondersteuning voor legacy‑tools, en **Store** archiveert bestanden simpelweg zonder ze te verkleinen, waardoor originele tijdstempels perfect behouden blijven.

## Voorvereisten

- Basiskennis van C# en Visual Studio.  
- De Aspose.Zip for .NET bibliotheek geïnstalleerd. Haal deze op van de officiële downloadpagina **[hier](https://releases.aspose.com/zip/net/)**.  
- Een map (`dataDir`) die de bestanden bevat die u wilt archiveren.

## Namespaces importeren

Ten eerste voegt u de vereiste namespaces toe aan uw C#‑bestand:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Deze klassen geven u toegang tot de compressie‑instellingen en archiefverwerking.

## LZMA2-compressie – Hoe een 7z met maximale verhouding te maken

De `Archive`‑klasse vertegenwoordigt een 7z‑archief dat meerdere bestanden kan bevatten.  
Het LZMA2‑algoritme biedt de hoogste compressieverhouding van de ondersteunde methoden. Het werkt door de invoer in blokken te verdelen en een geavanceerde woordenboekcompressie toe te passen. In Aspose.Zip stelt u de `CompressionMethod` in op `CompressionMethod.Lzma2` op het `Archive`‑object voordat u bestanden toevoegt.

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

## BZip2-compressie – Een evenwichtige keuze

De `Archive`‑klasse vertegenwoordigt een 7z‑archief dat meerdere bestanden kan bevatten.  
BZip2 biedt solide compressie met goede compatibiliteit voor oudere tools. Het gebruikt de Burrows‑Wheeler‑transformatie en Huffman‑codering om de grootte te verkleinen. In Aspose.Zip selecteert u `CompressionMethod.BZip2` bij het configureren van de `Archive`‑instantie, wat snelheid en compressieverhouding in evenwicht brengt voor de meeste tekst‑ en binaire bestanden.

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

De `Archive`‑klasse vertegenwoordigt een 7z‑archief dat meerdere bestanden kan bevatten.  
De Store‑methode maakt een archief zonder de gegevens te comprimeren. Het kopieert simpelweg de originele bestanden naar de 7z‑container, waarbij tijdstempels en mappenstructuur behouden blijven. Om het in Aspose.Zip te gebruiken, stelt u `CompressionMethod.Store` in op het `Archive` voordat u de bestanden toevoegt die u wilt bundelen.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Gebruik de Store‑methode als u simpelweg bestanden wilt bundelen zonder hun grootte te wijzigen—perfect voor het behouden van originele tijdstempels of wanneer het archief on-the-fly wordt uitgepakt.

## Hoe voeg ik bestanden toe aan 7z?

Voeg bestanden toe aan een 7z‑archief door een `Archive`‑instantie te maken, de gewenste `CompressionMethod` in te stellen en `AddAllFiles(dataDir)` aan te roepen. De methode scant de opgegeven map recursief en behoudt de mappenhiërarchie binnen het archief. Deze aanpak stelt u in staat om **compress folder to 7z** met één regel code na de initiële configuratie.

## Veelvoorkomende gebruikssituaties

| Scenario | Aanbevolen methode |
|----------|--------------------|
| Grote installateurs distribueren | LZMA2 |
| Logbestanden delen met legacy‑tools | BZip2 |
| Bestanden verpakken voor snelle extractie | Store (geen compressie) |
| Moet **compress folder to 7z** on the fly in een webservice | LZMA2 (voor de beste verhouding) |

## Problemen oplossen & Tips

- **Ontbrekende bestanden in het archief?** Controleer of `dataDir` naar de juiste map wijst en of het proces leesrechten heeft.  
- **Archief kan niet worden geopend in oudere 7‑Zip‑versies?** Gebruik BZip2 of Store, aangezien LZMA2 mogelijk nieuwere decompressiebibliotheken vereist.  
- **Prestatieknelpunt?** Overweeg bij enorme datasets het archief te streamen in plaats van alle items in het geheugen te laden.

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip for .NET gebruiken met elk type bestand?**  
A: Ja, Aspose.Zip ondersteunt een breed scala aan bestandsformaten, waardoor u vrijwel elk bestandstype kunt comprimeren en decomprimeren.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Zip for .NET?**  
A: Ja, u kunt een gratis proefversie verkrijgen **[hier](https://releases.aspose.com/)**.

**Q: Waar kan ik documentatie vinden voor Aspose.Zip for .NET?**  
A: De volledige API‑referentie is beschikbaar **[hier](https://reference.aspose.com/zip/net/)**.

**Q: Hoe kan ik tijdelijke licenties krijgen voor Aspose.Zip for .NET?**  
A: Tijdelijke licenties kunnen worden verkregen **[hier](https://purchase.aspose.com/temporary-license/)**.

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Zip for .NET?**  
A: U kunt ondersteuning zoeken op het **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Laatst bijgewerkt:** 2026-06-29  
**Getest met:** Aspose.Zip for .NET 24.12  
**Auteur:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Gerelateerde handleidingen

- [bestanden comprimeren c# – 7z-archief maken met Aspose.Zip voor .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Hoe map zippen met Aspose.Zip voor .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Hoe LZMA comprimeren in Aspose.Zip voor .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}