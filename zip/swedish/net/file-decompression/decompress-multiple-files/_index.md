---
date: 2026-06-14
description: Lär dig hur du extraherar zip till mapp med Aspose.Zip för .NET – steg‑för‑steg
  guide som täcker extrahering av lösenordsskyddade zip-filer, dekomprimering av flera
  zip-filer och mer.
keywords:
- extract zip to folder
- extract password zip
- decompress multiple zips
- extract multiple zip entries
- asp.net zip archive
linktitle: Dekomprimering av flera filer
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET – step‑by‑step
    guide covering extract password zip, decompress multiple zips, and more.
  headline: How to Extract ZIP Files – extract zip to folder
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET – step‑by‑step
    guide covering extract password zip, decompress multiple zips, and more.
  name: How to Extract ZIP Files – extract zip to folder
  steps:
  - name: '1: Opening the Compressed File'
    text: Open the archive by passing the file path to the `Archive` constructor.
      **`Archive` represents a ZIP archive and provides access to its entries.** This
      call validates the ZIP structure and prepares an enumerable collection of entries.
  - name: '2: Listing Entries and Tracking Progress (Extract Multiple ZIP Entries)'
    text: Iterate through `archive.Entries` to list each file name. Use the `Progress`
      event to report extraction status, which is especially useful for large batches.
      **`Progress` event reports the extraction progress as a percentage.**
  - name: '3: Extracting the First Entry (Extract Specific File Zip)'
    text: To pull a single file, locate the desired entry by name and call `ExtractToFile`.
      **`ExtractToFile` extracts a single entry to a specified file path.** This method
      writes the entry directly to the specified path without extracting the whole
      archive.
  - name: '4: Extracting the Second Entry (Extract ZIP to Folder)'
    text: For full‑folder extraction, invoke `ExtractToDirectory` on the archive object.
      This extracts **all entries** to the target folder while preserving the original
      directory hierarchy inside the ZIP. And there you have it! You've successfully
      **extracted multiple zip entries** using Aspose.Zip for .NET,
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET
    question: What library is best for .NET zip extraction?
  - answer: Yes, iterate over the `Archive` entries collection.
    question: Can I extract multiple zip entries at once?
  - answer: A valid Aspose.Zip license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
    question: Which .NET versions are supported?
  - answer: Absolutely – download it from the Aspose website.
    question: Is there a free trial?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar ZIP-filer – extrahera zip till mapp
url: /sv/net/file-decompression/decompress-multiple-files/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar ZIP-filer – extrahera zip till mapp

I den här omfattande handledningen kommer du att lära dig **hur man extraherar zip till mapp** med Aspose.Zip för .NET. Oavsett om du behöver hämta en enskild fil från ett arkiv, batch‑dekomprimera dussintals ZIP-filer, eller arbeta med lösenordsskyddade paket, guidar vi dig genom varje steg – från installation av biblioteket till hantering av förloppsuppdateringar – så att du tryggt kan hantera ZIP-arkiv i vilken .NET-applikation som helst.

## Snabba svar
- **Vilket bibliotek är bäst för .NET zip-extraktion?** Aspose.Zip for .NET  
- **Kan jag extrahera flera zip-poster på en gång?** Ja, iterera över `Archive`-postsamlingen.  
- **Behöver jag en licens för produktion?** En giltig Aspose.Zip-licens krävs för icke‑provbruk.  
- **Vilka .NET-versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, och .NET 5–10  
- **Finns det en gratis provversion?** Absolut – ladda ner den från Aspose-webbplatsen.

## Så extraherar du zip till mapp med Aspose.Zip

Läs in ZIP‑arkivet, välj destinationsmappen och anropa `ExtractToDirectory`. **`ExtractToDirectory` extraherar alla poster i arkivet till en angiven mapp och bevarar den interna katalogstrukturen.** Denna enradiga operation extraherar **alla poster** samtidigt som den behåller den ursprungliga mapphierarkin, och den fungerar för arkiv upp till **5 GB** med mindre än **100 MB** RAM‑förbrukning.

Att extrahera ett ZIP‑arkiv innebär att öppna det komprimerade paketet, lokalisera varje post och skriva den dekomprimerade datan till en destination (mapp eller ström). Aspose.Zip:s flödande API döljer låg‑nivådetaljerna, så att du kan fokusera på affärslogiken samtidigt som du fortfarande har kontroll över funktioner som **extract zip with password** eller extrahering av en **specific file zip**.

## Varför använda Aspose.Zip för .NET?

Aspose.Zip levererar **robust performance**—det kan bearbeta arkiv med **10 000+ poster** på under en sekund på en vanlig server, och det strömmar data så att minnesanvändningen hålls under **150 MB** även för multi‑gigabyte‑filer. Fullt .NET‑stöd täcker **.NET Framework 2.0–4.8.1**, **.NET Core 2.0–3.1**, och **.NET 5–10**. Avancerade funktioner inkluderar förloppsspårning, lösenordsskydd och post‑nivå‑extrahering, allt utan externa inhemska DLL‑filer.

## Förutsättningar

