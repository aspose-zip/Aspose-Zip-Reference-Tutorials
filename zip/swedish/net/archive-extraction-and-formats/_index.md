---
date: 2026-01-28
description: Lär dig hur du extraherar arkiv med lösenord, komprimerar filer till
  TarBz2 och skapar TarGz‑arkiv med Aspose.Zip för .NET. Öka lagringseffektiviteten
  och säkerheten.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Extrahera arkiv med lösenord och komprimera till TarBz2 (.NET)
url: /sv/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera arkiv med lösenord och komprimera till TarBz2 (.NET)

I den här guiden kommer du att upptäcka **hur man extraherar arkiv med lösenord** och även bemästra **komprimera filer till TarBz2** med Aspose.Zip för .NET. Oavsett om du bygger en backup‑tjänst, en moln‑lagringsklient eller en databehandlings‑pipeline, låter dessa tekniker dig minska lagringsutrymmet, snabba upp överföringar och hålla känslig data skyddad.

## Snabba svar
- **What is TarBz2?** Ett komprimerat arkiv som kombinerar TAR‑paketering med BZIP2‑komprimering för höga komprimeringsförhållanden.  
- **Why choose Aspose.Zip for .NET?** Det erbjuder ett enhetligt, flytande API för många arkivformat utan inhemska beroenden.  
- **Can I create a TarGz archive?** Ja – Aspose.Zip stödjer TarGz, TarLz, TarXz, TarZ och mer.  
- **How do I extract a password‑protected archive?** Ställ in `Password`‑egenskapen på varje `ArchiveEntry` innan extrahering.  
- **Do I need a license for production use?** En kommersiell licens krävs för produktion; en gratis provversion finns tillgänglig för utvärdering.

## Så extraherar du arkiv med lösenord med Aspose.Zip för .NET
Att extrahera ett arkiv som är **lösenordsskyddat zip‑arkiv** skyddat är enkelt. Du öppnar arkivet, hittar den post du behöver, tilldelar dess lösenord och anropar sedan `Extract`. Detta tillvägagångssätt fungerar för TarBz2, TarGz och andra stödda format.

## Vad betyder egentligen “compress files to TarBz2”?
Att komprimera filer till TarBz2 innebär först att samla flera filer och kataloger i en enda **TAR**‑behållare och sedan applicera **BZIP2**‑komprimering. Resultatet blir en `.tar.bz2`‑fil som både är lätt att transportera och starkt komprimerad.

