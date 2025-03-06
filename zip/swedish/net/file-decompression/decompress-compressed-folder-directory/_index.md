---
title: Dekomprimera komprimerad mapp till katalog i Aspose.Zip för .NET
linktitle: Dekomprimera komprimerad mapp till katalog
second_title: Aspose.Zip .NET API för filkomprimering och arkivering
description: Lås upp potentialen hos Aspose.Zip för .NET! Lär dig hur du enkelt dekomprimerar mappar med denna steg-för-steg-guide. Dyk in i en värld av sömlös kompression och extraktion.
weight: 14
url: /sv/net/file-decompression/decompress-compressed-folder-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dekomprimera komprimerad mapp till katalog i Aspose.Zip för .NET

## Introduktion

Välkommen till Aspose.Zip för .NET-världen, ett robust bibliotek som gör det möjligt för utvecklare att hantera komprimerade mappar utan ansträngning. I den här handledningen kommer vi att fördjupa oss i processen att dekomprimera en komprimerad mapp till en katalog med Aspose.Zip för .NET. Spänn upp dig när vi tar dig igenom varje steg i detalj, och avmystifiera krångligheterna med detta kraftfulla verktyg.

## Förutsättningar

Innan vi ger oss ut på denna resa, se till att du har följande förutsättningar på plats:

-  Aspose.Zip för .NET Library: Ladda ner och installera biblioteket från[Aspose.Zip för .NET-dokumentation](https://reference.aspose.com/zip/net/).

## Importera namnområden

I ditt .NET-projekt importerar du nödvändiga namnområden för att utnyttja funktionerna i Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Låt oss nu dela upp exemplet i flera steg för en heltäckande förståelse.

## Steg 1: Öppna den komprimerade mappen

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

 Börja med att öppna den komprimerade mappen med a`FileStream`Justera filsökvägen enligt ditt projekts struktur.

## Steg 2: Skapa en arkivinstans

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

 Instantiera en`Archive` objekt, som passerar`zipFile` stream och tillhandahåller valfria laddningsalternativ, såsom dekrypteringslösenord i det här fallet.

## Steg 3: Extrahera till en katalog

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

 Använd slutligen`ExtractToDirectory` metod för att dekomprimera och extrahera innehållet i den komprimerade mappen till den angivna katalogen.

Upprepa dessa steg för andra komprimerade mappar, vilket säkerställer sömlös integration med Aspose.Zip för .NET.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur man dekomprimerar en komprimerad mapp till en katalog med Aspose.Zip för .NET. Detta bibliotek visar sig vara en ovärderlig tillgång för utvecklare som hanterar komprimerad data i sina projekt.

## FAQ's

### F1: Är Aspose.Zip för .NET kompatibelt med olika komprimeringsformat?

S1: Ja, Aspose.Zip för .NET stöder populära komprimeringsformat som ZIP, GZIP och mer.

### F2: Kan jag använda Aspose.Zip för .NET i både kommersiella och icke-kommersiella projekt?

S2: Absolut, du kan använda Aspose.Zip för .NET i både kommersiella och icke-kommersiella applikationer.

### F3: Finns det en gratis testversion tillgänglig för Aspose.Zip för .NET?

 S3: Ja, du kan utforska funktionerna med en gratis provperiod genom att besöka[här](https://releases.aspose.com/).

### F4: Hur kan jag få support för Aspose.Zip för .NET?

 S4: Sök hjälp från Aspose.Zip-communityt på[supportforum](https://forum.aspose.com/c/zip/37).

### F5: Behöver jag en tillfällig licens för att testa Aspose.Zip för .NET?

 S5: Ja, du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/) för teständamål.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
