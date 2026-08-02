---
date: 2026-08-02
description: Hur du zippar en mapp i .NET med Aspose.Zip – lär dig att komprimera
  en katalog till zip och extrahera zip till en katalog med steg‑för‑steg‑kod och
  bästa praxis.
keywords:
- compress directory to zip
- zip folder programmatically
- extract zip to directory
- extract zip archive .net
- how to zip folder
lastmod: 2026-08-02
linktitle: Dekomprimering av en mapp
og_description: Hur du zippar en mapp i .NET med Aspose.Zip. Den här guiden visar
  hur du komprimerar en katalog till zip och extraherar zip till en katalog på ett
  effektivt sätt.
og_image_alt: Guide showing how to zip folder and unzip archive with Aspose.Zip in
  .NET
og_title: Hur man zippar en mapp – komprimerar katalog med Aspose.Zip för .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: How to zip folder in .NET using Aspose.Zip – learn to compress directory
    to zip and extract zip to directory with step‑by‑step code and best practices.
  headline: How to Zip Folder – Compress Directory with Aspose.Zip for .NET
  type: TechArticle
- description: How to zip folder in .NET using Aspose.Zip – learn to compress directory
    to zip and extract zip to directory with step‑by‑step code and best practices.
  name: How to Zip Folder – Compress Directory with Aspose.Zip for .NET
  steps:
  - name: Zip folder programmatically
    text: 'The `CompressDirectory` class provides a static `Run` method that creates
      a zip archive from a folder. We’ll create a zip file from the directory you
      plan to decompress later. The `CompressDirectory.Run()` helper does the heavy
      lifting. > **Pro tip:** The `CompressDirectory` sample packs every file '
  - name: extract zip to directory – How to unzip folder in .NET
    text: '#### Step 2.1: Open the Zip File Open the generated archive with a `FileStream`.
      This prepares the file for reading.'
  - name: '2: Create Archive Instance'
    text: Instantiate the `Archive` object, which represents the zip container.
  - name: '3: extract zip archive .net'
    text: Finally, extract the contents to a new folder. This is the **extract zip
      to directory** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip supports all file types—text, binary, images, PDFs, and
      more—because it treats files as byte streams without format restrictions.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Absolutely. It processes multi‑gigabyte archives using less than 10 MB
      of RAM and can compress at speeds exceeding 150 MB/s on a typical server CPU.
    question: Is Aspose.Zip suitable for large‑scale applications?
  - answer: Explore the detailed docs [here](https://reference.aspose.com/zip/net/).
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/).
    question: Can I try Aspose.Zip before purchasing?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community
      help and official assistance.
    question: How can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip folder
- Aspose.Zip
- .NET compression
- file archiving
title: Hur man zippar en mapp – komprimerar katalog med Aspose.Zip för .NET
url: /sv/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man zippar mapp – Komprimera katalog med Aspose.Zip för .NET

Om du letar efter en tydlig **compress directory to zip**-lösning i en .NET-applikation, har du hamnat på rätt plats. I den här handledningen går vi igenom hela arbetsflödet – först **compress directory to zip**, sedan visar vi dig de exakta stegen för att **extract zip to directory** (även känt som hur man packar upp en mapp). I slutet har du ett återanvändbart, programatiskt mönster för zip‑mappsoperationer som fungerar över .NET Framework, .NET Core och .NET 5/6+.

## Snabba svar
`Archive.ExtractToDirectory`-metoden extraherar alla poster från ett zip‑arkiv till en angiven mapp.

- **What does “compress directory to zip” mean?** Det betyder att omvandla innehållet i en mapp till en enda .zip‑fil.  
- **How do I extract zip to directory?** Använd `Archive.ExtractToDirectory`‑metoden som visas i guiden.  
- **Which .NET versions are supported?** Alla moderna .NET Framework-, .NET Core- och .NET 5/6+-versioner.  
- **Is a license required for production?** Ja, en kommersiell Aspose.Zip‑licens krävs för icke‑testanvändning.  
- **Can I automate this in CI/CD pipelines?** Absolut – lägg bara till samma kod i dina byggskript.

## Vad är “how to zip folder”?
**How to zip folder** är processen att ta varje fil och undermapp i en katalog och packa dem i ett enda komprimerat .zip‑arkiv. Denna operation minskar lagringsstorlek, snabbar upp nätverkstransfer och skapar ett portabelt paket som kan flyttas eller versionskontrolleras som en enhet.

