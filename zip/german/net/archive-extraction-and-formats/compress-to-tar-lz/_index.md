---
date: 2026-07-04
description: Erfahren Sie, wie Sie mehrere Dateien tar mit Aspose.Zip für .NET komprimieren
  und tar.lz-Archive effizient erstellen.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Komprimieren zu TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man mehrere Dateien tar mit Aspose.Zip für .NET komprimiert
url: /de/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man mehrere Dateien tar mit Aspose.Zip für .NET komprimiert

In der modernen .NET-Entwicklung kann das effiziente Verpacken von Dateien die Bereitstellungsgröße und die Netzwerkübertragungszeiten erheblich verbessern. **Compress multiple files tar** ist ein häufiger Bedarf, wenn Sie ein leichtgewichtiges, LZ‑komprimiertes TAR-Archiv für Backups, Verteilung oder Cloud‑Uploads benötigen. In diesem Tutorial führen wir Sie Schritt für Schritt durch ein klares **tar.lz-Kompressionsbeispiel** mit der Aspose.Zip-Bibliothek, sodass Sie schnell ein **tar.lz-Archiv** in Ihren eigenen Anwendungen erstellen können.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip for .NET.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Beispiel.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich mehrere Dateien gleichzeitig komprimieren?** Ja – fügen Sie einfach vor dem Speichern weitere Einträge hinzu.

## Wie komprimiere ich mehrere Dateien tar mit Aspose.Zip für .NET?
Laden Sie Ihre Quelldateien, erstellen Sie eine `TarArchive`-Instanz, fügen Sie jede Datei mit `CreateEntry` hinzu und schließen Sie ab, indem Sie `SaveLzipped` aufrufen. Die Bibliothek verarbeitet die TAR-Struktur und die LZ-Kompression intern, sodass Sie nach nur wenigen Codezeilen eine einzelne `*.tar.lz`-Datei erhalten. Dieser Ansatz funktioniert unter Windows, Linux und macOS ohne native Abhängigkeiten.

## Was ist tar.lz-Kompression?
`tar.lz` ist ein TAR-Archiv, das mit dem LZMA-Algorithmus komprimiert wurde (oft einfach als **LZ** bezeichnet). Es kombiniert die Einfachheit der TAR-Dateigruppierung mit dem hohen Kompressionsverhältnis von LZ und ist ideal für Sicherungsdateien, Paketverteilung oder jede Situation, in der Bandbreite wichtig ist.

## Warum Aspose.Zip für .NET verwenden?
Aspose.Zip bietet eine rein verwaltete, plattformübergreifende Lösung, die TAR-, ZIP- und LZ-basierte Archive ohne externe Werkzeuge erstellt, über 30 Archivformate unterstützt und bis zu 30 % bessere Kompression bei großen Dateien liefert, während detaillierte Ausnahmen für eine robuste Fehlerbehandlung bereitgestellt werden. Es integriert sich zudem nahtlos in .NET-Logging‑Frameworks und bietet detaillierte Fortschrittsereignisse.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

