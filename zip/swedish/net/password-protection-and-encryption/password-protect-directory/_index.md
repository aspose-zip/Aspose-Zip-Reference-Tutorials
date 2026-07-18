---
date: 2026-07-18
description: Lär dig hur du skapar lösenordsskyddade zip‑filer, lösenordsskyddar zip‑mapp
  och ändrar zip‑lösenord med Aspose.Zip för .NET.
keywords:
- create password protected zip
- zip folder with password
- how to encrypt zip
- password protect zip folder
- encrypt zip archive c#
lastmod: 2026-07-18
linktitle: Lösenordsskydda katalog
og_description: Skapa lösenordsskyddade zip‑arkiv för .NET‑kataloger med Aspose.Zip.
  Denna steg‑för‑steg‑handledning visar hur du krypterar mappar, ändrar lösenord och
  utnyttjar AES‑kryptering.
og_image_alt: 'Developer guide: Create password protected zip for .NET directories
  with Aspose.Zip'
og_title: Skapa lösenordsskyddad zip – Aspose.Zip .NET‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to create password protected zip files, password protect
    zip folder, and change zip password using Aspose.Zip for .NET.
  headline: Create password protected zip for .NET directories – Aspose.Zip Tutorial
  type: TechArticle
- questions:
  - answer: Use `TraditionalEncryptionSettings` when creating the `Archive` object,
      then call `CreateEntries` on the target folder.
    question: How do I encrypt a folder with zip using Aspose.Zip?
  - answer: No, the password must be defined at creation time; to change it, recreate
      the archive with a new password.
    question: Can I set a zip folder password after the archive is created?
  - answer: '`AesEncryptionSettings` configures AES‑256 encryption for a ZIP archive.
      Yes, you can switch to `AesEncryptionSettings` for AES‑256 encryption instead
      of the traditional ZipCrypto.'
    question: Does Aspose.Zip support AES encryption for stronger security?
  - answer: Absolutely – the current release works with all modern .NET runtimes.
    question: Is the library compatible with .NET 6 and .NET 7?
  - answer: Aspose.Zip will throw a `PasswordRequiredException`, prompting you to
      supply the correct password.
    question: What happens if I try to open a password‑protected zip without a password?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip encryption
- Aspose.Zip
- .NET compression
- password protected archive
title: Skapa lösenordsskyddad zip för .NET‑kataloger – Aspose.Zip‑handledning
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa lösenordsskyddad zip för .NET‑kataloger – Aspose.Zip‑handledning

I den här handledningen kommer du att **skapa lösenordsskyddade zip**‑arkiv för hela kataloger med Aspose.Zip‑biblioteket för .NET. Oavsett om du behöver **kryptera en mapp**, säkra säkerhetskopior eller helt enkelt begränsa åtkomsten till känslig data, visar den här steg‑för‑steg‑guiden exakt hur du gör det med ren C#‑kod. I slutet kommer du att förstå hur du skyddar en katalog, byter krypteringsläge och ändrar lösenordet på ett befintligt arkiv.

## Snabba svar
- **Vilket bibliotek rekommenderas?** Aspose.Zip för .NET  
- **Kan jag kryptera en hel mapp?** Ja – peka bara API:et på den mapp du vill zipa.  
- **Stöds det att ändra zip‑lösenordet?** Absolut, använd `TraditionalEncryptionSettings`.  
- **Behöver jag en licens för produktion?** En giltig Aspose.Zip‑licens krävs för kommersiell användning.  
- **Fungerar det med .NET Core/5/6?** Ja, API:et är fullt kompatibelt med moderna .NET‑runtime‑miljöer.  

## Vad betyder “skapa lösenordsskyddad zip”?
Att skapa en lösenordsskyddad zip innebär att komprimera filer eller kataloger till ett ZIP‑arkiv samtidigt som kryptering appliceras så att arkivet endast kan öppnas med rätt lösenord. Detta skyddar innehållet från obehörig åtkomst och uppfyller många dataskyddsregler.

## Hur man skapar lösenordsskyddad zip för en katalog
Läs in mål‑mappen, konfigurera ett lösenord med `TraditionalEncryptionSettings` och strömma data till en ny ZIP‑fil – allt i några koncisa satser. API:et skriver varje post direkt till utdata‑strömmen, så även kataloger på flera gigabyte bearbetas med minimal minnesanvändning.

## Varför använda Aspose.Zip för att lösenordsskydda katalog i .NET?
Aspose.Zip stöder **30+ komprimerings‑ och krypteringsalgoritmer**, kan hantera mappar större än **10 GB** utan att ladda hela arkivet i minnet, och erbjuder både den äldre ZipCrypto och modern AES‑256‑kryptering. Biblioteket är helt trådsäkert, körs på **.NET Framework 4.6+**, **.NET Core 3.1+** och **.NET 6/7**, och inkluderar detaljerad loggning för att hjälpa dig felsöka eventuella problem.

