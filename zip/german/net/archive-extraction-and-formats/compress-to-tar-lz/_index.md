---
date: 2025-12-01
description: Erfahren Sie, wie Sie tar.lz‑Dateien in .NET mit Aspose.Zip komprimieren
  und tar.lz‑Archive einfach erstellen können.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man tar.lz mit Aspose.Zip für .NET komprimiert
url: /de/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man tar.lz mit Aspose.Zip für .NET komprimiert

In der modernen .NET-Entwicklung kann das effiziente Verpacken von Dateien die Größe der Bereitstellung und die Netzwerkübertragungszeiten erheblich verbessern. **Wie man tar.lz komprimiert** ist ein häufiges Bedürfnis, wenn Sie ein leichtgewichtiges, LZ‑komprimiertes TAR-Archiv benötigen. In diesem Tutorial führen wir Sie Schritt für Schritt durch ein klares **tar.lz-Komprimierungsbeispiel** mit der Aspose.Zip-Bibliothek, sodass Sie schnell ein tar.lz-Archiv in Ihren eigenen Anwendungen erstellen können.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip for .NET.
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Beispiel.
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kann ich mehrere Dateien gleichzeitig komprimieren?** Ja – einfach weitere Einträge hinzufügen, bevor Sie speichern.

## Was ist tar.lz-Kompression?
`tar.lz` ist ein TAR-Archiv, das mit dem LZMA-Algorithmus (oft einfach **LZ** genannt) komprimiert wurde. Es kombiniert die Einfachheit der Dateigruppierung von TAR mit dem hohen Kompressionsverhältnis von LZ und ist ideal für Sicherungsdateien, Paketdistribution oder jede Situation, in der Bandbreite wichtig ist.

## Warum Aspose.Zip für .NET verwenden?
* **Keine externen Abhängigkeiten** – reine .NET-Implementierung.  
* **Plattformübergreifende Unterstützung** – funktioniert unter Windows, Linux und macOS.  
* **Integrierte LZ-Kompression** – keine zusätzlichen nativen Tools erforderlich.  
* **Robuste Fehlerbehandlung** – Ausnahmen sind beschreibend, was das Debuggen erleichtert.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

- **Aspose.Zip for .NET** Bibliothek – laden Sie sie von [hier](https://releases.aspose.com/zip/net/) herunter.  
- Einen Ordner, der die zu archivierenden Dateien enthält. Der Pfad zu diesem Ordner wird in der Variable `dataDir` gespeichert (Sie setzen ihn in Schritt 3).

## Namespaces importieren
Fügen Sie die erforderlichen Namespaces hinzu, damit der Compiler weiß, wo die Klassen zu finden sind, die wir verwenden werden.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Wie man ein tar.lz-Archiv erstellt – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Eine einzelne Datei komprimieren
Das erste Beispiel zeigt das grundlegendste Szenario – das Hinzufügen einer Datei zu einem TAR-Archiv und das anschließende Speichern als **tar.lz**-Datei.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Erklärung**

- `new TarArchive()` erstellt einen leeren TAR-Container.  
- `CreateEntry` fügt die Datei `alice29.txt` aus Ihrem `dataDir` hinzu.  
- `SaveLzipped` schreibt das Archiv auf die Festplatte und wendet LZ-Kompression an, wodurch `archive.tar.lz` entsteht.

### Schritt 2: Mehrere Dateien in einem Archiv komprimieren
Oft müssen Sie mehrere Dateien zusammen bündeln. Rufen Sie einfach `CreateEntry` für jede Datei auf, bevor Sie speichern.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Erklärung**

- Der Code folgt dem gleichen Muster wie Schritt 1, fügt jedoch einen zweiten Eintrag (`lcet10.txt`) hinzu.  
- Sie können `CreateEntry` beliebig oft wiederholen; die Bibliothek verwaltet die interne TAR-Struktur automatisch.

### Schritt 3: Ihr Dokumentenverzeichnis angeben
Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad, in dem Ihre Quelldateien liegen. Dieser Pfad wird von den obigen Beispielen verwendet.

```csharp
string dataDir = "Your Document Directory";
```

**Erklärung**

- Setzen Sie `dataDir` auf einen vollqualifizierten Ordnerpfad, z. B. `@"C:\MyFiles\"`.  
- Das Verzeichnis in einer Variable zu halten, macht den Code wiederverwendbar und leichter zu warten.

## Häufige Fallstricke & Fehlersuche
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| `FileNotFoundException` beim Ausführen des Beispiels | `dataDir` verweist auf einen nicht existierenden Ordner oder der Dateiname ist falsch geschrieben | Überprüfen Sie den Pfad und die Dateinamen; verwenden Sie `Path.Combine` zur Sicherheit. |
| Ausgabedatei ist **0 KB** | `archive.SaveLzipped` wurde aufgerufen, bevor Einträge hinzugefügt wurden | Stellen Sie sicher, dass mindestens ein `CreateEntry`-Aufruf vor `SaveLzipped` erfolgt. |
| Kompression scheint langsam | Große Dateien mit Standard-Puffergröße | Erwägen Sie, Dateien in Teilen zu verarbeiten oder asynchrones I/O zu nutzen, wenn die Leistung kritisch ist. |

## Fazit
Sie wissen jetzt, **wie man tar.lz**-Dateien mit Aspose.Zip für .NET komprimiert, egal ob Sie ein einzelnes Dokument oder eine Sammlung von Dateien verarbeiten. Dieses **tar.lz compression example** zeigt eine saubere, produktionsreife Methode, leichte Archive zu erstellen, die einfach übertragen oder gespeichert werden können.

## Häufig gestellte Fragen

**F:** Kann ich Dateien beliebiger Größe mit Aspose.Zip für .NET komprimieren?  
**A:** Ja, die Bibliothek verarbeitet sowohl kleine als auch sehr große Dateien; stellen Sie lediglich sicher, dass Sie über genügend Speicher und Festplattenspeicher für die temporäre TAR-Struktur verfügen.

**F:** Ist der Code mit der neuesten Aspose.Zip-Version kompatibel?  
**A:** Das Beispiel richtet sich an die aktuelle Version; halten Sie das NuGet-Paket stets aktuell, um Fehlerbehebungen und neue Funktionen zu erhalten.

**F:** Gibt es Lizenzüberlegungen?  
**A:** Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich. Siehe die Lizenzdetails auf der [Aspose-Website](https://purchase.aspose.com/buy).

**F:** Kann ich das in einem kommerziellen Projekt verwenden?  
**A:** Absolut – sobald Sie eine gültige Lizenz besitzen, können Sie die Bibliothek in jede kommerzielle Anwendung einbinden.

**F:** Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?  
**A:** Besuchen Sie das [Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37) für Community‑Support und offizielle Unterstützung.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-01  
**Getestet mit:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

---