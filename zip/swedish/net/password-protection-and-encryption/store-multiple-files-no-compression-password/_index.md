---
date: 2026-03-08
description: Lär dig hur du lösenordsskyddar zip‑arkiv med Aspose.Zip för .NET, lagrar
  flera filer utan komprimering och tillämpar zip‑filens lösenordsskydd med AES‑kryptering.
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip för .NET - Lösenordsskydda zip-arkivet & lagra flera filer utan
  komprimering
url: /sv/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

 .NET 24.12 (latest at time of writing)" keep.

"**Author:** Aspose" keep.

Close shortcodes.

Add backtop button shortcode unchanged.

Now produce final content with all translations.

Be careful not to translate URLs, code placeholders.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip för .NET – Lösenordsskydda Zip‑arkiv handledning

I modern .NET‑utveckling är säker arkivering av filer ett vanligt krav. Med **Aspose.Zip för .NET** kan du **lösenordsskydda zip‑arkiv**‑filer, lagra flera objekt utan någon komprimering och tillämpa stark AES‑kryptering – allt i bara några rader C#. Denna handledning visar exakt hur du skapar ett zip‑arkiv som innehåller flera filer, använder *store* (ingen komprimering) och är låst med ett lösenord.

## Snabba svar
- **Vad betyder “password protect zip archive”?** Det krypterar zip‑innehållet så att det bara kan öppnas med rätt lösenord.  
- **Vilken krypteringsalgoritm används?** AES‑256 via `AesEcryptionSettings`.  
- **Kan jag lägga till mer än en fil?** Ja – upprepa `CreateEntry`‑anropet för varje källfil.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provversion finns tillgänglig.  
- **Stöds detta på .NET 6/7?** Absolut – Aspose.Zip fungerar med .NET Framework, .NET Core och .NET 5/6/7.

## Vad är ett lösenordsskyddat zip‑arkiv?
*Ett lösenordsskyddat zip‑arkiv* är en ZIP‑fil vars poster är krypterade med ett användardefinierat lösenord. När arkivet öppnas måste lösenordet anges; annars förblir innehållet oläsligt. Aspose.Zip implementerar detta via AES‑256‑kryptering, vilket ger stark säkerhet för känslig data.

## Varför använda lösenordsskydd för zip‑filer med Aspose.Zip?
- **Ingen komprimering** – `StoreCompressionSettings` behåller originalfilens storlek, idealiskt för redan komprimerad media.  
- **Stark kryptering** – AES‑256 skyddar data mot brute‑force‑attacker.  
- **Full .NET‑integration** – Fungerar med .NET Framework, .NET Core och .NET 5/6/7 utan inhemska beroenden.  
- **Enkelt API** – Skapa ett arkiv, ange lösenord, lägg till poster och spara – allt på några få rader.

## Förutsättningar

Innan vi dyker in i koden, se till att du har:

- **Aspose.Zip för .NET** installerat. Du kan ladda ner det [här](https://releases.aspose.com/zip/net/).  
- En mapp som innehåller filerna du vill arkivera. I exemplen nedan pekar variabeln `dataDir` på den mappen.

## Importera namnrymder

Först importerar vi de nödvändiga namnrymderna:

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Hur man lösenordsskyddar zip‑arkiv och lagrar flera filer utan komprimering

Nedan följer en steg‑för‑steg‑guide. Varje steg innehåller en kort förklaring följt av den ursprungliga kodblocket (oförändrat).

### Steg 1: Öppna Zip‑filen

Vi skapar ett nytt `FileStream` som kommer att hålla det resulterande arkivet.

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

### Steg 2: Öppna källfilen

Öppna den första filen du vill lägga till i arkivet. Du kan upprepa detta block för ytterligare filer.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

### Steg 3: Skapa ett arkiv med lagring utan komprimering och AES‑kryptering

Här konfigurerar vi arkivet för att **store** (ingen komprimering) filerna och tillämpa **zip‑fil lösenordsskydd** med AES‑256.

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

### Steg 4: Skapa arkivpost och spara – *create archive entry c#*

Nu lägger vi till filen i arkivet och skriver den krypterade zip‑filen till disk.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

> **Proffstips:** För att lägga till fler filer, anropa helt enkelt `archive.CreateEntry("anotherFile.txt", anotherStream);` innan `archive.Save(zipFile);`.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **“Invalid password”‑undantag** | Fel lösenord eller felaktig krypteringsmetod. | Se till att lösenordet i `AesEcryptionSettings` matchar det du använder för att öppna zip‑filen, och verifiera att du använder `EncryptionMethod.AES256`. |
| **Filstorlek större än förväntat** | Komprimering används av misstag. | Bekräfta att du använder `StoreCompressionSettings` (ingen komprimering) istället för `DeflateCompressionSettings`. |
| **Ström inte stängd** | Saknad avslutningsklammer för `using`‑satser. | Se till att varje `using`‑block är korrekt avslutat; exempel­koden visar rätt nestning. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Zip för .NET med andra krypteringsmetoder?**  
A: Ja – Aspose.Zip stöder flera krypteringsalgoritmer, inklusive AES‑128 och ZipCrypto. Se dokumentationen [här](https://reference.aspose.com/zip/net/) för detaljer.

**Q: Var kan jag få support för Aspose.Zip för .NET?**  
A: Besök [Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37) för gemenskaps­hjälp och officiell support.

**Q: Finns det en gratis provversion av Aspose.Zip för .NET?**  
A: Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Zip för .NET?**  
A: Begär en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.Zip för .NET?**  
A: Du kan köpa Aspose.Zip för .NET [här](https://purchase.aspose.com/buy).

## Slutsats

I den här guiden har vi visat hur du **lösenordsskyddar zip‑arkiv**‑filer, lagrar flera objekt utan komprimering och tillämpar AES‑256‑kryptering med Aspose.Zip för .NET. Genom att följa dessa steg kan du säkra känslig data, uppfylla efterlevnadskrav och hålla dina arkiv lätta. Känn dig fri att experimentera med att lägga till fler filer, ändra lösenord eller byta till andra krypteringsmetoder – Aspose.Zip gör allt enkelt och tydligt.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}