---
date: 2026-06-29
description: Lär dig hur du extraherar WIM-filer till en mapp med Aspose.Zip för .NET.
  Följ den här steg‑för‑steg‑guiden för att dekomprimera WIM‑arkiv effektivt i dina
  .NET‑appar.
keywords:
- how to extract wim
- asp
- aspose zip
- wim extraction .net
linktitle: Dekomprimera Wim till mapp
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  headline: How to Extract WIM to Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  name: How to Extract WIM to Folder Using Aspose.Zip for .NET
  steps:
  - name: Set Your Document Directory
    text: Define the folder that contains the source `.wim` file and the output folder
      where the extracted files will be written. Replace the placeholder path with
      your actual locations. The `dataDir` variable holds the source directory, while
      `outDir` is the destination for the extracted image.
  - name: Open the WIM Archive
    text: Create a `FileStream` for the `.wim` file and instantiate a `WimArchive`.
      The constructor reads the archive header without loading all image data into
      memory.
  - name: Extract the Desired Image
    text: Select the first image (`Images[0]`) and invoke `ExtractAll`. `ExtractAll`
      extracts all files from the selected image to a directory. If the archive contains
      multiple images, change the index to target a different one. The snippet reads
      the WIM file, accesses its first image, and writes all files to
  type: HowTo
