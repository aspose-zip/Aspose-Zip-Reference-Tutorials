---
date: 2025-12-23
description: Lär dig hur du lösenordsskyddar zip-filer och hur du krypterar zip-arkiv
  med Aspose.Zip för .NET. Spara flera filer utan komprimering med ett säkert lösenord.
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Hur man lösenordsskyddar ZIP med Aspose.Zip för .NET
url: /sv/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du lösenordsskyddar ZIP med Aspose.Zip för .NET

I modern .NET‑utveckling är det lika viktigt att säkra dina arkiv som att komprimera dem. Denna handledning visar **hur du lösenordsskyddar zip**‑filer med Aspose.Zip för .NET, samtidigt som den demonstrerar hur du **skapar zip‑arkiv .net** utan komprimering och **hur du krypterar zip‑arkiv** med AES‑kryptering. I slutet av guiden har du en tydlig, steg‑för‑steg‑lösning som du kan klistra in i vilket C#‑projekt som helst.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.Zip för .NET  
- **Kan jag lagra filer utan komprimering?** Ja – använd `StoreCompressionSettings`.  
- **Hur lägger jag till ett lösenord?** Tillhandahåll en `AesEcryptionSettings`‑instans med ditt lösenord.  
- **Stöds AES‑256?** Absolut – sätt `EncryptionMethod.AES256`.  
- **Vilka .NET‑versioner fungerar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Vad är “hur du lösenordsskyddar zip”?
Lösenordsskydd lägger ett lager av kryptering på ett ZIP‑arkiv, vilket säkerställer att endast användare som känner till lösenordet kan extrahera dess innehåll. Aspose.Zip gör denna process enkel genom att låta dig definiera krypteringsinställningar när du skapar arkivet.

## Varför använda Aspose.Zip för .NET?
- **Inga externa beroenden** – rent .NET‑bibliotek.  
- **Full kontroll** över komprimering, kryptering och arkivstruktur.  
- **Stöder moderna krypteringsmetoder** som AES‑256.  
- **Hantera stora filer** effektivt med streaming‑API:er.

## Förutsättningar

Innan vi dyker ner, se till att du har följande:

- **Aspose.Zip för .NET‑bibliotek** – ladda ner det **[här](https://releases.aspose.com/zip/net/)**.  
- **Dokumentkatalog** – en mapp som innehåller filerna du vill arkivera. I exemplen pekar variabeln `dataDir` på den här platsen.

## Importera namnrymder

Först importerar du de namnrymder som krävs för att arbeta med Aspose.Zip:

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Hur du skapar ett Zip‑arkiv .NET utan komprimering

### Steg 1: Öppna Zip‑filen

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

Här skapar vi en ny arkivfil som kommer att hålla våra poster. Flaggan `FileMode.Create` säkerställer att en ny fil genereras varje körning.

### Steg 2: Öppna källfilen

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Vi öppnar den första källfilen (`alice29.txt`). Du kan upprepa detta block för ytterligare filer du vill lagra.

### Steg 3: Skapa ett arkiv med “zip‑arkiv utan komprimering”

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

- `StoreCompressionSettings()` talar om för Aspose.Zip **att inte komprimera** filen, vilket ger dig ett **zip‑arkiv utan komprimering**.  
- `AesEcryptionSettings("p@s$", EncryptionMethod.AES256)` är där vi **hur du krypterar zip‑arkiv** – lösenordet är `"p@s$"` och krypteringsmetoden är AES‑256.

### Steg 4: Lägg till arkivpost och spara

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Filen läggs till i arkivet och arkivet sparas till disk, vilket slutför processen **hur du lösenordsskyddar zip**.

## Vanliga fallgropar & tips

- **Lösenordskomplexitet** – Använd ett starkt lösenord; enkla strängar är lätta att brute‑force.  
- **Strömavslut** – `using`‑satserna stänger automatiskt strömmar och förhindrar fil‑lås.  
- **Flera filer** – För att lägga till fler filer, öppna helt enkelt ytterligare `FileStream`‑objekt och anropa `CreateEntry` för var och en.  
- **Kompatibilitet** – AES‑256‑krypterade ZIP‑filer stöds av de flesta moderna arkivverktyg (WinRAR, 7‑Zip, osv.).

## Vanliga frågor

**Q: Kan jag använda andra krypteringsmetoder än AES‑256?**  
A: Ja, Aspose.Zip stöder ZipCrypto och andra AES‑nivåer. Justera `EncryptionMethod`‑enumen därefter.

**Q: Är det möjligt att kryptera ett befintligt arkiv?**  
A: Du måste återskapa arkivet med önskade krypteringsinställningar; Aspose.Zip kan inte ändra kryptering i befintliga arkiv.

**Q: Ökar lagring av filer utan komprimering arkivets storlek?**  
A: Lite grann, eftersom de ursprungliga filbytes lagras direkt. Detta är användbart när du behöver snabb extraktion eller vill bevara filens integritet.

**Q: Hur hämtar jag de lösenordsskyddade filerna?**  
A: Öppna arkivet med en `Archive`‑instans som inkluderar samma `AesEcryptionSettings` (lösenord) som användes vid skapandet.

**Q: Finns det begränsningar för filstorlek eller antal poster?**  
A: Aspose.Zip hanterar stora filer och tusentals poster, begränsat endast av systemets minne och lagringsutrymme.

## Ytterligare resurser

- **Aspose.Zip‑dokumentation** – detaljerad API‑referens **[här](https://reference.aspose.com/zip/net/)**.  
- **Community‑support** – ställ frågor på **[Aspose.Zip‑forumet](https://forum.aspose.com/c/zip/37)**.  
- **Gratis provversion** – få en provversion **[här](https://releases.aspose.com/)**.  
- **Tillfällig licens** – begär en tillfällig licens **[här](https://purchase.aspose.com/temporary-license/)**.  
- **Köpalternativ** – köp en full licens **[här](https://purchase.aspose.com/buy)**.

---

**Senast uppdaterad:** 2025-12-23  
**Testat med:** Aspose.Zip 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}