---
date: 2026-05-15
description: Lär dig hur du skapar lösenordsskyddade zip-filer och komprimerar filer
  med lösenord med Aspose.Zip för .NET i några enkla steg.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Komprimera filer med individuella lösenord
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Skapa lösenordsskyddad ZIP i .NET med Aspose.Zip
url: /sv/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa lösenordsskyddad ZIP i .NET med Aspose.Zip

## Introduktion

I den här handledningen kommer du att lära dig hur du **skapar lösenordsskyddade zip**‑filer i en .NET‑applikation med Aspose.Zip. Säker komprimering är avgörande när du behöver överföra konfidentiella data eller lagra känsliga dokument utan att de exponeras för obehörig åtkomst.

**Aspose.Zip** är ett .NET‑bibliotek som möjliggör att skapa, läsa och kryptera ZIP‑arkiv programmässigt. Det stöder AES‑256‑kryptering och låter dig tilldela ett unikt lösenord till varje post i arkivet.

## Snabba svar
- **Vad gör Aspose.Zip?** Den skapar och manipulerar ZIP‑arkiv, inklusive lösenordsskydd per fil.  
- **Hur många lösenord kan jag tilldela?** Ett unikt lösenord per fil; obegränsat antal poster.  
- **Vilken krypteringsalgoritm används?** AES‑256, vilket ger 256‑bits säkerhet.  
- **Behöver jag en licens för testning?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

- Aspose.Zip for .NET: Se till att du har Aspose.Zip‑biblioteket installerat i ditt .NET‑projekt. Du kan hitta den nödvändiga dokumentationen [here](https://reference.aspose.com/zip/net/).

- Download: Om du ännu inte har gjort det, ladda ner Aspose.Zip för .NET‑biblioteket från [this link](https://releases.aspose.com/zip/net/).

- Document Directory: Förbered en katalog som innehåller filerna du vill komprimera.

## Importera namnrymder

I ditt .NET‑projekt, se till att importera de nödvändiga namnrymderna:

`ZipFile` är Aspose.Zip:s primära klass för att skapa ZIP‑arkiv och tilldela individuella lösenord till varje post.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Hur skapar man lösenordsskyddade zip‑filer i .NET?

Läs in målmappen, skapa ett `ZipFile`‑objekt, lägg till varje fil med sitt eget lösenord och anropa slutligen `Save` för att skriva arkivet. Hela processen kräver bara några kodrader och garanterar att varje post krypteras med det lösenord du anger.

### Steg 1: Ange sökvägen till resurskatalogen

Definiera sökvägen till resurskatalogen där dina filer finns.

```csharp
string dataDir = "Your Document Directory";
```

### Steg 2: Komprimera filer med individuella lösenord

Nu ska vi komprimera filer med individuella lösenord. Vi kommer att använda tre exempel‑filer (`alice29.txt`, `asyoulik.txt` och `fields.c`) med olika lösenord för var och en.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

## Varför använda lösenordsskydd för ZIP‑arkiv?

Aspose.Zip stöder **30+ komprimeringsalgoritmer** och kan kryptera arkiv med AES‑256, vilket ger upp till **256‑bits säkerhet**. Det kan bearbeta arkiv på flera hundra megabyte utan att ladda hela filen i minnet, vilket gör det idealiskt för högpresterande server‑sidor scenarier. Dessutom hjälper lösenordsskydd att uppfylla regulatoriska krav som GDPR och HIPAA genom att säkerställa att känslig data förblir krypterad både i vila och under överföring.

## Slutsats

Grattis! Du har nu framgångsrikt lärt dig hur du **skapar lösenordsskyddade zip**‑filer och **komprimerar filer med lösenord** med Aspose.Zip för .NET. Denna funktion lägger till ett extra säkerhetslager för dina komprimerade filer, vilket säkerställer konfidentialitet och efterlevnad av dataskyddspolicys.

## Vanliga frågor

**Q: Kan jag använda olika krypteringsmetoder för varje fil?**  
A: Ja, Aspose.Zip låter dig välja krypteringsalgoritmen (t.ex. AES‑256) för varje post när du lägger till den i arkivet.

**Q: Finns det en provversion tillgänglig?**  
A: Ja, du kan komma åt den gratis provversionen av Aspose.Zip för .NET [here](https://releases.aspose.com/).

**Q: Hur kan jag få support om jag stöter på problem?**  
A: Besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för hjälp från communityn och Aspose‑support.

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Zip för .NET?**  
A: Dokumentationen finns tillgänglig [here](https://reference.aspose.com/zip/net/).

**Q: Kan jag köpa en tillfällig licens för teständamål?**  
A: Ja, du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-05-15  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Skapa lösenordsskyddad ZIP med Aspose.Zip för .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Lösenordsskydda ZIP‑filer med AES‑kryptering med Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Komprimera flera filer med kryptering i Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}