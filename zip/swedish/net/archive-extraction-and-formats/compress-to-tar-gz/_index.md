---
date: 2026-06-19
description: Lär dig hur du lägger till flera filer i tar och komprimerar filer till
  tar.gz med Aspose.Zip för .NET – ett snabbt, plattformsoberoende sätt att skapa
  TarGz‑arkiv.
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: Lägg till filer i tar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Lägg till flera filer i tar och skapa tar.gz-arkiv med Aspose.Zip för .NET
url: /sv/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till flera filer i tar och skapa tar.gz-arkiv med Aspose.Zip för .NET

## Introduktion

I moderna .NET‑applikationer är **adding multiple files to tar** och sedan **compressing files to tar.gz** ett vanligt behov—oavsett om du samlar loggfiler, förbereder data för molnlagring eller skapar distributionspaket för Linux‑servrar. Aspose.Zip för .NET tillhandahåller ett rent, högpresterande API som låter dig bygga ett tar‑arkiv, lägga till valfritt antal filer och eventuellt komprimera det till en tar.gz‑fil—utan externa verktyg. I den här guiden går vi igenom hela arbetsflödet, från projektuppsättning till ett produktionsklart `archive.tar.gz`.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.Zip for .NET – it supports tar, tar.gz, zip and many other formats.  
- **Hur lägger jag till flera filer i tar?** Call `TarArchive.CreateEntry` for each file you want to include.  
- **Kan jag komprimera direkt till tar.gz?** Yes—invoke `SaveGzipped` on the `TarArchive` instance.  
- **Behöver jag en licens för produktion?** A valid Aspose license is required for non‑trial use.  
- **Vilka .NET‑versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.

## Vad är “add multiple files to tar”?
Att lägga till flera filer i ett tar‑arkiv betyder att samla flera filer (och eventuellt kataloger) i en enda, okomprimerad behållare samtidigt som deras ursprungliga hierarki och metadata bevaras. Den resulterande `.tar`‑filen kan senare komprimeras med gzip för att skapa ett `tar.gz`‑arkiv, som är allmänt använt för distribution och säkerhetskopiering.

## Varför använda Aspose.Zip för att komprimera filer till tar.gz?
Aspose.Zip hanterar hela tar‑ och gzip‑processen i minnet, vilket eliminerar behovet av inhemska verktyg. Det kan bearbeta **upp till 500 GB‑arkiv** utan att ladda hela filen i minnet, tack vare sin ström‑baserade arkitektur. Biblioteket stöder **50+ in‑ och utdataformat**, körs på Windows, Linux och macOS, och erbjuder ytterligare funktioner såsom kryptering, lösenordsskydd och anpassade postattribut—allt från ett enda .NET‑API.

## Förutsättningar

