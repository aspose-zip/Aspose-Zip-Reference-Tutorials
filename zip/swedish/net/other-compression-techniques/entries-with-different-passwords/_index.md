---
date: 2026-05-05
description: Lär dig hur du komprimerar filer med lösenord och krypterar ZIP-arkiv
  med Aspose.Zip för .NET, inklusive 7z-lösenordsskydd och per fil ZIP-lösenord i
  C#.
keywords:
- compress files with password
- how to encrypt zip
- aes 256 zip encryption
- encrypt zip entries
- per file zip password
linktitle: Poster med olika lösenord
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man komprimerar filer med lösenord och krypterar ZIP-poster med olika lösenord
  med Aspose.Zip för .NET
url: /sv/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man komprimerar filer med lösenord och krypterar ZIP-poster med olika lösenord med Aspose.Zip för .NET

## Introduktion

Om du behöver **komprimera filer med lösenord** och ge varje post sitt eget lösenord, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen för att skapa ett 7‑zip‑arkiv där varje fil är skyddad med ett unikt lösenord, med hjälp av Aspose.Zip‑biblioteket för .NET. I slutet kommer du att förstå varför kryptering per post är viktigt, hur du konfigurerar det och hur du verifierar resultatet i dina egna projekt.

## Snabba svar
- **Vad betyder “encrypt zip”?** Det betyder att tillämpa lösenordsbaserat skydd (AES eller ZipCrypto) på innehållet i ett ZIP/7z‑arkiv.  
- **Kan varje post ha ett annat lösenord?** Ja—Aspose.Zip låter dig tilldela olika lösenord per fil.  
- **Vilka .NET‑versioner stöds?** Alla moderna .NET Framework, .NET Core och .NET 5/6‑versioner.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **Vilket komprimeringsformat används i exemplet?** Exemplet skapar ett 7z‑arkiv med AES‑256‑kryptering.

## Vad är “how to encrypt zip” med Aspose.Zip?
Att kryptera en ZIP (eller 7z)‑fil betyder att säkra dess poster så att de inte kan öppnas utan rätt lösenord. Aspose.Zip för .NET stöder både klassisk ZipCrypto och starkare AES‑kryptering, och det låter dig ange krypteringsinställningar per post, vilket ger dig fin‑granulär kontroll över säkerheten.

## Varför komprimera filer med lösenord?
- **Säkerhetssegmentering:** Om ett lösenord blir komprometterat, förblir de andra filerna skyddade.  
- **Regulatorisk efterlevnad:** Vissa branscher kräver separata autentiseringsuppgifter för olika datakategorier.  
- **Användarspecifik distribution:** Ett enda arkiv kan levereras till många användare, där varje användare bara låser upp de filer de har behörighet att se.

## Varför använda AES 256 zip‑kryptering?
AES‑256 är den nuvarande branschstandarden för stark symmetrisk kryptering. Jämfört med ZipCrypto motstår den moderna brute‑force‑attacker och är fullt kompatibel med 7‑Zip och andra moderna extraherare. När du behöver **aes 256 zip encryption**, gör Aspose.Zip konfigurationen enkel.

## Förutsättningar

Innan vi dyker ner, se till att du har:

- **Aspose.Zip for .NET** installerat – se den officiella [documentation](https://reference.aspose.com/zip/net/) för nedladdnings- och installationsinstruktioner.  
- En mapp på din dator där du sparar källfilerna (”Document Directory”).  
- Grundläggande kunskap om C# och Visual Studio (eller din föredragna .NET‑IDE).

## Importera namnrymder

Vi börjar med att importera namnrymderna som innehåller de klasser vi kommer att behöva.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Ange din dokumentkatalog

Definiera sökvägen som innehåller filerna du vill arkivera.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa poster med olika lösenord

Här är kärnan i handledningen. Vi öppnar en ny 7z‑fil, skapar tre `FileInfo`‑objekt och lägger till varje som en post med sitt eget AES‑lösenord.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Så här fungerar det

- `SevenZipArchive` är behållaren för ett 7‑z‑arkiv.  
- `CreateEntry` tar postnamnet, källfilen, en flagga för överskrivning och ett `SevenZipEntrySettings`‑objekt.  
- Inom `SevenZipEntrySettings` tillhandahåller vi två inställningsobjekt: ett för komprimering (`SevenZipStoreCompressionSettings`) och ett för kryptering (`SevenZipAESEncryptionSettings`).  
- Varje anrop anger ett **annat lösenord** (`"test1"`, `"test2"`, `"test3"`), vilket ger per‑post skydd.

## Steg 3: Verifiering

Efter att arkivet har sparats kan du skriva ut ett enkelt bekräftelsemeddelande.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Kör programmet och försök sedan öppna `archive.7z` med ett verktyg som 7‑Zip. Det kommer att be dig om ett lösenord för varje post, vilket bekräftar att lösenorden faktiskt är olika.

## Kryptera zip‑poster med per‑fil‑lösenord – bästa praxis

När du **encrypt zip entries** med ett per‑fil‑lösenord, tänk på följande tips:

1. **Use strong, unique passwords** – undvik vanliga ord och återanvändning.  
2. **Store passwords securely** – överväg en lösenordshanterare eller ett säkert valv om du behöver distribuera dem.  
3. **Test with multiple tools** – säkerställ att både 7‑Zip och WinRAR kan läsa arkivet, eftersom vissa äldre verktyg kanske inte stödjer AES‑256.  
4. **Document the password‑file mapping** – en enkel CSV (fil, lösenord) hjälper administratörer att hålla reda på vilket lösenord som tillhör vilken post.

## Zip‑arkiv lösenordsskydd – vanliga fallgropar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Incorrect password error** | Lösenordsträngen innehåller oönskade mellanslag eller osynliga tecken. | Trimma lösenordsträngarna (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archive not opening in older tools** | Vissa äldre ZIP‑verktyg stödjer inte AES‑256‑kryptering som används av 7z. | Använd en modern extraherare (7‑Zip 19.00+). |
| **File not added to archive** | Källfilens sökväg är fel eller filen finns inte. | Verifiera `dataDir` och filnamnen, eller använd `Path.Combine(dataDir, "data1.bin")`. |

## Vanliga frågor

### Q1: Är Aspose.Zip för .NET kompatibel med alla versioner av .NET?
A1: Ja, Aspose.Zip för .NET är designad för att sömlöst integreras med alla versioner av .NET‑ramverket.

### Q2: Kan jag använda Aspose.Zip för .NET i mina kommersiella projekt?
A2: Absolut! Aspose.Zip för .NET erbjuder kommersiella licenser, och du kan hitta mer information om hur du köper [here](https://purchase.aspose.com/buy).

### Q3: Finns det en gratis provversion tillgänglig?
A3: Ja, du kan utforska funktionerna i Aspose.Zip för .NET med en gratis provversion. Kom igång [here](https://releases.aspose.com/).

### Q4: Hur kan jag få support för Aspose.Zip för .NET?
A4: För eventuella frågor eller hjälp, besök [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Kan jag använda Aspose.Zip för .NET utan en permanent licens?
A5: Ja, du kan skaffa en tillfällig licens för dina kortsiktiga behov. Hitta mer information [here](https://purchase.aspose.com/temporary-license/).

## Slutsats

Du har precis lärt dig **hur man komprimerar filer med lösenord** och krypterar ZIP‑arkiv med per‑post lösenord med Aspose.Zip för .NET. Denna teknik ger dig flexibiliteten att skydda varje fil individuellt, uppfyller striktare säkerhetskrav och förenklar användarspecifik distribution. Känn dig fri att experimentera med andra komprimeringsinställningar, större filuppsättningar, eller integrera denna logik i en webbtjänst som genererar säkra arkiv i realtid.

---

**Senast uppdaterad:** 2026-05-05  
**Testat med:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}