## Vanliga användningsområden
- **Säkerhetskopieringsskydd:** Zippa en daglig backup‑mapp och lås den med ett starkt lösenord.  
- **Säker filutbyte:** Skicka ett zip‑mappslösenord till en kund utan att avslöja innehållet.  
- **Regulatorisk efterlevnad:** Lagra personligt identifierbar information (PII) i ett krypterat zip‑arkiv för att uppfylla dataskyddsstandarder.  

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskap i C#‑programmering.  
- Visual Studio (någon recent version).  
- Aspose.Zip för .NET‑biblioteket – ladda ner det **[här](https://releases.aspose.com/zip/net/)**.  
- En mapp på disken som du vill skydda med ett lösenord.

## Importera namnrymder
Lägg till de nödvändiga namnrymderna i din C#‑fil så kompilatorn vet var den ska hitta Aspose.Zip‑klasserna.

## Steg 1: Ange sökvägen till resurskatalogen
Definiera sökvägen som pekar på den katalog du avser att zipa och skydda.

## Steg 2: Lösenordsskydda katalogen
`TraditionalEncryptionSettings` definierar lösenordet och krypteringsalgoritmen för ett ZIP‑arkiv.  
Använd detta inställningsobjekt när du skapar `Archive`‑instansen för att tillämpa ZipCrypto‑skydd.

## Steg 3: Förklaring av koden
`Archive` representerar ett ZIP‑arkiv och tillhandahåller metoder för att lägga till poster och spara arkivet.

- **Skapa utdatafilen:** `File.Open(..., FileMode.Create)` öppnar (eller skapar) ZIP‑filen som kommer att innehålla den krypterade datan.  
- **Välja källmappen:** `new DirectoryInfo(".\\CanterburyCorpus")` talar om för Aspose.Zip vilken katalog som ska komprimeras.  
- **Applicera lösenordet:** `new TraditionalEncryptionSettings("p@s$")` sätter lösenordet som kommer att skydda arkivet.  
- **Lägga till poster & spara:** `archive.CreateEntries(corpus)` lägger till varje fil i mappen, och `archive.Save(zipFile)` skriver den krypterade ZIP‑filen till disk.  

## Hur ändrar man zip‑lösenordet senare?
För att ändra lösenordet måste du återskapa arkivet eftersom lösenordet lagras i huvudfilen för den centrala katalogen. Skapa en ny `TraditionalEncryptionSettings` med önskat lösenord, öppna det befintliga arkivet, kopiera dess poster till en ny `Archive`‑instans med de nya inställningarna och spara sedan det nya arkivet. Denna process krypterar om alla poster med det nya lösenordet.

## Tips för ett starkt zip‑mappslösenord
- Använd en blandning av versaler, gemener, siffror och symboler.  
- Sikta på minst 12 tecken; längre lösenord är exponentiellt svårare att knäcka.  
- Undvik vanliga ord eller mönster; överväg att använda en lösenfras.  

## Vanliga problem & tips
- **Stora mappar:** Aspose.Zip strömmar data, så minnesanvändningen hålls under **150 MB** även för 5 GB‑kataloger.  
- **Lösenordskomplexitet:** Använd ett starkt lösenord (blandning av bokstäver, siffror, symboler) för att förbättra säkerheten.  
- **Licensfel:** Se till att du har applicerat en giltig licensfil; annars körs biblioteket i utvärderingsläge med begränsningar.  
- **zip‑mappslösenordet känns inte igen:** Verifiera att du använder samma krypteringsmetod (`TraditionalEncryptionSettings`) när du öppnar arkivet.  

## Vanliga frågor

### Är Aspose.Zip för .NET lämplig för stora kataloger?
Ja, Aspose.Zip för .NET är designat för att hantera stora kataloger effektivt och levererar optimal prestanda.

### Kan jag ändra lösenordet för en redan skyddad katalog?
Ja, du kan ändra lösenordet genom att justera `TraditionalEncryptionSettings` i koden på lämpligt sätt.

### Finns det licenskrav för att använda Aspose.Zip för .NET?
Ja, en giltig licens krävs för att använda Aspose.Zip för .NET i en produktionsmiljö. Du kan skaffa en licens **[här](https://purchase.aspose.com/buy)**.

### Finns det en gratis provversion av Aspose.Zip för .NET?
Ja, du kan komma åt en gratis provversion **[här](https://releases.aspose.com/)**.

### Var kan jag hitta ytterligare support för Aspose.Zip för .NET?
Du kan besöka **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** för support eller frågor.

## Snabb FAQ (AI‑vänlig)

**Q: Hur krypterar jag en mapp med zip med hjälp av Aspose.Zip?**  
A: Använd `TraditionalEncryptionSettings` när du skapar `Archive`‑objektet, och anropa sedan `CreateEntries` på mål‑mappen.

**Q: Kan jag sätta ett zip‑mappslösenord efter att arkivet har skapats?**  
A: Nej, lösenordet måste definieras vid skapandet; för att ändra det, återskapa arkivet med ett nytt lösenord.

**Q: Stöder Aspose.Zip AES‑kryptering för starkare säkerhet?**  
A: `AesEncryptionSettings` konfigurerar AES‑256‑kryptering för ett ZIP‑arkiv. Ja, du kan byta till `AesEncryptionSettings` för AES‑256‑kryptering istället för den traditionella ZipCrypto.

**Q: Är biblioteket kompatibelt med .NET 6 och .NET 7?**  
A: Absolut – den nuvarande releasen fungerar med alla moderna .NET‑runtime‑miljöer.

**Q: Vad händer om jag försöker öppna en lösenordsskyddad zip utan ett lösenord?**  
A: Aspose.Zip kommer att kasta ett `PasswordRequiredException`, vilket uppmanar dig att ange rätt lösenord.

**Senast uppdaterad:** 2026-07-18  
**Testad med:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

```csharp
string dataDir = "Your Document Directory";
```

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

## Relaterade handledningar

- [Skapa lösenordsskyddad ZIP med Aspose.Zip för .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Skapa lösenordsskyddade ZIP‑filer med AES‑kryptering med Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Aspose.Zip för .NET – Lösenordsskydda Zip‑arkiv & lagra flera filer utan komprimering](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}