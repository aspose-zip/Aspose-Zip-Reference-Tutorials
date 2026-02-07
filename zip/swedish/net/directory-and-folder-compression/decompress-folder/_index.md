---
date: 2026-02-07
description: Lär dig hur du zippar en mapp i .NET genom att komprimera en katalog
  till zip och packa upp den igen. Den här guiden visar hur du zippar en mapp med
  Aspose.Zip för .NET.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man zippar en mapp – Komprimera katalog med Aspose.Zip
url: /sv/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man zippar en mapp – Komprimerar katalog med Aspose.Zip för .NET

Om du letar efter en tydlig **how to zip folder**‑lösning i en .NET‑applikation, har du hamnat på rätt ställe. I den här handledningen går vi igenom hela arbetsflödet—först **compress directory to zip**, sedan visar vi dig de exakta stegen för att **extract zip to directory** (även kallat how to unzip folder). I slutet har du ett återanvändbart, programatiskt mönster för zip‑folder‑operationer som fungerar över .NET Framework, .NET Core och .NET 5/6+.

## Snabba svar
- **Vad betyder “compress directory to zip”?** Det betyder att omvandla innehållet i en mapp till en enda .zip‑fil.  
- **Hur extraherar jag zip till katalog?** Använd metoden `Archive.ExtractToDirectory` som visas i guiden.  
- **Vilka .NET‑versioner stöds?** Alla moderna .NET Framework, .NET Core och .NET 5/6+ versioner.  
- **Krävs en licens för produktion?** Ja, en kommersiell Aspose.Zip‑licens behövs för icke‑testanvändning.  
- **Kan jag automatisera detta i CI/CD‑pipelines?** Absolut—lägg bara till samma kod i dina byggskript.

## Vad är “how to zip folder”?
**How to zip folder** betyder helt enkelt att ta varje fil och undermapp i en katalog och packa dem i ett enda komprimerat arkiv. Detta minskar lagringsstorlek, snabbar upp överföringar och skapar ett portabelt paket för distribution.

## Varför använda Aspose.Zip för .NET?
Aspose.Zip erbjuder ett **pure‑managed** API som inte kräver några inhemska DLL‑filer, stödjer enorma arkiv och hanterar kantfall som **zip archive password protection** och Unicode‑filnamn automatiskt. Det är också optimerat för prestanda, vilket gör det idealiskt när du behöver zip‑folder programatiskt i hög‑genomströmnings‑scenarier.

## Förutsättningar
- **Aspose.Zip for .NET**‑biblioteket installerat (ladda ner det [here](https://releases.aspose.com/zip/net/)).  
- En mapp på disken som du vill arkivera – ange dess sökväg i variabeln `dataDir`.  
- .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon annan IDE du föredrar).

## Importera namnrymder
Först, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Zip;
using System.IO;
```

## Steg‑för‑steg‑guide

### Steg 1: Komprimera katalog till zip (zip folder programmatically)
Vi kommer att skapa en zip‑fil från katalogen som du planerar att dekomprimera senare. Hjälpmetoden `CompressDirectory.Run()` sköter det tunga arbetet.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Proffstips:** Exemplet `CompressDirectory` packar varje fil i `dataDir` till `CompressDirectory_out.zip`. Du kan gärna byta namn på utdatafilen så att den matchar dina namngivningskonventioner.

### Steg 2: Dekomprimera mappen – How to Unzip Folder i .NET

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

#### Steg 2.3: Extrahera till katalog
Till sist, extrahera innehållet till en ny mapp. Detta är steget **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Varför detta är viktigt
- **Consistency:** Att använda samma bibliotek för både komprimering och extrahering garanterar kompatibla arkivformat.  
- **Performance:** Aspose.Zip strömmar data effektivt, så även multi‑gigabyte‑arkiv hanteras med låg minnesanvändning.  
- **Security:** Inbyggt stöd för lösenordsskydd innebär att du kan säkra zip‑arkivet utan extra kod.

## Vanliga användningsområden
- **Automated backups** – zip en loggmapp varje natt och lagra den i molnlagring.  
- **Deployment packages** – paketera statiska webb‑tillgångar innan publicering till en server.  
- **Data exchange** – skicka en samling filer mellan tjänster som ett enda arkiv.

## Vanliga problem & lösningar
| Symtom | Trolig orsak | Lösning |
|---------|--------------|-----|
| `UnauthorizedAccessException` vid extrahering | Målmappen är skrivskyddad eller används | Se till att destinationssökvägen är skrivbar och inte låst |
| Tom utdata‑mapp efter extrahering | Fel sökväg till käll‑zip | Dubbelkolla att `dataDir + "CompressDirectory_out.zip"` pekar på rätt fil |
| Stora filer orsakar OutOfMemoryException | Använder standardbufferstorlek på mycket stora arkiv | Använd `ArchiveOptions` för att öka bufferstorleken eller strömma filer i delar |

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med vilken filtyp som helst?**  
A: Ja, Aspose.Zip stödjer alla filtyper—text, binär, bilder, PDF‑filer, du namnger dem.

**Q: Är Aspose.Zip lämplig för storskaliga applikationer?**  
A: Absolut. Den är designad för högpresterande zip‑komprimering .NET‑scenarier, hanterar multi‑gigabyte‑arkiv med låg minnesanvändning.

**Q: Var kan jag hitta omfattande dokumentation för Aspose.Zip för .NET?**  
A: Utforska den detaljerade dokumentationen [här](https://reference.aspose.com/zip/net/).

**Q: Kan jag prova Aspose.Zip innan köp?**  
A: Ja, en gratis provversion finns på [Aspose.Zip download page](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip för .NET?**  
A: Besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för gemenskapsstöd och officiell hjälp.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}