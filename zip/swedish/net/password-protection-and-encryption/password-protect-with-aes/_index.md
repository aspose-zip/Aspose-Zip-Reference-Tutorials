---
title: Säkra dina filer - AES-kryptering med Aspose.Zip
linktitle: Lösenordsskydd med AES
second_title: Aspose.Zip .NET API för filkomprimering och arkivering
description: Lär dig hur du förbättrar din filsäkerhet med Aspose.Zip för .NET med AES-kryptering. Följ vår steg-för-steg-guide för optimalt skydd.
weight: 11
url: /sv/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Säkra dina filer - AES-kryptering med Aspose.Zip


## Introduktion

Att skydda dina känsliga filer är avgörande i dagens digitala tidsålder, och Aspose.Zip för .NET tillhandahåller en robust lösning för lösenordsskydd av dina arkiv med Advanced Encryption Standard (AES). I den här handledningen kommer vi att utforska hur man implementerar AES-kryptering med tre nyckellängder – 128-bitars, 192-bitars och 256-bitars – för att säkerställa högsta säkerhetsnivå för dina komprimerade filer.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Zip för .NET: Se till att du har Aspose.Zip-biblioteket integrerat i ditt .NET-projekt. Du kan ladda ner den[här](https://releases.aspose.com/zip/net/).

- Dokumentkatalog: Ha en katalog där dina källfiler finns.

## Importera namnområden

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Steg 1: Lösenordsskydd med AES-128

```csharp
//ExStart:PasswordProtectWithAES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//Exend: PasswordProtectWithAES128
```

det här steget skapar vi en zip-fil och skyddar den med AES-128-kryptering. Lösenordet "p@s$" garanterar säkerheten för ditt arkiv.

## Steg 2: Lösenordsskydd med AES-192

```csharp
//ExStart:PasswordProtectWithAES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//Exend: PasswordProtectWithAES192
```

Det här steget visar hur man implementerar AES-192-kryptering för förbättrad säkerhet. Samma lösenord "p@s$" används för konsekvens.

## Steg 3: Lösenordsskydd med AES-256

```csharp
//ExStart:PasswordProtectWithAES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: PasswordProtectWithAES256
```

I det här sista steget implementerar vi den högsta krypteringsnivån, AES-256, vilket ger ett extra lager av säkerhet för dina komprimerade filer.

## Slutsats

I den här handledningen har vi täckt de väsentliga stegen för att lösenordsskydda dina arkiv med AES-kryptering i Aspose.Zip för .NET. Oavsett om du väljer 128-bitars, 192-bitars eller 256-bitars kryptering kommer dina filer att vara säkra från obehörig åtkomst.

## Vanliga frågor

### Kan jag använda Aspose.Zip för .NET med andra programmeringsspråk?
Aspose.Zip är i första hand designad för .NET-applikationer, vilket säkerställer sömlös integration och optimal prestanda.

### Är AES-krypteringsmetoden säker för känslig data?
Ja, AES-kryptering är allmänt erkänt som en säker och robust metod för att skydda känslig information.

### Kan jag ändra lösenordet för ett redan krypterat arkiv?
Nej, lösenordet för ett krypterat arkiv kan inte ändras när det väl är inställt. Du måste skapa ett nytt krypterat arkiv med ett annat lösenord.

### Finns det några begränsningar för filtyperna som kan krypteras med Aspose.Zip?
Aspose.Zip stöder kryptering av olika filtyper, vilket säkerställer flexibilitet när det gäller att säkra olika typer av data.

### Vad händer om jag glömmer lösenordet för ett krypterat arkiv?
Tyvärr finns det inget sätt att återställa ett krypterat arkivs lösenord. Det är viktigt att förvara lösenordet på en säker plats.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
