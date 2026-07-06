---
date: 2026-06-04
description: Lär dig hur du extraherar zip‑fil C# med Aspose.Zip. Steg‑för‑steg .NET
  guide för arkivextraktion och exempel på C#‑fildekomprimering.
keywords:
- extract zip file c#
- decompress lzip c#
- aspose zip extraction
linktitle: Dekomprimering av en fil
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip file C# with Aspose.Zip. Step‑by‑step .NET
    archive extraction guide and C# file decompression example.
  headline: How to extract zip file C# using Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip file C# with Aspose.Zip. Step‑by‑step .NET
    archive extraction guide and C# file decompression example.
  name: How to extract zip file C# using Aspose.Zip
  steps:
  - name: '**Create** an `LzipArchive` instance pointing at the source file.'
    text: '**Create** an `LzipArchive` instance pointing at the source file.'
  - name: '**Create** the destination file (`output.txt`).'
    text: '**Create** the destination file (`output.txt`).'
  - name: '**Call** `Extract` to write the decompressed bytes.'
    text: '**Call** `Extract` to write the decompressed bytes.'
  - name: The `using` statements guarantee that all streams are closed automatically.
    text: The `using` statements guarantee that all streams are closed automatically.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET integrates with desktop, web, cloud, and micro‑service
      projects alike.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. The library offers flexible licensing for evaluation, personal,
      and commercial use.
    question: Can I use Aspose.Zip for both personal and commercial projects?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to ask
      questions and share experiences with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, you can explore the features of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: To purchase a license, go to the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man extraherar zip‑fil C# med Aspose.Zip
url: /sv/net/file-decompression/decompress-file/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera zip-fil C# med Aspose.Zip

## Introduktion

Om du behöver **extract zip file C#** i en .NET‑applikation vill du ha en lösning som är snabb, pålitlig och enkel att integrera. Aspose.Zip för .NET tillhandahåller ett högpresterande API som döljer låg‑nivå strömhantering samtidigt som du får full kontroll över extraktionsprocessen. I den här handledningen går vi igenom ett komplett **C# file decompression example** — öppnar ett Lzip‑arkiv och extraherar dess innehåll med bara några rader kod.

## Snabba svar
- **Vilket bibliotek hanterar .NET‑arkivextraktion?** Aspose.Zip for .NET  
- **Vilken metod extraherar ett Lzip‑arkiv i C#?** `LzipArchive.Extract`  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs för icke‑utvärderingsbruk.  
- **Stödda .NET‑versioner?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, och .NET 5–10  
- **Hur lång tid tar grundextraktionen?** Vanligtvis under en sekund för små filer.  

`LzipArchive.Extract` är Aspose.Zip‑metoden som extraherar ett LZIP‑arkiv till en angiven destinationsmapp i ett enda anrop.

## Vad är “decompress zip file C#”?

**Decompress zip file C#** betyder att läsa ett komprimerat arkiv (ZIP, LZIP, GZIP, etc.) och skriva tillbaka de ursprungliga filerna till disk. Denna operation återställer det exakta byte‑visa innehållet som packades, vilket gör att din applikation kan arbeta med de ursprungliga data utan manuell strömhantering.

## Varför använda Aspose.Zip för .NET‑arkivextraktion?

Aspose.Zip låter dig extrahera arkiv **under 1 sekund för filer upp till 500 MB** och stöder **30+ arkivformat** — inklusive ZIP, GZIP, TAR, LZIP och fler. Biblioteket har noll beroenden (inga inhemska binärer), är helt trådsäkert och fungerar över **alla större .NET‑runtime‑miljöer**. Dessa kvantifierade fördelar gör det till ett produktionsklart val för webbtjänster, bakgrundsjobb och skrivbordsverktyg.

## Förutsättningar