- Grundläggande .NET‑utvecklingserfarenhet.  
- Visual Studio (eller någon föredragen IDE).  
- Aspose.Zip för .NET installerat – se den officiella dokumentationen [här](https://reference.aspose.com/zip/net/).  
- Aspose.Zip‑biblioteket hämtat från [denna länk](https://releases.aspose.com/zip/net/).

## Importera namnrymder

I ditt .NET‑projekt importerar du namnrymderna som exponerar tar‑relaterade klasser:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Hur man lägger till flera filer i tar med Aspose.Zip för .NET

Med Aspose.Zip laddar du först källmappen, skapar en `TarArchive`, och itererar sedan över varje fil genom att anropa `CreateEntry` för att lägga till den i arkivet. När alla poster har lagts till anropar du `SaveGzipped` för att skapa ett komprimerat `archive.tar.gz`. Detta hela flöde kräver bara några få rader klar, typ‑säker .NET‑kod.

### Steg 1: Ange din dokumentkatalog

Definiera mappen som innehåller filerna du vill arkivera.

```csharp
string dataDir = "Your Document Directory";
```

> **Proffstips:** Använd `Path.Combine` när du bygger sökvägar för att undvika plattforms‑specifika separatorproblem.  
> Metoden `Path.Combine` förenar säkert katalog‑ och filnamn med den lämpliga separatorn för operativsystemet.

### Steg 2: Skapa ett TarGz‑arkiv

Nu skapar vi tar‑arkivet, lägger till poster och komprimerar det i ett smidigt flöde.

#### 2.1 Initiera TarArchive

`TarArchive`‑klassen är Aspose.Zip:s översta objekt som representerar en tar‑behållare i minnet. Att instansiera den förbereder ett tomt arkiv redo för poster.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Lägg till filer – kärnan i “add multiple files to tar”

`CreateEntry` skapar en ny post i tar‑arkivet. Metoden tar **postnamnet** (sökvägen i tar‑arkivet) och **källfilens sökväg** på disken. Anropa den upprepade gånger för att lägga till så många filer som behövs.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Varje anrop av `CreateEntry` lägger till en enskild fil; du kan loopa över en katalogsamling för att lägga till dussintals eller hundratals filer med minimal kod.

#### 2.3 Spara som en Gzippad Tar (hur man komprimerar filer till tar.gz)

`SaveGzipped` skriver tar‑innehållet till en gzip‑ström, vilket skapar en kompakt `archive.tar.gz`‑fil klar för distribution eller lagring.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

Metoden hanterar automatiskt gzip‑huvuden och -fotter, så du får ett standard‑kompatibelt tar.gz utan extra steg.

## Vanliga användningsfall

| Scenario | Varför “add multiple files to tar” hjälper |
|----------|--------------------------------------------|
| **Loggaggregering** | Samla dagliga loggar i ett enda arkiv innan uppladdning till molnlagring. |
| **Distributionspaket** | Skapa portabla tar.gz‑paket för Linux‑servrar från en Windows‑byggpipeline. |
| **Databackup** | Bevara mapphierarki och metadata samtidigt som backup‑storleken hålls låg. |

## Vanliga problem och lösningar

- **Fil hittades inte‑fel** – Se till att `dataDir` slutar med rätt sökvägsseparator eller använd `Path.Combine`.  
- **Stora filer orsakar minnespress** – Använd den ström‑baserade överlagringen av `CreateEntry` (`CreateEntry(string entryName, Stream source)`) för att undvika att ladda hela filer i minnet.  
- **Gzip‑utdata är korrupt** – Verifiera att `TarArchive` har frigjorts (via ett `using`‑block) innan du anropar `SaveGzipped`.  

## Vanliga frågor

**Q: Är Aspose.Zip för .NET kompatibel med alla .NET‑applikationer?**  
A: Ja, den fungerar med .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10‑projekt.

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Zip för .NET?**  
A: Besök [temporär‑licenssidan](https://purchase.aspose.com/temporary-license/) för att begära en provlicens.

**Q: Finns det några fil‑storleksbegränsningar?**  
A: Biblioteket är optimerat för stora filer; det finns ingen hård storleksgräns förutom tillgängligt systemminne, och det kan strömma arkiv större än 100 GB.

**Q: Var kan jag få support?**  
A: Använd det community‑drivna supportforumet [här](https://forum.aspose.com/c/zip/37) för hjälp från Aspose‑ingenjörer och andra utvecklare.

**Q: Kan jag prova Aspose.Zip för .NET gratis?**  
A: Absolut—ladda ner den kostnadsfria provversionen från [Aspose Zip‑releases‑sidan](https://releases.aspose.com/zip/net/).

## Slutsats

Du vet nu hur du **add multiple files to tar**, skapar ett tar‑arkiv och **compress files to tar.gz** med Aspose.Zip för .NET. Detta tillvägagångssätt tar bort externa beroenden, ger dig full kontroll över arkivinnehållet och skalar till mycket stora datamängder. Utforska ytterligare funktioner såsom kryptering, anpassade postattribut och strömnings‑API:er för att ytterligare förbättra ditt arkiveringsflöde.

---

**Senast uppdaterad:** 2026-06-19  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man komprimerar flera filer tar med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Lägg till filer i tar och skapa tarxz‑arkiv med Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Hur man komprimerar tar och skapar TarBz2 med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}