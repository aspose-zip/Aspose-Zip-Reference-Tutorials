---
date: 2026-07-09
description: Lär dig hur du lägger till lösenordsskyddad zip i ASP.NET med Aspose.Zip
  för .NET, med zip‑mappkryptering och katalogkomprimering. Steg‑för‑steg‑guide för
  .NET‑projekt.
keywords:
- add password zip
- zip folder encryption
- compress entire directory
- .net zip encryption
- zip directory .net
lastmod: 2026-07-09
linktitle: Lägg till lösenordsskyddad zip i ASP.NET – Katalog‑ och mappkomprimering
og_description: Lägg till lösenordsskyddad zip i ASP.NET med Aspose.Zip. Lär dig zip‑mappkryptering,
  komprimera hela katalogen och hantera zip‑arkiv effektivt.
og_image_alt: 'Developer guide: add password zip in ASP.NET with Aspose.Zip'
og_title: Lägg till lösenordsskyddad zip i ASP.NET – Katalog‑ och mappkomprimering
schemas:
- author: Aspose
  dateModified: '2026-07-09'
  description: Learn how to add password zip in ASP.NET using Aspose.Zip for .NET,
    with zip folder encryption and directory compression. Step‑by‑step guide for .NET
    projects.
  headline: Add Password Zip in ASP.NET – Directory & Folder Compression
  type: TechArticle
- description: Learn how to add password zip in ASP.NET using Aspose.Zip for .NET,
    with zip folder encryption and directory compression. Step‑by‑step guide for .NET
    projects.
  name: Add Password Zip in ASP.NET – Directory & Folder Compression
  steps:
  - name: '**Instantiate `ZipPackage`** – this object will hold the archive you are
      building.'
    text: '**Instantiate `ZipPackage`** – this object will hold the archive you are
      building.'
  - name: '**Add the target directory** using `AddFolder`, which automatically includes
      sub‑folders and files.'
    text: '**Add the target directory** using `AddFolder`, which automatically includes
      sub‑folders and files.'
  - name: '**Configure encryption** (optional) by setting `ZipPassword` and `EncryptionAlgorithm`.'
    text: '**Configure encryption** (optional) by setting `ZipPassword` and `EncryptionAlgorithm`.'
  - name: '**Save the archive** to a `.zip` file.'
    text: '**Save the archive** to a `.zip` file.'
  type: HowTo
- questions:
  - answer: Yes. When saving the archive, provide a `ZipPassword` and select `EncryptionAlgorithm.Aes256`
      to secure the file.
    question: Can I create a password‑protected zip archive using Aspose.Zip?
  - answer: Absolutely. You can work with `FileStream` objects, allowing you to compress
      or extract files of any size efficiently.
    question: Does Aspose.Zip support streaming large files without loading them entirely
      into memory?
  - answer: Use the `SplitArchive` method to define a maximum part size; Aspose.Zip
      will automatically create sequential split files.
    question: What if I need to split a large archive into multiple parts?
  - answer: Yes. Open the archive in `Update` mode and call `AddFile` or `AddFolder`
      to append new content.
    question: Is it possible to add files to an existing zip archive?
  - answer: Aspose.Zip for .NET supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10.
    question: Which .NET runtimes are officially supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip archive
- Aspose.Zip
- .NET compression
title: Lägg till lösenordsskyddad zip i ASP.NET – Katalog‑ och mappkomprimering
url: /sv/net/directory-and-folder-compression/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till lösenordsskyddad zip i ASP.NET – Katalog- och mappkomprimering

## Introduktion

I modern .NET-utveckling är **add password zip**-funktionaliteten avgörande för att skydda känsliga data, minska lagringskostnader och förenkla distributionen av filer. Denna handledning guidar dig genom att använda Aspose.Zip för .NET för att komprimera hela kataloger, tillämpa zip‑mappkryptering och extrahera dem senare. Oavsett om du bygger en CI/CD‑pipeline, levererar uppdateringspaket eller bara rensar loggfiler, så kommer behärskning av skapande av zip‑arkiv med lösenordsskydd att göra dina projekt säkrare och mer professionella.

## Snabba svar
- **Vilket bibliotek lägger till lösenordsskyddad zip?** Aspose.Zip för .NET levererar högpresterande zip‑mappkryptering på några rader kod.  
- **Kan jag komprimera en hel katalog med ett anrop?** Ja – `AddFolder` inkluderar rekursivt underkataloger och filer.  
- **Stöds AES‑256‑kryptering?** Absolut; sätt `ZipPassword` och välj `EncryptionAlgorithm.Aes256`.  
- **Behöver jag en licens för produktion?** En gratis provversion är tillräcklig för utvärdering; en kommersiell licens krävs för produktionsanvändning.  
- **Vilka .NET‑runtime‑miljöer stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.

## Vad är add password zip?
`add password zip` är processen att skapa ett ZIP‑arkiv samtidigt som krypteringsdata (vanligtvis AES‑256) inbäddas så att endast användare som känner till lösenordet kan öppna arkivet. Detta skyddar konfidentiella filer under lagring eller överföring och är fullt kompatibelt med alla standard‑ZIP‑verktyg.

## Varför använda Aspose.Zip för .NET?
Aspose.Zip stöder **30+ arkiv- och komprimeringsformat**, behandlar filer upp till **10 GB** utan att ladda hela filen i minnet, och erbjuder inbyggd Zip64, delat arkiv och AES‑256‑kryptering. Dess noll‑beroende design innebär att du inte behöver externa verktyg som 7‑Zip, och API‑et är konsekvent över .NET Framework, .NET Core och .NET 5‑10.

