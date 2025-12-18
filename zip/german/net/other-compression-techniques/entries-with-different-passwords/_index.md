---
date: 2025-12-18
description: Erfahren Sie, wie Sie ZIP-Dateien mit verschiedenen Passwörtern mithilfe
  von Aspose.Zip für .NET verschlüsseln. Dieser Leitfaden zeigt Ihnen, wie Sie Dateien
  mit Passwörtern komprimieren und ein 7z-Archiv in C# erstellen.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man ZIP-Dateien mit unterschiedlichen Passwörtern in Aspose.Zip für .NET
  verschlüsselt
url: /de/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ZIP-Dateien mit unterschiedlichen Passwörtern in Aspose.Zip für .NET verschlüsselt

## Einführung

Wenn Sie **wie man ZIP verschlüsselt** Archive benötigen und jedem Eintrag ein eigenes Passwort zuweisen möchten, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung eines 7‑Zip‑Archivs, bei dem jede Datei mit einem eindeutigen Passwort geschützt ist, mithilfe der Aspose.Zip‑Bibliothek für .NET. Am Ende verstehen Sie, warum die Verschlüsselung pro Eintrag wichtig ist, wie Sie sie einrichten und wie Sie das Ergebnis in Ihren eigenen Projekten überprüfen können.

## Schnelle Antworten
- **Was bedeutet „encrypt zip“?** Es bedeutet, dass ein passwortbasierter Schutz (AES oder ZipCrypto) auf den Inhalt eines ZIP/7z-Archivs angewendet wird.  
- **Kann jeder Eintrag ein anderes Passwort haben?** Ja – Aspose.Zip ermöglicht es, für jede Datei ein separates Passwort zu vergeben.  
- **Welche .NET-Versionen werden unterstützt?** Alle modernen .NET Framework-, .NET Core- und .NET 5/6-Versionen.  
- **Benötige ich eine Lizenz für die Produktion?** Für den produktiven Einsatz ist eine kommerzielle Lizenz erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Welches Kompressionsformat wird im Beispiel verwendet?** Das Beispiel erstellt ein 7z-Archiv mit AES‑256-Verschlüsselung.

## Was ist „how to encrypt zip“ mit Aspose.Zip?

Das Verschlüsseln einer ZIP‑ (oder 7z‑) Datei bedeutet, dass ihre Einträge gesichert werden, sodass sie ohne das korrekte Passwort nicht geöffnet werden können. Aspose.Zip für .NET unterstützt sowohl das klassische ZipCrypto als auch die stärkere AES‑Verschlüsselung und ermöglicht es, Verschlüsselungseinstellungen pro Eintrag festzulegen, was Ihnen eine feinkörnige Kontrolle über die Sicherheit gibt.

## Warum unterschiedliche Passwörter für jeden Eintrag verwenden?

- **Sicherheitssegmentierung:** Wenn ein Passwort kompromittiert wird, bleiben die anderen Dateien geschützt.  
- **Regulatorische Konformität:** In einigen Branchen sind separate Zugangsdaten für verschiedene Datenkategorien erforderlich.  
- **Benutzerspezifischer Zugriff:** Sie können ein einzelnes Archiv an mehrere Benutzer verteilen, wobei jeder nur die Dateien entsperrt, für die er autorisiert ist.

