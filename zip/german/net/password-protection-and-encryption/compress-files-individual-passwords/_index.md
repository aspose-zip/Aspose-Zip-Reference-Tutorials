---
date: 2025-12-20
description: Erfahren Sie, wie Sie passwortgeschützte Zip-Archive in .NET mit Aspose.Zip
  erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie Dateien mit Passwörtern
  komprimieren, das Zip‑Eintrags‑Passwort festlegen und AES‑Verschlüsselung verwenden.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Passwortgeschützte ZIP-Dateien in .NET mit Aspose.Zip erstellen
url: /de/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Passwortgeschützte ZIP‑Dateien in .NET mit Aspose.Zip erstellen

## Einführung

Wenn Sie **passwortgeschützte ZIP**‑Archive in einer .NET‑Anwendung erstellen müssen, macht Aspose.Zip das ganz einfach. Durch die Zuweisung eines eindeutigen Passworts zu jedem Eintrag können Sie sensible Dokumente schützen und gleichzeitig den Komfort der ZIP‑Kompression nutzen. In diesem Tutorial lernen Sie, wie Sie Dateien mit individuellen Passwörtern komprimieren, verschiedene Verschlüsselungsmethoden wählen und ein ZIP‑Eintragspasswort festlegen – alles mit klaren, produktionsreifen Code‑Beispielen.

## Schnellantworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET.  
- **Kann ich für jede Datei ein anderes Passwort festlegen?** Ja, jeder Eintrag kann sein eigenes Passwort haben.  
- **Welche Verschlüsselungsalgorithmen werden unterstützt?** Traditionelles ZipCrypto, AES‑128 und AES‑256.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Ist das mit .NET 6+ kompatibel?** Absolut – die API zielt auf .NET Standard 2.0 und höher ab.

## Was bedeutet „passwortgeschützte ZIP erstellen“?
Ein passwortgeschütztes ZIP zu erstellen bedeutet, einer oder mehreren Einträgen innerhalb eines ZIP‑Archivs Verschlüsselung hinzuzufügen, sodass der Inhalt ohne das korrekte Passwort nicht geöffnet werden kann. Das ist ideal für den Versand vertraulicher Dateien, die Speicherung von Backups oder die Einhaltung von Datenschutzrichtlinien.