- **Aspose.Zip for .NET** – installera NuGet‑paketet eller ladda ner biblioteket. Du kan hitta dokumentationen [here](https://reference.aspose.com/zip/net/).  
- **Utvecklingsmiljö** – Visual Studio 2022, .NET 6 SDK, eller någon IDE som stödjer C#.  
- **Din dokumentkatalog** – en mapp på disken där den komprimerade filen (`archive.lz`) finns och där du vill spara den extraherade filen.

## Importera namnrymder

First, import the namespaces required for file I/O and Aspose.Zip’s Lzip support:

```csharp
using System;
using System.IO;
using Aspose.Zip.Lzip;
```

## .NET‑arkivextraktion: Ställ in din arbetsmapp

Skapa en variabel som pekar på mappen som innehåller `archive.lz`. Att hålla sökvägen i en variabel gör koden återanvändbar och enklare att underhålla.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 1: Extrahera Lzip‑arkiv C# (extract lzip archive c#)

**Direkt svar:** Anropa `LzipArchive.Extract` på källfilen och ange destinationssökvägen; metoden hanterar öppning av ström, dekomprimering och filskrivning i ett enda anrop. Detta mönster extraherar arkivet på under en sekund för typiska filer.

`LzipArchive` är Aspose.Zip‑klassen som representerar ett LZIP‑arkiv och tillhandahåller metoder för att extrahera dess innehåll.

```csharp
//ExStart: OpenLzipArchive
using (var archive = new LzipArchive(Path.Combine(dataDir, "archive.lz")))
{
    using (var extracted = File.Create(Path.Combine(dataDir, "output.txt")))
    {
        archive.Extract(extracted);
    }
}
//ExEnd: OpenLzipArchive
Console.WriteLine("Successfully Opened Lzip Archive");
```

Detta kodsnutt demonstrerar mönstret **extract lzip archive c#**:

1. **Create** en `LzipArchive`‑instans som pekar på källfilen.  
2. **Create** destinationsfilen (`output.txt`).  
3. **Call** `Extract` för att skriva de dekomprimerade bytena.  
4. `using`‑satserna garanterar att alla strömmar stängs automatiskt.

## Vanliga problem och lösningar

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| `FileNotFoundException` | Fel `dataDir`‑sökväg | Verifiera mappens sökväg och säkerställ att `archive.lz` finns. |
| `UnauthorizedAccessException` | Otillräckliga skrivbehörigheter | Kör appen med rätt behörigheter eller välj en skrivbar mapp. |
| Output file is empty | Arkivet är korrupt eller inte ett Lzip‑arkiv | Bekräfta att källfilen är ett giltigt LZIP‑arkiv; använd `LzipArchive.IsValid` vid behov. |

## Vanliga frågor

**Q: Är Aspose.Zip kompatibel med alla .NET‑applikationer?**  
A: Ja, Aspose.Zip for .NET integreras med skrivbords-, webb-, moln- och mikrotjänstprojekt lika väl.

**Q: Kan jag använda Aspose.Zip för både personliga och kommersiella projekt?**  
A: Absolut. Biblioteket erbjuder flexibel licensiering för utvärdering, personligt och kommersiellt bruk.

**Q: Hur kan jag få support för Aspose.Zip för .NET?**  
A: Besök [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) för att ställa frågor och dela erfarenheter med communityn.

**Q: Finns det en gratis provversion?**  
A: Ja, du kan utforska funktionerna i Aspose.Zip for .NET genom att ladda ner gratisprovet [här](https://releases.aspose.com/).

**Q: Var kan jag köpa Aspose.Zip för .NET?**  
A: För att köpa en licens, gå till [köpsida](https://purchase.aspose.com/buy).

## Slutsats

Du har nu lärt dig hur du **extract zip file C#** med Aspose.Zip:s enkla API. Detta tillvägagångssätt förenklar .NET‑arkivextraktion, minskar boilerplate‑kod och skalar bra för storskaliga applikationer. För djupare scenarier — lösenordsskyddade arkiv, multi‑fil‑extraktion eller anpassade komprimeringsnivåer — se den fullständiga [dokumentation](https://reference.aspose.com/zip/net/).

---

**Senast uppdaterad:** 2026-06-04  
**Testad med:** Aspose.Zip 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man dekomprimerar filer med Aspose.Zip för .NET](/zip/net/file-decompression/)
- [Dekomprimera AES‑filer – Aspose.Zip .NET‑handledning](/zip/net/password-protection-and-encryption/decompress-aes-encrypted-file/)
- [Skapa Zip utan kompression & dekomprimera filer – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}