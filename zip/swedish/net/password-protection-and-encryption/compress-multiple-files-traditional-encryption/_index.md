---
date: 2025-12-20
description: Lär dig hur du lösenordsskyddar zip‑arkiv med Aspose.Zip för .NET med
  traditionell kryptering. Denna guide visar hur du krypterar zip‑filer och lägger
  till filer i zip på ett effektivt sätt.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Lösenordsskydda Zip-arkiv med Aspose.Zip .NET
url: /sv/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lösenordsskydda Zip‑arkiv med Aspose.Zip .NET

## Introduktion

Välkommen till denna steg‑för‑steg‑handledning om **hur man lösenordsskyddar zip‑arkiv** med traditionell kryptering med Aspose.Zip för .NET. Aspose.Zip är ett kraftfullt bibliotek som låter utvecklare skapa, läsa och manipulera zip‑arkiv utan ansträngning. I den här guiden går vi igenom hur du komprimerar flera filer, lägger till dem i ett zip‑arkiv och säkrar arkivet med ett lösenord – allt medan koden hålls ren och underhållbar.

## Snabba svar
- **Vad betyder “password protect zip archive”?** Det innebär att kryptera en zip‑fil så att dess innehåll bara kan öppnas efter att rätt lösenord har angetts.  
- **Vilket bibliotek hanterar detta i .NET?** Aspose.Zip för .NET erbjuder inbyggt stöd för traditionell kryptering.  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.  
- **Kan jag köra detta på Linux?** Absolut – Aspose.Zip är plattformsoberoende och fungerar på Windows, Linux och macOS.  
- **Hur många filer kan jag lägga till?** Du kan lägga till hur många filer du vill; exemplet visar tre, men metoden skalar.

## Vad är “password protect zip archive”?

Ett lösenordsskyddat zip‑arkiv använder kryptering (i detta fall traditionell PKZIP‑kryptering) för att förvränga fildatan i arkivet. När en användare försöker extrahera arkivet måste rätt lösenord anges för att dekryptera innehållet.

## Varför använda Aspose.Zip för denna uppgift?

- **Enkel API** – En rad kod för att aktivera kryptering.  
- **Inga externa beroenden** – Ren .NET, inga inhemska DLL‑filer.  
- **Plattformsoberoende** – Fungerar med .NET Framework, .NET Core och .NET 5/6+.  
- **Prestandaoptimerad** – Hanterar stora filer effektivt.

## Förutsättningar

Innan vi dyker ner, se till att du har följande:

- **Aspose.Zip för .NET** – Ladda ner det från den officiella sidan [här](https://releases.aspose.com/zip/net/).  
- **En mapp med filer** – Ersätt `"Your Document Directory"` i exempel­koden med den faktiska sökvägen som innehåller de filer du vill zip‑a.

## Importera namnrymder

Börja med att importera de nödvändiga namnrymderna så att du kan arbeta med Aspose.Zip‑klasserna:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Så krypterar du zip med traditionell kryptering

### Steg 1: Skapa zip‑filen (Password Protect Zip Archive)

Skapa zip‑filen och konfigurera de traditionella krypteringsinställningarna. Lösenordet `"p@s$"` är bara ett exempel – ersätt det med ett starkt lösenord för riktiga projekt.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Lägg till filer i zip‑arkivet

Nu lägger du till varje fil du vill inkludera. Metoden `CreateEntry` tar filnamnet i zip‑arkivet och en ström (`source1`, `source2`, `source3`) som pekar på den faktiska fildatan.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Spara zip‑filen (komprimera filer med lösenord)

Till sist sparar du arkivet på disk. Detta steg skriver den krypterade zip‑filen till den plats du angav tidigare.

```csharp
archive.Save(zipFile);
```

> **Proffstips:** Stäng alltid strömmar (`using`‑satser) för att frigöra filhandtag omedelbart, särskilt när du arbetar med stora filer.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Fel lösenord‑fel** | Lösenordet matchar inte eller stavfel i `TraditionalEncryptionSettings` | Kontrollera lösenordsträngen och säkerställ att samma lösenord används vid extrahering. |
| **Filen lades inte till** | Källström (`sourceX`) är null eller har frigjorts | Öppna källströmmarna med `File.OpenRead` innan du skickar dem till `CreateEntry`. |
| **Prestanda‑nedgång vid stora filer** | Standardkomprimeringsnivå används med många stora poster | Överväg att sätta `CompressionLevel` i `ArchiveEntrySettings` för snabbare bearbetning. |

## Vanliga frågor

**Q: Kan jag använda detta både i Windows‑ och Linux‑miljöer?**  
A: Ja, Aspose.Zip för .NET är helt plattformsoberoende och fungerar på Windows, Linux och macOS.

**Q: Finns det en gratis provversion?**  
A: Absolut – du kan utforska en gratis provversion av Aspose.Zip för .NET [här](https://releases.aspose.com/).

**Q: Vart kan jag få support om jag stöter på problem?**  
A: Besök det officiella [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för gemenskaps‑hjälp och officiell support.

**Q: Är tillfälliga licenser ett alternativ för utvärdering?**  
A: Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var finns den fullständiga API‑dokumentationen?**  
A: Detaljerad referens finns tillgänglig [här](https://reference.aspose.com/zip/net/).

---

**Senast uppdaterad:** 2025-12-20  
**Testad med:** Aspose.Zip 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}