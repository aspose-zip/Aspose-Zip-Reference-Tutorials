---
date: 2026-06-09
description: Erfahren Sie, wie Sie ein Passwort zu ZIP hinzufügen und LZMA-ZIP-Archive
  mit Aspose.Zip für .NET erstellen. Dieses Tutorial behandelt Bzip2, LZMA (Wörterbuchgröße),
  PPMd, Enhanced Deflate, Store compression und die ASP.NET-Dateikompression großer
  Dateien.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Kompressionseinstellungen optimieren
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Passwort zu ZIP hinzufügen und LZMA-Archiv mit Aspose.Zip für .NET erstellen
url: /de/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Passwort zu ZIP hinzufügen und LZMA-Archiv mit Aspose.Zip für .NET erstellen

In modernen .NET-Anwendungen kann das **Passwort zu ZIP hinzufügen** beim Erstellen eines hochkomprimierten LZMA‑ZIP‑Archivs sensible Daten schützen und gleichzeitig die bestmögliche Kompression bieten. Egal, ob Sie einen ASP.NET‑Dateikomprimierungs‑Dienst, ein Desktop‑Dienstprogramm für Multi‑Gigabyte‑Dateien oder einen cloud‑basierten Workflow erstellen, führt Sie dieses Tutorial Schritt für Schritt durch das Sichern und Komprimieren Ihrer Dateien mit Aspose.Zip für .NET.

## Schnelle Antworten
- **Was ist der Hauptvorteil der LZMA‑Kompression?** Höchstes Kompressionsverhältnis bei angemessener Geschwindigkeit für die meisten Dateitypen.  
- **Welche Methode speichert Dateien ohne Kompression?** Store‑Kompression (auch „store compression zip“ genannt).  
- **Kann ich diese Einstellungen in einer ASP.NET‑Anwendung verwenden?** Ja – einfach Aspose.Zip in Ihrem Projekt referenzieren und dieselbe API aufrufen.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Für die Produktion ist eine kommerzielle Lizenz erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 und .NET 5–10.

## Was bedeutet „Passwort zu ZIP hinzufügen“ in Aspose.Zip?
**Das Hinzufügen eines ZIP‑Passworts verschlüsselt jeden Eintrag in einem ZIP‑Archiv, sodass nur Benutzer, die das Passwort kennen, die Dateien extrahieren können.** Aspose.Zip unterstützt sowohl die traditionelle ZipCrypto‑Verschlüsselung als auch AES‑Verschlüsselung (128, 192 oder 256 Bit). Die Verschlüsselungseinstellungen werden als zweites Argument an `ArchiveEntrySettings` übergeben, wenn ein `Archive` erstellt wird; es gibt keine separate `SetPassword`‑Methode.

## Warum Aspose.Zip für .NET‑Dateikompression verwenden?
Aspose.Zip bietet eine einheitliche API, die viele Algorithmen abdeckt und dabei hohe Leistung sowie geringen Speicherverbrauch liefert. Sie ermöglicht Entwicklern, für jedes Szenario die beste Kompressionsmethode zu wählen und die Verschlüsselung in einem Schritt anzuwenden, wodurch Code vereinfacht und Wartungsaufwand reduziert wird.

- **Einheitliche API** – Eine konsistente Schnittstelle für Bzip2, LZMA, PPMd, Enhanced Deflate und Store.  
- **Leistungsoptimiert** – Die optimierte native Implementierung verarbeitet **Dateien bis zu 10 GB** ohne das gesamte File in den Speicher zu laden.  
- **ASP.NET‑freundlich** – Funktioniert nahtlos in Webprojekten, Hintergrunddiensten und Azure Functions.  
- **Fein abgestimmte Kontrolle** – Passen Sie Wörterbuchgröße, Kompressionsgrad und Verschlüsselung mit einem einzigen Konstruktoraufruf an.  
- **Unterstützt mehr als 10 Kompressionsalgorithmen** – deckt die gängigsten Anwendungsfälle in Unternehmens‑Datenpipelines ab.

