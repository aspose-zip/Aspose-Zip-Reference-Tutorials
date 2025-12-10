---
date: 2025-12-10
description: Lär dig hur du lagrar filer utan komprimering med Aspose.Zip för .NET.
  Denna guide visar hur du skapar ett okomprimerat zip‑arkiv, sparar filer i zip‑filen
  och hanterar arkiv på ett effektivt sätt.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man lagrar filer okomprimerade med Aspose.Zip för .NET
url: /sv/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lagrar filer okomprimerade med Aspose.Zip för .NET

I modern .NET‑utveckling kan **hur man lagrar filer** effektivt göra en stor skillnad i prestanda och lagringskostnader. När du behöver behålla filer exakt som de är—utan någon komprimering—så erbjuder Aspose.Zip för .NET ett rent, enkelt API. I den här handledningen går vi igenom stegen för att skapa ett okomprimerat ZIP‑arkiv, spara filer till ZIP och integrera lösningen i din applikation.

## Snabba svar
- **Vad betyder “uncompressed zip”?** Det är ett ZIP‑arkiv där varje post lagras med “store”-metoden, vilket lämnar de ursprungliga filbytena orörda.  
- **Varför undvika komprimering?** För att snabba upp arkivering, bevara originalfilstorlekar för efterföljande bearbetning, eller uppfylla regulatoriska krav som förbjuder dataändring.  
- **Vilken Aspose.Zip‑klass hanterar detta?** `ArchiveEntrySettings` kombinerat med `StoreCompressionSettings`.  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework, .NET Core, .NET 5/6/7 och senare.

## Vad innebär att lagra flera filer utan komprimering?
Att lagra flera filer utan komprimering innebär att lägga till varje fil i en ZIP‑behållare med *store*-komprimeringsmetoden. Filerna förblir byte‑för‑byte identiska med originalen, vilket är idealiskt när du vill ha snabb arkivering eller behöver hålla data oförändrade.

## Varför använda Aspose.Zip för okomprimerade arkiv?
- **Hastighet:** Inga CPU‑intensiva komprimeringsalgoritmer körs.  
- **Förutsägbar storlek:** Arkivets storlek är lika med summan av originalfilerna plus minimal ZIP‑overhead.  
- **Kompatibilitet:** Det resulterande ZIP‑filen fungerar med alla standardverktyg för uppackning.  
- **Flexibilitet:** Du kan fortfarande blanda komprimerade och okomprimerade poster i samma arkiv om så behövs.

## Förutsättningar
- **Aspose.Zip for .NET** – integrerad i ditt projekt. Se den officiella [dokumentationen](https://reference.aspose.com/zip/net/) för installationssteg.  
- **.NET Development Environment** – Visual Studio, VS Code eller någon IDE du föredrar.  
- **Document Directory** – en mapp på din maskin som innehåller filerna du vill arkivera (t.ex. “Your Document Directory”).

## Importera namnrymder
Innan du skriver någon kod, importera de nödvändiga namnrymderna så att kompilatorn vet var den ska hitta Aspose‑klasserna.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Steg 1: Ange dokumentkatalog
Definiera sökvägen där dina källfiler finns. Ersätt platshållaren med den faktiska mappen på ditt system.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa ZIP‑arkiv utan kompression
Kärnan i handledningen – vi skapar en `Archive`‑instans konfigurerad med `StoreCompressionSettings`. Detta instruerar Aspose.Zip att *store* (dvs. inte komprimera) varje post.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Proffstips:** Om du behöver **spara filer till zip** samtidigt som du komprimerar vissa och lämnar andra okomprimerade, skapa separata `ArchiveEntrySettings`‑instanser för varje fil och lägg till dem i samma `Archive`.

## Vanliga problem och lösningar
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Filen hittades inte** | Felaktig `dataDir`‑sökväg eller saknad filändelse. | Verifiera sökvägen och säkerställ att filerna finns. Använd `Path.Combine` för säkrare sammanslagning. |
| **Åtkomst nekad** | Processen saknar behörighet att läsa källfilerna eller skriva ZIP‑filen. | Kör applikationen med lämpliga rättigheter eller välj en mapp med skrivbehörighet. |
| **Oväntad filstorlek i ZIP** | Arkivet skapades med standardkomprimering. | Se till att `new StoreCompressionSettings()` skickas till `ArchiveEntrySettings`. |

## Vanliga frågor

**Q: Kan jag komprimera specifika filtyper medan jag lagrar andra utan kompression?**  
A: Ja, du kan skapa olika `ArchiveEntrySettings` för varje fil och blanda komprimerade och okomprimerade poster i samma arkiv.

**Q: Är Aspose.Zip för .NET kompatibel med .NET Core och .NET 5/6?**  
A: Absolut. Biblioteket stöder .NET Framework, .NET Core, .NET Standard och de senaste .NET‑versionerna.

**Q: Hur bör jag hantera undantag under arkiveringsprocessen?**  
A: Omge arkiveringskoden med ett `try‑catch`‑block och logga undantagsdetaljerna. Detta säkerställer en kontrollerad felhantering och underlättar felsökning.

**Q: Stöder Aspose.Zip flerkärnig (multi‑threaded) arkivering?**  
A: Ja, du kan bearbeta flera filer parallellt och lägga till dem i arkivet, men kom ihåg att `Archive`‑objektet i sig inte är trådsäkert; synkronisera åtkomst när du lägger till poster.

**Q: Kan jag integrera Aspose.Zip i ett befintligt projekt utan stora kodändringar?**  
A: Definitivt. API‑et är utformat för enkel drop‑in‑användning. Se den officiella [dokumentationen](https://reference.aspose.com/zip/net/) för migrationsvägledning.

---

**Senast uppdaterad:** 2025-12-10  
**Testad med:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}