---
date: 2026-06-29
description: Lär dig hur du extraherar xar-arkiv och dekomprimerar xar-fil till en
  mapp med Aspose.Zip för .NET. Följ den här steg‑för‑steg‑guiden.
keywords:
- extract xar archive
- how to extract xar
- decompress xar file
- aspose zip decompress
linktitle: Dekomprimera Xar till mapp
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract xar archive and decompress xar file to a folder
    using Aspose.Zip for .NET. Follow this step‑by‑step guide.
  headline: How to Extract Xar Archive to Folder Using Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip is regularly updated to ensure compatibility with the
      latest .NET framework versions. Refer to the [documentation](https://reference.aspose.com/zip/net/)
      for specific details.
    question: Is Aspose.Zip compatible with the latest .NET framework versions?
  - answer: Absolutely! You can download a free trial version from [here](https://releases.aspose.com/).
    question: Can I try Aspose.Zip before making a purchase?
  - answer: For any queries or assistance, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: How can I get support for Aspose.Zip?
  - answer: Yes, temporary licenses can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.Zip?
  - answer: You can purchase Aspose.Zip for .NET [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar Xar-arkiv till mapp med Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar Xar-arkiv till mapp med Aspose.Zip för .NET

Om du är en .NET‑utvecklare som behöver **extract xar archive** snabbt och pålitligt, erbjuder Aspose.Zip för .NET ett rent, högpresterande API som hanterar hela processen utan externa verktyg. I den här handledningen går vi igenom varje steg som krävs för att dekomprimera ett Xar‑arkiv till en mapp, förklarar varför denna metod sparar dig tid och ger dig färdig‑körbar kod. I slutet kommer du att förstå när du ska använda detta tillvägagångssätt, hur du integrerar det i ditt projekt och hur du undviker vanliga fallgropar.

## Snabba svar
- **Vad gör biblioteket?** Det läser och extraherar Xar‑arkiv utan externa verktyg.  
- **Vilka .NET‑versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, och .NET 5–10.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter.  
- **Kan jag extrahera till en anpassad mapp?** Ja—ange bara målvägen i `ExtractToDirectory`.

## Vad är “how to extract xar”?
Att extrahera ett Xar‑arkiv innebär att läsa det komprimerade paketet och skriva dess interna filer till en katalog på disken. Detta är användbart när du får XAR‑paket från macOS‑installationsprogram, backup‑verktyg eller tredjepartsverktyg och behöver bearbeta deras innehåll i en .NET‑applikation.

## Varför använda Aspose.Zip för denna uppgift?
Aspose.Zip tillhandahåller en inbyggd .NET‑lösning som eliminerar behovet av externa verktyg och erbjuder snabb, pålitlig extrahering med fullt plattformsoberoende stöd.  
- **Zero external dependencies** – ren .NET, inga inhemska binärer.  
- **Stream‑based API** – fungerar med filer, minnesströmmar eller nätverksströmmar.  
- **Robust error handling** – detaljerade undantag hjälper dig att felsöka korrupta arkiv.  
- **Full .NET compatibility** – fungerar på Windows-, Linux- och macOS‑körmiljöer.  
- **Broad format support** – Aspose.Zip kan extrahera från över 30 arkivtyper (ZIP, TAR, XAR, 7z osv.) och hanterar filer upp till 2 GB utan att läsa in hela arkivet i minnet, vilket ger förutsägbar prestanda även på mindre servrar.

## Förutsättningar
Innan vi börjar, se till att du har följande:

- **Aspose.Zip for .NET** – integrerat i ditt projekt. Du kan ladda ner det från [here](https://releases.aspose.com/zip/net/).
- **Document Directory** – en mapp i din lösning där exempel‑`.xar`‑filen och den extraherade utdata kommer att ligga.

## Importera namnrymder
I ditt .NET‑projekt, inkludera de nödvändiga namnrymderna för att få åtkomst till Aspose.Zip‑funktionaliteten:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Steg 1: Definiera din dokumentkatalog
Byt ut `"Your Document Directory"` mot den absoluta eller relativa sökvägen som innehåller `sample.xar` och där du vill att utdata‑mappen ska skapas. Att senare använda `Path.Combine` hjälper till att undvika problem med sökvägsseparatorer på olika operativsystem.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Dekomprimera Xar‑arkiv
`XarArchive`‑klassen är Aspose.Zip:s ingångspunkt för att läsa XAR‑behållare och exponera deras poster. Den tillhandahåller metoder för att lista filer och extrahera dem till disk.

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Detta kodsnutt öppnar Xar‑filen, skapar en `XarArchive`‑instans och extraherar **the entire decompress xar archive** till `DecompressXar_out`. Operationen är helt strömbaserad, så den fungerar effektivt även med stora paket.

## Hur man extraherar xar‑arkiv till en mapp?
`XarArchive.Open` öppnar ett XAR‑arkiv och returnerar en `XarArchive`‑instans. `ExtractToDirectory` extraherar arkivets innehåll till en angiven mapp.  
Läs in XAR‑filen med `XarArchive.Open("sample.xar")` och anropa `archive.ExtractToDirectory("DecompressXar_out")`. API:et skapar automatiskt mål‑mappen, bevarar den ursprungliga katalogstrukturen och skriver varje post med buffrade strömmar, så du får en trogen kopia av det ursprungliga paketet med bara två metodanrop.

### Steg 3: Kör koden
Bygg och kör ditt program. Efter körning hittar du en ny mapp med namnet `DecompressXar_out` i din dokumentkatalog, som innehåller alla filer som var paketerade i det ursprungliga `.xar`‑arkivet.

## Vanliga problem & tips
- **Fil ej hittad** – Se till att sökvägen i `File.OpenRead` pekar korrekt på `sample.xar`. Använd `Path.Combine` för säkrare sökvägshantering.  
- **Åtkomst nekad** – Kör programmet med tillräckliga filsystembehörigheter, särskilt när du skriver till skyddade kataloger.  
- **Korrupt arkiv** – Aspose.Zip kastar `InvalidDataException`; verifiera att källfilen `.xar` är intakt.  
- **Stora arkiv** – Om du arbetar med arkiv större än 1 GB, överväg att öka buffertstorleken via `ArchiveOptions` för att förbättra genomströmning.

## Vanliga frågor

**Q: Är Aspose.Zip kompatibel med de senaste .NET‑ramverksversionerna?**  
A: Ja, Aspose.Zip uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET‑ramverksversionerna. Se [documentation](https://reference.aspose.com/zip/net/) för specifika detaljer.

**Q: Kan jag prova Aspose.Zip innan jag köper?**  
A: Absolut! Du kan ladda ner en gratis provversion från [here](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip?**  
A: För frågor eller hjälp, besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: Finns tillfälliga licenser tillgängliga för Aspose.Zip?**  
A: Ja, tillfälliga licenser kan erhållas från [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.Zip för .NET?**  
A: Du kan köpa Aspose.Zip för .NET [here](https://purchase.aspose.com/buy).

**Q: Kan jag extrahera endast specifika filer från ett Xar‑arkiv?**  
A: Ja—använd `archive.Entries` för att lista poster och anropa `ExtractToFile` på valda poster.

**Q: Stöder biblioteket lösenordsskyddade Xar‑filer?**  
A: För närvarande stödjer inte Xar‑arkiv kryptering; om du stöter på en skyddad fil måste du dekryptera den innan du använder Aspose.Zip.

**Last Updated:** 2026-06-29  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man dekomprimerar filer med Aspose.Zip för .NET](/zip/net/file-decompression/)
- [Hur man extraherar zip till mapp med Aspose.Zip för .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [Skapa tar‑arkiv och lägg till filer i tar med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}