---
date: 2026-08-07
description: Erfahren Sie, wie Sie Dateien zu tar hinzufügen und ein TarBz2-Archiv
  in .NET mit Aspose.Zip erzeugen. Die Schritt‑für‑Schritt‑Anleitung zeigt die Erstellung
  von tar, Bzip2‑Kompression und Tipps zu bewährten Verfahren.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Komprimieren zu TarBz2
og_description: Dateien zu tar hinzufügen und ein TarBz2-Archiv in .NET mit Aspose.Zip
  erzeugen. Diese Anleitung behandelt die Erstellung von tar, Bzip2‑Kompression und
  Tipps zur Fehlerbehebung.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Dateien zu tar hinzufügen und ein TarBz2-Archiv mit Aspose.Zip erstellen
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
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
title: Dateien zu tar hinzufügen und ein TarBz2-Archiv mit Aspose.Zip erstellen
url: /de/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dateien zu tar hinzufügen und ein TarBz2-Archiv mit Aspose.Zip erstellen

In diesem Tutorial erfahren Sie **wie man Dateien zu tar**-Archiven hinzufügt und sie mit der **Aspose.Zip**‑Bibliothek für .NET in ein kompaktes **TarBz2**‑Dateiformat umwandelt. Egal, ob Sie ein Backup‑Tool entwickeln, Bereitstellungspakete veröffentlichen oder ein leichtgewichtiges Bündel für die Verteilung benötigen – die nachfolgenden Schritte zeigen Ihnen, wie Sie Dateien zu einem tar‑Container hinzufügen, Bzip2‑Kompression anwenden und ein sofort einsetzbares Archiv erzeugen.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten  
- **Benötige ich eine Lizenz?** Für die Produktion ist eine temporäre Lizenz erforderlich; eine kostenlose Testversion ist verfügbar  
- **Kann ich mehrere Dateien komprimieren?** Ja – Sie können beliebig viele Einträge zum tar‑Archiv hinzufügen  
- **Ist es kompatibel mit .NET 6+?** Absolut, Aspose.Zip unterstützt .NET Framework und .NET Core/5/6  

## Was ist ein TarBz2-Archiv?

Eine TarBz2‑Datei kombiniert den traditionellen **tar**‑Container (der Verzeichnisstruktur und Dateimetadaten bewahrt) mit **Bzip2**‑Kompression und ergibt ein stark komprimiertes `.tar.bz2`‑Paket. Dieses Format ist auf Unix‑ähnlichen Systemen beliebt, weil es ein gutes Gleichgewicht zwischen Kompressionsrate und Dekompressionsgeschwindigkeit bietet.

## Warum Dateien mit Aspose.Zip zu TarBz2 komprimieren?

Aspose.Zip kann ein TarBz2‑Archiv in **zwei API‑Aufrufen** erzeugen und dabei Streams effizient verarbeiten. Es unterstützt **über 50 Archiv‑ und Kompressionsformate**, verarbeitet Dateien bis zu **2 GB**, ohne das gesamte Archiv in den Speicher zu laden, und läuft auf Windows, Linux und macOS .NET‑Laufzeiten. Die Bibliothek bietet zudem feinkörnige Kontrolle über Eintragsnamen, Zeitstempel und Kompressionsstufen, was sie ideal für Konsolen‑Utilities und Web‑Services macht.

## Voraussetzungen

- **Aspose.Zip für .NET** – laden Sie das neueste Paket von der offiziellen Seite herunter: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Dokumentverzeichnis** – ein Ordner, der die zu archivierenden Dateien enthält. In den Beispielen referenzieren wir ihn mit der Variable `dataDir`.

> **Pro Tipp:** Bewahren Sie Ihre Quelldateien in einem eigenen Ordner auf, um ein versehentliches Einbeziehen unerwünschter Dateien zu vermeiden.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces, damit Sie auf die Tar‑ und Bzip2‑Klassen von Aspose.Zip zugreifen können.

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

## Schritt 2: Dateien zu tar hinzufügen und ein TarBz2-Archiv erstellen

