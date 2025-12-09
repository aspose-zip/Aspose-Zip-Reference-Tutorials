---
date: 2025-12-01
description: Lär dig hur du komprimerar en katalog till zip och extraherar zip till
  en katalog med Aspose.Zip för .NET – en komplett guide till zip‑komprimering .net
  och att skapa zip‑arkiv .net.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Komprimera katalog till zip och dekomprimera – Aspose.Zip för .NET
url: /sv/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Komprimera katalog till zip & dekomprimera – Aspose.Zip för .NET

Om du behöver **komprimera katalog till zip** och sedan extrahera det arkivet i en .NET‑applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom hela arbetsflödet—börjar med att skapa ett zip‑arkiv, och visar sedan en ren, steg‑för‑steg‑avzipning med Aspose.Zip för .NET. I slutet har du ett återanvändbart mönster för zip‑komprimering .NET‑projekt och en solid förståelse för hur man avzippar .NET‑stil.

## Snabba svar
- **Vad betyder “compress directory to zip”?** Det betyder att omvandla innehållet i en mapp till en enda .zip‑fil.  
- **Hur extraherar jag zip till katalog?** Använd metoden `Archive.ExtractToDirectory` som visas i guiden.  
- **Vilka .NET‑versioner stöds?** Alla moderna .NET Framework, .NET Core och .NET 5/6+ versioner.  
- **Krävs en licens för produktion?** Ja, en kommersiell Aspose.Zip‑licens behövs för icke‑testanvändning.  
- **Kan jag automatisera detta i CI/CD‑pipelines?** Absolut—lägg bara till samma kod i dina byggskript.

## Vad är “compress directory to zip”?
Att komprimera en katalog till zip samlar varje fil och undermapp i ett enda komprimerat arkiv. Detta minskar lagringsstorlek, förenklar överföring och är ett standard sätt att paketera resurser för distribution.

## Varför använda Aspose.Zip för .NET?
Aspose.Zip erbjuder ett **pure‑managed** API som fungerar utan inhemska beroenden, stödjer stora filer och ger högpresterande zip‑komprimerings‑funktioner .NET. Det hanterar även specialfall som lösenordsskyddade arkiv och Unicode‑filnamn direkt ur lådan.

## Förutsättningar
- **Aspose.Zip for .NET**‑biblioteket installerat (ladda ner det [här](https://releases.aspose.com/zip/net/)).  
- En mapp på disken som du vill arkivera – ange dess sökväg i variabeln `dataDir`.  
- .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon IDE du föredrar).

## Importera namnrymder
Först, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Zip;
using System.IO;
```

## Steg 1: Komprimera katalog till zip
Vi kommer att skapa en zip‑fil från katalogen som du senare planerar att dekomprimera. Hjälpmetoden `CompressDirectory.Run()` sköter det tunga arbetet.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Proffstips:** `CompressDirectory`‑exemplet packar varje fil i `dataDir` till `CompressDirectory_out.zip`. Du kan gärna byta namn på utdatafilen så den matchar dina namngivningskonventioner.

## Steg 2: Dekomprimera mappen (Hur man avzippar .NET)

### Steg 2.1: Öppna zip‑filen
Öppna det genererade arkivet med en `FileStream`. Detta förbereder filen för läsning.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### Steg 2.2: Skapa Archive‑instans
Instansiera `Archive`‑objektet, som representerar zip‑behållaren.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### Steg 2.3: Extrahera till katalog
Till sist, extrahera innehållet till en ny mapp. Detta är steget **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Grattis! Du har framgångsrikt **komprimerat en katalog till zip** och sedan **extraherat zip‑filen till en katalog** med Aspose.Zip för .NET. Detta tillvägagångssätt garanterar dataintegritet samtidigt som koden förblir kortfattad och läsbar.

## Vanliga problem & lösningar
| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|--------|
| `UnauthorizedAccessException` när du extraherar | Målmappen är skrivskyddad eller används | Se till att destinationssökvägen är skrivbar och inte låst |
| Tom utdata-mapp efter extrahering | Fel sökväg till käll‑zip | Dubbelkolla att `dataDir + "CompressDirectory_out.zip"` pekar på rätt fil |
| Stora filer orsakar OutOfMemoryException | Använder standardbuffertstorlek på mycket stora arkiv | Använd `ArchiveOptions` för att öka buffertstorleken eller strömma filer i delar |

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med vilken filtyp som helst?**  
A: Ja, Aspose.Zip stödjer alla filtyper—text, binär, bilder, PDF‑filer, du namnger det.

**Q: Är Aspose.Zip lämplig för storskaliga applikationer?**  
A: Absolut. Den är designad för högpresterande zip‑komprimerings‑scenarier .NET, hanterar multi‑gigabyte‑arkiv med låg minnesanvändning.

**Q: Var kan jag hitta omfattande dokumentation för Aspose.Zip för .NET?**  
A: Utforska den detaljerade dokumentationen [här](https://reference.aspose.com/zip/net/).

**Q: Kan jag prova Aspose.Zip innan jag köper?**  
A: Ja, en gratis provversion finns på [Aspose.Zip‑nedladdningssidan](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Zip för .NET?**  
A: Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för gemenskapsstöd och officiell hjälp.

---

**Last Updated:** 2025-12-01  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}