- **Aspose.Zip for .NET** Bibliothek – laden Sie sie von [hier](https://releases.aspose.com/zip/net/) herunter.  
- Ein Ordner, der die Dateien enthält, die Sie archivieren möchten. Der Pfad zu diesem Ordner wird in der Variable `dataDir` gespeichert (Sie setzen ihn in Schritt 3).

## Namespaces importieren
Fügen Sie die erforderlichen Namespaces hinzu, damit der Compiler weiß, wo die Klassen zu finden sind, die wir verwenden werden.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Wie man ein tar.lz-Archiv erstellt – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Eine einzelne Datei komprimieren
Das erste Beispiel zeigt das grundlegendste Szenario – das Hinzufügen einer Datei zu einem TAR-Archiv und das anschließende Speichern als **tar.lz**-Datei.

Die Klasse `TarArchive` repräsentiert einen TAR-Container, der mehrere Dateien in einem einzigen Archiv halten kann.  

**Erklärung**

- `new TarArchive()` erstellt einen leeren TAR-Container.  
- `CreateEntry` fügt die Datei `alice29.txt` aus Ihrem `dataDir` hinzu.  
- `SaveLzipped` schreibt das Archiv auf die Festplatte und wendet LZ-Kompression an, wodurch `archive.tar.lz` entsteht.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Schritt 2: Mehrere Dateien in einem Archiv komprimieren
Oft müssen Sie mehrere Dateien zusammen bündeln. Rufen Sie einfach `CreateEntry` für jede Datei vor dem Speichern auf. Dies demonstriert **add files to tar lz** und effektiv **compress multiple files tar**.

**Erklärung**

- Der Code folgt dem gleichen Muster wie Schritt 1, fügt jedoch einen zweiten Eintrag (`lcet10.txt`) hinzu.  
- Sie können `CreateEntry` beliebig oft wiederholen; die Bibliothek verwaltet die interne TAR-Struktur automatisch.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Schritt 3: Ihr Dokumentenverzeichnis angeben
Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad, in dem Ihre Quelldateien liegen. Dieser Pfad wird von den obigen Beispielen verwendet.

**Erklärung**

- Setzen Sie `dataDir` auf einen vollqualifizierten Ordnerpfad, z. B. `@\"C:\\MyFiles\\\"`.  
- Das Halten des Verzeichnisses in einer Variablen macht den Code wiederverwendbar und leichter zu warten.

```csharp
string dataDir = "Your Document Directory";
```

## Häufige Fallstricke & Fehlersuche
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `FileNotFoundException` beim Ausführen des Beispiels | `dataDir` verweist auf einen nicht existierenden Ordner oder der Dateiname ist falsch geschrieben | Überprüfen Sie den Pfad und die Dateinamen; verwenden Sie `Path.Combine` zur Sicherheit. |
| Ausgabedatei ist **0 KB** | `archive.SaveLzipped` wurde aufgerufen, bevor Einträge hinzugefügt wurden | Stellen Sie sicher, dass mindestens ein `CreateEntry`-Aufruf `SaveLzipped` vorausgeht. |
| Kompression scheint langsam zu sein | Große Dateien mit Standard-Puffergröße | Erwägen Sie, Dateien in Teilen zu verarbeiten oder asynchrones I/O zu verwenden, wenn die Leistung kritisch ist. |

## Fazit
Sie wissen jetzt, **wie man tar.lz**-Dateien mit Aspose.Zip für .NET komprimiert, egal ob Sie ein einzelnes Dokument oder eine Sammlung von Dateien verarbeiten. Dieses **tar.lz-Kompressionsbeispiel** zeigt eine saubere, produktionsreife Methode, **tar lz-Archive** zu erstellen, die leicht übertragen oder gespeichert werden können. Sie können Dateien zu tar.lz komprimieren, indem Sie dieselbe API verwenden und `SaveLzipped` nach dem Hinzufügen aller gewünschten Einträge aufrufen.

## Häufig gestellte Fragen

**Q:** Kann ich Dateien beliebiger Größe mit Aspose.Zip für .NET komprimieren?  
**A:** Ja, die Bibliothek verarbeitet sowohl kleine als auch sehr große Dateien; stellen Sie lediglich sicher, dass Sie genügend Speicher und Festplattenspeicher für die temporäre TAR-Struktur haben.

**Q:** Ist der Code mit der neuesten Aspose.Zip-Version kompatibel?  
**A:** Das Beispiel richtet sich an die aktuelle Version; halten Sie das NuGet-Paket stets auf dem neuesten Stand für Fehlerbehebungen und neue Funktionen.

**Q:** Gibt es Lizenzüberlegungen?  
**A:** Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich. Siehe die Lizenzdetails auf der [Aspose-Website](https://purchase.aspose.com/buy).

**Q:** Kann ich dies in einem kommerziellen Projekt verwenden?  
**A:** Absolut – sobald Sie eine gültige Lizenz besitzen, können Sie die Bibliothek in jede kommerzielle Anwendung einbetten.

**Q:** Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?  
**A:** Besuchen Sie das [Aspose.Zip-Forum](https://forum.aspose.com/c/zip/37) für Community‑Support und offizielle Unterstützung.

---

**Zuletzt aktualisiert:** 2026-07-04  
**Getestet mit:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [TAR-Archiv erstellen und Dateien zu TAR hinzufügen mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Wie man TAR komprimiert und TarBz2 mit Aspose.Zip für .NET erstellt](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dateien zu TAR hinzufügen und tarxz-Archiv mit Aspose.Zip erstellen](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}