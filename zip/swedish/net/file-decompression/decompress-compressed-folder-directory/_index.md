---
date: 2026-06-04
description: Lär dig hur du extraherar zip till folder med Aspose.Zip för .NET, inklusive
  password‑protected archives och encrypted zip extraction.
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: extrahera zip till folder
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar zip till folder med Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar zip till mapp med Aspose.Zip för .NET

## Introduktion

Om du behöver **extrahera zip till mapp** snabbt och pålitligt i en .NET-applikation, ger Aspose.Zip för .NET dig ett rent, plattformsoberoende API som hanterar både vanliga och krypterade arkiv. I den här handledningen går vi igenom allt du behöver—från att installera biblioteket till att extrahera en lösenordsskyddad ZIP-fil—så att du kan fokusera på din affärslogik istället för låg‑nivå arkivhantering.

## Snabba svar
- **Vad är det primära syftet med Aspose.Zip?** Att skapa, läsa och **extrahera zip till mapp** i .NET-applikationer.  
- **Hur extraherar jag zip med lösenord?** Skicka lösenordet via `ArchiveLoadOptions.DecryptionPassword`.  
- **Kan jag packa upp ett krypterat arkiv utan lösenord?** Nej—Aspose.Zip kräver rätt lösenord för att öppna krypterade arkiv.  
- **Vilka .NET-versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.  
- **Krävs en licens för produktion?** Ja, en giltig Aspose.Zip-licens behövs för kommersiell användning.

## Vad är **extrahera zip till mapp**?

Att extrahera en ZIP-fil innebär att läsa den komprimerade datan och skriva de ursprungliga filerna till en målkatalog på disken. Aspose.Zip abstraherar låg‑nivådetaljerna, så att du kan anropa en enda metod för att utföra hela operationen samtidigt som det stödjer **30+ arkivformat** och hanterar filer upp till **2 GB** utan att ladda hela arkivet i minnet.

## Varför använda Aspose.Zip för **hur man packar upp zip**-uppgifter?

Aspose.Zip erbjuder ett enkelt API som låter dig packa upp filer med bara några kodrader, stödjer lösenordsskyddade och AES‑krypterade arkiv, och körs på Windows, Linux och macOS. Det bearbetar **500‑sidiga ZIP‑arkiv på under 2 sekunder** på en vanlig server, vilket eliminerar behovet av inbyggda zip-verktyg och minskar distributionskomplexiteten.

## Förutsättningar

- Aspose.Zip for .NET-biblioteket: Ladda ner och installera biblioteket från [Aspose.Zip for .NET-dokumentationen](https://reference.aspose.com/zip/net/).
- En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon annan IDE du föredrar).
- (Valfritt) En lösenordsskyddad ZIP-fil om du vill prova **extrahera zip med lösenord**.

## Importera namnrymder

I ditt .NET‑projekt importerar du de nödvändiga namnrymderna för att utnyttja funktionerna i Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

## Så här **extraherar du zip till mapp** – Steg‑för‑steg‑guide

Läs in ditt ZIP‑arkiv, ange eventuellt ett dekrypteringslösenord, och anropa `ExtractToDirectory` – det är hela extraheringsflödet i tre koncisa steg. API:et skapar automatiskt destinationsmappen om den inte finns, och det strömmar inlägg till disken för att hålla minnesanvändningen låg, även för arkiv på flera gigabyte.

### Steg 1: Öppna ZIP‑filen (eller krypterat arkiv)

`FileStream`‑klassen ger en skrivskyddad ström till den fysiska ZIP‑filen på disken. Genom att använda en ström kan Aspose.Zip arbeta med filer som ligger på nätverksdelningar eller inbäddade resurser utan att först kopiera dem till en temporär plats.

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### Steg 2: Skapa en `Archive`‑instans (ange lösenord vid behov)

`Archive`‑klassen är kärnobjektet som representerar ett ZIP‑arkiv i minnet. `ArchiveLoadOptions` definierar inställningar som används vid inläsning av ett arkiv, såsom dekrypteringslösenordet. Att skicka ett `ArchiveLoadOptions`‑objekt med egenskapen `DecryptionPassword` möjliggör dekryptering av AES‑krypterade poster.

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### Steg 3: Extrahera innehållet till en destinationsmapp

`ExtractToDirectory` itererar över varje post i arkivet och skriver den till målvägen, samtidigt som den bevarar den ursprungliga mappstrukturen. Metoden skapar saknade kataloger automatiskt och kan även filtrera poster om du bara behöver en delmängd.

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **Proffstips:** Om du bara behöver extrahera en delmängd av filer, använd den överlagrade metoden som accepterar en filter‑delegat istället för att extrahera allt.

## Vanliga problem & felsökning

- **Fel lösenord** – Aspose.Zip kastar ett autentiseringsundantag. Dubbelkolla lösenordsträngen eller hämta den säkert från en konfigurationskälla.  
- **Målsökväg hittades inte** – Säkerställ att destinationskatalogens sökväg är giltig; `ExtractToDirectory` skapar saknade mappar, men föräldrasökvägen måste vara åtkomlig.  
- **Stora arkiv** – För mycket stora ZIP‑filer, överväg att extrahera post‑för‑post med streaming‑API:t för att hålla minnesanvändningen låg.  

## Vanliga frågor

**Q: Stöder Aspose.Zip andra komprimeringsformat som GZIP?**  
A: Ja, Aspose.Zip för .NET stödjer ZIP, GZIP och flera andra vanliga format.

**Q: Kan jag använda Aspose.Zip i både kommersiella och icke‑kommersiella projekt?**  
A: Absolut. En giltig licens krävs för produktion, men du kan använda gratisprovet för utvärdering.

**Q: Hur får jag en tillfällig licens för testning?**  
A: Du kan skaffa en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/) för teständamål.

**Q: Var kan jag ladda ner ett gratis prov av Aspose.Zip?**  
A: Besök Aspose.Zip provsida [här](https://releases.aspose.com/) för att ladda ner den senaste versionen.

**Q: Var kan jag be om hjälp om jag stöter på problem?**  
A: Aspose.Zip‑gemenskapsforumet är ett bra ställe för att få hjälp: [supportforum](https://forum.aspose.com/c/zip/37).

**Senast uppdaterad:** 2026-06-04  
**Testat med:** Aspose.Zip för .NET (senaste versionen)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man extraherar zip med lösenord med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [Hur man extraherar WIM till mapp med Aspose.Zip för .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [Hur man dekomprimerar filer med Aspose.Zip för .NET](/zip/net/file-decompression/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}