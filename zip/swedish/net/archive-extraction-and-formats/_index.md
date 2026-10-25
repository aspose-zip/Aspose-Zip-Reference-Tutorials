---
date: 2026-10-25
description: Lär dig hur du extraherar zip-lösenord och ställer in komprimeringsalgoritm
  när du komprimerar tar-filer med Aspose.Zip för .NET, vilket ökar lagringseffektiviteten
  och säkerheten.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Arkivextraktion och format
og_description: Lär dig hur du extraherar zip-lösenord och ställer in komprimeringsalgoritm
  när du komprimerar tar-filer med Aspose.Zip för .NET, vilket ökar lagringseffektiviteten
  och säkerheten.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Extrahera zip-lösenord och komprimera tar-filer med Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Extrahera zip-lösenord och komprimera tar-filer med Aspose.Zip
url: /sv/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera zip-lösenord och komprimera tar-filer med Aspose.Zip

## Introduktion

I den här guiden kommer du att upptäcka **extract zip password**-tekniker, lära dig hur du ställer in komprimeringsalgoritm när du skapar tar‑baserade arkiv, och se hur du bygger TarGz, TarBz2 och andra format med Aspose.Zip för .NET. Oavsett om du bygger en backup‑tjänst, en moln‑lagringsklient eller en databehandlingspipeline, minskar behärskning av dessa operationer lagringskostnader, snabbar upp överföringar och skyddar känsliga filer.

## Snabba svar
- **What is TarBz2?** Ett komprimerat arkiv som kombinerar TAR‑paketering med BZIP2‑komprimering för hög komprimeringsgrad.  
- **Why choose Aspose.Zip for .NET?** Det stöder 50+ arkiv‑ och komprimeringsformat, körs på Windows, Linux och macOS, och håller minnesanvändning under 10 MB för flera hundra megabyte stora arkiv.  
- **Can I create a TarGz archive?** Ja – Aspose.Zip erbjuder TarGz, TarLz, TarXz, TarZ och mer.  
- **How do I extract a password‑protected zip archive?** Ställ in `Password`‑egenskapen på varje `ArchiveEntry` innan du anropar `Extract`.  
- **Do I need a license for production use?** En kommersiell licens krävs för produktion; en gratis provperiod finns tillgänglig för utvärdering.

## Vad är tar-komprimering?

Tar‑komprimering kombinerar TAR‑behållaren med en komprimeringsalgoritm såsom BZIP2, GZIP, LZMA eller XZ. Resultatet är en enda fil (t.ex. `.tar.gz`, `.tar.bz2`) som kan packas upp på Linux, macOS och Windows. Den bevarar den ursprungliga kataloghierarkin, möjliggör slumpmässig åtkomst vid extrahering och stöds brett av kommandoradsverktyg och programmeringsbibliotek, vilket gör den idealisk för plattformsoberoende distribution och arkiveringslagring.

## Varför använda Aspose.Zip för .NET för att hantera dessa format?

Aspose.Zip tillhandahåller ett enhetligt, beroende‑fritt API som stöder **50+** arkiv‑ och komprimeringsformat, inklusive alla större tar‑baserade typer. Dess streaming‑arkitektur bearbetar arkiv större än 10 GB samtidigt som RAM‑användningen hålls under 10 MB, vilket gör den idealisk för hög‑genomströmning serverarbetsbelastningar.  

**Direct answer:** Du använder Aspose.Zip eftersom det låter dig skapa, komprimera och extrahera tar‑baserade arkiv och lösenordsskyddade zip‑filer med ett enda flytande API, utan externa verktyg, samtidigt som du hanterar multi‑gigabyte‑arkiv i ett minnes‑effektivt streaming‑läge.

## Förutsättningar
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, eller .NET 5–10.  
- Aspose.Zip för .NET NuGet‑paket (`Install-Package Aspose.Zip`).  
- Grundläggande kunskap om C# fil‑I/O och .NET‑projektssystemet.

## Steg‑för‑steg guide

### Så komprimerar du tar‑filer – direkt svar
Skapa en `Archive`‑instans, lägg till filerna du vill paketera, sätt `CompressionType.BZip2` (eller en annan algoritm) och anropa `Save` med `ArchiveFormat.TarBz2`. Biblioteket skriver TAR‑behållaren och komprimerar den i ett enda streaming‑pass, så du aldrig laddar hela arkivet i minnet.

### Steg 1: Välj det arkivformat du behöver
Bestäm vilket tar‑baserat format som bäst matchar din komprimerings‑hastighetsavvägning:

- **TarBz2** – Högsta komprimeringsförhållandet (≈30 % mindre än TarGz) men långsammare.  
- **TarGz** – Bra balans mellan hastighet och storlek; idealiskt för de flesta moln‑lagringsscenarier.  
- **TarLz / TarXz** – Mycket hög kompression med måttlig hastighet, användbart för arkiveringslagring.  
- **TarZ** – Äldre format för kompatibilitet med äldre Unix‑verktyg.

### Steg 2: Skapa en ny `Archive`‑instans
`Archive` representerar en enskild arkivfil och tillhandahåller metoder för att lägga till poster och spara arkivet.  

`Archive`‑klassen hanterar packnings‑ och komprimeringsflödet, och exponerar metoder för att lägga till poster och skriva den slutliga filen.

### Steg 3: Lägg till filer och mappar
Du kan lägga till ett helt katalogträd med `AddAll` eller lägga till enskilda filer med `AddFile`.  

