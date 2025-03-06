---
title: Aspose.Zip för .NET - Handledning för säker fillagring
linktitle: Lagra flera filer utan komprimering med lösenord
second_title: Aspose.Zip .NET API för filkomprimering och arkivering
description: Utforska hur du använder Aspose.Zip för .NET för att säkert lagra flera filer utan komprimering. Enkla steg för lösenordsskydd. Lås upp kraften med filhantering!
weight: 13
url: /sv/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip för .NET - Handledning för säker fillagring


I en värld av .NET-utveckling är hantering och manipulering av filer en vanlig uppgift. Aspose.Zip för .NET är ett kraftfullt bibliotek som ger utvecklare möjlighet att komprimera, dekomprimera och manipulera zip-arkiv sömlöst. I den här handledningen kommer vi att fördjupa oss i ett specifikt scenario: lagra flera filer utan komprimering och skydda dem med ett lösenord. I slutet av den här guiden kommer du att vara utrustad med kunskapen för att implementera denna funktionalitet med Aspose.Zip för .NET.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Zip for .NET Library: Se till att du har Aspose.Zip for .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/zip/net/).

-  Dokumentkatalog: Förbered en katalog där dina källfiler finns. I det angivna exemplet, variabeln`dataDir` representerar din dokumentkatalog.

## Importera namnområden

Till att börja med, låt oss importera de nödvändiga namnrymden för vår kod:

```csharp
// Sökvägen till resurskatalogen.
string dataDir = "Your Document Directory"

// Importera Aspose.Zip-namnområden
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Steg 1: Öppna zip-filen

```csharp
//ExStart: Lagra Flera FilerUtanKompressionMedLösenord
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Detta steg innebär att skapa en ny zip-fil med hjälp av`FileStream`. Filen kommer att heta "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## Steg 2: Öppna källfilen

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Här öppnar vi den första källfilen, "alice29.txt", som kommer att lagras i zip-arkivet.

## Steg 3: Skapa ett arkiv

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 I det här steget skapar vi en instans av`Archive` klass, som anger inställningarna för komprimering och kryptering. Vi använder`StoreCompressionSettings` för att lagra filer utan komprimering och`AesEcryptionSettings` för att tillämpa AES-kryptering med ett lösenord ("p@s$").

## Steg 4: Skapa arkivpost och spara

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Detta sista steg innebär att skapa en post i arkivet för "alice29.txt" och spara arkivet, slutföra processen med att lagra en fil utan komprimering och med lösenordsskydd.

Avsluta din handledning med att sammanfatta nyckelpunkterna och uppmuntra läsarna att utforska ytterligare möjligheter med Aspose.Zip för .NET.

## Slutsats

I den här handledningen undersökte vi hur man använder Aspose.Zip för .NET för att lagra flera filer utan komprimering och säkra dem med ett lösenord. När du fortsätter din resa med .NET-utveckling, utnyttja funktionerna i Aspose.Zip för att effektivisera filhanteringsuppgifter och förbättra säkerheten för dina applikationer.

---

### Vanliga frågor

### Kan jag använda Aspose.Zip för .NET med andra krypteringsmetoder?
 Ja, Aspose.Zip stöder olika krypteringsmetoder. Kontrollera dokumentationen[här](https://reference.aspose.com/zip/net/) för detaljer.

### Var kan jag få support för Aspose.Zip för .NET?
 Besök[Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för samhällsstöd och diskussioner.

### Finns det en gratis testversion tillgänglig för Aspose.Zip för .NET?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Zip för .NET?
 Begär en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).

### Var kan jag köpa Aspose.Zip för .NET?
 Du kan köpa Aspose.Zip för .NET[här](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