`TarArchive` repräsentiert einen In‑Memory‑tar‑Container, der mehrere Dateieinträge aufnehmen kann.  
`Bzip2Archive` komprimiert einen Stream mit dem Bzip2‑Algorithmus.  
Die Methode `CreateEntry` fügt eine Datei dem tar‑Archiv als neuen Eintrag hinzu.

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

- `CreateEntry` **fügt Dateien zu tar hinzu** – Sie können diese Methode für jede Datei aufrufen, die im Archiv enthalten sein soll.  
- `bz2.SetSource(archive)` weist das Bzip2‑Archiv an, den gesamten tar‑Stream zu komprimieren.  
- `bz2.Save(...)` schreibt die endgültige **TarBz2**‑Datei auf die Festplatte.

**Tipp:** Um **Dateien zu tar in großen Mengen** hinzuzufügen, wiederholen Sie einfach `archive.CreateEntry` für jede Datei, bevor Sie `bz2.Save` aufrufen.

## Wie fügt man Dateien zu tar hinzu?

Laden Sie das Quellverzeichnis, erstellen Sie eine `TarArchive`‑Instanz, fügen Sie jede Datei mit `CreateEntry` hinzu, wickeln Sie den tar‑Stream in ein `Bzip2Archive` ein und rufen Sie `Save` auf. Dieses Zwei‑Schritt‑Muster fügt beliebig viele Dateien hinzu und erzeugt in einem einzigen, flüssigen Ablauf eine `.tar.bz2`‑Datei, ohne temporäre Dateien oder externe Werkzeuge zu benötigen.

## Häufige Probleme & Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| **Datei nicht gefunden**‑Fehler | Falscher `dataDir`‑Pfad oder fehlende Dateierweiterung | Überprüfen Sie den vollständigen Pfad und stellen Sie sicher, dass die Datei existiert. |
| **Leeres Archiv** | Keine Einträge vor `bz2.Save` hinzugefügt | Fügen Sie mindestens einen `CreateEntry`‑Aufruf hinzu. |
| **Zugriff verweigert** | Anwendung hat keine Schreibberechtigung für das Ausgabeverzeichnis | Starten Sie die Anwendung mit entsprechenden Rechten oder wählen Sie ein beschreibbares Verzeichnis. |

## Häufig gestellte Fragen

**F: Ist Aspose.Zip mit allen .NET-Anwendungen kompatibel?**  
A: Ja. Es funktioniert mit .NET Framework, .NET Core, .NET 5/6 und neueren Laufzeiten.

**F: Kann ich mehrere Dateien gleichzeitig komprimieren?**  
A: Absolut. Rufen Sie `CreateEntry` für jede Datei auf, bevor Sie das Archiv speichern.

**F: Wo finde ich zusätzliche Dokumentation?**  
A: Detaillierte Dokumentation finden Sie in der **Aspose.Zip .NET API‑Referenz**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**F: Wie erhalte ich eine temporäre Lizenz für Aspose.Zip?**  
A: Sie können **hier eine temporäre Lizenz anfordern**: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, **laden Sie eine Testversion von den Aspose‑Releases herunter**: [download a trial version](https://releases.aspose.com/).

## Fazit

Sie wissen jetzt **wie man Dateien zu tar hinzufügt**, den tar‑Stream mit Bzip2 komprimiert und mit Aspose.Zip für .NET ein **TarBz2**‑Archiv erzeugt. Der Ansatz ist schnell, speichereffizient und funktioniert auf allen modernen .NET‑Plattformen. Experimentieren Sie gern mit größeren Dateimengen, benutzerdefinierten Eintragsnamen oder integrieren Sie den Code in Ihre eigenen Backup‑ oder Bereitstellungspipelines.

Falls Sie auf Probleme stoßen, steht die Aspose.Zip‑Community bereit, Ihnen zu helfen – besuchen Sie einfach das **Aspose.Zip‑Support‑Forum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-08-07  
**Tested With:** Aspose.Zip für .NET (neueste Version)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Tar-Archiv erstellen und Dateien zu tar hinzufügen mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Dateien zu tar hinzufügen und tarxz‑Archiv mit Aspose.Zip erstellen](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Dateien zu tar hinzufügen und zu TarZ mit Aspose.Zip für .NET komprimieren](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}