`AddAll` lägger till ett helt katalogträd i arkivet och bevarar dess struktur.  
`AddFile` lägger till en enskild fil i arkivet. Att bevara den ursprungliga mapphierarkin är så enkelt som att ange bas‑katalogsökvägen.

### Steg 4: Ställ in önskad komprimeringstyp
`CompressionType`‑enum specificerar den komprimeringsalgoritm som tillämpas på TAR‑strömmen.  

`CompressionType` enumererar de stödda algoritmerna (BZip2, GZip, LZMA, XZ, etc.) som kommer att tillämpas vid sparande.

### Steg 5: Spara arkivet
`ArchiveFormat`‑enum väljer behållare‑ och komprimeringskombination för utdatafilen.  

Att anropa `Save` skriver arkivet till disk med det valda formatet.

### Steg 6: Extrahera arkiv med lösenord
`ArchiveEntry` representerar en enskild fil‑ eller katalogpost i ett arkiv.  

För att extrahera ett lösenordsskyddat zip, öppna arkivet, lokalisera varje `ArchiveEntry`, tilldela dess `Password`‑egenskap och anropa `Extract`. `Password`‑egenskapen anger dekrypteringslösenordet för en zip‑post. Denna per‑post lösenordmodell låter dig skydda enskilda filer i ett enda zip.

### Steg 7: Verifiera resultatet
Efter extrahering, jämför filstorlekar och SHA‑256‑kontrollsummor för att bekräfta att arkivets rundresa bevarade dataintegriteten.

## Vanliga användningsfall
- **Backup‑verktyg** – Spara dagliga säkerhetskopior som `.tar.bz2` för att minska lagringskostnaderna med upp till 30 %.  
- **Plattformsoberoende datautbyte** – Tar‑baserade format förstås nativt av Linux-, macOS- och Windows‑verktyg.  
- **Säker distribution** – Tilldela lösenord till känsliga poster, vilket uppfyller efterlevnadskrav utan extra krypteringsverktyg.

## Felsökning & tips
- **Stora arkiv** – Använd streaming‑API:t (`Archive.CreateEntryFromFile`) för att hålla minnesanvändningen låg.  
- **Lösenordsmissmatchning** – Lösenordet som sätts på varje `ArchiveEntry` måste matcha exakt; annars kastas `InvalidPasswordException`.  
- **Komprimeringsnivå** – BZIP2 exponerar inte anpassade nivåer; om du behöver finare kontroll, byt till LZMA (`CompressionType.LZMA`) eller XZ (`CompressionType.XZ`).  

## Vanliga frågor

**Q: Hur skapar jag ett TarGz‑arkiv?**  
A: Ställ in `CompressionType.GZip` och använd `ArchiveFormat.TarGz` när du anropar `Save`. Detta skapar en `.tar.gz`‑fil i ett enda steg.

**Q: Kan jag extrahera ett lösenordsskyddat arkiv utan att känna till lösenordet?**  
A: Nej. Varje post måste förses med rätt lösenord; annars misslyckas extraheringen med ett `InvalidPasswordException`.

**Q: Stöder Aspose.Zip att extrahera arkiv med olika lösenord per post?**  
A: Ja. Tilldela ett lösenord till varje `ArchiveEntry` individuellt innan du anropar `Extract`.

**Q: Vilket format ger bästa komprimeringen?**  
A: TarBz2 ger vanligtvis den minsta storleken, följt av TarLz och TarXz. TarGz erbjuder ett snabbare, fortfarande effektivt alternativ.

**Q: Finns det någon gräns för hur många filer jag kan lägga till i ett TAR‑arkiv?**  
A: Praktiskt taget ingen, men extremt stora arkiv (>10 GB) kan ha nytta av att delas upp i flera delar för enklare hantering.

## Arkivextrahering och format‑handledningar
### [Filkomprimering till TarBz2 med Aspose.Zip för .NET](./compress-to-tar-bz2/)
Lär dig hur du komprimerar filer till TarBz2‑format i .NET med Aspose.Zip. Följ vår steg‑för‑steg‑guide för effektiv filkomprimering.  
### [Komprimering till TarGz med Aspose.Zip för .NET](./compress-to-tar-gz/)
Utforska effektiv filkomprimering i .NET med Aspose.Zip. Komprimera till TarGz utan ansträngning.  
### [Komprimering till TarLz med Aspose.Zip för .NET](./compress-to-tar-lz/)
Komprimera enkelt filer i .NET med Aspose.Zip. Lär dig skapa TarLz‑arkiv steg‑för‑steg.  
### [Komprimering till TarXz med Aspose.Zip för .NET](./compress-to-tar-xz/)
Lär dig komprimera filer till TarXz‑format i .NET med Aspose.Zip. Följ vår guide för effektiv lagring och överföring.  
### [Komprimering till TarZ med Aspose.Zip för .NET](./compress-to-tar-z/)
Utforska steg‑för‑steg‑komprimering till TarZ med Aspose.Zip för .NET. Effektiv filhantering för dina .NET‑projekt.  
### [Extrahera arkivposter med olika lösenord i Aspose.Zip för .NET](./extract-archive-different-passwords/)
Lär dig hur du extraherar arkivposter med olika lösenord i Aspose.Zip för .NET. Öka säkerhet och flexibilitet i dina applikationer.

## Relaterade handledningar

- [Skapa tar‑arkiv och lägg till filer i tar med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hur man komprimerar tar och skapar TarBz2 med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Lägg till filer i tar och skapa tarxz‑arkiv med Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Senast uppdaterad:** 2026-10-25  
**Testat med:** Aspose.Zip för .NET 24.11  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}