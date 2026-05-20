---
description: Lär dig hur du extraherar RAR till en mapp och dekrypterar krypterade
  RAR‑filer med Aspose.Zip för .NET. Följ en steg‑för‑steg‑guide för att läsa en krypterad
  RAR‑fil och ange RAR‑lösenordet.
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Extrahera RAR till mapp med Aspose.Zip för .NET
url: /sv/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera RAR till mapp med Aspose.Zip för .NET

## Introduktion

Om du behöver **extrahera RAR till mapp** och arbeta med lösenordsskyddade arkiv, gör Aspose.Zip för .NET jobbet smärtfritt. I den här handledningen går vi igenom de exakta stegen för att läsa en krypterad RAR‑fil, ange RAR‑lösenordet och extrahera arkivets innehåll till en målkatalog. Oavsett om du bygger ett skrivbordsverktyg eller en server‑sidig tjänst, kommer du att se hur du snabbt och pålitligt integrerar dekrypteringslogik.

## Snabba svar
- **Vad betyder “extrahera RAR till mapp”?** Det betyder att öppna ett RAR‑arkiv och skriva varje post till en specificerad katalog på disken.  
- **Vilket bibliotek hanterar dekryptering?** Aspose.Zip för .NET erbjuder inbyggt stöd för krypterade RAR‑arkiv.  
- **Behöver jag en licens för testning?** En tillfällig licens finns tillgänglig för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter för ett grundläggande extraheringsscenario.

## Vad är “extrahera RAR till mapp”?
Att extrahera ett RAR‑arkiv till en mapp innebär att dekomprimera varje fil som lagras i arkivet och placera dem i en katalog du väljer. När arkivet är krypterat måste du också ange rätt lösenord innan extraheringen kan ske.

## Varför använda Aspose.Zip för att extrahera krypterade RAR‑filer?
Aspose.Zip döljer komplexiteten i RAR‑formatet och hanterar både standard‑ och krypterade arkiv utan externa beroenden. Det erbjuder ett rent, objekt‑orienterat API, hög prestanda och utmärkt felhantering—perfekt för .NET‑utvecklare som vill ha en pålitlig lösning för **hur man dekrypterar RAR**‑filer.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:

1. Aspose.Zip för .NET‑bibliotek: Se till att du har Aspose.Zip‑biblioteket installerat i ditt .NET‑projekt. Du kan ladda ner det från [Aspose.Zip-dokumentationen](https://reference.aspose.com/zip/net/).
2. Dokumentkatalog: Skapa en katalog där ditt krypterade RAR‑arkiv finns. Ersätt "Your Document Directory" i exempel‑koden med den faktiska sökvägen till den katalogen.

## Importera namnrymder

Låt oss börja med att importera de nödvändiga namnrymderna för att använda Aspose.Zip‑biblioteket effektivt. Lägg till följande rader högst upp i din .NET‑fil:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Steg 1 – Öppna det krypterade RAR‑arkivet

Först, öppna en skrivskyddad ström för den krypterade RAR‑filen. Detta förbereder filen för dekryptering och extrahering.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Steg 2 – Ange RAR‑lösenordet (hur man dekrypterar RAR)

Skapa nu en `RarArchive`‑instans och meddela Aspose.Zip lösenordet som skyddar arkivet. Ersätt `"p@s$"` med det faktiska lösenordet du använde när du skapade den krypterade RAR‑filen.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Steg 3 – Extrahera innehållet till en mapp (extrahera krypterad RAR)

Slutligen, extrahera varje post till den mapp du väljer. Detta slutför **extrahera RAR till mapp**‑operationen.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

Upprepa dessa steg för varje RAR‑arkiv du behöver dekryptera, så att du får en sömlös integration av Aspose.Zip för .NET i ditt projekt.

## Vanliga fallgropar & tips

- **Fel lösenord** – Om lösenordet är fel kastar Aspose.Zip ett `WrongPasswordException`. Dubbelkolla strängen du skickar till `DecryptionPassword`.
- **Stora arkiv** – För mycket stora RAR‑filer, överväg att först extrahera till en temporär mapp och sedan flytta filerna till den slutgiltiga platsen för att undvika att få slut på diskutrymme.
- **Sökvägssäkerhet** – Validera alltid `dataDir` och utdata‑sökvägar för att förhindra katalog‑traverseringssårbarheter.

## Slutsats

Grattis! Du har framgångsrikt **extraherat en RAR till mapp** och lärt dig hur du **läser en krypterad RAR‑fil** med Aspose.Zip för .NET. Detta kraftfulla bibliotek förenklar den komplexa processen att låsa upp lösenordsskyddade arkiv, vilket gör det till ett ovärderligt verktyg för utvecklare som arbetar med .NET‑applikationer.

## Vanliga frågor (FAQ)

### Är Aspose.Zip för .NET kompatibel med alla RAR‑arkivversioner?
Aspose.Zip för .NET stöder olika RAR‑arkivversioner, vilket säkerställer kompatibilitet med ett brett spektrum av filer.

### Kan jag använda Aspose.Zip för .NET i kommersiella projekt?
Ja, Aspose.Zip för .NET är tillgängligt för kommersiell användning. Besök [köpsidan](https://purchase.aspose.com/buy) för licensinformation.

### Finns tillfälliga licenser tillgängliga för teständamål?
Ja, du kan få en tillfällig licens för testning från [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta ytterligare support eller community‑diskussioner?
Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för support och community‑diskussioner.

### Hur får jag åtkomst till dokumentationen för Aspose.Zip för .NET?
[Dokumentationen](https://reference.aspose.com/zip/net/) ger omfattande information om hur du använder Aspose.Zip för .NET.

**Additional Q&A**

**Q:** Hur kan jag extrahera endast specifika filer från en krypterad RAR?  
**A:** Använd `RarArchiveEntry` för att hitta den önskade posten och anropa `ExtractToFile` med dekrypteringslösenordet redan satt på arkivet.

**Q:** Vad händer om jag behöver ändra namn på utdata‑mappen dynamiskt?  
**A:** Bygg utdata‑sökvägen med `Path.Combine` och eventuella kör‑tidsvariabler innan du anropar `ExtractToDirectory`.

**Q:** Stöder Aspose.Zip multi‑volym RAR‑arkiv?  
**A:** Ja, biblioteket kan öppna och extrahera multi‑volym RAR‑set så länge alla delar är åtkomliga.

---

**Senast uppdaterad:** 2026-03-13  
**Testat med:** Aspose.Zip för .NET 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}