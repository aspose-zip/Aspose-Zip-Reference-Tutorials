---
title: Lösenordsskydda kataloger i .NET med Aspose.Zip Tutorial
linktitle: Lösenordsskyddad katalog
second_title: Aspose.Zip .NET API för filkomprimering och arkivering
description: Lär dig hur du lösenordsskyddar kataloger i .NET med Aspose.Zip. Säkra dina filer utan ansträngning med denna steg-för-steg handledning.
type: docs
weight: 10
url: /sv/net/password-protection-and-encryption/password-protect-directory/
---

## Introduktion

I en värld av .NET-utveckling är hantering och säkrande av kataloger en avgörande aspekt av filhantering. Aspose.Zip för .NET tillhandahåller en robust lösning för lösenordsskyddande kataloger, vilket säkerställer konfidentialitet och integritet för dina känsliga data. I den här handledningen guidar vi dig genom processen att lösenordsskydda en katalog steg för steg, med Aspose.Zip för .NET.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

- Grundläggande förståelse för programmeringsspråket C#.
- Visual Studio installerat på din dator.
-  Aspose.Zip för .NET-bibliotek. Du kan ladda ner den[här](https://releases.aspose.com/zip/net/).
- En katalog som innehåller filer som du vill lösenordsskydda.

## Importera namnområden

För att komma igång måste du importera de nödvändiga namnrymden till ditt C#-projekt. Dessa namnutrymmen är avgörande för att använda funktionerna som tillhandahålls av Aspose.Zip för .NET.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Steg 1: Ställ in sökvägen till resurskatalogen

Först definierar du sökvägen till katalogen som innehåller de filer du vill skydda med ett lösenord.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Lösenordsskydda katalogen

 Låt oss nu fördjupa oss i koden som utför lösenordsskyddet för katalogen. Vi använder`TraditionalEncryptionSettings` klass för att ställa in ett lösenord och tillämpa det på den angivna katalogen.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Steg 3: Förklaring av koden

Låt oss dela upp koden för att förstå varje steg:

-  Ställa in utdatafilen:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` skapar en ny ZIP-fil för den krypterade utdata.

-  Definiera katalogen:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` anger katalogen som ska lösenordsskyddas.

-  Skapa och spara poster:`archive.CreateEntries(corpus)` skapar poster för filerna i den angivna katalogen, och`archive.Save(zipFile)`sparar det lösenordsskyddade arkivet.

## Slutsats

I den här handledningen gick vi igenom processen att lösenordsskydda en katalog med Aspose.Zip för .NET. Genom att följa dessa steg kan du säkerställa säkerheten för dina känsliga filer på ett användarvänligt och effektivt sätt.

---

## Vanliga frågor

### Är Aspose.Zip för .NET lämplig för stora kataloger?
Ja, Aspose.Zip för .NET är designat för att hantera stora kataloger effektivt, vilket ger optimal prestanda.

### Kan jag ändra lösenordet för en redan skyddad katalog?
 Ja, du kan ändra lösenordet genom att justera`TraditionalEncryptionSettings` i koden i enlighet med detta.

### Finns det några licenskrav för att använda Aspose.Zip för .NET?
 Ja, en giltig licens krävs för att använda Aspose.Zip för .NET i en produktionsmiljö. Du kan få en licens[här](https://purchase.aspose.com/buy).

### Finns det en gratis testversion tillgänglig för Aspose.Zip för .NET?
 Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).

### Var kan jag hitta ytterligare stöd för Aspose.Zip för .NET?
 Du kan besöka[Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för support eller frågor.

