---
date: 2026-06-19
description: Lär dig hur du komprimerar tar-filer, skapar targz-arkiv och extraherar
  lösenordsskyddade zip-filer med Aspose.Zip för .NET – förbättrar lagringseffektivitet
  och säkerhet.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Arkivextraktion och format
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man komprimerar tar-filer med Aspose.Zip för .NET
url: /sv/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man komprimerar Tar-filer med Aspose.Zip för .NET

## Introduktion

I den här guiden kommer du att upptäcka **hur man komprimerar tar** filer med Aspose.Zip för .NET, lära dig att skapa TarGz‑arkiv och se hur du extraherar lösenordsskyddade zip‑arkiv. Effektiv hantering av arkiv är en grundläggande färdighet för moderna .NET‑utvecklare—oavsett om du bygger en backup‑tjänst, en molnlagringsklient eller en databehandlingspipeline, så minskar behärskning av dessa format lagringskostnader, snabbar upp överföringar och håller känslig data säker.

## Snabba svar
- **Vad är TarBz2?** Ett komprimerat arkiv som kombinerar TAR‑paketering med BZIP2‑komprimering för höga komprimeringsförhållanden.  
- **Varför välja Aspose.Zip för .NET?** Den erbjuder ett enhetligt, flytande API för att skapa och extrahera många arkivformat utan externa beroenden.  
- **Kan jag skapa ett TarGz‑arkiv?** Ja – Aspose.Zip stöder TarGz, TarLz, TarXz, TarZ och mer.  
- **Hur extraherar jag ett lösenordsskyddat zip‑arkiv?** Använd `Password`‑egenskapen på `ArchiveEntry`‑objektet vid extrahering.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs för produktion; en gratis provversion finns tillgänglig för utvärdering.

## Vad är Tar-komprimering?
Tar (Tape Archive) är ett containerformat som samlar flera filer och kataloger i en enda ström utan komprimering. När du applicerar en komprimeringsalgoritm som BZIP2, GZip, LZMA eller XZ blir resultatet ett **tar‑baserat arkiv** som `.tar.bz2`, `.tar.gz`, `.tar.lz` osv. Dessa format stöds brett på Linux, macOS och Windows, vilket gör dem idealiska för plattformsoberoende datautbyte.

## Varför använda Aspose.Zip för .NET för att hantera dessa format?
Aspose.Zip tillhandahåller ett **enhetligt, beroendefritt API** som stödjer över 50 arkiv‑ och komprimeringsformat, inklusive TarBz2, TarGz, TarLz, TarXz och TarZ. Det körs på Windows, Linux och macOS, och dess strömbaserade arkitektur håller minnesanvändningen under 10 MB även för arkiv på flera hundra megabyte. Lösenordsskydd är inbyggt, vilket möjliggör per‑post‑kryptering utan extra bibliotek.

## Förutsättningar
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 eller .NET 5–10.  
- Aspose.Zip för .NET NuGet‑paket installerat (`Install-Package Aspose.Zip`).  
- Grundläggande kunskap om C# fil‑I/O och .NET‑projektssystemet.

## Steg‑för‑steg‑guide

### Så här komprimerar du Tar-filer – Direkt svar
`Archive` representerar en arkivfil och tillhandahåller metoder för att lägga till poster och spara den.  
Skapa en `Archive`‑instans, lägg till filerna du vill paketera, sätt `CompressionType.BZip2` och anropa `Save` med `ArchiveFormat.TarBz2`. Biblioteket skriver TAR‑containern och komprimerar den i ett enda strömförlopp, så du laddar aldrig hela arkivet i minnet.

### Steg 1: Välj det arkivformat du behöver
Bestäm vilket tar‑baserat format som bäst matchar ditt komprimerings‑/hastighets‑trade‑off:

- **TarBz2** – Högsta komprimeringsförhållande (≈30 % mindre än TarGz) men långsammare.  
- **TarGz** – Bra balans mellan hastighet och storlek; idealisk för de flesta molnlagringsscenario.  
- **TarLz / TarXz** – Mycket hög kompression med måttlig hastighet, användbart för arkiveringslagring.  
- **TarZ** – Äldre format för kompatibilitet med äldre Unix‑verktyg.

### Steg 2: Skapa en ny `Archive`‑instans
`Archive` är top‑nivå‑objektet som representerar en enskild arkivfil i minnet.  

`Archive`‑klassen hanterar packnings‑ och komprimeringsflödet och exponerar metoder för att lägga till poster och skriva den slutliga filen.

### Steg 3: Lägg till filer och mappar
Du kan lägga till ett helt katalogträd med `AddAll` eller lägga till enskilda filer med `AddFile`. Att bevara den ursprungliga mappstrukturen är så enkelt som att ange bas‑katalogsökvägen.

### Steg 4: Ange önskad komprimeringstyp
`CompressionType` enumererar de stödjade algoritmerna.  

`CompressionType` definierar algoritmen (BZip2, GZip, LZMA, XZ osv.) som kommer att appliceras på TAR‑strömmen under sparandet.

