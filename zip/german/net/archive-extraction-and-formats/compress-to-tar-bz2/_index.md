---
date: 2026-10-31
description: Erfahren Sie, wie Sie ein tar-Archiv erstellen und es mit Aspose.Zip
  in .NET zu einer TarBz2-Datei komprimieren. Die Schritt‑für‑Schritt‑Anleitung zeigt
  die Erstellung des tar-Archivs, Bzip2‑Kompression und Tipps zu bewährten Verfahren.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Komprimierung zu TarBz2
og_description: Erfahren Sie, wie Sie ein tar-Archiv erstellen und es mit Aspose.Zip
  für .NET zu einer TarBz2-Datei komprimieren. Die Schritt‑für‑Schritt‑Anleitung behandelt
  die Erstellung des tar-Archivs, Bzip2‑Kompression und Tipps zu bewährten Verfahren.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Erstellen Sie ein tar-Archiv und komprimieren Sie es zu TarBz2 mit .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Wie man ein tar-Archiv erstellt und mit .NET zu TarBz2 komprimiert
url: /de/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Tar-Archiv erstellt und mit .NET zu TarBz2 komprimiert

In diesem Tutorial lernen Sie **wie man Tar-Archive** erstellt und diese anschließend mit dem kompakten **TarBz2**‑Paket mithilfe der **Aspose.Zip**‑Bibliothek für .NET komprimiert. Egal, ob Sie ein Backup‑Utility bauen, Deploy‑Bundles vorbereiten oder ein leichtgewichtiges Distributionsformat benötigen – die nachfolgenden Schritte zeigen Ihnen, wie Sie Dateien zu einem Tar‑Container hinzufügen, Bzip2‑Kompression anwenden und die finale `.tar.bz2`‑Datei schreiben.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten  
- **Benötige ich eine Lizenz?** Für die Produktion ist eine temporäre Lizenz erforderlich; eine kostenlose Testversion ist verfügbar  
- **Kann ich mehrere Dateien komprimieren?** Ja – fügen Sie beliebig viele Einträge zum Tar‑Archiv hinzu  
- **Ist es kompatibel mit .NET 6+?** Absolut, Aspose.Zip unterstützt .NET Framework und .NET Core/5/6  

## Was ist ein TarBz2-Archiv?

Eine TarBz2‑Datei kombiniert den traditionellen **tar**‑Container (der Verzeichnisstruktur und Dateimetadaten bewahrt) mit **Bzip2**‑Kompression und ergibt ein stark komprimiertes `.tar.bz2`‑Paket. Dieses Format ist auf Unix‑ähnlichen Systemen beliebt, da es ein gutes Gleichgewicht zwischen Kompressionsrate und Dekompressionsgeschwindigkeit bietet.

## Warum Dateien mit Aspose.Zip zu TarBz2 komprimieren?

Aspose.Zip kann ein TarBz2‑Archiv in **zwei API‑Aufrufen** erzeugen und dabei Streams effizient verarbeiten. Es unterstützt **über 50 Archiv‑ und Kompressionsformate**, verarbeitet Dateien bis zu **2 GB**, ohne das gesamte Archiv in den Speicher zu laden, und läuft auf Windows, Linux und macOS .NET‑Runtimes. Die Bibliothek bietet zudem feinkörnige Kontrolle über Eintragsnamen, Zeitstempel und Kompressionsstufen, was sie ideal für Konsolen‑Utilities und Web‑Services macht.

## Voraussetzungen

- **Aspose.Zip für .NET** – laden Sie das neueste Paket von der offiziellen Seite herunter: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Dokumentverzeichnis** – ein Ordner, der die zu archivierenden Dateien enthält. In den Beispielen referenzieren wir ihn mit der Variable `dataDir`.

> **Pro Tipp:** Bewahren Sie Ihre Quelldateien in einem eigenen Ordner auf, um ein versehentliches Einbeziehen unerwünschter Dateien zu vermeiden.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces, um auf die Tar‑ und Bzip2‑Klassen von Aspose.Zip zugreifen zu können.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Schritt 1: Dokumentverzeichnis festlegen

Definieren Sie den Pfad, der auf den Ordner mit den zu archivierenden Dateien zeigt.

```csharp
string dataDir = "Your Document Directory";
```

> Ersetzen Sie `"Your Document Directory"` durch den absoluten oder relativen Pfad zu Ihrem Quellordner.

## Schritt 2: Dateien zum Tar hinzufügen und ein TarBz2-Archiv erstellen