## Voraussetzungen

Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Zip für .NET** installiert – siehe die offizielle [Dokumentation](https://reference.aspose.com/zip/net/) für Download- und Installationsanweisungen.  
- Einen Ordner auf Ihrem Rechner, in dem Sie die Quelldateien (das „Document Directory“) aufbewahren.  
- Grundlegende Kenntnisse in C# und Visual Studio (oder Ihrer bevorzugten .NET‑IDE).

## Namespaces importieren

Wir beginnen damit, die Namespaces zu importieren, die die Klassen enthalten, die wir benötigen.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Legen Sie Ihr Document Directory fest

Definieren Sie den Pfad, der die Dateien enthält, die Sie archivieren möchten.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Erstellen Sie Einträge mit unterschiedlichen Passwörtern

Hier ist der Kern des Tutorials. Wir öffnen eine neue 7z‑Datei, erstellen drei `FileInfo`‑Objekte und fügen jedes als Eintrag mit eigenem AES‑Passwort hinzu.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Wie das funktioniert

- `SevenZipArchive` ist der Container für ein 7‑z‑Archiv.  
- `CreateEntry` nimmt den Eintragsnamen, die Quelldatei, ein Überschreib‑Flag und ein `SevenZipEntrySettings`‑Objekt.  
- Innerhalb von `SevenZipEntrySettings` geben wir zwei Einstellungsobjekte an: eines für die Kompression (`SevenZipStoreCompressionSettings`) und eines für die Verschlüsselung (`SevenZipAESEncryptionSettings`).  
- Jeder Aufruf liefert ein **anderes Passwort** (`"test1"`, `"test2"`, `"test3"`), wodurch ein Schutz pro Eintrag erreicht wird.

## Schritt 3: Verifizierung

Nachdem das Archiv gespeichert wurde, können Sie eine einfache Bestätigungsnachricht ausgeben.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Führen Sie das Programm aus und versuchen Sie anschließend, `archive.7z` mit einem Tool wie 7‑Zip zu öffnen. Es wird Sie für jeden Eintrag nach einem Passwort fragen und bestätigen, dass die Passwörter tatsächlich unterschiedlich sind.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|-------|--------|-----|
| **Fehler: Ungültiges Passwort** | Die Passwortzeichenkette enthält überflüssige Leerzeichen oder unsichtbare Zeichen. | Entfernen Sie überflüssige Leerzeichen aus den Passwortzeichenketten (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archiv lässt sich in älteren Tools nicht öffnen** | Einige ältere ZIP-Tools unterstützen die von 7z verwendete AES‑256‑Verschlüsselung nicht. | Verwenden Sie einen modernen Extraktor (7‑Zip 19.00+). |
| **Datei wurde nicht zum Archiv hinzugefügt** | Der Pfad zur Quelldatei ist falsch oder die Datei existiert nicht. | Überprüfen Sie `dataDir` und die Dateinamen oder verwenden Sie `Path.Combine(dataDir, "data1.bin")`. |

## Häufig gestellte Fragen

### Q1: Ist Aspose.Zip für .NET mit allen .NET-Versionen kompatibel?

A1: Ja, Aspose.Zip für .NET ist so konzipiert, dass es nahtlos mit allen Versionen des .NET‑Frameworks zusammenarbeitet.

### Q2: Kann ich Aspose.Zip für .NET in meinen kommerziellen Projekten verwenden?

A2: Auf jeden Fall! Aspose.Zip für .NET bietet kommerzielle Lizenzen, und weitere Informationen zum Kauf finden Sie [hier](https://purchase.aspose.com/buy).

### Q3: Gibt es eine kostenlose Testversion?

A3: Ja, Sie können die Funktionen von Aspose.Zip für .NET mit einer kostenlosen Testversion ausprobieren. Starten Sie [hier](https://releases.aspose.com/).

### Q4: Wie kann ich Support für Aspose.Zip für .NET erhalten?

A4: Bei Fragen oder Unterstützung besuchen Sie das [Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37).

### Q5: Kann ich Aspose.Zip für .NET ohne permanente Lizenz verwenden?

A5: Ja, Sie können eine temporäre Lizenz für kurzfristige Bedürfnisse erhalten. Weitere Details finden Sie [hier](https://purchase.aspose.com/temporary-license/).

## Fazit

Sie haben gerade gelernt, **wie man ZIP-Archive** mit per‑Eintrag‑Passwörtern mithilfe von Aspose.Zip für .NET verschlüsselt. Diese Technik bietet Ihnen die Flexibilität, jede Datei einzeln zu schützen, strengere Sicherheitsanforderungen zu erfüllen und die benutzerspezifische Verteilung zu vereinfachen. Experimentieren Sie gern mit anderen Kompressionseinstellungen, größeren Dateimengen oder integrieren Sie diese Logik in einen Web‑Service, der on‑the‑fly sichere Archive erzeugt.

---

**Zuletzt aktualisiert:** 2025-12-18  
**Getestet mit:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}