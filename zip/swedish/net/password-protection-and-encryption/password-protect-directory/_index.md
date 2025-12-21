---
date: 2025-12-21
description: Lär dig hur du skapar lösenordsskyddade zip‑filer i .NET, krypterar mappar
  och ändrar zip‑lösenord med Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Skapa lösenordsskyddat zip för .NET‑kataloger – Aspose.Zip‑handledning
url: /sv/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa lösenordsskyddat zip för .NET‑kataloger – Aspose.Zip‑handledning

I den här guiden kommer du att **skapa lösenordsskyddade zip**‑arkiv för hela kataloger med hjälp av Aspose.Zip‑biblioteket för .NET. Oavsett om du behöver **kryptera en mapp**, säkra säkerhetskopior eller helt enkelt begränsa åtkomsten till känslig data, visar denna steg‑för‑steg‑handledning exakt hur du gör det med ren C#‑kod.

## Snabba svar
- **Vilket bibliotek rekommenderas?** Aspose.Zip for .NET  
- **Kan jag kryptera en hel mapp?** Ja – peka bara API‑et på den mapp du vill zip‑komprimera.  
- **Stöds det att ändra zip‑lösenordet?** Absolut, använd `TraditionalEncryptionSettings`.  
- **Behöver jag en licens för produktion?** En giltig Aspose.Zip‑licens krävs för kommersiell användning.  
- **Fungerar det med .NET Core/5/6?** Ja, API‑et är fullt kompatibelt med moderna .NET‑runtime‑miljöer.  

## Vad betyder “skapa lösenordsskyddat zip”?
Att skapa ett lösenordsskyddat zip innebär att komprimera filer eller kataloger till ett ZIP‑arkiv samtidigt som du applicerar kryptering så att arkivet bara kan öppnas med rätt lösenord. Detta skyddar innehållet mot obehörig åtkomst.

## Varför använda Aspose.Zip för att lösenordsskydda katalog i .NET?
Aspose.Zip erbjuder ett enkelt, högpresterande API som stödjer **c# zip password protection**, traditionell ZipCrypto‑kryptering och AES‑kryptering. Det hanterar stora kataloger effektivt och integreras sömlöst i alla .NET‑projekt.

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskaper i C#‑programmering.  
- Visual Studio (valfri nyare version).  
- Aspose.Zip for .NET‑biblioteket – ladda ner det **[here](https://releases.aspose.com/zip/net/)**.  
- En mapp på disken som du vill skydda med ett lösenord.

## Importera namnrymder
Lägg till de nödvändiga namnrymderna i din C#‑fil så att kompilatorn vet var den ska hitta Aspose.Zip‑klasserna.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Steg 1: Ange sökvägen till resurskatalogen
Definiera sökvägen som pekar på den katalog du avser att zip‑komprimera och skydda.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Lösenordsskydda katalogen
Använd `TraditionalEncryptionSettings` för att ange lösenordet och skapa det krypterade arkivet. Detta är kärnan i **c# zip password protection**.

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
- **Skapar utdatafilen:** `File.Open(..., FileMode.Create)` öppnar (eller skapar) ZIP‑filen som kommer att innehålla den krypterade datan.  
- **Väljer källmappen:** `new DirectoryInfo(".\\CanterburyCorpus")` talar om för Aspose.Zip vilken katalog som ska komprimeras.  
- **Applicerar lösenordet:** `new TraditionalEncryptionSettings("p@s$")` sätter lösenordet som skyddar arkivet.  
- **Lägger till poster & sparar:** `archive.CreateEntries(corpus)` lägger till varje fil i mappen, och `archive.Save(zipFile)` skriver den krypterade ZIP‑filen till disk.

## Hur ändrar man zip‑lösenordet senare?
Om du behöver **change zip password**, återskapa helt enkelt arkivet med en ny `TraditionalEncryptionSettings`‑instans som innehåller det nya lösenordet, och spara det igen.

## Vanliga problem & tips
- **Stora mappar:** Aspose.Zip strömmar data, så minnesanvändningen förblir låg även för enorma kataloger.  
- **Lösenordskomplexitet:** Använd ett starkt lösenord (blanda bokstäver, siffror, symboler) för att förbättra säkerheten.  
- **Licensfel:** Se till att du har applicerat en giltig licensfil; annars körs biblioteket i utvärderingsläge med begränsningar.

## Vanliga frågor

### Är Aspose.Zip för .NET lämplig för stora kataloger?
Ja, Aspose.Zip för .NET är designat för att hantera stora kataloger effektivt och leverera optimal prestanda.

### Kan jag ändra lösenordet för en redan skyddad katalog?
Ja, du kan ändra lösenordet genom att justera `TraditionalEncryptionSettings` i koden enligt behov.

### Finns det några licenskrav för att använda Aspose.Zip för .NET?
Ja, en giltig licens krävs för att använda Aspose.Zip för .NET i en produktionsmiljö. Du kan skaffa en licens **[here](https://purchase.aspose.com/buy)**.

### Finns det en gratis provversion av Aspose.Zip för .NET?
Ja, du kan komma åt en gratis provversion **[here](https://releases.aspose.com/)**.

### Var kan jag hitta ytterligare support för Aspose.Zip för .NET?
Du kan besöka **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** för support eller frågor.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}