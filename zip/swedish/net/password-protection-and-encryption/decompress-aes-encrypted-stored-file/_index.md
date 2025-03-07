---
title: Aspose.Zip för .NET - Dekryptering av AES-krypterade filer
linktitle: Dekomprimera AES-krypterad lagrad fil
second_title: Aspose.Zip .NET API för filkomprimering och arkivering
description: Lär dig hur du dekomprimerar AES-krypterade lagrade filer i Aspose.Zip för .NET med den här omfattande steg-för-steg-guiden. Förbättra dina .NET-utvecklingsfärdigheter idag!
weight: 19
url: /sv/net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip för .NET - Dekryptering av AES-krypterade filer


## Introduktion

Välkommen till denna steg-för-steg-guide för att dekomprimera AES-krypterade lagrade filer med Aspose.Zip för .NET. Aspose.Zip är ett kraftfullt .NET-bibliotek som gör det möjligt för utvecklare att arbeta med komprimerade filer utan ansträngning. I den här handledningen kommer vi att fokusera på att dekomprimera filer som är AES-krypterade, vilket ger dig en tydlig förståelse av processen.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Zip för .NET: Se till att du har Aspose.Zip-biblioteket installerat. Du hittar dokumentationen[här](https://reference.aspose.com/zip/net/).

-  Exempel på AES-krypterad fil: Ladda ner ett exempel på AES-krypterad fil från[den här länken](https://releases.aspose.com/zip/net/).

- Din dokumentkatalog: Skapa en katalog där du vill lagra den dekomprimerade filen. Ersätt "Din dokumentkatalog" i kodavsnittet med din faktiska katalogsökväg.

## Importera namnområden

I kodavsnittet som tillhandahålls kommer du att märka användningen av olika namnområden. Se till att inkludera dessa i ditt projekt:

```csharp
using System.IO;
using Aspose.Zip;
```

## Steg 1: Definiera resurskatalogen

Se till att du anger sökvägen till din resurskatalog. I exemplet, ersätt "Din dokumentkatalog" med den faktiska sökvägen.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Öppna det krypterade arkivet

```csharp
using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
{
    using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
    {
        using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
        {
            // Fortsätt till nästa steg...
        }
    }
}
```

## Steg 3: Dekomprimera den krypterade posten

```csharp
using (var decompressed = archive.Entries[0].Open())
{
    byte[] b = new byte[8192];
    int bytesRead;
    while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
    {
        extracted.Write(b, 0, bytesRead);
    }
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du dekomprimerar AES-krypterade lagrade filer med Aspose.Zip för .NET. Denna process låter dig arbeta effektivt med krypterade arkiv i dina .NET-applikationer.

## Vanliga frågor

### Kan jag använda Aspose.Zip för .NET med andra krypteringsalgoritmer?
Aspose.Zip stöder främst AES-kryptering. Se dokumentationen för de senaste uppdateringarna.

### Finns det en testversion tillgänglig?
 Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).

### Hur kan jag få support för Aspose.Zip för .NET?
 Besök supportforumet[här](https://forum.aspose.com/c/zip/37) för att få hjälp från samhället.

### Vilka filformat stöds för komprimering och dekomprimering?
Aspose.Zip stöder olika format, inklusive ZIP, 7z och TAR. Se dokumentationen för en fullständig lista.

### Kan jag använda Aspose.Zip för kommersiella ändamål?
 Ja, du kan köpa en licens[här](https://purchase.aspose.com/buy) för kommersiellt bruk.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
