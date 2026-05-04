---
date: 2026-02-28
description: Lär dig hur du lägger till en mapp i zip och lägger till filer i zip
  med Aspose.Zip för .NET. Denna steg‑för‑steg‑guide visar hur du komprimerar filer
  med FileInfo i ASP.NET‑projekt.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man lägger till en mapp i en zip‑fil med Aspose.Zip för .NET – Komprimera
  filer med FileInfo
url: /sv/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till mapp i zip med Aspose.Zip för .NET

## Introduktion

Om du behöver **skapa ett zip‑arkiv** programatiskt, ger Aspose.Zip för .NET dig ett rent, högpresterande API som fungerar i alla .NET‑applikationer (inklusive ASP.NET). I den här handledningen går vi igenom hur du komprimerar filer med `FileInfo`‑klassen, visar hur du **lägger till filer i zip**, och förklarar varför detta tillvägagångssätt är idealiskt för moderna .NET‑projekt. Vi kommer också att behandla hur du **lägger till mapp i zip** så att du kan paketera hela kataloger i ett enda steg. Låt oss komma igång!

## Snabba svar
- **Vad är det enklaste sättet att skapa ett zip‑arkiv?** Använd Aspose.Zip‑klassen `Archive` tillsammans med `FileInfo`‑objekt.  
- **Kan jag lägga till flera filer på en gång?** Ja – skapa helt enkelt ett `FileInfo` för varje fil och anropa `CreateEntry`.  
- **Behöver jag en speciell licens för ASP.NET?** En kommersiell Aspose.Zip‑licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Är API‑et trådsäkert?** Ja, så länge varje tråd arbetar med sin egen `Archive`‑instans.

## Vad är ett Zip‑arkiv och varför skapa ett?
Ett zip‑arkiv samlar en eller flera filer i en enda, komprimerad behållare. Detta minskar lagringsutrymme, snabbar upp nätverkstransfer och förenklar distribution. Oavsett om du levererar loggar, exporterar rapporter eller paketerar resurser för en kund, är kunskapen **hur man skapar zip‑arkiv** programatiskt en värdefull färdighet för alla .NET‑utvecklare.

## Varför använda Aspose.Zip för att lägga till filer i zip?
- **Inga externa beroenden** – ren .NET‑implementation.  
- **Full kontroll över komprimeringsnivå och kodning** (ASCII, UTF‑8 osv.).  
- **Stöder stora filer** (> 4 GB) och lösenordsskydd.  
- **Enhetligt API över .NET Framework, .NET Core och .NET 5+**.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har:

1. **Aspose.Zip för .NET** installerat. Ladda ner det senaste paketet från [Aspose.Zip nedladdningssida](https://releases.aspose.com/zip/net/).  
2. En mapp på din maskin som innehåller filerna du vill komprimera (t.ex. `alice29.txt` och `fields.c`).  

## Importera namnrymder

I vilken C#‑fil som helst där du arbetar med zip‑arkiv, lägg till följande `using`‑satser:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Dessa namnrymder ger dig åtkomst till `Archive`‑klassen, sparalternativ och de vanliga I/O‑verktygen.

## Steg‑för‑steg‑guide

### Steg 1: Ställ in din dokumentkatalog

Definiera först den mapp som innehåller källfilerna. Ersätt platshållaren med den absoluta eller relativa sökvägen på ditt system:

```csharp
string dataDir = "Your Document Directory";
```

> **Proffstips:** Använd `Path.Combine` för att bygga sökvägar på ett plattformsoberoende sätt.

### Steg 2: Öppna en zip‑fil för skrivning

Skapa ett `FileStream` som pekar på den utgående zip‑filen. Strömmen öppnas i **Create**‑läge, vilket skriver över eventuell befintlig fil med samma namn:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Steg 3: Förbered `FileInfo`‑objekt för varje källfil

`FileInfo` ger Aspose.Zip direkt åtkomst till de fysiska filerna på disken. Skapa en instans per fil du vill komprimera:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Varför använda `FileInfo`?** Det undviker att hela filen laddas in i minnet, vilket är särskilt hjälpsamt för stora filer.

### Steg 4: Skapa arkivet och lägg till poster

Instansiera ett `Archive`‑objekt och anropa sedan `CreateEntry` för varje `FileInfo`. Det första argumentet är namnet filen ska ha i zip‑filen, det andra argumentet är käll‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Steg 5: Spara zip‑arkivet med önskad kodning

Till sist, skriv arkivet till det `FileStream` du öppnade tidigare. Här använder vi ASCII‑kodning för postnamn, men du kan byta till UTF‑8 om dina filnamn innehåller icke‑ASCII‑tecken:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

När `using`‑blocken avslutas stängs strömmarna automatiskt och zip‑filen är klar för användning.

## Hur man lägger till mapp i zip med Aspose.Zip

Om du behöver **lägga till mapp i zip** istället för enskilda filer är processen enkel:

1. **Enumerera mappen** med `DirectoryInfo.GetFiles` (och eventuellt `GetDirectories` för rekursion).  
2. **Skapa ett `FileInfo`** för varje upptäckt fil.  
3. **Anropa `CreateEntry`** med en relativ sökväg som inkluderar mappnamnet, t.ex. `"MyFolder/Report.pdf"`.

Eftersom API:t arbetar med `FileInfo` behöver du aldrig ladda hela filer i minnet, vilket gör det säkert för stora kataloger. Denna teknik fungerar också för **zip multiple files asp.net**‑scenarier där du genererar en rapportuppsättning i farten och behöver leverera den som ett enda arkiv.

## Vanliga problem & lösningar

| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Tom zip‑fil** | `FileInfo` pekar på en icke‑existerande sökväg | Verifiera `dataDir` och filnamn; använd `File.Exists` för att kontrollera innan du skapar poster. |
| **Felaktig filnamnskodning** | Använder standardkodning med icke‑ASCII‑namn | Ställ in `Encoding = Encoding.UTF8` i `ArchiveSaveOptions`. |
| **OutOfMemoryException på stora filer** | Laddar hela filen i minnet | `FileInfo` strömmar filen; se till att du inte läser filen till en byte‑array någon annanstans. |
| **Åtkomst nekad** | Applikationen saknar skrivbehörighet för mål‑mappen | Kör appen med lämpliga rättigheter eller välj en skrivbar katalog. |

### Vanliga frågor

#### F1: Är Aspose.Zip kompatibelt med alla filtyper?

S1: Aspose.Zip stöder ett brett utbud av filtyper, vilket säkerställer mångsidighet i komprimering.

#### F2: Kan jag använda Aspose.Zip för kommersiella projekt?

S2: Absolut! Besök vår [köpsida](https://purchase.aspose.com/buy) för att utforska licensalternativ.

#### F3: Hur kan jag få support för Aspose.Zip?

S3: Gå med i vår community på [Aspose.Zip-forumet](https://forum.aspose.com/c/zip/37) för hjälp och diskussioner.

#### F4: Finns det en gratis provperiod tillgänglig?

S4: Ja, du kan hämta din [kostnadsfria provperiod här](https://releases.aspose.com/).

#### F5: Hur kan jag få en tillfällig licens för Aspose.Zip?

A5: Besök [denna länk](https://purchase.aspose.com/temporary-license/) för information om hur du får en tillfällig licens.

## Slutsats

Du vet nu **hur man lägger till mapp i zip** och **hur man skapar zip‑arkiv** med Aspose.Zip för .NET, hur man **lägger till filer i zip**, och varför denna metod är idealisk för ASP.NET och andra .NET‑applikationer. Experimentera med olika komprimeringsnivåer, kodningar och krypteringsalternativ för att anpassa arkivet exakt efter dina behov. Lycka till med komprimeringen!

---

**Senast uppdaterad:** 2026-02-28  
**Testat med:** Aspose.Zip för .NET 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}