## Varför använda Aspose.Zip för .NET?
Aspose.Zip erbjuder ett **pure‑managed** API som inte kräver några inhemska DLL‑filer, stöder **50+** in‑ och utdataformat och kan hantera arkiv större än 2 GB utan att ladda hela filen i minnet. Det erbjuder också inbyggt lösenordsskydd, Unicode‑filnamnshantering och streaming som håller minnesanvändningen under 10 MB även för multi‑gigabyte‑arkiv, vilket gör det idealiskt för höggenomströmning på serversidan.

## Förutsättningar
- **Aspose.Zip for .NET**-biblioteket installerat (ladda ner det [här](https://releases.aspose.com/zip/net/)).  
- En mapp på disken som du vill arkivera – ange dess sökväg i variabeln `dataDir`.  
- .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon IDE du föredrar).  

## Importera namnrymder
Först, importera de nödvändiga namnrymderna.

```csharp
using Aspose.Zip;
using System.IO;
```

## compress directory to zip – Steg‑för‑steg‑guide

### Steg 1: Zip mapp programatiskt
`CompressDirectory`‑klassen tillhandahåller en statisk `Run`‑metod som skapar ett zip‑arkiv från en mapp.

Vi kommer att skapa en zip‑fil från katalogen som du planerar att packa upp senare. Hjälpmetoden `CompressDirectory.Run()` gör det tunga arbetet.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** `CompressDirectory`‑exemplet packar varje fil i `dataDir` till `CompressDirectory_out.zip`. Du kan gärna byta namn på utdatafilen så att den matchar dina namngivningskonventioner.

### Steg 2: extract zip to directory – Hur man packar upp mapp i .NET

#### Steg 2.1: Öppna zip‑filen
Öppna det genererade arkivet med en `FileStream`. Detta förbereder filen för läsning.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Steg 2.2: Skapa Archive‑instans
Instansiera `Archive`‑objektet, som representerar zip‑behållaren.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Steg 2.3: extrahera zip‑arkiv .net
Slutligen extraheras innehållet till en ny mapp. Detta är steget **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Varför detta är viktigt
- **Consistency:** Att använda samma bibliotek för både komprimering och extrahering garanterar kompatibla arkivformat.  
- **Performance:** Aspose.Zip strömmar data effektivt, så även multi‑gigabyte‑arkiv hanteras med låg minnesbelastning.  
- **Security:** Inbyggt stöd för lösenordsskydd betyder att du kan säkra zip‑arkivet utan extra kod.

## Vanliga användningsfall
- **Automated backups** – zip en loggmapp varje natt och lagra den i molnlagring.  
- **Deployment packages** – paketera statiska webbresurser innan publicering till en server.  
- **Data exchange** – skicka en samling filer mellan tjänster som ett enda arkiv.

## Vanliga problem & lösningar
| Symptom | Trolig orsak | Lösning |
|---------|--------------|--------|
| `UnauthorizedAccessException` när du extraherar | Målmappen är skrivskyddad eller används | Se till att destinationssökvägen är skrivbar och inte låst |
| Tom utmatningsmapp efter extrahering | Fel zip‑sökväg | Dubbelkolla att `dataDir + "CompressDirectory_out.zip"` pekar på rätt fil |
| Stora filer orsakar OutOfMemoryException | Använder standardbuffertstorlek på mycket stora arkiv | Använd `ArchiveOptions` för att öka buffertstorleken eller strömma filer i delar |

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med vilken filtyp som helst?**  
A: Ja, Aspose.Zip stöder alla filtyper – text, binär, bilder, PDF‑filer och mer – eftersom det behandlar filer som byte‑strömmar utan formatbegränsningar.

**Q: Är Aspose.Zip lämplig för storskaliga applikationer?**  
A: Absolut. Det bearbetar multi‑gigabyte‑arkiv med mindre än 10 MB RAM och kan komprimera med hastigheter över 150 MB/s på en vanlig server‑CPU.

**Q: Var kan jag hitta omfattande dokumentation för Aspose.Zip för .NET?**  
A: Utforska den detaljerade dokumentationen [här](https://reference.aspose.com/zip/net/).

**Q: Kan jag prova Aspose.Zip innan jag köper?**  
A: Ja, en gratis provversion finns på [Aspose.Zip nedladdningssida](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip för .NET?**  
A: Besök [Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37) för gemenskapsstöd och officiell hjälp.

**Senast uppdaterad:** 2026-08-02  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man lägger till mapp i zip med Aspose.Zip för .NET – Komprimera filer med FileInfo](/zip/net/file-compression/compress-files-fileinfo/)
- [zip flera filer c# – Enkel komprimering med Aspose.Zip för .NET](/zip/net/file-compression/compress-multiple-files/)
- [Hur man extraherar zip till mapp med Aspose.Zip för .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}