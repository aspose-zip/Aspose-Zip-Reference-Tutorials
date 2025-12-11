---
date: 2025-12-10
description: Lås upp potentialen i Aspose.Zip för .NET! Lär dig hur du enkelt dekomprimerar
  mappar med den här steg‑för‑steg‑guiden. Dyk in i en värld av sömlös komprimering
  och extraktion.
linktitle: Decompress Compressed Folder to Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dekomprimera komprimerad mapp till katalog i Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar ZIP-filer med Aspose.Zip för .NET

## Introduktion

Välkommen till världen av Aspose.Zip för .NET, ett robust bibliotek som ger utvecklare möjlighet att hantera komprimerade mappar utan ansträngning. Om du undrar **hur man extraherar zip** filer i .NET, så har den här guiden svaret. I den här handledningen kommer vi att gå igenom processen att dekomprimera en komprimerad mapp till en katalog med hjälp av Aspose.Zip för .NET. Spänn fast dig så tar vi dig igenom varje steg i detalj och avmystifierar komplexiteten i detta kraftfulla verktyg.

## Snabba svar
- **Vad är det primära syftet med Aspose.Zip?** Att skapa, läsa och extrahera ZIP-arkiv i .NET-applikationer.  
- **Hur man extraherar zip** med ett lösenord? Använd `ArchiveLoadOptions` med egenskapen `DecryptionPassword`.  
- **Kan jag packa upp ett krypterat arkiv** utan ett lösenord? Nej – du måste ange rätt lösenord.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Krävs en licens för produktion?** Ja, en giltig Aspose.Zip-licens behövs för kommersiell användning.

## Vad är **hur man extraherar zip**?
Att extrahera en ZIP-fil innebär att läsa den komprimerade datan och skriva de ursprungliga filerna till en mål katalog. Aspose.Zip abstraherar de lågnivådetaljerna, så att du kan fokusera på affärslogik snarare än arkivhantering.

## Varför använda Aspose.Zip för **hur man packar upp mapp**-uppgifter?
- **Enkel API** – minimal kod för att öppna, dekryptera och extrahera arkiv.  
- **Stöder krypterade arkiv** – perfekt för säker datautbyte.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS med .NET Core/.NET 5+.  
- **Inga externa beroenden** – ingen behov av att installera inhemska zip-verktyg.

## Förutsättningar

Innan vi ger oss i kast med detta, se till att du har följande förutsättningar på plats:

- Aspose.Zip för .NET-biblioteket: Ladda ner och installera biblioteket från [Aspose.Zip för .NET-dokumentationen](https://reference.aspose.com/zip/net/).

## Importera namnrymder

I ditt .NET‑projekt importerar du de nödvändiga namnrymderna för att utnyttja funktionerna i Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Nu ska vi bryta ner det medföljande exemplet i flera steg för en heltäckande förståelse.

## Hur man **packar upp mapp** – Steg‑för‑steg-guide

### Steg 1: Öppna den komprimerade mappen

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

Börja med att öppna den komprimerade mappen med en `FileStream`. Justera filsökvägen efter ditt projekts struktur.

### Steg 2: Skapa ett Archive‑objekt (Dekryptera ZIP‑filen)

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

Instansiera ett `Archive`‑objekt, skicka in `zipFile`‑strömmen och ange valfria laddningsalternativ, såsom dekrypteringslösenordet i detta fall. Detta är nyckelsteget när du behöver **packa upp krypterat arkiv**‑filer.

### Steg 3: Extrahera till en katalog

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

Slutligen använder du `ExtractToDirectory`‑metoden för att dekomprimera och extrahera innehållet i den komprimerade mappen till den angivna katalogen. Detta slutför processen **hur man dekomprimerar zip**.

Upprepa dessa steg för andra komprimerade mappar och säkerställ sömlös integration med Aspose.Zip för .NET.

## Vanliga problem & felsökning

- **Fel lösenord** – Om dekrypteringslösenordet är fel, kommer Aspose.Zip att kasta ett autentiseringsundantag. Dubbelkolla lösenordsträngen.  
- **Sökväg ej hittad** – Säkerställ att mål katalogen finns eller låt `ExtractToDirectory` skapa den automatiskt.  
- **Stora arkiv** – För mycket stora ZIP-filer, överväg att extrahera i delar eller använda streaming‑API:er för att minska minnesbelastning.

## Vanliga frågor

**Q: Är Aspose.Zip för .NET kompatibel med olika komprimeringsformat?**  
A: Ja, Aspose.Zip för .NET stöder populära komprimeringsformat som ZIP, GZIP och fler.

**Q: Kan jag använda Aspose.Zip för .NET i både kommersiella och icke‑komersiella projekt?**  
A: Absolut, du kan använda Aspose.Zip för .NET i både kommersiella och icke‑komersiella applikationer.

**Q: Finns det en gratis provperiod för Aspose.Zip för .NET?**  
A: Ja, du kan utforska funktionerna med en gratis provperiod genom att besöka [här](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip för .NET?**  
A: Sök hjälp från Aspose.Zip‑gemenskapen på [supportforumet](https://forum.aspose.com/c/zip/37).

**Q: Behöver jag en tillfällig licens för att testa Aspose.Zip för .NET?**  
A: Ja, du kan skaffa en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/) för teständamål.

**Senast uppdaterad:** 2025-12-10  
**Testad med:** Aspose.Zip för .NET (senaste versionen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}