Die Klasse `TarArchive` repräsentiert einen Tar‑Container im Speicher, während `Bzip2Archive` Streams mit dem Bzip2‑Algorithmus komprimiert.  
Die Methode `CreateEntry` fügt dem Tar‑Archiv einen neuen Dateieintrag hinzu.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **fügt Dateien zum Tar hinzu** – Sie können diese Methode für jede Datei aufrufen, die im Archiv enthalten sein soll.  
- `bz2.SetSource(archive)` weist das Bzip2‑Archiv an, den gesamten Tar‑Stream zu komprimieren.  
- `bz2.Save(...)` schreibt die finale **TarBz2**‑Datei auf die Festplatte.

**Tipp:** Um **Dateien in großen Mengen zum Tar hinzuzufügen**, wiederholen Sie einfach `archive.CreateEntry` für jede Datei, bevor Sie `bz2.Save` aufrufen.

## Wie fügt man Dateien zum Tar hinzu?

Laden Sie das Quellverzeichnis, erstellen Sie eine `TarArchive`‑Instanz, fügen Sie jede Datei mit `CreateEntry` hinzu, wickeln Sie den Tar‑Stream in ein `Bzip2Archive` ein und rufen Sie `Save` auf. Dieses Zwei‑Schritt‑Muster fügt beliebig viele Dateien hinzu und erzeugt in einem einzigen, flüssigen Ablauf eine `.tar.bz2`‑Datei, ohne temporäre Dateien oder externe Werkzeuge zu benötigen.

## Häufige Probleme & Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| **Datei nicht gefunden**‑Fehler | Falscher `dataDir`‑Pfad oder fehlende Dateierweiterung | Überprüfen Sie den vollständigen Pfad und stellen Sie sicher, dass die Datei existiert. |
| **Leeres Archiv** | Keine Einträge vor `bz2.Save` hinzugefügt | Fügen Sie mindestens einen `CreateEntry`‑Aufruf hinzu. |
| **Zugriff verweigert** | Anwendung hat keine Schreibberechtigung für das Ausgabeverzeichnis | Führen Sie die Anwendung mit entsprechenden Rechten aus oder wählen Sie ein beschreibbares Verzeichnis. |

## Häufig gestellte Fragen

**Q: Ist Aspose.Zip mit allen .NET‑Anwendungen kompatibel?**  
A: Ja. Es funktioniert mit .NET Framework, .NET Core, .NET 5/6 und neueren Runtimes.

**Q: Kann ich mehrere Dateien gleichzeitig komprimieren?**  
A: Absolut. Rufen Sie `CreateEntry` für jede Datei auf, bevor Sie das Archiv speichern.

**Q: Wo finde ich zusätzliche Dokumentation?**  
A: Detaillierte Dokumentation finden Sie in der **Aspose.Zip .NET API‑Referenz**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Wie erhalte ich eine temporäre Lizenz für Aspose.Zip?**  
A: Sie können **hier eine temporäre Lizenz anfordern**: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja, **laden Sie eine Testversion von den Aspose‑Releases herunter**: [download a trial version](https://releases.aspose.com/).

Sie können auch [laden Sie eine Testversion herunter](https://releases.aspose.com/).

## Fazit

Sie wissen jetzt **wie man ein Tar‑Archiv erstellt**, den Tar‑Stream mit Bzip2 komprimiert und ein **TarBz2**‑Archiv mithilfe von Aspose.Zip für .NET erzeugt. Der Ansatz ist schnell, speichereffizient und funktioniert auf allen modernen .NET‑Plattformen. Experimentieren Sie gern mit größeren Dateimengen, benutzerdefinierten Eintragsnamen oder integrieren Sie den Code in Ihre eigenen Backup‑ oder Deploy‑Pipelines.

Falls Sie auf Probleme stoßen, steht die Aspose.Zip‑Community bereit, Ihnen zu helfen – besuchen Sie einfach das **Aspose.Zip‑Support‑Forum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Zuletzt aktualisiert:** 2026-10-31  
**Getestet mit:** Aspose.Zip für .NET (neueste Version)  
**Autor:** Aspose  

## Verwandte Tutorials

- [Tar-Archiv erstellen und Dateien zu Tar hinzufügen mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Dateien zu Tar hinzufügen und Tarxz-Archiv mit Aspose.Zip erstellen](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Dateien zu Tar hinzufügen und zu TarZ komprimieren mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}