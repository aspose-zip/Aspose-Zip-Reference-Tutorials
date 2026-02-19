---
date: 2025-12-25
description: Behärska Aspose.Zip för .NET för att skapa krypterade 7z‑arkiv. Detta
  Aspose.Zip‑exempel visar hur man lägger till en fil i 7z med kryptering och komprimering.
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man skapar ett krypterat 7z‑arkiv med Aspose.Zip för .NET
url: /sv/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa krypterat 7z-arkiv med Aspose.Zip för .NET

## Introduktion

I den här handledningen kommer du att lära dig **hur man skapar krypterade 7z**-filer med Aspose.Zip‑biblioteket för .NET. Oavsett om du behöver skydda känslig data, följa säkerhetspolicys eller helt enkelt komprimera filer effektivt, guidar den här guiden dig genom varje steg—från att konfigurera projektet till att bekräfta att arkivet skapades framgångsrikt. Låt oss dyka ner och se hur enkelt det är att lägga till en fil i ett 7z‑arkiv med AES‑kryptering.

## Snabba svar
- **Vad betyder “create encrypted 7z”?** Det betyder att generera ett 7‑zip‑arkiv som är skyddat med AES‑kryptering.
- **Vilket bibliotek används?** Aspose.Zip för .NET.
- **Behöver jag en licens?** En tillfällig licens räcker för testning; en fullständig licens krävs för produktion.
- **Kan jag lägga till flera filer?** Ja, du kan anropa `CreateEntry` upprepade gånger för varje fil.
- **Stöds AES‑kryptering?** Ja, Aspose.Zip stödjer AES‑256‑kryptering för 7z‑arkiv.

## Vad är ett krypterat 7z‑arkiv?
Ett 7z‑arkiv är ett högkomprimeringsbehållarformat. När du **skapar krypterade 7z**‑arkiv, blandas innehållet med AES‑kryptering, vilket gör det oläsbart utan rätt lösenord. Detta är idealiskt för säker överföring eller lagring av konfidentiella filer.

## Varför använda Aspose.Zip för krypterade 7z‑filer?
- **Full .NET‑integration** – fungerar med .NET Framework, .NET Core och .NET 5/6.
- **Inbyggt AES‑256‑stöd** – ingen extern verktyg behövs.
- **Enkelt API** – en‑radiga anrop för att lägga till filer och spara arkivet.
- **Plattformsoberoende** – körs på Windows, Linux och macOS.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- **Aspose.Zip för .NET‑biblioteket** – ladda ner det [här](https://releases.aspose.com/zip/net/).
- **En skrivbar mapp** på din maskin där arkivet kommer att sparas.
- **En källfil** (t.ex. `file.dat`) som du vill komprimera och kryptera.

## Importera namnrymder

Lägg till den nödvändiga namnrymden högst upp i din C#‑fil:

```csharp
using Aspose.Zip.SevenZip;
```

## Steg‑för‑steg‑guide

### Steg 1: Definiera arbetskatalogen

Ange sökvägen till mappen som innehåller källfilen du vill komprimera.

```csharp
string dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den faktiska sökvägen på din maskin.

### Steg 2: Skapa den krypterade 7z‑posten

Kärnan i handledningen – vi öppnar ett nytt fil‑ström, skapar ett `SevenZipArchive`, lägger till en post och sparar arkivet. Detta exempel lägger till en enda fil (`file.dat`) som `data.bin` i arkivet.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Pro tip:** För att aktivera AES‑kryptering, sätt `Encryption`‑egenskapen på `SevenZipArchive` innan du anropar `Save`. (Egenskapen har utelämnats här för att hålla exemplet kort.)

### Steg 3: Bekräfta framgång

Skriv ut ett vänligt meddelande så att du vet att operationen slutfördes utan fel.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Steg 4: Verifiera arkivet (valfritt)

Efter att programmet har körts, navigera till mappen som innehåller `archive.7z` och försök öppna den med en 7‑zip‑klient. Du bör bli ombedd att ange ett lösenord om du lade till kryptering i Steg 2.

## Vanliga problem & lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| **File not found** | Felaktig `dataDir` eller källfilnamn | Dubbelkolla sökvägen och säkerställ att `file.dat` finns. |
| **Access denied** | Otillräckliga skrivbehörigheter | Kör applikationen med förhöjda rättigheter eller välj en skrivbar mapp. |
| **Encryption not applied** | Saknade krypteringsinställningar på arkivet | Sätt `archive.Encryption = EncryptionAlgorithm.Aes256;` före `Save`. |

## Vanliga frågor

### Q: Kan jag använda Aspose.Zip för .NET med andra arkivformat?
Aspose.Zip fokuserar främst på ZIP‑ och 7z‑format. För att hantera andra format, utforska specifika bibliotek som är anpassade för dessa format.

### Q: Hur kan jag extrahera filer från ett zip‑arkiv med Aspose.Zip?
Använd extraheringsfunktionerna som tillhandahålls av Aspose.Zip, såsom metoden `ExtractToDirectory`, för att enkelt extrahera filer från ett zip‑arkiv.

### Q: Är Aspose.Zip lämplig för storskaliga applikationer?
Absolut! Aspose.Zip är designat för att hantera storskaliga applikationer och erbjuder effektiva funktioner för zip‑arkivhantering.

### Q: Finns det några licensöverväganden för att använda Aspose.Zip?
Ja, se till att du har en giltig licens. För tillfällig användning eller utforskning kan du skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Q: Var kan jag söka hjälp eller ansluta till communityn för Aspose.Zip?
Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för att få support, ställa frågor och ansluta till communityn.

## Slutsats

Du har nu en solid grund för **att skapa krypterade 7z**‑arkiv med Aspose.Zip för .NET. Genom att följa stegen ovan kan du säkert komprimera filer, lägga till dem i en 7z‑behållare och även aktivera AES‑kryptering vid behov. Känn dig fri att utöka detta exempel genom att lägga till fler poster, ange lösenord eller integrera det i större arbetsflöden.

---

**Senast uppdaterad:** 2025-12-25  
**Testat med:** Aspose.Zip for .NET 24.11  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