- questions:
  - answer: Yes. Aspose.Zip supports **50+ formats** including ZIP, TAR, GZIP, 7z,
      and WIM, allowing you to handle virtually any compression scenario.
    question: Can I use Aspose.Zip for .NET with other archive formats?
  - answer: Explore the [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)
      for in‑depth guides, code samples, and performance best practices.
    question: Where can I find more examples and detailed API docs?
  - answer: Absolutely. You can download a trial version from the [website](https://releases.aspose.com/zip/net/)
      and evaluate all features without a license.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: Temporary licenses are provided through the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      – use **[this link](https://purchase.aspose.com/temporary-license/)** to request
      one.
    question: How do I obtain a temporary license for testing?
  - answer: The official [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) is
      the best place to interact with other developers and Aspose engineers.
    question: Where can I get community support or ask technical questions?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar WIM till mapp med Aspose.Zip för .NET
url: /sv/net/file-decompression/decompress-wim-folder/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar WIM till mapp med Aspose.Zip för .NET

## Introduktion

I den här handledningen kommer du att lära dig **hur man extraherar WIM**-filer till en mapp med Aspose.Zip för .NET. Oavsett om du bygger ett Windows‑distributionsverktyg, ett backup‑verktyg eller helt enkelt behöver inspektera innehållet i ett Windows Imaging Format‑arkiv, kommer stegen nedan att ta dig från en rå `.wim`‑fil till en fullt fylld katalog på någon stödjande .NET‑runtime. Vi kommer att gå igenom miljöinställning, de exakta API‑anropen och tips efter extraktion så att du kan integrera denna logik i verkliga projekt med förtroende.

## Snabba svar
- **Vilket bibliotek rekommenderas?** Aspose.Zip for .NET  
- **Kan jag extrahera WIM-filer på .NET Core?** Ja – API:et stöder .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktion; en gratis provversion finns tillgänglig för utvärdering.  
- **Vad är den minsta .NET‑versionen?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.  
- **Hur lång tid tar extraktionen vanligtvis?** Standardbilder slutförs på några sekunder; bilder på flera hundra megabyte kan ta längre tid, men API:et strömmar data för att hålla minnesanvändningen låg.

## Vad är en WIM‑fil?

Ett WIM‑arkiv (Windows Imaging Format) lagrar en eller flera diskavbilder i en enda komprimerad behållare. Det är det grundläggande formatet bakom Windows Setup, DISM och många företagsdistributionspipeline, vilket möjliggör selektiv extraktion av enskilda avbilder utan att packa upp hela filen.

## Varför använda Aspose.Zip för .NET?

Aspose.Zip erbjuder en ren‑hanterad, plattformsoberoende lösning som eliminerar beroenden på inhemska DLL‑filer. Det stöder **50+ in‑ och utdataformat** (inklusive ZIP, TAR, GZIP, 7z och WIM) och kan bearbeta **arkiv med flera hundra sidor utan att läsa in hela filen i minnet**. Strömbaserad extraktion håller RAM‑användningen under 10 MB för typiska WIM‑filer, vilket gör det idealiskt för server‑sida eller containeriserade arbetsbelastningar.

## Förutsättningar

- **Aspose.Zip Library** – ladda ner den senaste versionen från [webbplatsen](https://releases.aspose.com/zip/net/) eller från huvudsidan för releaser [här](https://releases.aspose.com/).  
- **Ett WIM‑arkiv** – placera den `.wim` du vill dekomprimera i en känd mapp (t.ex. `C:\Archives`).  
- **.NET‑utvecklingsmiljö** – Visual Studio, VS Code eller någon editor som stödjer C#.  
- **En giltig Aspose.Zip‑licens** för produktionsbyggen (gratis provversion fungerar för testning).

## Importera namnrymder

Följande `using`‑direktiv ger dig åtkomst till de centrala Aspose.Zip‑klasserna som behövs för hantering av WIM.

```csharp
using Aspose.Zip;
using System.IO;
```

Dessa två namnrymder är allt du behöver; biblioteket hanterar komprimering, dekomprimering och avbildningsenumerering internt.

## Hur man extraherar WIM till en mapp?

Läs in WIM‑filen, välj den avbild du vill ha och strömma dess innehåll till en mål katalog. Aspose.Zip‑API:et utför extraktionen i tre koncisa steg, hanterar komprimering internt och håller minnesanvändningen låg även för stora arkiv. Detta tillvägagångssätt fungerar på alla stödjande .NET‑runtime och kräver bara några rader kod. `WimArchive` är Aspose.Zip‑klassen som representerar en WIM‑fil och ger åtkomst till dess innehållna avbilder.

### Direkt svar
Läs in WIM med `new WimArchive(stream)`, välj den första avbilden via `Images[0]` och anropa `ExtractAll(destinationPath)`. Detta enradiga anrop extraherar varje fil i den valda avbilden medan data strömmas, så minnesförbrukningen förblir minimal även för stora arkiv.

### Steg 1: Ange din dokumentkatalog

Definiera mappen som innehåller käll‑`.wim`‑filen och utmatningsmappen där de extraherade filerna ska skrivas. Ersätt platshållar‑sökvägen med dina faktiska platser.

`dataDir`‑variabeln innehåller källkatalogen, medan `outDir` är destinationen för den extraherade avbilden.

```csharp
string dataDir = @"C:\Archives";          // folder with your .wim file
string outDir = Path.Combine(dataDir, "DecompressWim_out"); // extraction target
```

### Steg 2: Öppna WIM‑arkivet

Skapa ett `FileStream` för `.wim`‑filen och instansiera ett `WimArchive`. Konstruktorn läser arkivhuvudet utan att ladda all avbildsdata i minnet.

```csharp
using (FileStream wimStream = File.OpenRead(Path.Combine(dataDir, "corpus.wim")))
{
    WimArchive wim = new WimArchive(wimStream);
```

### Steg 3: Extrahera önskad avbild

Välj den första avbilden (`Images[0]`) och anropa `ExtractAll`. `ExtractAll` extraherar alla filer från den valda avbilden till en katalog. Om arkivet innehåller flera avbilder, ändra indexet för att rikta in dig på en annan.

```csharp
    // Extract the first image to the output directory
    wim.Images[0].ExtractAll(outDir);
}
```

Kodsnutten läser WIM‑filen, får åtkomst till dess första avbild och skriver alla filer till **DecompressWim_out**. Justera indexet för att extrahera någon annan avbild som finns i arkivet.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|---------|-------|---------|
| **`FileNotFoundException`** | Fel `dataDir` eller filnamn | Verifiera sökvägen och säkerställ att `corpus.wim` finns på den angivna platsen. |
| **`UnauthorizedAccessException`** | Målmappen är skrivskyddad | Kör applikationen med förhöjda rättigheter eller välj en skrivbar katalog. |
| **Extraktionen är långsam** | Mycket stor WIM eller svag hårdvara | Extrahera en specifik avbild istället för hela arkivet, eller använd asynkrona strömmar för mycket stora filer. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med andra arkivformat?**  
A: Ja. Aspose.Zip stöder **50+ format** inklusive ZIP, TAR, GZIP, 7z och WIM, vilket låter dig hantera i princip alla komprimeringsscenarier.

**Q: Var kan jag hitta fler exempel och detaljerad API‑dokumentation?**  
A: Utforska [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) för djupgående guider, kodexempel och bästa praxis för prestanda.

**Q: Finns en gratis provversion av Aspose.Zip för .NET?**  
A: Absolut. Du kan ladda ner en provversion från [website](https://releases.aspose.com/zip/net/) och utvärdera alla funktioner utan licens.

**Q: Hur får jag en tillfällig licens för testning?**  
A: Tillfälliga licenser tillhandahålls via [temporary‑license page](https://purchase.aspose.com/temporary-license/) – använd **[this link](https://purchase.aspose.com/temporary-license/)** för att begära en.

**Q: Var kan jag få community‑support eller ställa tekniska frågor?**  
A: Det officiella [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) är den bästa platsen för att interagera med andra utvecklare och Aspose‑ingenjörer.

---

**Senast uppdaterad:** 2026-06-29  
**Testad med:** Aspose.Zip for .NET (latest release)  
**Författare:** Aspose  

```csharp
using System.IO;
using Aspose.Zip.Wim;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
{
    using (WimArchive archive = new WimArchive(fs))
    {
        archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man dekomprimerar filer med Aspose.Zip för .NET](/zip/net/file-decompression/)
- [Hur man extraherar zip till mapp med Aspose.Zip för .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [Hur man extraherar Xar‑arkiv till mapp med Aspose.Zip för .NET](/zip/net/file-decompression/decompress-xar-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}