## Varför använda Aspose.Zip för .NET för att hantera dessa format?
- **Unified API** – Ett bibliotek, många format (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Fungerar på Windows, Linux och macOS direkt ur lådan.  
- **Password support** – Skydda och extrahera arkiv säkert med lösenord per post.  
- **Performance‑focused** – Ström‑baserad bearbetning minimerar minnesanvändning.

## Förutsättningar
- .NET 6.0 eller senare (eller .NET Core 3.1+ / .NET Framework 4.5+).  
- Aspose.Zip för .NET NuGet‑paket installerat (`Install-Package Aspose.Zip`).  
- Grundläggande kunskap om C# och fil‑I/O.

## Steg‑för‑steg‑guide

### Steg 1: Välj det arkivformat du behöver
Bestäm om **TarBz2**, **TarGz**, **TarLz**, **TarXz** eller **TarZ** passar bäst för ditt komprimeringsförhållande och dina kompatibilitetskrav.  
- **TarBz2** – Bästa komprimeringen, långsammare bearbetning.  
- **TarGz** – Bra balans mellan hastighet och storlek (täckning av sekundärt nyckelord *compress files to targz*).  
- **TarZ** – Äldre format för äldre Unix‑verktyg.

### Steg 2: Skapa en ny `Archive`‑instans
Instansiera `Archive`‑klassen och peka den mot utdatafilens sökväg. Detta objekt hanterar packnings‑ och komprimeringsprocessen.

### Steg 3: Lägg till filer och mappar
Använd `AddAll`‑ eller `AddFile`‑metoderna för att inkludera de filer du vill komprimera. Bevara katalogstrukturen genom att lägga till en basmapp.

### Steg 4: Ange önskad komprimeringstyp
Ange komprimeringsalgoritmen (`CompressionType.BZip2`, `CompressionType.GZip`, etc.) när du sparar arkivet. Här **komprimerar du faktiskt filer till tarbz2** eller något annat format.

### Steg 5: Spara arkivet
Anropa `Save` med rätt format‑enum (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, etc.). Biblioteket skriver TAR‑behållaren och applicerar den valda komprimeringen i ett enda pass.

### Steg 6: Extrahera arkiv med lösenord
Om du behöver **extrahera arkivposter med olika lösenord** (sekundärt nyckelord *how to extract password protected archive*), öppna arkivet, hitta varje post, tilldela dess lösenord och extrahera sedan.

### Steg 7: Verifiera resultatet
Efter extrahering, jämför filstorlekar och kontrollsummor för att säkerställa att arkivet skapades och packades upp korrekt.

## Vanliga användningsfall
- **Backup utilities** – Spara dagliga säkerhetskopior som `.tar.bz2` för att minimera lagringskostnader.  
- **Cross‑platform data exchange** – Tar‑baserade format förstås universellt på Linux, macOS och Windows.  
- **Secure distribution** – Skydda enskilda poster med lösenord för efterlevnads‑drivna miljöer.

## Felsökning & tips
- **Large archives** – Använd streaming‑API:er (`Archive.CreateEntryFromFile`) för att undvika att ladda hela filer i minnet.  
- **Password mismatches** – Säkerställ att lösenordet som satts på varje `ArchiveEntry` matchar det som används vid extrahering; annars får du `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 stödjer inte anpassade komprimeringsnivåer; om du behöver finare kontroll, överväg TarLz eller TarXz.  
- **Performance tip** – När du skapar ett **create tarbz2 archive**, aktivera buffring på den underliggande strömmen för att förbättra skrivhastigheten.

## Vanliga frågor

**Q: How do I create a TarGz archive?**  
A: Ställ in komprimeringstypen till `CompressionType.GZip` och formatet till `ArchiveFormat.TarGz` när du anropar `Save`.

**Q: Can I extract a password‑protected archive without knowing the password?**  
A: Nej. Varje post måste förses med rätt lösenord; annars misslyckas extraheringen.

**Q: Does Aspose.Zip support extracting archives with different passwords per entry?**  
A: Ja. Du kan tilldela ett lösenord till varje `ArchiveEntry` individuellt innan extrahering.

**Q: Which format gives the best compression?**  
A: TarBz2 ger vanligtvis den högsta komprimeringsgraden, följt av TarLz och TarXz. TarGz erbjuder en bra balans mellan hastighet och storlek.

**Q: Is there a limit to the number of files I can add to a TAR archive?**  
A: Praktiskt taget ingen, men extremt stora arkiv kan ha nytta av att delas upp i flera delar för enklare hantering.

## Handledning för arkivextraktion och format
### [Filkomprimering till TarBz2 med Aspose.Zip för .NET](./compress-to-tar-bz2/)
Lär dig komprimera filer till TarBz2‑format i .NET med Aspose.Zip. Följ vår steg‑för‑steg‑guide för effektiv filkomprimering.
### [Komprimering till TarGz med Aspose.Zip för .NET](./compress-to-tar-gz/)
Utforska effektiv filkomprimering i .NET med Aspose.Zip. Komprimera till TarGz utan ansträngning.
### [Komprimering till TarLz med Aspose.Zip för .NET](./compress-to-tar-lz/)
Komprimera filer i .NET med Aspose.Zip. Lär dig skapa TarLz‑arkiv steg‑för‑steg.
### [Komprimering till TarXz med Aspose.Zip för .NET](./compress-to-tar-xz/)
Lär dig komprimera filer till TarXz‑format i .NET med Aspose.Zip. Följ vår steg‑för‑steg‑guide för effektiv lagring och överföring.
### [Komprimering till TarZ med Aspose.Zip för .NET](./compress-to-tar-z/)
Utforska steg‑för‑steg‑komprimering till TarZ med Aspose.Zip för .NET. Effektiv filhantering för dina .NET‑projekt.
### [Extrahera arkivposter med olika lösenord i Aspose.Zip för .NET](./extract-archive-different-passwords/)
Lär dig extrahera arkivposter med olika lösenord i Aspose.Zip för .NET. Öka säkerheten och flexibiliteten i dina applikationer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-28  
**Testat med:** Aspose.Zip för .NET 24.11  
**Författare:** Aspose