---
date: 2026-03-08
description: Lär dig hur du skapar lösenordsskyddade zip-filer, lösenordsskyddar zip-mapp
  och ändrar zip-lösenord med Aspose.Zip för .NET.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Skapa lösenordsskyddad zip för .NET‑kataloger – Aspose.Zip‑handledning
url: /sv/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa lösenordsskyddad zip för .NET‑kataloger – Aspose.Zip‑handledning

I den här guiden kommer du att **skapa lösenordsskyddade zip**‑arkiv för hela kataloger med hjälp av Aspose.Zip‑biblioteket för .NET. Oavsett om du behöver **kryptera en mapp**, säkra säkerhetskopior eller helt enkelt begränsa åtkomsten till känslig data, visar denna steg‑för‑steg‑handledning exakt hur du gör det med ren C#‑kod.

## Snabba svar
- **Vilket bibliotek rekommenderas?** Aspose.Zip för .NET  
- **Kan jag kryptera en hel mapp?** Ja – peka bara API:et på den mapp du vill zipa.  
- **Stöds ändring av zip‑lösenordet?** Absolut, använd `TraditionalEncryptionSettings`.  
- **Behöver jag en licens för produktion?** En giltig Aspose.Zip‑licens krävs för kommersiell användning.  
- **Fungerar med .NET Core/5/6?** Ja, API:et är fullt kompatibelt med moderna .NET‑runtime‑miljöer.  

## Vad betyder “skapa lösenordsskyddad zip”?
Att skapa en lösenordsskyddad zip innebär att komprimera filer eller kataloger till ett ZIP‑arkiv samtidigt som kryptering appliceras så att arkivet endast kan öppnas med rätt lösenord. Detta skyddar innehållet från obehörig åtkomst.

## Så skapar du en lösenordsskyddad zip för en katalog
Nedan hittar du en komplett, lättläst genomgång som täcker allt från projektuppsättning till att ändra lösenordet senare.

## Varför använda Aspose.Zip för att lösenordsskydda katalog i .NET?
Aspose.Zip erbjuder ett enkelt, högpresterande API som stödjer **c# zip password protection**, traditionell ZipCrypto‑kryptering och AES‑kryptering. Det hanterar stora kataloger effektivt och integreras sömlöst med alla .NET‑projekt.

## Vanliga användningsområden
- **Säkerhetskopianskydd:** Zippa en daglig backup‑mapp och lås den med ett starkt lösenord.  
- **Säker filutbyte:** Skicka ett zip‑mappslösenord till en kund utan att avslöja innehållet.  
- **Regulatorisk efterlevnad:** Lagra personligt identifierbar information (PII) i ett krypterat zip‑arkiv för att uppfylla dataskyddsstandarder.  

## Förutsättningar
- Grundläggande kunskap i C#‑programmering.  
- Visual Studio (valfri nyare version).  
- Aspose.Zip för .NET‑biblioteket – ladda ner det **[här](https://releases.aspose.com/zip/net/)**.  
- En mapp på disken som du vill skydda med ett lösenord.

## Importera namnrymder
Lägg till de nödvändiga namnrymderna i din C#‑fil så kompilatorn vet var den ska hitta Aspose.Zip‑klasserna.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Steg 1: Ange sökvägen till resurskatalogen
Definiera sökvägen som pekar på den katalog du avser att zipa och skydda.

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
- **Skapa utdatafilen:** `File.Open(..., FileMode.Create)` öppnar (eller skapar) ZIP‑filen som kommer att innehålla den krypterade datan.  
- **Välja källmappen:** `new DirectoryInfo(".\\CanterburyCorpus")` talar om för Aspose.Zip vilken katalog som ska komprimeras.  
- **Applicera lösenordet:** `new TraditionalEncryptionSettings("p@s$")` anger lösenordet som kommer att skydda arkivet.  
- **Lägga till poster & spara:** `archive.CreateEntries(corpus)` lägger till varje fil i mappen, och `archive.Save(zipFile)` skriver den krypterade ZIP‑filen till disk.  

## Hur ändrar man zip‑lösenordet senare?
Om du behöver **ändra zip‑lösenordet**, återskapa helt enkelt arkivet med en ny `TraditionalEncryptionSettings`‑instans som innehåller det nya lösenordet, och spara det igen. Detta tillvägagångssätt fungerar också när du vill **skapa ett krypterat zip‑arkiv** från en befintlig mapp med ett annat lösenord.

## Tips för ett starkt zip‑mappslösenord
- Använd en blandning av stora och små bokstäver, siffror och symboler.  
- Sikta på minst 12 tecken; längre lösenord är exponentiellt svårare att knäcka.  
- Undvik vanliga ord eller mönster; överväg att använda en lösenfras.

## Vanliga problem & tips
- **Stora mappar:** Aspose.Zip strömmar data, så minnesanvändningen förblir låg även för enorma kataloger.  
- **Lösenordskomplexitet:** Använd ett starkt lösenord (blandning av bokstäver, siffror, symboler) för att förbättra säkerheten.  
- **Licensfel:** Se till att du har applicerat en giltig licensfil; annars körs biblioteket i utvärderingsläge med begränsningar.  
- **zip‑mappslösenord känns inte igen:** Verifiera att du använder samma krypteringsmetod (`TraditionalEncryptionSettings`) när du öppnar arkivet.

## Vanliga frågor

### Är Aspose.Zip för .NET lämplig för stora kataloger?
Ja, Aspose.Zip för .NET är utformad för att hantera stora kataloger effektivt och leverera optimal prestanda.

### Kan jag ändra lösenordet för en redan skyddad katalog?
Ja, du kan ändra lösenordet genom att justera `TraditionalEncryptionSettings` i koden enligt behov.

### Finns det licenskrav för att använda Aspose.Zip för .NET?
Ja, en giltig licens krävs för att använda Aspose.Zip för .NET i en produktionsmiljö. Du kan skaffa en licens **[här](https://purchase.aspose.com/buy)**.

### Finns det en gratis provversion av Aspose.Zip för .NET?
Ja, du kan få åtkomst till en gratis provversion **[här](https://releases.aspose.com/)**.

### Var kan jag hitta ytterligare support för Aspose.Zip för .NET?
Du kan besöka **[Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37)** för support eller frågor.

## Snabb FAQ (AI‑vänlig)

**Q: Hur krypterar jag en mapp med zip med hjälp av Aspose.Zip?**  
A: Använd `TraditionalEncryptionSettings` när du skapar `Archive`‑objektet, och anropa sedan `CreateEntries` på mål‑mappen.

**Q: Kan jag sätta ett zip‑mappslösenord efter att arkivet har skapats?**  
A: Nej, lösenordet måste definieras vid skapandet; för att ändra det, återskapa arkivet med ett nytt lösenord.

**Q: Stöder Aspose.Zip AES‑kryptering för starkare säkerhet?**  
A: Ja, du kan byta till `AesEncryptionSettings` för AES‑256‑kryptering istället för den traditionella ZipCrypto.

**Q: Är biblioteket kompatibelt med .NET 6 och .NET 7?**  
A: Absolut – den aktuella versionen fungerar med alla moderna .NET‑runtime‑miljöer.

**Q: Vad händer om jag försöker öppna en lösenordsskyddad zip utan lösenord?**  
A: Aspose.Zip kastar ett `PasswordRequiredException` och ber dig ange rätt lösenord.

---

**Senast uppdaterad:** 2026-03-08  
**Testat med:** Aspose.Zip för .NET (senaste version)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}