## Förutsättningar
- Visual Studio 2022 (eller någon IDE som stödjer .NET 6+)  
- Aspose.Zip för .NET NuGet‑paket (`Install-Package Aspose.Zip`)  
- Grundläggande kunskap om C#‑fil‑systemoperationer  

## Hur lägger man till lösenordsskyddad zip i ASP.NET?
`ZipPackage` är den primära Aspose.Zip‑klassen som representerar ett ZIP‑arkiv i minnet.  
För att skapa ett lösenordsskyddat arkiv, ladda först den mapp du vill komprimera, skapa sedan ett `ZipPackage`‑objekt som representerar ZIP‑filen i minnet. Sätt `ZipPassword`‑egenskapen till önskat lösenord och välj eventuellt en krypteringsalgoritm såsom AES‑256. Slutligen, anropa `Save` för att skriva den krypterade zip‑filen till disk.

## Hur komprimerar man en mapp i .NET med Aspose.Zip
`ZipPackage` är den primära Aspose.Zip‑klassen som representerar ett ZIP‑arkiv i minnet.  
`AddFolder` lägger till en katalog och dess innehåll rekursivt i arkivet.  
Att komprimera en katalog är enkelt med Aspose.Zip. Börja med att skapa en `ZipPackage`‑instans, använd sedan dess `AddFolder`‑metod för att inkludera mål‑mappen och alla underkataloger. Du kan konfigurera komprimeringsnivå och kryptering innan du sparar arkivet till en .zip‑fil.

1. **Instansiera `ZipPackage`** – detta objekt kommer att hålla det arkiv du bygger.  
2. **Lägg till mål‑katalogen** med `AddFolder`, som automatiskt inkluderar underkataloger och filer.  
3. **Konfigurera kryptering** (valfritt) genom att sätta `ZipPassword` och `EncryptionAlgorithm`.  
4. **Spara arkivet** till en `.zip`‑fil.

> *Obs:* Den faktiska C#‑koden för dessa steg finns i den länkade handledningssidan “Effortless Directory Compression”.

## Lägga till lösenordsskyddade zip .NET‑arkiv
Ange ett `ZipPassword` när du sparar arkivet och välj `EncryptionAlgorithm.Aes256`. Detta skapar en **lösenordsskyddad zip .NET**‑fil som endast auktoriserade användare kan öppna. Krypteringen tillämpas per fil och bevarar den ursprungliga mappstrukturen.

## Extrahera en mapp med Aspose.Zip för .NET
Öppna zip‑filen med `ZipPackage` i läsläge, anropa sedan `ExtractAll` eller `ExtractFolder` för att återställa den ursprungliga hierarkin. Aspose.Zip strömmar data, så även multi‑gigabyte‑arkiv extraheras utan att minnet tar slut.

## Vanliga fallgropar & tips
- **Stora filer:** Aktivera `Zip64` när du hanterar filer större än 2 GB för att undvika storleksgränser.  
- **Sökvägslängd:** Sätt `UseLongFileNames = true` om din mapphierarki överstiger Windows 260‑teckensgräns.  
- **Prestanda:** Använd `CompressionLevel.Fast` för snabba byggen, eller `CompressionLevel.Maximum` när du behöver den minsta arkivstorleken.  

## Verkliga användningsfall
- **CI/CD‑pipelines:** Paketera byggartefakter i ett zip‑arkiv innan publicering till ett artefaktlager.  
- **Loggrotation:** Komprimera nattliga loggmappar för att spara diskutrymme samtidigt som de är lösenordsskyddade.  
- **Programuppdateringar:** Samla uppdateringsfiler i ett enda krypterat arkiv för säker nedladdning och installation.  

## Handledningar för katalog- och mappkomprimering
### [Problemfri katalogkomprimering med Aspose.Zip för .NET](./compress-directory/)
Lär dig att komprimera kataloger utan ansträngning med Aspose.Zip för .NET. Förbättra din .NET‑utveckling genom att effektivt optimera lagringsutrymme.

### [Extrahera en mapp med Aspose.Zip för .NET](./decompress-folder/)
Behärska konsten att extrahera mappar med Aspose.Zip för .NET. Hantera komprimeringsuppgifter i dina projekt utan ansträngning.

## Vanliga frågor

**Q: Kan jag skapa ett lösenordsskyddat zip‑arkiv med Aspose.Zip?**  
A: Ja. När du sparar arkivet, ange ett `ZipPassword` och välj `EncryptionAlgorithm.Aes256` för att säkra filen.

**Q: Stöder Aspose.Zip streaming av stora filer utan att ladda dem helt i minnet?**  
A: Absolut. Du kan arbeta med `FileStream`‑objekt, vilket gör att du kan komprimera eller extrahera filer av vilken storlek som helst effektivt.

**Q: Vad händer om jag behöver dela ett stort arkiv i flera delar?**  
A: Använd `SplitArchive`‑metoden för att definiera en maximal delstorlek; Aspose.Zip skapar automatiskt sekventiella delade filer.

**Q: Är det möjligt att lägga till filer i ett befintligt zip‑arkiv?**  
A: Ja. Öppna arkivet i `Update`‑läge och anropa `AddFile` eller `AddFolder` för att lägga till nytt innehåll.

**Q: Vilka .NET‑runtime‑miljöer stöds officiellt?**  
A: Aspose.Zip för .NET stödjer .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 och .NET 5–10.

---

**Senast uppdaterad:** 2026-07-09  
**Testad med:** Aspose.Zip för .NET 24.11  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Lägg till lösenord till Zip – Aspose.Zip för .NET‑guide](/zip/net/password-protection-and-encryption/)
- [Skapa lösenordsskyddade ZIP‑filer med AES‑kryptering med Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Hur man zippar en mapp med Aspose.Zip för .NET](/zip/net/directory-and-folder-compression/compress-directory/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}