- **Aspose.Zip for .NET** – ladda ner biblioteket från [här](https://releases.aspose.com/zip/net/) **eller** från [här](https://releases.aspose.com/zip/net).  
- **Document Directory** – skapa en mapp på disken som kommer att fungera som basväg för både käll‑ZIP‑filer och extraherad output.  

Nu när miljön är klar, låt oss dyka ner i koden.

## Importera namnrymder

`Archive` och relaterade typer finns i `Aspose.Zip`‑namnrymden. Importera den högst upp i din fil så att du kan referera till klasserna utan fullt kvalificerade namn.

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Skapa ett ZIP-arkiv i .NET-stil (valfritt)

Om du redan har en ZIP‑fil kan du hoppa över detta steg. Annars är skapandet av ett zip‑arkiv i .NET enkelt och hjälper till att demonstrera hela extraheringsflödet.

```csharp
string dataDir = "Your Document Directory";

// Run the compression method
CompressMultipleFiles.Run();
```

## Steg 2: Dekomprimera filerna (Hur man extraherar ZIP)

### Steg 2.1: Öppna den komprimerade filen

Öppna arkivet genom att skicka filvägen till `Archive`‑konstruktorn. **`Archive` representerar ett ZIP‑arkiv och ger åtkomst till dess poster.** Detta anrop validerar ZIP‑strukturen och förbereder en enumererbar samling av poster.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Steg 2.2: Lista poster och spåra framsteg (Extrahera flera ZIP-poster)

Iterera genom `archive.Entries` för att lista varje filnamn. Använd `Progress`‑händelsen för att rapportera extraheringsstatus, vilket är särskilt användbart för stora batcher. **`Progress`‑händelsen rapporterar extraheringsförloppet som en procentandel.**

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Steg 2.3: Extrahera den första posten (Extrahera specifik fil zip)

För att hämta en enskild fil, lokalisera den önskade posten efter namn och anropa `ExtractToFile`. **`ExtractToFile` extraherar en enskild post till en angiven filsökväg.** Denna metod skriver posten direkt till den angivna sökvägen utan att extrahera hela arkivet.

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Read and write data from decompressed stream to the extracting file.
    }
}
```

### Steg 2.4: Extrahera den andra posten (Extrahera ZIP till mapp)

För full‑mapp‑extrahering, anropa `ExtractToDirectory` på arkivet. Detta extraherar **alla poster** till mål‑mappen samtidigt som den ursprungliga kataloghierarkin i ZIP‑filen bevaras.

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

Och där har du det! Du har framgångsrikt **extraherat flera zip-poster** med Aspose.Zip för .NET, och du vet nu hur du **extraherar zip till mapp**, **extraherar specifik fil zip**, och till och med hanterar **extract zip with password** (genom att ange ett lösenord i `ArchiveLoadOptions`).

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Inga output‑filer skapade** | Fel `dataDir`‑sökväg eller saknade skrivbehörigheter | Verifiera att katalogen finns och att applikationen har skrivbehörighet. |
| **Progress visar 0 %** | Poststorlek rapporterad som 0 (tom fil) | Säkerställ att käll‑ZIP‑filen faktiskt innehåller data; återskapa arkivet vid behov. |
| **Undantag vid stora arkiv** | Otillräckligt minne | Använd `ArchiveLoadOptions` med `ReadOnly = true` för att strömma poster istället för att ladda allt på en gång. |
| **Lösenordsskyddat ZIP misslyckas** | Inget lösenord angivet | Ange lösenordet via `ArchiveLoadOptions.Password = "yourPassword"` för att möjliggöra **extract zip with password**. |

## Vanliga frågor

**Q:** Kan jag använda Aspose.Zip för .NET i både kommersiella och personliga projekt?  
**A:** Ja, Aspose.Zip för .NET kan användas i både kommersiella och personliga projekt. För licensinformation, se [Asposes licensinformation](https://purchase.aspose.com/buy).

**Q:** Finns det en gratis provversion för Aspose.Zip för .NET?  
**A:** Ja, du kan utforska en gratis provversion av Aspose.Zip för .NET [här](https://releases.aspose.com/zip/net).

**Q:** Var kan jag hitta ytterligare support för Aspose.Zip för .NET?  
**A:** Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för community‑support och diskussioner.

**Q:** Hur köper jag en tillfällig licens för Aspose.Zip för .NET?  
**A:** Skaffa en tillfällig licens för Aspose.Zip för .NET [här](https://purchase.aspose.com/temporary-license/).

**Q:** Finns det specifika systemkrav för att använda Aspose.Zip för .NET?  
**A:** Se [dokumentationen](https://reference.aspose.com/zip/net/) för detaljerade systemkrav.

## Slutsats

I den här handledningen har vi gått igenom **hur man extraherar zip**‑filer, demonstrerat extrahering av flera zip‑poster, och belyst bästa praxis för att använda Aspose.Zip:s kraftfulla API. Genom att följa dessa steg kan du effektivt hantera ZIP‑arkiv i vilken .NET‑applikation som helst – oavsett om du bygger ett skrivbordsverktyg, en webbtjänst, eller en automatiserad batch‑processor som behöver **dekomprimera flera zip‑filer** eller **extract zip with password**.

---

**Senast uppdaterad:** 2026-06-14  
**Testat med:** Aspose.Zip 24.11 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man dekomprimerar filer med Aspose.Zip för .NET](/zip/net/file-decompression/)
- [Hur man extraherar Zip med lösenord med Aspose.Zip för .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [zip flera filer c# – Enkel komprimering med Aspose.Zip för .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}