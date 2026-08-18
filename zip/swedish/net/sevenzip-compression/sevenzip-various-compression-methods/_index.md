---
date: 2026-06-29
description: Lär dig hur du komprimerar en mapp till 7z med Aspose.Zip for .NET, som
  täcker sju zip-komprimeringsmetoder såsom LZMA2, BZip2 och Store. Perfekt för att
  skapa 7z-arkiv programatiskt.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip med olika komprimeringsmetoder
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
title: Hur man komprimerar en mapp till 7z – Aspose.Zip for .NET Handledning
url: /sv/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man komprimerar mapp till 7z – Aspose.Zip för .NET handledning

## Introduktion

Om du behöver **compress folder to 7z** arkiv programatiskt i en .NET-applikation, har du kommit till rätt ställe. Aspose.Zip för .NET gör det enkelt att skapa Seven Zip‑arkiv med någon av de stödjade komprimeringsalgoritmerna, oavsett om du vill paketera en hel katalog för distribution eller bara behöver en pålitlig **seven zip archive .net**‑lösning. I den här guiden går vi igenom tre populära komprimeringsmetoder—LZMA2, BZip2 och Store (ingen komprimering)—och visar exakt hur du skapar en 7z‑fil med bara några rader C#‑kod.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.Zip för .NET tillhandahåller den mest kompletta uppsättningen av Seven Zip‑funktioner.  
- **Vilken komprimeringsmetod ger bäst förhållande?** LZMA2 ger vanligtvis den högsta komprimeringen för blandade data.  
- **Kan jag skapa en 7z utan någon komprimering?** Ja—använd Store‑metoden (ingen kompression).  
- **Behöver jag en licens för utveckling?** En gratis provversion finns tillgänglig; en licens krävs för produktionsanvändning.  
- **Är detta kompatibelt med .NET 6/7?** Absolut—Aspose.Zip stöder .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.

## Vilka är Seven Zip‑komprimeringsmetoderna?

Seven Zip stöder flera algoritmer, var och en optimerad för olika scenarier. **LZMA2** erbjuder den högsta komprimeringsgraden (ofta 30‑40 % mindre än BZip2), **BZip2** ger solid komprimering med bredare stöd för äldre verktyg, och **Store** arkiverar helt enkelt filer utan att krympa dem, och bevarar ursprungliga tidsstämplar perfekt.

## Förutsättningar

- Grundläggande kunskap om C# och Visual Studio.  
- Aspose.Zip för .NET‑biblioteket installerat. Hämta det från den officiella nedladdningssidan **[here](https://releases.aspose.com/zip/net/)**.  
- En mapp (`dataDir`) som innehåller filerna du vill arkivera.

## Importera namnrymder

Först, lägg till de nödvändiga namnrymderna i din C#‑fil:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Dessa klasser ger dig åtkomst till komprimeringsinställningarna och arkivhanteringen.

## LZMA2‑komprimering – Så skapar du en 7z med maximal komprimeringsgrad

`Archive`‑klassen representerar ett 7z‑arkiv som kan innehålla flera filer.  
LZMA2‑algoritmen ger den högsta komprimeringsgraden bland de stödjade metoderna. Den fungerar genom att dela indata i block och tillämpa en sofistikerad ordboks‑komprimering. I Aspose.Zip sätter du `CompressionMethod` till `CompressionMethod.Lzma2` på `Archive`‑objektet innan du lägger till filer.

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

> **Pro tip:** LZMA2 fungerar bäst när källfilerna är större än 1 MB. För många små filer kan BZip2 vara snabbare.

## BZip2‑komprimering – Ett balanserat val

`Archive`‑klassen representerar ett 7z‑arkiv som kan innehålla flera filer.  
BZip2 erbjuder solid komprimering med god kompatibilitet för äldre verktyg. Den använder Burrows‑Wheeler‑transformen och Huffman‑kodning för att minska storleken. I Aspose.Zip väljer du `CompressionMethod.BZip2` när du konfigurerar `Archive`‑instansen, vilket balanserar hastighet och komprimeringsgrad för de flesta text‑ och binära filer.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 erbjuder solid komprimering samtidigt som den behåller rimlig hastighet, vilket gör den till ett bra alternativ när LZMA2 inte stöds av målmiljön.

## Store (Ingen komprimering) – När storlek inte spelar någon roll

`Archive`‑klassen representerar ett 7z‑arkiv som kan innehålla flera filer.  
Store‑metoden skapar ett arkiv utan att komprimera data. Den kopierar helt enkelt de ursprungliga filerna till 7z‑behållaren, och bevarar tidsstämplar och katalogstruktur. För att använda den i Aspose.Zip, sätt `CompressionMethod.Store` på `Archive` innan du lägger till de filer du vill paketera.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Använd Store‑metoden om du bara behöver paketera filer tillsammans utan att ändra deras storlek—perfekt för att bevara ursprungliga tidsstämplar eller när arkivet kommer att dekomprimeras i farten.

## Hur lägger jag till filer i 7z?

Lägg till filer i ett 7z‑arkiv genom att skapa en `Archive`‑instans, sätta önskad `CompressionMethod` och anropa `AddAllFiles(dataDir)`. Metoden skannar den angivna mappen rekursivt och bevarar kataloghierarkin i arkivet. Detta tillvägagångssätt låter dig **compress folder to 7z** med en enda kodrad efter den initiala konfigurationen.

## Vanliga användningsfall

| Scenario | Rekommenderad metod |
|----------|--------------------|
| Distribuera stora installationsprogram | LZMA2 |
| Dela loggar med äldre verktyg | BZip2 |
| Paketera filer för snabb extraktion | Store (no compression) |
| Behöver **compress folder to 7z** i realtid i en webbtjänst | LZMA2 (for best ratio) |

## Felsökning & tips

- **Saknas filer i arkivet?** Verifiera att `dataDir` pekar på rätt katalog och att processen har läsbehörighet.  
- **Arkivet går inte att öppna i äldre 7‑Zip‑versioner?** Håll dig till BZip2 eller Store, eftersom LZMA2 kan kräva nyare dekomprimeringsbibliotek.  
- **Prestandaflaskhals?** För enorma datamängder, överväg att strömma arkivet istället för att ladda alla poster i minnet.

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med vilken filtyp som helst?**  
A: Ja, Aspose.Zip stöder ett brett sortiment av filformat, vilket gör att du kan komprimera och dekomprimera praktiskt taget alla filtyper.

**Q: Finns en gratis provversion tillgänglig för Aspose.Zip för .NET?**  
A: Ja, du kan få en gratis provversion **[here](https://releases.aspose.com/)**.

**Q: Var kan jag hitta dokumentation för Aspose.Zip för .NET?**  
A: Den fullständiga API‑referensen finns **[here](https://reference.aspose.com/zip/net/)**.

**Q: Hur kan jag få tillfälliga licenser för Aspose.Zip för .NET?**  
A: Tillfälliga licenser kan erhållas **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Var kan jag få support för Aspose.Zip för .NET?**  
A: Du kan söka support på **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Senast uppdaterad:** 2026-06-29  
**Testad med:** Aspose.Zip för .NET 24.12  
**Författare:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [komprimera filer c# – Skapa 7z‑arkiv med Aspose.Zip för .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Hur man zippar mapp med Aspose.Zip för .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Hur man komprimerar LZMA i Aspose.Zip för .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}