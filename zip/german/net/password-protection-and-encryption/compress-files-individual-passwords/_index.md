---
date: 2026-03-02
description: Erfahren Sie, wie Sie ein passwortgeschütztes Zip‑Archiv erstellen und
  Dateien mit Passwörtern in .NET mithilfe von Aspose.Zip komprimieren. Folgen Sie
  unserer Schritt‑für‑Schritt‑Anleitung.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ein passwortgeschütztes ZIP‑Archiv in .NET mit Aspose.Zip erstellen
url: /de/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines passwortgeschützten ZIP-Archivs in .NET mit Aspose.Zip

## Einführung

Wenn Sie sensible Daten teilen müssen, ist ein **passwortgeschütztes ZIP-Archiv** eine der einfachsten und gleichzeitig effektivsten Methoden, um Informationen sicher zu halten. In .NET‑Anwendungen ermöglicht Aspose.Zip das **Komprimieren von Dateien mit Passwörtern** und gibt jeder Datei einen eigenen Verschlüsselungsschlüssel. In diesem Tutorial lernen Sie genau, wie Sie ein solches Archiv erstellen, warum es wichtig ist und wo Sie es in realen Projekten einsetzen können.

## Schnellantworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET bietet integrierte Unterstützung für Passwörter pro Datei und mehrere Verschlüsselungsmethoden.  
- **Wie viele Codezeilen?** Etwa 30 Zeilen, inklusive Einrichtung und Speichern des Archivs.  
- **Kann jede Datei ein anderes Passwort haben?** Ja – Sie können jedem Eintrag ein eindeutiges Passwort zuweisen.  
- **Welche Verschlüsselungsmethoden sind verfügbar?** Traditionelles ZipCrypto, AES‑128 und AES‑256.  
- **Brauche ich eine Lizenz für die Produktion?** Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich; eine kostenlose Testversion ist verfügbar.

## Was ist ein passwortgeschütztes ZIP-Archiv?
Ein passwortgeschütztes ZIP-Archiv ist eine komprimierte Datei (ZIP), für deren Entpacken ein Passwort erforderlich ist. Das Passwort kann das gesamte Archiv oder einzelne Einträge schützen, und moderne Algorithmen wie AES‑128/256 bieten starke Verschlüsselung.

## Warum Dateien mit Passwörtern komprimieren mit Aspose.Zip?
- **Granulare Sicherheit** – jedem File ein eindeutiges Passwort zuweisen, ideal für Multi‑Tenant‑Szenarien.  
- **Mehrere Verschlüsselungsstandards** – wählen Sie zwischen dem Legacy‑ZipCrypto und starkem AES.  
- **Keine externen Tools** – alles wird programmgesteuert innerhalb Ihres .NET‑Codebases verarbeitet.  
- **Performance** – schnelle Kompression mit Deflate bei gleichzeitig kleiner Archivgröße.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Zip für .NET** – installieren Sie die Bibliothek in Ihrem Projekt. Detaillierte Dokumentation finden Sie [hier](https://reference.aspose.com/zip/net/).  
- **Laden Sie das neueste Paket herunter**, falls Sie das noch nicht getan haben, über [diesen Link](https://releases.aspose.com/zip/net/).  
- Einen Ordner, der die zu komprimierenden Dateien enthält.

## Namespaces importieren

Fügen Sie die erforderlichen Namespaces am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Schritt 1: Pfad des Ressourcenverzeichnisses festlegen

Verweisen Sie im Code auf den Ordner, der die Quelldateien enthält:

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Dateien mit individuellen Passwörtern komprimieren

Jetzt erstellen wir ein **passwortgeschütztes ZIP-Archiv**, bei dem jede Datei ihr eigenes Passwort und ihre eigene Verschlüsselungsmethode verwendet. Das Beispiel nutzt drei Beispieldateien (`alice29.txt`, `asyoulik.txt` und `fields.c`) mit unterschiedlichen Passwörtern.

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

### Wie es funktioniert
- **CreateEntry** fügt dem Archiv eine Datei hinzu.  
- Das vierte Argument (`ArchiveEntrySettings`) ermöglicht die Angabe sowohl der Kompression (`DeflateCompressionSettings`) als auch der Verschlüsselung (`TraditionalEncryptionSettings` oder `AesEcryptionSettings`).  
- Durch die Übergabe einer unterschiedlichen Passwortzeichenfolge für jeden Eintrag erhalten Sie ein **passwortgeschütztes ZIP-Archiv**, bei dem jede Datei nur mit ihrem eigenen Schlüssel entsperrt werden kann.

## Häufige Probleme & Fehlerbehebung

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Entpacken schlägt mit „Falsches Passwort“ fehl | Passwort stimmt nicht überein oder falsche Verschlüsselungsmethode | Überprüfen Sie die genaue Passwortzeichenfolge und stellen Sie sicher, dass Sie beim Entpacken dieselbe `EncryptionMethod` verwendet haben. |
| Archivgröße ist größer als erwartet | Die Verwendung von AES‑256 bei kleinen Textdateien kann zusätzlichen Overhead erzeugen | Für kleine Dateien kann AES‑128 ausreichend sein und ein kleineres Archiv erzeugen. |
| Laufzeitausnahme bei `archive.Save` | Fehlende Schreibberechtigung im Zielordner | Stellen Sie sicher, dass die Anwendung Schreibzugriff auf `dataDir` hat oder verwenden Sie einen anderen Ausgabepfad. |

## Häufig gestellte Fragen (FAQs)

### Kann ich für jede Datei unterschiedliche Verschlüsselungsmethoden verwenden?
Ja, Aspose.Zip für .NET erlaubt das Mischen von Verschlüsselungsmethoden — traditionelles ZipCrypto, AES‑128 und AES‑256 — auf Dateiebene.

### Gibt es eine Testversion?
Ja, Sie können die kostenlose Testversion von Aspose.Zip für .NET [hier](https://releases.aspose.com/) abrufen.

### Wie kann ich Unterstützung erhalten, wenn ich Probleme habe?
Besuchen Sie das [Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37) für Hilfe von der Community und dem Aspose‑Support.

### Wo finde ich die detaillierte Dokumentation für Aspose.Zip für .NET?
Die Dokumentation ist [hier](https://reference.aspose.com/zip/net/) verfügbar.

### Kann ich eine temporäre Lizenz für Testzwecke erwerben?
Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-02  
**Getestet mit:** Aspose.Zip für .NET (neueste Version)  
**Autor:** Aspose  

---