### Steg 5: Spara arkivet
`ArchiveFormat` är en enum‑uppsättning (t.ex. `TarBz2`, `TarGz`) som talar om för skrivaren vilken container och komprimering som ska användas.  

Genom att anropa `Save` skrivs arkivet till disk med det valda formatet.

### Steg 6: Extrahera arkiv med lösenord
`ArchiveEntry` representerar en enskild fil‑ eller katalogpost i ett arkiv.  

För att extrahera ett lösenordsskyddat zip‑arkiv, öppna arkivet, lokalisera varje `ArchiveEntry`, tilldela dess `Password`‑egenskap och anropa `Extract`. Denna per‑post‑lösenordsmodell låter dig skydda individuella filer i ett enda zip‑arkiv.

### Steg 7: Verifiera resultatet
Efter extrahering, jämför filstorlekar och SHA‑256‑kontrollsummor för att bekräfta att arkiv‑rundresan bevarade dataintegriteten.

## Vanliga användningsfall
- **Backup‑verktyg** – Spara dagliga säkerhetskopior som `.tar.bz2` för att minska lagringskostnaderna med upp till 30 %.  
- **Plattformsoberoende datautbyte** – Tar‑baserade format förstås nativt av Linux-, macOS- och Windows‑verktyg.  
- **Säker distribution** – Tilldela lösenord till känsliga poster, uppfyller efterlevnadskrav utan extra krypteringsverktyg.

## Felsökning & tips
- **Stora arkiv** – Föredra streaming‑API:n (`Archive.CreateEntryFromFile`) för att hålla minnesanvändningen låg.  
- **Lösenordsmissmatch** – Lösenordet som sätts på varje `ArchiveEntry` måste matcha exakt; annars kastas `InvalidPasswordException`.  
- **Komprimeringsnivå** – BZIP2 erbjuder inga anpassade nivåer; om du behöver finare kontroll, byt till LZMA (`CompressionType.LZMA`) eller XZ (`CompressionType.XZ`).  

## Vanliga frågor

**Q: Hur skapar jag ett TarGz‑arkiv?**  
A: Sätt `CompressionType.GZip` och använd `ArchiveFormat.TarGz` när du anropar `Save`. Detta producerar en `.tar.gz`‑fil i ett enda steg.

**Q: Kan jag extrahera ett lösenordsskyddat arkiv utan att känna till lösenordet?**  
A: Nej. Varje post måste förses med rätt lösenord; annars misslyckas extraheringen med en `InvalidPasswordException`.

**Q: Stöder Aspose.Zip att extrahera arkiv med olika lösenord per post?**  
A: Ja. Tilldela ett lösenord till varje `ArchiveEntry` individuellt innan du anropar `Extract`.

**Q: Vilket format ger bäst kompression?**  
A: TarBz2 ger vanligtvis den minsta storleken, följt av TarLz och TarXz. TarGz erbjuder ett snabbare, fortfarande effektivt alternativ.

**Q: Finns det någon gräns för hur många filer jag kan lägga till i ett TAR‑arkiv?**  
A: Praktiskt taget ingen, men extremt stora arkiv (>10 GB) kan ha nytta av att delas upp i flera delar för enklare hantering.

## Handledning för arkivextraktion och format
### [Filkomprimering till TarBz2 med Aspose.Zip för .NET](./compress-to-tar-bz2/)
Lär dig hur du komprimerar filer till TarBz2‑format i .NET med Aspose.Zip. Följ vår steg‑för‑steg‑guide för effektiv filkomprimering.  
### [Komprimering till TarGz med Aspose.Zip för .NET](./compress-to-tar-gz/)
Utforska effektiv filkomprimering i .NET med Aspose.Zip. Komprimera till TarGz utan ansträngning.  
### [Komprimering till TarLz med Aspose.Zip för .NET](./compress-to-tar-lz/)
Komprimera filer i .NET med Aspose.Zip. Lär dig skapa TarLz‑arkiv steg‑för‑steg.  
### [Komprimering till TarXz med Aspose.Zip för .NET](./compress-to-tar-xz/)
Lär dig komprimera filer till TarXz‑format i .NET med Aspose.Zip. Följ vår guide för effektiv lagring och överföring.  
### [Komprimering till TarZ med Aspose.Zip för .NET](./compress-to-tar-z/)
Utforska steg‑för‑steg‑komprimering till TarZ med Aspose.Zip för .NET. Effektiv filhantering för dina .NET‑projekt.  
### [Extrahera arkivposter med olika lösenord i Aspose.Zip för .NET](./extract-archive-different-passwords/)
Lär dig hur du extraherar arkivposter med olika lösenord i Aspose.Zip för .NET. Öka säkerheten och flexibiliteten i dina applikationer.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Relaterade handledningar

- [Skapa tar‑arkiv och lägg till filer i tar med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Hur man komprimerar tar och skapar TarBz2 med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Lägg till filer i tar och skapa tarxz‑arkiv med Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}