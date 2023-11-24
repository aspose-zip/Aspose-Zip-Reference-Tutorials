---
title: Aspose.Zip für .NET – Tutorial zur sicheren Dateispeicherung
linktitle: Speichern Sie mehrere Dateien ohne Komprimierung mit Passwort
second_title: Aspose.Zip .NET API für Dateikomprimierung und -archivierung
description: Erfahren Sie, wie Sie mit Aspose.Zip für .NET mehrere Dateien ohne Komprimierung sicher speichern können. Einfache Schritte zum Passwortschutz. Nutzen Sie die Macht der Dateiverwaltung!
type: docs
weight: 13
url: /de/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

In der Welt der .NET-Entwicklung ist die Verwaltung und Bearbeitung von Dateien eine häufige Aufgabe. Aspose.Zip für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die Möglichkeit bietet, Zip-Archive nahtlos zu komprimieren, zu dekomprimieren und zu bearbeiten. In diesem Tutorial befassen wir uns mit einem konkreten Szenario: dem Speichern mehrerer Dateien ohne Komprimierung und dem Schutz mit einem Passwort. Am Ende dieses Handbuchs verfügen Sie über das Wissen, diese Funktionalität mit Aspose.Zip für .NET zu implementieren.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Zip für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Zip für .NET-Bibliothek installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/zip/net/).

-  Dokumentverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem sich Ihre Quelldateien befinden. Im bereitgestellten Beispiel ist die Variable`dataDir` stellt Ihr Dokumentenverzeichnis dar.

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces für unseren Code:

```csharp
// Der Pfad zum Ressourcenverzeichnis.
string dataDir = "Your Document Directory"

// Importieren Sie Aspose.Zip-Namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Schritt 1: Öffnen Sie die Zip-Datei

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Dieser Schritt umfasst das Erstellen einer neuen ZIP-Datei mit`FileStream`. Die Datei wird „StoreMutlipleFilesWithoutCompressionWithPassword_out.zip“ genannt.

## Schritt 2: Öffnen Sie die Quelldatei

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Hier öffnen wir die erste Quelldatei, „alice29.txt“, die im Zip-Archiv gespeichert wird.

## Schritt 3: Erstellen Sie ein Archiv

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 In diesem Schritt erstellen wir eine Instanz von`Archive` Klasse, die die Komprimierungs- und Verschlüsselungseinstellungen angibt. Wir benutzen das`StoreCompressionSettings` um Dateien ohne Komprimierung zu speichern und`AesEcryptionSettings` um die AES-Verschlüsselung mit einem Passwort („p@s$“) anzuwenden.

## Schritt 4: Archiveintrag erstellen und speichern

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Dieser letzte Schritt umfasst das Erstellen eines Eintrags im Archiv für „alice29.txt“ und das Speichern des Archivs. Damit ist der Vorgang des Speicherns einer Datei ohne Komprimierung und mit Passwortschutz abgeschlossen.

Schließen Sie Ihr Tutorial ab, indem Sie die wichtigsten Punkte zusammenfassen und die Leser ermutigen, weitere Möglichkeiten mit Aspose.Zip für .NET zu erkunden.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Zip für .NET mehrere Dateien ohne Komprimierung speichern und mit einem Passwort sichern können. Nutzen Sie auf Ihrer weiteren Reise mit der .NET-Entwicklung die Funktionen von Aspose.Zip, um Dateiverwaltungsaufgaben zu rationalisieren und die Sicherheit Ihrer Anwendungen zu erhöhen.

---

### FAQs

### Kann ich Aspose.Zip für .NET mit anderen Verschlüsselungsmethoden verwenden?
 Ja, Aspose.Zip unterstützt verschiedene Verschlüsselungsmethoden. Überprüfen Sie die Dokumentation[Hier](https://reference.aspose.com/zip/net/) für Details.

### Wo erhalte ich Unterstützung für Aspose.Zip für .NET?
 Besuche den[Aspose.Zip-Forum](https://forum.aspose.com/c/zip/37) für Community-Unterstützung und Diskussionen.

### Gibt es eine kostenlose Testversion für Aspose.Zip für .NET?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Zip für .NET erhalten?
 Fordern Sie eine temporäre Lizenz an[Hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Aspose.Zip für .NET kaufen?
 Sie können Aspose.Zip für .NET kaufen[Hier](https://purchase.aspose.com/buy).
