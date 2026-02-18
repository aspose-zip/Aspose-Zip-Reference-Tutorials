---
date: 2025-12-17
description: Lär dig hur du extraherar Xar‑arkiv och dekomprimerar Xar‑arkiv till
  en mapp med Aspose.Zip för .NET. Följ denna steg‑för‑steg‑guide.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar Xar till mapp med Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar Xar till mapp med Aspose.Zip för .NET

## Introduktion

Om du är en .NET‑utvecklare som letar efter ett pålitligt sätt **hur man extraherar xar**, så erbjuder Aspose.Zip för .NET ett rent, högpresterande API. I den här handledningen går vi igenom hela processen för att dekomprimera ett Xar‑arkiv till en mapp, förklarar varför detta tillvägagångssätt sparar dig tid, och visar den exakta koden du behöver köra.

## Snabba svar
- **Vad gör biblioteket?** Det läser och extraherar Xar‑arkiv utan externa verktyg.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter.  
- **Kan jag extrahera till en anpassad mapp?** Ja—ange bara målvägen i `ExtractToDirectory`.

## Vad är “hur man extraherar xar”?
Att extrahera ett Xar‑arkiv betyder att läsa det komprimerade paketet och skriva dess interna filer till en katalog på disken. Detta är användbart när du får XAR‑paket från macOS‑installationsprogram, backup‑verktyg eller tredjepartsverktyg och behöver bearbeta deras innehåll i en .NET‑applikation.

## Varför använda Aspose.Zip för denna uppgift?
- **Inga externa beroenden** – ren .NET, inga inhemska binärer.  
- **Ström‑baserat API** – fungerar med filer, minnesströmmar eller nätverksströmmar.  
- **Robust felhantering** – detaljerade undantag hjälper dig att felsöka korrupta arkiv.  
- **Full .NET‑kompatibilitet** – fungerar på Windows, Linux och macOS‑miljöer.

## Förutsättningar

Innan vi dyker ner, se till att du har följande:

- **Aspose.Zip för .NET** – integrerat i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/zip/net/).
- **Document Directory** – en mapp i din lösning där exempel‑`.xar`‑filen och den extraherade utdata kommer att ligga.

## Importera namnrymder

I ditt .NET‑projekt, inkludera de nödvändiga namnrymderna för att få åtkomst till Aspose.Zip‑funktionaliteten:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Steg 1: Definiera din Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den absoluta eller relativa sökvägen som innehåller `sample.xar` och där du vill att utmatningsmappen ska skapas.

## Steg 2: Dekomprimera Xar‑arkivet

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

Detta kodsnutt öppnar Xar‑filen, skapar en `XarArchive`‑instans och extraherar **hela dekomprimerade xar‑arkivet** till `DecompressXar_out`. Operationen är helt ström‑baserad, så den fungerar effektivt även med stora paket.

## Steg 3: Kör koden

Bygg och kör din applikation. Efter körning hittar du en ny mapp med namnet `DecompressXar_out` i din dokumentkatalog, som innehåller alla filer som paketades i det ursprungliga `.xar`‑arkivet.

## Vanliga problem & tips

- **Fil ej hittad** – Säkerställ att sökvägen i `File.OpenRead` korrekt pekar på `sample.xar`. Använd `Path.Combine` för säkrare sökvägshantering.  
- **Åtkomst nekad** – Kör applikationen med tillräckliga filsystembehörigheter, särskilt när du skriver till skyddade kataloger.  
- **Korrupt arkiv** – Aspose.Zip kastar `InvalidDataException`; verifiera att källfilen `.xar` är intakt.

## Vanliga frågor

**Q: Är Aspose.Zip kompatibel med de senaste .NET‑ramverksversionerna?**  
A: Ja, Aspose.Zip uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET‑ramverksversionerna. Se [dokumentation](https://reference.aspose.com/zip/net/) för specifika detaljer.

**Q: Kan jag prova Aspose.Zip innan jag köper?**  
A: Absolut! Du kan ladda ner en gratis provversion från [här](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip?**  
A: För frågor eller hjälp, besök [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37).

**Q: Finns tillfälliga licenser för Aspose.Zip?**  
A: Ja, tillfälliga licenser kan erhållas från [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.Zip för .NET?**  
A: Du kan köpa Aspose.Zip för .NET [här](https://purchase.aspose.com/buy).

**Q: Kan jag extrahera endast specifika filer från ett Xar‑arkiv?**  
A: Ja—använd `archive.Entries` för att lista poster och anropa `ExtractToFile` på de valda posterna.

**Q: Stöder biblioteket lösenordsskyddade Xar‑filer?**  
A: För närvarande stödjer inte Xar‑arkiv kryptering; om du stöter på en skyddad fil måste du dekryptera den innan du använder Aspose.Zip.

**Senast uppdaterad:** 2025-12-17  
**Testad med:** Aspose.Zip 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}