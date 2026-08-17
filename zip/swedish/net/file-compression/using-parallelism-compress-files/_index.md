---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip flera filer c# med Aspose.Zip parallell komprimering

## Introduktion

Om du behöver **zip flera filer c#** snabbt och effektivt, är det att utnyttja parallell bearbetning vägen att gå. I moderna .NET‑applikationer kan skapandet av stora zip‑arkiv bli en flaskhals—särskilt när du hanterar dussintals eller hundratals filer. Aspose.Zip för .NET eliminerar detta problem genom att erbjuda inbyggd **parallel zip compression** som fördelar arbetet över alla tillgängliga CPU‑kärnor. I den här handledningen går vi igenom hela processen: från att konfigurera miljön till att spara ett zip‑arkiv med parallellism aktiverad, och vi visar också hur du **skapar zip‑arkiv c#** som körs smidigt på .NET Core.

## Snabba svar
- **What is parallel zip compression?** Det komprimerar flera filer samtidigt, med flera trådar för att minska den totala bearbetningstiden.  
- **Which .NET library supports it?** Aspose.Zip for .NET tillhandahåller ett enkelt API för parallel compression.  
- **Do I need a license for production?** Ja—en full licens krävs; en tillfällig licens finns tillgänglig för testning.  
- **Can I add files to zip on the fly?** Absolut—använd `Archive.CreateEntry` för varje fil du vill inkludera.  
- **Is it compatible with .NET 6/7?** Ja, API:et fungerar på alla moderna .NET‑runtime.

## Vad är zip multiple files c#?
`zip multiple files c#` avser processen att skapa ett enda ZIP‑arkiv som innehåller många enskilda filer, med C#‑kod. När du kombinerar detta med **parallel zip compression** bearbetar biblioteket varje fil i en separat tråd, vilket dramatiskt minskar den tid som krävs för att producera det slutliga arkivet.

## Varför använda Aspose.Zip för parallel compression?
Parallell komprimering låter dig utnyttja varje kärna i en multi‑processor‑maskin, och ger ofta **2‑3× snabbare** genomströmning än ett enkeltrådat tillvägagångssätt. Den skalar också smidigt: att lägga till fler filer ökar inte den faktiska körtiden linjärt, och API:et hanterar trådhanteringen åt dig, så att du kan fokusera på affärslogiken.  

- **Speed:** Använder alla logiska processorer, vilket minskar tiden för att skapa zip‑arkivet med upp till 70 % vid typiska arbetsbelastningar.  
- **Scalability:** Hanterar batcher på 500+ filer utan en proportionell ökning av CPU‑tiden.  
- **Simplicity:** Metoder på hög nivå döljer komplexiteten i `System.Threading.Tasks`.  
- **Flexibility:** Stöder .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10, inklusive .NET 6/7 för molnbaserade tjänster.

## Förutsättningar

- Grundläggande kunskap om C# och .NET‑utveckling.  
- Aspose.Zip för .NET installerat. Du kan ladda ner det **[här](https://releases.aspose.com/zip/net/)**.  
- En tillfällig eller full licens (den tillfälliga licensen räcker för den här handledningen).

## Importera namnrymder

`Aspose.Zip`‑namnrymden innehåller alla typer du behöver för att arbeta med ZIP‑arkiv.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Först, importera de nödvändiga namnrymderna i din C#‑fil så att kompilatorn vet var den ska hitta de klasser du kommer att använda.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Steg 1: Ställ in din dokumentkatalog

Definiera mappen som innehåller filerna du vill komprimera. Denna sökväg lagras i variabeln `dataDir`, som du kan peka på vilken plats på disken som helst.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Initiera komprimeringsprocessen

Öppna en ny ZIP‑fil för skrivning. `using`‑satsen säkerställer att filströmmen tas bort korrekt efter operationen, vilket förhindrar läckage av filhandtag.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Steg 3: Läs och komprimera filer parallellt

`Parallel.ForEach` kör en foreach‑loop där iterationerna kan köras samtidigt på flera trådar.  

Öppna varje källfil du avser att lägga till i arkivet. I detta exempel arbetar vi med två klassiska texter, men du kan **add files to zip** för valfritt antal dokument. `Parallel.ForEach`‑loopen fördelar arbetet över trådar automatiskt.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Steg 4: Skapa arkivposter

`Archive`‑klassen är Aspose.Zip:s överordnade objekt som representerar ZIP‑behållaren du bygger.  

`CreateEntry` skapar en ny post i ZIP‑arkivet för en specificerad fil. Varje anrop till `CreateEntry` lägger till en ny filpost i arkivet.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Steg 5: Definiera parallellismskriterium

`ParallelOptions` är en .NET‑typ som styr hur parallella loopar körs.  

Konfigurera komprimeringen att köras parallellt genom att sätta `ParallelOptions`. Flaggan `ParallelCompressInMemory` talar om för Aspose.Zip att alltid använda parallell bearbetning, medan `MaxDegreeOfParallelism` låter dig begränsa antalet samtidiga trådar.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Steg 6: Spara det komprimerade arkivet

Slutligen, skriv arkivet till disk med önskade alternativ, inklusive kodning, en kommentar och de parallella inställningarna som definierades tidigare. `Save`‑metoden slutför ZIP‑filen.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Om du komprimerar mycket stora filer, överväg att sätta `ParallelOptions.MaxDegreeOfParallelism` till ett värde lägre än antalet logiska processorer. Detta hjälper till att hålla din server responsiv under belastning.

### Vanliga användningsfall

- **Batch reporting:** Generera ett zip‑paket med dagliga CSV‑rapporter för downstream‑system.  
- **Document archiving:** Lagra stora samlingar av PDF‑filer, bilder eller loggar i ett enda arkiv för backup.  
- **Data export APIs:** Returnera en zip‑fil som innehåller flera datafiler till en klient i ett enda HTTP‑svar.  

## Vanliga problem & tips

- **Memory pressure on huge files:** Istället för att ladda en hel fil i minnet, strömma filen i bitar eller använd `ParallelCompressInMemory`‑läget selektivt.  
- **Thread safety:** Aspose.Zip‑API:et är trådsäkert för parallellt läge, men undvik att modifiera samma `FileStream` utanför biblioteket medan komprimeringen pågår.  
- **Performance tuning:** Experimentera med `ParallelOptions.MaxDegreeOfParallelism` om du behöver begränsa CPU‑användning på delade servrar.  

## Vanliga frågor

**Q: Can I use Aspose.Zip for .NET together with other compression libraries?**  
A: Ja, Aspose.Zip kan samexistera med andra .NET‑bibliotek; håll bara deras namnrymder separata.

**Q: Is a temporary license available for testing purposes?**  
A: Ja, du kan skaffa en tillfällig licens för testning från **[här](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I ask for help if I run into problems?**  
A: Besök **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** för gemenskapsstöd och diskussioner.

**Q: Where can I find more code examples and detailed API docs?**  
A: Utforska **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** för omfattande exempel.

**Q: How do I purchase a full license for Aspose.Zip?**  
A: Du kan köpa Aspose.Zip för .NET **[här](https://purchase.aspose.com/buy)**.

---

**Senast uppdaterad:** 2026-06-09  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [zip multiple files c# – Smidig komprimering med Aspose.Zip för .NET](/zip/net/file-compression/compress-multiple-files/)
- [How to Create Zip Archive and Add File to Zip Using Aspose.Zip for .NET](/zip/net/file-compression/compress-single-file/)
- [Compress Multiple Files with Encryption in Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}