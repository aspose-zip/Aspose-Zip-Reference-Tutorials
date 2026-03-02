---
date: 2026-03-02
description: Lär dig hur du skapar ett lösenordsskyddat zip‑arkiv och komprimerar
  filer med lösenord i .NET med Aspose.Zip. Följ vår steg‑för‑steg‑guide.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Skapa ett lösenordsskyddat ZIP‑arkiv i .NET med Aspose.Zip
url: /sv/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa ett lösenordsskyddat ZIP-arkiv i .NET med Aspose.Zip

## Introduction

När du behöver dela känslig data är ett **lösenordsskyddat zip-arkiv** ett av de enklaste men ändå mest effektiva sätten att hålla information säker. I .NET‑applikationer gör Aspose.Zip det enkelt att **komprimera filer med lösenord**, vilket ger varje fil sin egen krypteringsnyckel. I den här handledningen lär du dig exakt hur du skapar ett sådant arkiv, varför det är viktigt och var du kan använda det i verkliga projekt.

## Quick Answers
- **Vilket bibliotek ska jag använda?** Aspose.Zip för .NET erbjuder inbyggt stöd för lösenord per fil och flera krypteringsmetoder.  
- **Hur många kodrader?** Ungefär 30 rader, inklusive konfiguration och sparande av arkivet.  
- **Kan varje fil ha ett annat lösenord?** Ja – du kan tilldela ett unikt lösenord till varje post.  
- **Vilka krypteringsmetoder finns tillgängliga?** Traditionell ZipCrypto, AES‑128 och AES‑256.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig.

## What is a password protected zip archive?
Ett lösenordsskyddat zip‑arkiv är en komprimerad fil (ZIP) som kräver ett lösenord för att extrahera dess innehåll. Lösenordet kan skydda hela arkivet eller enskilda poster, och moderna algoritmer som AES‑128/256 ger stark kryptering.

## Why compress files with passwords using Aspose.Zip?
- **Granulär säkerhet** – tilldela ett separat lösenord per fil, idealiskt för flermandatscenarier.  
- **Flera krypteringsstandarder** – välj mellan äldre ZipCrypto och stark AES.  
- **Inga externa verktyg** – allt hanteras programatiskt inom din .NET‑kodbas.  
- **Prestanda** – snabb komprimering med Deflate samtidigt som arkivstorleken hålls liten.

## Prerequisites

Innan du börjar, se till att du har:

- **Aspose.Zip för .NET** – installera biblioteket i ditt projekt. Detaljerad dokumentation finns tillgänglig [här](https://reference.aspose.com/zip/net/).  
- **Ladda ner det senaste paketet** om du inte redan har gjort det, från [denna länk](https://releases.aspose.com/zip/net/).  
- En mapp som innehåller filerna du vill komprimera.

## Import Namespaces

Lägg till de nödvändiga namnrymderna högst upp i din C#‑fil:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

Steg 1: Ange sökvägen till resurskatalogen

Peka koden på mappen som innehåller källfilerna:

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

Steg 2: Komprimera filer med individuella lösenord

Nu ska vi skapa ett **lösenordsskyddat zip‑arkiv** där varje fil använder sitt eget lösenord och krypteringsmetod. Exemplet använder tre exempel-filer (`alice29.txt`, `asyoulik.txt` och `fields.c`) med olika lösenord.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Så fungerar det
- **CreateEntry** lägger till en fil i arkivet.  
- Det fjärde argumentet (`ArchiveEntrySettings`) låter dig ange både komprimering (`DeflateCompressionSettings`) och kryptering (`TraditionalEncryptionSettings` eller `AesEcryptionSettings`).  
- Genom att skicka en annan lösenordsträng för varje post får du ett **lösenordsskyddat zip‑arkiv** där varje fil endast kan låsas upp med sin egen nyckel.

## Common Issues & Troubleshooting

| Symptom | Trolig orsak | Lösning |
|---------|--------------|-----|
| Uttag misslyckas med “Fel lösenord” | Lösenordet matchar inte eller fel krypteringsmetod | Verifiera den exakta lösenordsträngen och säkerställ att du använde samma `EncryptionMethod` vid extrahering. |
| Arkivstorleken är större än förväntat | Att använda AES‑256 på små textfiler kan lägga till extra overhead | För små filer kan AES‑128 vara tillräckligt och ger ett mindre arkiv. |
| Körtidsundantag på `archive.Save` | Saknar skrivbehörighet i målmappen | Se till att applikationen har skrivbehörighet till `dataDir` eller använd en annan utdatamapp. |

## Frequently Asked Questions (FAQs)

### Kan jag använda olika krypteringsmetoder för varje fil?
Ja, Aspose.Zip för .NET tillåter dig att blanda krypteringsmetoder—traditionell ZipCrypto, AES‑128 och AES‑256—på per‑fil‑basis.

### Finns det en provversion tillgänglig?
Ja, du kan komma åt den kostnadsfria provversionen av Aspose.Zip för .NET [här](https://releases.aspose.com/).

### Hur kan jag få support om jag stöter på problem?
Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för hjälp från communityn och Aspose‑support.

### Var kan jag hitta detaljerad dokumentation för Aspose.Zip för .NET?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/zip/net/).

### Kan jag köpa en tillfällig licens för teständamål?
Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose