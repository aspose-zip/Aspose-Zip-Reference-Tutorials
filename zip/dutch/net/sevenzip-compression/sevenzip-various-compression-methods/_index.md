---
title: Zeven zip-bestanden maken - Aspose.Zip voor .NET-zelfstudie
linktitle: SevenZip met verschillende compressiemethoden
second_title: Aspose.Zip .NET API voor bestandscompressie en archivering
description: Leer zeven zip-bestanden maken met Aspose.Zip voor .NET met behulp van verschillende compressiemethoden. Eenvoudige stappen voor LZMA2, BZip2 en Store (geen compressie).
weight: 12
url: /nl/net/sevenzip-compression/sevenzip-various-compression-methods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zeven zip-bestanden maken - Aspose.Zip voor .NET-zelfstudie


## Invoering

Op het gebied van .NET-ontwikkeling is het beheren en comprimeren van bestanden een veel voorkomende taak. Aspose.Zip voor .NET biedt een krachtige oplossing voor het werken met gecomprimeerde archieven en biedt een verscheidenheid aan compressiemethoden. In deze zelfstudie onderzoeken we hoe u Aspose.Zip voor .NET kunt gebruiken om zeven zip-bestanden te maken met verschillende compressiemethoden.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:

- Basiskennis van programmeren in C#.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Zip voor .NET-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/zip/net/).

## Naamruimten importeren

Begin met het importeren van de benodigde naamruimten in uw C#-project. Gebruik het volgende codefragment om aan de slag te gaan:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2-compressie

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

## BZip2-compressie

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Winkel, geen compressie

```csharp
//Winkel, geen compressie
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Conclusie

In deze tutorial hebben we de veelzijdigheid van Aspose.Zip voor .NET onderzocht bij het maken van zeven zip-bestanden met verschillende compressiemethoden. Of u nu hoge compressieverhoudingen nodig heeft of helemaal geen compressie wilt, Aspose.Zip biedt de flexibiliteit om aan uw eisen te voldoen.

## Veelgestelde vragen

### Kan ik Aspose.Zip voor .NET gebruiken met elk type bestand?
Ja, Aspose.Zip voor .NET ondersteunt een breed scala aan bestandstypen, waardoor u verschillende formaten kunt comprimeren en decomprimeren.

### Is er een gratis proefversie beschikbaar voor Aspose.Zip voor .NET?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### Waar kan ik documentatie vinden voor Aspose.Zip voor .NET?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/zip/net/).

### Hoe kan ik tijdelijke licenties krijgen voor Aspose.Zip voor .NET?
 Er kunnen tijdelijke licenties worden verkregen[hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik ondersteuning krijgen voor Aspose.Zip voor .NET?
 U kunt ondersteuning zoeken op de[Aspose.Zip-forum](https://forum.aspose.com/c/zip/37).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