## Voraussetzungen
- **Aspose.Zip für .NET‑Bibliothek** – Herunterladen und installieren von der [Aspose-Dokumentation](https://reference.aspose.com/zip/net/).  
- **Beispiel‑Textdatei** – Bereiten Sie eine Beispieldatei (z. B. `sample.txt`) vor, die Sie komprimieren werden.  
- **.NET‑Entwicklungsumgebung** – Visual Studio 2022 oder eine kompatible IDE.  

## Namespaces importieren

Die Klassen `Archive`, `ArchiveEntrySettings` und die Verschlüsselungsklassen befinden sich im Namespace `Aspose.Zip`. Importieren Sie sie am Anfang Ihrer Datei:

- `Archive` repräsentiert einen ZIP‑Archiv‑Container.  
- `ArchiveEntrySettings` enthält Kompressions‑ und Verschlüsselungsoptionen für jeden Eintrag.  
- Verschlüsselungsklassen (z. B. `AesEncryptionSettings`) definieren, wie Daten verschlüsselt werden.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Jetzt erkunden wir jede Kompressionseinstellung und sehen, wie man **Passwort zu ZIP hinzufügen** dort anwendet, wo es passend ist.

## Verwendung von Bzip2‑Kompressionseinstellungen

### Schritt 1: Bzip2‑Kompression mit traditioneller Verschlüsselung initialisieren

`Bzip2CompressionSettings` konfiguriert den Bzip2‑Algorithmus (Blockgröße usw.).  
`TraditionalEncryptionSettings` wendet die Legacy‑ZipCrypto‑Verschlüsselung auf einen Eintrag an.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*Der Passwortschutz wird über `TraditionalEncryptionSettings` angewendet, das direkt an `ArchiveEntrySettings` übergeben wird.*

## Wie man mit Aspose.Zip für .NET Passwort zu ZIP hinzufügt

Laden Sie Ihre Quelldatei, erstellen Sie ein `Archive` mit den Entry‑Einstellungen und fügen Sie die Datei dem Archiv hinzu. Die Verschlüsselung wird automatisch angewendet, da sie beim Erstellen der `ArchiveEntrySettings`‑Instanz übergeben wurde.

**Direkte Antwort (40‑70 Wörter):**  
Erstellen Sie ein `ArchiveEntrySettings`‑Objekt, das sowohl die gewünschten Kompressionseinstellungen als auch entweder `TraditionalEncryptionSettings` oder `AesEncryptionSettings` enthält. Übergeben Sie dieses Objekt dann an den `Archive`‑Konstruktor und fügen Sie Dateien mit `AddEntry` hinzu. Das Archiv wird bereits mit dem eingebetteten Passwort geschrieben, sodass nach der Erstellung kein zusätzlicher Schritt erforderlich ist.

`ArchiveEntrySettings` ist der Konfigurationshalter, der Aspose.Zip mitteilt, wie jeder Eintrag komprimiert und verschlüsselt werden soll.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Wie man ein LZMA‑ZIP‑Archiv mit Aspose.Zip erstellt

### Schritt 1: LZMA‑Kompression mit AES256‑Verschlüsselung initialisieren

`LzmaCompressionSettings` steuert LZMA‑spezifische Parameter wie Wörterbuchgröße und Fast‑Bytes.  
`AesEncryptionSettings` bietet AES‑256‑Verschlüsselung für die Archiv‑Einträge.

**Direkte Antwort (40‑70 Wörter):**  
Instanziieren Sie `LzmaCompressionSettings` mit einer gewählten `DictionarySize`, erstellen Sie ein `AesEncryptionSettings`‑Objekt mit Ihrem Passwort und `EncryptionMethod.AES256` und bauen Sie daraus ein `ArchiveEntrySettings`. Übergeben Sie dieses an den `Archive`‑Konstruktor und fügen Sie Ihre Dateien hinzu; das resultierende ZIP wird LZMA‑komprimiert und AES‑geschützt in einem einzigen Vorgang.

`LzmaCompressionSettings` ist die Klasse, die LZMA‑spezifische Parameter wie Wörterbuchgröße und Fast‑Bytes steuert.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Tipp:** LZMA bietet eine konfigurierbare **LZMA‑Wörterbuchgröße**, die sowohl das Kompressionsverhältnis als auch den Speicherverbrauch beeinflusst. Sie können sie über `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` setzen, wenn Sie für sehr große Dateien feinabstimmen müssen.

## Verwendung von PPMd‑Kompressionseinstellungen

### Schritt 1: PPMd‑Kompression mit AES256‑Verschlüsselung initialisieren

`PpmdCompressionSettings` definiert die Ordnung und den Speicherverbrauch für den PPMd‑Algorithmus.  
`AesEncryptionSettings` bietet AES‑256‑Verschlüsselung für die Archiv‑Einträge.

**Direkte Antwort (40‑70 Wörter):**  
Erstellen Sie eine Instanz von `PpmdCompressionSettings`, kombinieren Sie sie mit einem `AesEncryptionSettings`‑Objekt, das Ihr Passwort enthält, und übergeben Sie beide an ein `ArchiveEntrySettings`. Verwenden Sie dieses Einstellungsobjekt beim Erzeugen des `Archive`; das resultierende ZIP wird PPMd‑komprimiert und passwortgeschützt sein, ohne zusätzliche Aufrufe.

`PpmdCompressionSettings` definiert die Ordnung und den Speicherverbrauch für den PPMd‑Algorithmus.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Verwendung von Enhanced‑Deflate‑Kompressionseinstellungen

### Schritt 1: Enhanced‑Deflate‑Kompression mit AES256‑Verschlüsselung initialisieren

`EnhancedDeflateCompressionSettings` ermöglicht die Angabe eines Kompressionsgrades, der Geschwindigkeit und Größe ausbalanciert.  
`AesEncryptionSettings` bietet AES‑256‑Verschlüsselung für die Archiv‑Einträge.

**Direkte Antwort (40‑70 Wörter):**  
Instanziieren Sie `EnhancedDeflateCompressionSettings` mit dem gewünschten Niveau (0‑9), kombinieren Sie es mit `AesEncryptionSettings` und verpacken Sie beides in `ArchiveEntrySettings`. Übergeben Sie dies an den `Archive`‑Konstruktor und fügen Sie Dateien hinzu; das Archiv wird mit Enhanced‑Deflate‑Kompression und AES‑256‑Passwortschutz in einem Durchlauf erstellt.

`EnhancedDeflateCompressionSettings` ermöglicht die Angabe eines Kompressionsgrades, der Geschwindigkeit und Größe ausbalanciert.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Verwendung von Store‑Kompressionseinstellungen (store compression zip)

### Schritt 1: Store‑Kompression mit traditioneller Verschlüsselung initialisieren

`StoreCompressionSettings` weist Aspose.Zip an, die Kompression vollständig zu überspringen und die Quelldatei byte‑für‑byte zu erhalten.  
`TraditionalEncryptionSettings` wendet die Legacy‑ZipCrypto‑Verschlüsselung an.

**Direkte Antwort (40‑70 Wörter):**  
Erstellen Sie eine Instanz von `StoreCompressionSettings` (die keine Kompression durchführt), kombinieren Sie sie mit `TraditionalEncryptionSettings`, das Ihr Passwort enthält, und verpacken Sie beide in `ArchiveEntrySettings`. Übergeben Sie dies an den `Archive`‑Konstruktor; das resultierende ZIP enthält die Originaldatei unkomprimiert, jedoch passwortgeschützt.

`StoreCompressionSettings` weist Aspose.Zip an, die Kompression vollständig zu überspringen und die Quelldatei byte‑für‑byte zu erhalten.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro‑Tipp:** Passen Sie die Variable `dataDir` an, damit sie auf Ihr tatsächliches Arbeitsverzeichnis zeigt, und verwenden Sie dieselbe `Archive`‑Instanz erneut, wenn Sie mehrere Dateien zu einem einzigen Archiv hinzufügen müssen.

## Häufige Probleme & Lösungen
- **„Datei nicht gefunden“-Fehler** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`\` oder `/`) endet und dass `sample.txt` existiert.  
- **Speicherverbrauch bei großen Dateien** – Verwenden Sie `ArchiveEntrySettings`, um den Streaming‑Modus zu aktivieren, der Daten direkt in den Ausgabestream schreibt.  
- **Inkompatibler Kompressionsgrad** – Einige Algorithmen (z. B. LZMA) bieten zusätzliche Eigenschaften wie `DictionarySize`. Konsultieren Sie die API‑Dokumentation, wenn Sie feinere Kontrolle benötigen.  
- **Passwort nicht angewendet** – Stellen Sie sicher, dass das Verschlüsselungseinstellungs‑Objekt beim Erzeugen von `ArchiveEntrySettings` als zweites Argument übergeben wird und nicht nach der Erstellung des Archivs.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Zip für .NET mit anderen Kompressionsbibliotheken verwenden?**  
A: Aspose.Zip ist dafür ausgelegt, mit seinen integrierten Algorithmen zu arbeiten. Die Integration von Drittanbieter‑Bibliotheken ist möglich, erfordert jedoch eine benutzerdefinierte Handhabung außerhalb der Aspose‑API.

**Q: Wie kann ich einem mit Aspose.Zip erstellten ZIP Passwortschutz hinzufügen?**  
A: Übergeben Sie entweder `TraditionalEncryptionSettings` oder `AesEncryptionSettings` als zweites Argument an `ArchiveEntrySettings`, wenn Sie das `Archive` erstellen. Siehe die [Dokumentation](https://docs.aspose.com/zip/net/password-protecting-archives/) für vollständige Beispiele.

**Q: Gibt es eine Testversion, die ich ausprobieren kann?**  
A: Ja, Sie können die Testversion [hier](https://releases.aspose.com/) abrufen.

**Q: Wo kann ich Community‑Hilfe erhalten oder Fragen stellen?**  
A: Für Support und Community‑Diskussionen besuchen Sie das [Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37).

**Q: Kann ich eine temporäre Lizenz für die Evaluierung erhalten?**  
A: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wie hilft das bei der ASP.NET‑Dateikompression?**  
A: Durch Aufruf derselben API aus einem ASP.NET‑Controller oder Middleware können Sie Dateien on‑the‑fly komprimieren, bevor Sie sie an den Client senden, wodurch Bandbreite reduziert und die wahrgenommene Leistung verbessert wird.

**Q: Was ist der beste Weg, große Dateien effizient zu komprimieren?**  
A: Kombinieren Sie den Streaming‑Modus mit LZMA‑Kompression und einer geeigneten `DictionarySize`. Das balanciert Speicherverbrauch und Kompressionsverhältnis für massive Datensätze.

---

**Zuletzt aktualisiert:** 2026-06-09  
**Getestet mit:** Aspose.Zip 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Aspose.Zip für .NET – ZIP-Archiv mit Passwort schützen & mehrere Dateien ohne Kompression speichern](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Passwortgeschützten ZIP für .NET‑Verzeichnisse erstellen – Aspose.Zip‑Tutorial](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [Mehrere Dateien zippen C# – Mühelose Kompression mit Aspose.Zip für .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}