## Warum Aspose.Zip für passwortgeschützte Archive verwenden?
- **Fein abgestimmte Kontrolle** – ein separates Passwort pro Datei festlegen.  
- **Mehrere Verschlüsselungsoptionen** – von legacy ZipCrypto bis zu starkem AES‑128/256.  
- **Keine externen Abhängigkeiten** – reine .NET‑Bibliothek, leicht zu integrieren.  
- **Umfangreiche Dokumentation** – beinhaltet ein **aspose zip tutorial** für weiterführende Szenarien.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Aspose.Zip für .NET: Vergewissern Sie sich, dass die Aspose.Zip‑Bibliothek in Ihrem .NET‑Projekt installiert ist. Die notwendige Dokumentation finden Sie [hier](https://reference.aspose.com/zip/net/).

- Download: Falls Sie die Bibliothek noch nicht haben, laden Sie Aspose.Zip für .NET von [diesem Link](https://releases.aspose.com/zip/net/) herunter.

- Dokumenten‑Verzeichnis: Legen Sie ein Verzeichnis an, das die zu komprimierenden Dateien enthält.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die erforderlichen Namespaces:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Schritt 1: Pfad zum Ressourcen‑Verzeichnis festlegen

Definieren Sie den Pfad zum Ressourcen‑Verzeichnis, in dem sich Ihre Quelldateien befinden.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Dateien mit individuellen Passwörtern komprimieren

Jetzt komprimieren wir Dateien mit individuellen Passwörtern. Wir verwenden drei Beispieldateien (`alice29.txt`, `asyoulik.txt` und `fields.c`) mit jeweils unterschiedlichen Passwörtern. Das demonstriert, wie man **Dateien mit Passwörtern komprimiert** und gleichzeitig **ZIP‑Eintragspasswort festlegt** unter Verwendung verschiedener Verschlüsselungsschemata, einschließlich eines **ZIP‑Archivs mit AES**.

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

### So funktioniert es
- **TraditionalEncryptionSettings** verwendet den älteren ZipCrypto‑Algorithmus (kompatibel mit den meisten ZIP‑Utilities).  
- **AesEcryptionSettings** ermöglicht die Auswahl von AES‑128 oder AES‑256 für höhere Sicherheit.  
- Jeder Aufruf von `CreateEntry` erhält ein `ArchiveEntrySettings`‑Objekt, in dem sowohl die Komprimierungsmethode als auch die Verschlüsselungseinstellungen angegeben werden, wodurch **ZIP‑Archiveinträge passwortgeschützt** werden.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| “Invalid password” beim Öffnen des ZIP | Das Passwort im Code stimmt nicht mit dem im Entpacker eingegebenen überein | Überprüfen Sie den genauen String, der an `TraditionalEncryptionSettings` oder `AesEcryptionSettings` übergeben wird. |
| Ältere Entpack‑Tools können AES‑verschlüsselte Einträge nicht öffnen | Nicht alle ZIP‑Utilities unterstützen AES‑Verschlüsselung | Verwenden Sie die traditionelle ZipCrypto‑Methode für maximale Kompatibilität oder empfehlen Sie den Einsatz eines modernen Tools (z. B. 7‑Zip). |
| Große Dateien verursachen `OutOfMemoryException` | Dateien werden vollständig in den Speicher geladen, bevor sie komprimiert werden | Streamen Sie die Datei direkt mit `FileStream`, ohne sie komplett in ein `FileInfo`‑Objekt zu laden. |

## Häufig gestellte Fragen (FAQ)

### Kann ich für jede Datei unterschiedliche Verschlüsselungsmethoden verwenden?
Ja, Aspose.Zip für .NET ermöglicht die Verwendung verschiedener Verschlüsselungsmethoden für jede Datei während der Kompression.

### Gibt es eine Testversion?
Ja, Sie können die kostenlose Testversion von Aspose.Zip für .NET [hier](https://releases.aspose.com/) nutzen.

### Wie erhalte ich Support, wenn ich Probleme habe?
Besuchen Sie das [Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37) für Unterstützung durch die Community und den Aspose‑Support.

### Wo finde ich die ausführliche Dokumentation für Aspose.Zip für .NET?
Die Dokumentation steht [hier](https://reference.aspose.com/zip/net/) zur Verfügung.

### Kann ich eine temporäre Lizenz für Testzwecke erwerben?
Ja, eine temporäre Lizenz können Sie [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Weitere schnelle FAQ

**F: Unterstützt die Bibliothek .NET Core und .NET 5/6?**  
A: Ja, Aspose.Zip zielt auf .NET Standard ab und ist damit kompatibel mit .NET Framework, .NET Core sowie .NET 5/6.

**F: Kann ich jedem ZIP‑Eintrag einen Kommentar hinzufügen?**  
A: Während Aspose.Zip den Fokus auf Kompression und Verschlüsselung legt, können Sie Metadaten in einer separaten Manifest‑Datei innerhalb des Archivs speichern.

**F: Ist es möglich, das gesamte Archiv mit einem einzigen Passwort zu verschlüsseln?**  
A: Sie können entweder jedem Eintrag ein individuelles Passwort zuweisen (wie gezeigt) oder dasselbe Passwort für alle Einträge verwenden, um einen einfacheren Ansatz für ein **ZIP‑Archiv mit AES** zu realisieren.

## Fazit

Sie haben nun gelernt, wie Sie **passwortgeschützte ZIP**‑Dateien in .NET mit Aspose.Zip erstellen. Durch das Zuweisen individueller Passwörter und die Auswahl der passenden Verschlüsselungsmethode können Sie Ihre Daten sichern, ohne auf die Vorteile der ZIP‑Kompression zu verzichten. Erkunden Sie weitere Aspose.Zip‑Funktionen wie das Streamen großer Dateien, das Hinzufügen benutzerdefinierter Metadaten und die Integration in Cloud‑Speicher für noch leistungsfähigere Szenarien.

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.Zip für .NET 23.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}