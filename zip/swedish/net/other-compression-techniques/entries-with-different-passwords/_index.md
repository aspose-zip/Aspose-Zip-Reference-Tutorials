---
date: 2025-12-18
description: Lär dig hur du krypterar zip‑filer med olika lösenord med Aspose.Zip
  för .NET. Den här guiden visar hur du komprimerar filer med lösenord och skapar
  7z‑arkiv i C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man krypterar ZIP-filer med olika lösenord i Aspose.Zip för .NET
url: /sv/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man krypterar ZIP-filer med olika lösenord i Aspose.Zip för .NET

## Introduktion

Om du behöver **how to encrypt zip** arkiv samtidigt som du ger varje post sitt eget lösenord, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen för att skapa ett 7‑zip‑arkiv där varje fil skyddas med ett unikt lösenord, med hjälp av Aspose.Zip‑biblioteket för .NET. I slutet kommer du att förstå varför kryptering per post är viktigt, hur du konfigurerar det och hur du verifierar resultatet i dina egna projekt.

## Snabba svar
- **What does “encrypt zip” mean?** Det betyder att tillämpa lösenordsbaserat skydd (AES eller ZipCrypto) på innehållet i ett ZIP/7z‑arkiv.  
- **Can each entry have a different password?** Ja—Aspose.Zip låter dig tilldela olika lösenord per fil.  
- **Which .NET versions are supported?** Alla moderna .NET Framework-, .NET Core- och .NET 5/6‑versioner.  
- **Do I need a license for production?** En kommersiell licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **What compression format is used in the example?** Exemplet skapar ett 7z‑arkiv med AES‑256‑kryptering.

## Vad är “how to encrypt zip” med Aspose.Zip?

Att kryptera en ZIP (eller 7z)‑fil innebär att säkra dess poster så att de inte kan öppnas utan rätt lösenord. Aspose.Zip för .NET stöder både klassisk ZipCrypto och starkare AES‑kryptering, och det låter dig ange krypteringsinställningar per post, vilket ger dig fin‑granulär kontroll över säkerheten.

## Varför använda olika lösenord för varje post?

- **Security segmentation:** Om ett lösenord komprometteras, förblir de andra filerna skyddade.  
- **Regulatory compliance:** Vissa branscher kräver separata autentiseringsuppgifter för olika datakategorier.  
- **User‑specific access:** Du kan distribuera ett enda arkiv till flera användare, där varje användare bara låser upp de filer de har behörighet att se.

## Förutsättningar

Innan vi dyker ner, se till att du har:

- **Aspose.Zip for .NET** installerat – se den officiella [dokumentationen](https://reference.aspose.com/zip/net/) för nedladdning och installationsinstruktioner.  
- En mapp på din dator där du kommer att lagra källfilerna (”Document Directory”).  
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
- Varje anrop anger ett **annorlunda lösenord** (`"test1"`, `"test2"`, `"test3"`), vilket ger per‑post skydd.

## Steg 3: Verifiering

Efter att arkivet har sparats kan du skriva ut ett enkelt bekräftelsemeddelande.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Kör programmet och försök sedan öppna `archive.7z` med ett verktyg som 7‑Zip. Det kommer att be dig om ett lösenord för varje post, vilket bekräftar att lösenorden faktiskt är olika.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Incorrect password error** | Lösenordsträngen innehåller oönskade mellanslag eller osynliga tecken. | Trimma lösenordsträngarna (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archive not opening in older tools** | Vissa äldre ZIP‑verktyg stödjer inte AES‑256‑kryptering som används av 7z. | Använd en modern extraherare (7‑Zip 19.00+). |
| **File not added to archive** | Källfilens sökväg är fel eller filen finns inte. | Verifiera `dataDir` och filnamnen, eller använd `Path.Combine(dataDir, "data1.bin")`. |

## Vanliga frågor

### Q1: Är Aspose.Zip för .NET kompatibel med alla versioner av .NET?

A1: Ja, Aspose.Zip för .NET är designad för att sömlöst integreras med alla versioner av .NET‑ramverket.

### Q2: Kan jag använda Aspose.Zip för .NET i mina kommersiella projekt?

A2: Absolut! Aspose.Zip för .NET erbjuder kommersiella licenser, och du kan hitta mer information om hur du köper [här](https://purchase.aspose.com/buy).

### Q3: Finns det en gratis provversion tillgänglig?

A3: Ja, du kan utforska funktionerna i Aspose.Zip för .NET med en gratis provversion. Kom igång [här](https://releases.aspose.com/).

### Q4: Hur kan jag få support för Aspose.Zip för .NET?

A4: För eventuella frågor eller hjälp, besök [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37).

### Q5: Kan jag använda Aspose.Zip för .NET utan en permanent licens?

A5: Ja, du kan skaffa en tillfällig licens för dina kortsiktiga behov. Läs mer [här](https://purchase.aspose.com/temporary-license/).

## Slutsats

Du har just lärt dig **how to encrypt zip** arkiv med per‑post lösenord med hjälp av Aspose.Zip för .NET. Denna teknik ger dig flexibiliteten att skydda varje fil individuellt, vilket uppfyller striktare säkerhetskrav och förenklar användarspecifik distribution. Känn dig fri att experimentera med andra komprimeringsinställningar, större filuppsättningar, eller integrera denna logik i en webbtjänst som genererar säkra arkiv i realtid.

---

**Senast uppdaterad:** 2025-12-18  
**Testad med:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}