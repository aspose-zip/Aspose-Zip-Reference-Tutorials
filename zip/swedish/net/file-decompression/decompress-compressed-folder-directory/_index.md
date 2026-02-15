---
date: 2026-02-15
description: Lär dig hur du extraherar zip‑filer till en mapp med Aspose.Zip för .NET,
  inklusive lösenordsskyddade arkiv och krypterad zip‑extraktion.
linktitle: extract zip to folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar zip till mapp med Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så extraherar du zip till mapp med Aspose.Zip för .NET

## Introduktion

Om du behöver **extrahera zip till mapp** snabbt och pålitligt i en .NET‑applikation, ger Aspose.Zip för .NET dig ett rent, plattformsoberoende API som hanterar både vanliga och krypterade arkiv. I den här handledningen går vi igenom allt du behöver – från att installera biblioteket till att extrahera en lösenordsskyddad ZIP‑fil – så att du kan fokusera på din affärslogik istället för låg‑nivå arkivhantering.

## Snabba svar
- **Vad är det primära syftet med Aspose.Zip?** Att skapa, läsa och **extrahera zip till mapp** i .NET‑applikationer.  
- **Hur extraherar jag zip med lösenord?** Skicka lösenordet via `ArchiveLoadOptions.DecryptionPassword`.  
- **Kan jag packa upp ett krypterat arkiv utan lösenord?** Nej – Aspose.Zip kräver rätt lösenord för att öppna krypterade arkiv.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Krävs en licens för produktion?** Ja, en giltig Aspose.Zip‑licens behövs för kommersiell användning.

## Vad är **extrahera zip till mapp**?

Att extrahera en ZIP‑fil innebär att läsa den komprimerade datan och skriva de ursprungliga filerna till en målkatalog på disken. Aspose.Zip abstraherar låg‑nivå‑detaljerna, så att du kan anropa en enda metod för att utföra hela operationen.

## Varför använda Aspose.Zip för **hur man packar upp zip**‑uppgifter?

- **Enkel API** – minimal kod för att öppna, dekryptera och extrahera arkiv.  
- **Stöder krypterade arkiv** – perfekt för säker datautbyte.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS med .NET Core/.NET 5+.  
- **Inga externa beroenden** – ingen installation av inhemska zip‑verktyg behövs.  

## Förutsättningar

Innan vi börjar, se till att du har:

- Aspose.Zip för .NET‑biblioteket: Ladda ner och installera biblioteket från den [Aspose.Zip för .NET-dokumentationen](https://reference.aspose.com/zip/net/).
- En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon annan IDE du föredrar).
- (Valfritt) En lösenordsskyddad ZIP‑fil om du vill prova **extrahera zip med lösenord**.

## Importera namnrymder

I ditt .NET‑projekt importerar du de nödvändiga namnutrymmena för att utnyttja funktionerna i Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Låt oss nu gå igenom extraktionsprocessen steg för steg.

## Så **extraherar du zip till mapp** – Steg‑för‑steg‑guide

### Steg 1: Öppna ZIP‑filen (eller krypterat arkiv)

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

Vi öppnar ZIP‑filen med ett `FileStream`. Anpassa sökvägen så att den pekar på ditt eget arkiv. Om arkivet inte är krypterat fungerar samma kod för ett vanligt **dekomprimera zip-mapp**‑scenario.

### Steg 2: Skapa en `Archive`‑instans (ange lösenord vid behov)

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

`Archive`‑konstruktorn tar emot strömmen och ett `ArchiveLoadOptions`‑objekt. Att ange `DecryptionPassword` är hur du **extraherar zip med lösenord** och hanterar **packa upp krypterat arkiv**‑fall.

### Steg 3: Extrahera innehållet till en mål‑mapp

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

Genom att anropa `ExtractToDirectory` skrivs varje post i arkivet till den angivna katalogen, vilket slutför **extrahera zip till mapp**‑operationen. Metoden skapar automatiskt mål‑mappen om den inte finns.

> **Proffstips:** Om du bara behöver extrahera en delmängd av filer, använd överlagringen som accepterar en filter‑delegat istället för att extrahera allt.

## Vanliga problem & felsökning

- **Fel lösenord** – Aspose.Zip kastar ett autentiseringsundantag. Dubbelkolla lösenordsträngen eller hämta den säkert från en konfigurationskälla.  
- **Målsökväg hittades inte** – Säkerställ att sökvägen till mål‑katalogen är giltig; `ExtractToDirectory` skapar saknade mappar, men föräldrasökvägen måste vara åtkomlig.  
- **Stora arkiv** – För mycket stora ZIP‑filer, överväg att extrahera post för post med streaming‑API:t för att hålla minnesanvändningen låg.  

## Vanliga frågor

**Q: Stöder Aspose.Zip andra komprimeringsformat som GZIP?**  
A: Ja, Aspose.Zip för .NET stöder ZIP, GZIP och flera andra vanliga format.

**Q: Kan jag använda Aspose.Zip i både kommersiella och icke‑kommersiella projekt?**  
A: Absolut. En giltig licens krävs för produktion, men du kan använda gratisprovversionen för utvärdering.

**Q: Hur får jag en tillfällig licens för testning?**  
A: Du kan skaffa en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/) för teständamål.

**Q: Var kan jag ladda ner en gratis provversion av Aspose.Zip?**  
A: Besök Aspose.Zip‑provversionssidan [här](https://releases.aspose.com/) för att ladda ner den senaste versionen.

**Q: Var kan jag be om hjälp om jag stöter på problem?**  
A: Aspose.Zip‑community‑forumet är ett bra ställe att få hjälp: [supportforum](https://forum.aspose.com/c/zip/37).

---

**Senast uppdaterad:** 2026-02-15  
**Testat med:** Aspose.Zip för .NET (senaste versionen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}