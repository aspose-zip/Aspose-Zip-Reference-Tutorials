---
date: 2025-12-20
description: Lär dig hur du skapar lösenordsskyddade zip‑arkiv i .NET med Aspose.Zip.
  Denna steg‑för‑steg‑guide visar hur du komprimerar filer med lösenord, sätter lösenord
  för zip‑posten och använder AES‑kryptering.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Skapa lösenordsskyddade ZIP-filer i .NET med Aspose.Zip
url: /sv/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa lösenordsskyddade ZIP-filer i .NET med Aspose.Zip

## Introduktion

Om du behöver **create password protected zip**-arkiv i en .NET-applikation gör Aspose.Zip det enkelt. Genom att tilldela ett unikt lösenord till varje post kan du hålla känsliga dokument säkra samtidigt som du får fördelarna med ZIP-komprimering. I den här handledningen lär du dig hur du komprimerar filer med individuella lösenord, väljer olika krypteringsmetoder och anger ett zip‑postlösenord – allt med tydlig, produktionsklar kod.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.Zip for .NET.
- **Kan jag tilldela ett annat lösenord per fil?** Ja, varje post kan ha sitt eget lösenord.
- **Vilka krypteringsalgoritmer stöds?** Traditional ZipCrypto, AES‑128, och AES‑256.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.
- **Är detta kompatibelt med .NET 6+?** Absolut – API:et riktar sig mot .NET Standard 2.0 och senare.

## Vad är “create password protected zip”?
Att skapa ett lösenordsskyddat zip innebär att lägga till kryptering på en eller flera poster i ett ZIP-arkiv så att innehållet inte kan öppnas utan rätt lösenord. Detta är idealiskt för att överföra konfidentiella filer, lagra säkerhetskopior eller följa dataskyddspolicyer.

## Varför använda Aspose.Zip för lösenordsskyddade arkiv?
- **Finjusterad kontroll** – ange ett separat lösenord per fil.
- **Flera krypteringsalternativ** – från äldre ZipCrypto till stark AES‑128/256.
- **Inga externa beroenden** – rent .NET-bibliotek, enkelt att integrera.
- **Omfattande dokumentation** – innehåller en **aspose zip tutorial** för djupare scenarier.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar:

- Aspose.Zip for .NET: Se till att du har Aspose.Zip‑biblioteket installerat i ditt .NET‑projekt. Du kan hitta den nödvändiga dokumentationen [här](https://reference.aspose.com/zip/net/).
- Nedladdning: Om du inte redan har gjort det, ladda ner Aspose.Zip för .NET‑biblioteket från [denna länk](https://releases.aspose.com/zip/net/).
- Dokumentkatalog: Förbered en katalog som innehåller filerna du vill komprimera.

## Importera namnrymder

I ditt .NET‑projekt, se till att importera de nödvändiga namnrymderna:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Steg 1: Ange sökvägen till resurskatalogen

Definiera sökvägen till resurskatalogen där dina källfiler finns.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Komprimera filer med individuella lösenord

Nu ska vi komprimera filer med individuella lösenord. Vi kommer att använda tre exempel-filer (`alice29.txt`, `asyoulik.txt` och `fields.c`) med olika lösenord för varje. Detta visar hur man **compress files with passwords** och även hur man **set zip entry password** med olika krypteringsscheman, inklusive ett **zip archive with aes**.

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

### Så här fungerar det
- **TraditionalEncryptionSettings** använder den äldre ZipCrypto-algoritmen (kompatibel med de flesta ZIP-verktyg).
- **AesEcryptionSettings** låter dig välja AES‑128 eller AES‑256 för starkare säkerhet.
- Varje `CreateEntry`‑anrop får ett `ArchiveEntrySettings`‑objekt där vi specificerar både komprimeringsmetod och krypteringsinställningar, vilket effektivt **password protect zip archive**-poster.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| “Invalid password” när ZIP‑filen öppnas | Mismatch mellan lösenordet som används i koden och det som anges i extraheringsprogrammet | Verifiera den exakta strängen som skickas till `TraditionalEncryptionSettings` eller `AesEcryptionSettings`. |
| Äldre extraheringsverktyg kan inte öppna AES‑krypterade poster | Inte alla ZIP‑verktyg stödjer AES‑kryptering | Använd den traditionella ZipCrypto‑metoden för maximal kompatibilitet, eller rekommendera användare att använda ett modernt verktyg (t.ex. 7‑Zip). |
| Stora filer orsakar `OutOfMemoryException` | Laddar in enorma filer i minnet innan komprimering | Strömma filen direkt med `FileStream` utan att ladda hela filen i ett `FileInfo`‑objekt. |

## Vanliga frågor (FAQ)

### Kan jag använda olika krypteringsmetoder för varje fil?
Ja, Aspose.Zip for .NET låter dig använda olika krypteringsmetoder för varje fil under komprimering.

### Finns det en provversion tillgänglig?
Ja, du kan komma åt den kostnadsfria provversionen av Aspose.Zip for .NET [här](https://releases.aspose.com/).

### Hur kan jag få support om jag stöter på problem?
Besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för hjälp från communityn och Aspose‑support.

### Var kan jag hitta detaljerad dokumentation för Aspose.Zip for .NET?
Dokumentationen finns [här](https://reference.aspose.com/zip/net/).

### Kan jag köpa en tillfällig licens för teständamål?
Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

## Ytterligare snabba FAQ

**Q: Stöder biblioteket .NET Core och .NET 5/6?**  
A: Ja, Aspose.Zip riktar sig mot .NET Standard, vilket gör det kompatibelt med .NET Framework, .NET Core och .NET 5/6.

**Q: Kan jag lägga till en kommentar till varje ZIP‑post?**  
A: Även om Aspose.Zip fokuserar på kompression och kryptering, kan du lagra metadata i en separat manifestfil i arkivet.

**Q: Är det möjligt att kryptera hela arkivet med ett enda lösenord?**  
A: Du kan sätta ett lösenord på varje post individuellt (som visat) eller använda samma lösenord för alla poster för ett enklare “zip archive with aes”-tillvägagångssätt.

## Slutsats

Du har nu lärt dig hur du **create password protected zip**-filer i .NET med Aspose.Zip. Genom att tilldela individuella lösenord och välja lämplig krypteringsmetod kan du hålla dina data säkra utan att offra fördelarna med ZIP‑komprimering. Utforska andra Aspose.Zip‑funktioner såsom strömning av stora filer, lägga till anpassad metadata och integrera med molnlagring för ännu kraftfullare scenarier.

---

**Senast uppdaterad:** 2025-12-20  
**Testad med:** Aspose.Zip for .NET 23.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}