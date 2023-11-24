---
title: Dekomprimieren mehrerer Dateien mit Aspose.Zip für .NET
linktitle: Mehrere Dateien dekomprimieren
second_title: Aspose.Zip .NET API für Dateikomprimierung und -archivierung
description: Erfahren Sie, wie Sie mehrere Dateien mit Aspose.Zip für .NET dekomprimieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine effiziente Dateiverwaltung.
type: docs
weight: 11
url: /de/net/file-decompression/decompress-multiple-files/
---
## Einführung

Willkommen zu unserem umfassenden Tutorial zum Dekomprimieren mehrerer Dateien mit Aspose.Zip für .NET! Wenn Sie komprimierte Dateien mit mehreren Einträgen effizient verarbeiten möchten, sind Sie hier richtig. In dieser Anleitung führen wir Sie Schritt für Schritt durch den Prozess mit Aspose.Zip für .NET.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Zip für .NET: Stellen Sie sicher, dass Sie die Aspose.Zip-Bibliothek für .NET installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/zip/net/).

- Dokumentenverzeichnis: Richten Sie ein Verzeichnis ein, in dem Ihre Dokumente gespeichert werden. Sie verwenden dies als Basisverzeichnis im Code.

Beginnen wir nun mit der Schritt-für-Schritt-Anleitung.

## Namespaces importieren

Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces für Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Komprimieren mehrerer Dateien

Um mehrere Dateien zu dekomprimieren, benötigen Sie zunächst eine komprimierte Datei mit mehreren Einträgen. Lassen Sie uns eines erstellen:

```csharp
string dataDir = "Your Document Directory";

// Führen Sie die Komprimierungsmethode aus
CompressMultipleFiles.Run();
```

## Schritt 2: Dekomprimieren der Dateien

Lassen Sie uns nun die Dateien Schritt für Schritt dekomprimieren:

### Schritt 2.1: Öffnen der komprimierten Datei

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Schritt 2.2: Einträge auflisten und Fortschritt verfolgen

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Schritt 2.3: Extrahieren des ersten Eintrags

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Lesen und schreiben Sie Daten aus dem dekomprimierten Stream in die Extrahierungsdatei.
    }
}
```

### Schritt 2.4: Extrahieren des zweiten Eintrags

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

Und da haben Sie es! Sie haben mehrere Dateien mit Aspose.Zip für .NET erfolgreich dekomprimiert.

## Abschluss

In diesem Tutorial haben wir die wesentlichen Schritte zum Dekomprimieren mehrerer Dateien mit Aspose.Zip für .NET behandelt. Wenn Sie dieser Anleitung folgen, können Sie komprimierte Dateien effizient und einfach verwalten.

## FAQs

### F1: Kann ich Aspose.Zip für .NET sowohl in kommerziellen als auch in persönlichen Projekten verwenden?

 A1: Ja, Aspose.Zip für .NET kann sowohl in kommerziellen als auch in persönlichen Projekten verwendet werden. Einzelheiten zur Lizenzierung finden Sie unter[Lizenzinformationen von Aspose](https://purchase.aspose.com/buy).

### F2: Gibt es eine kostenlose Testversion für Aspose.Zip für .NET?

 A2: Ja, Sie können eine kostenlose Testversion von Aspose.Zip für .NET ausprobieren[Hier](https://releases.aspose.com/zip/net).

### F3: Wo finde ich zusätzliche Unterstützung für Aspose.Zip für .NET?

 A3: Besuchen Sie die[Aspose.Zip-Forum](https://forum.aspose.com/c/zip/37) für Community-Unterstützung und Diskussionen.

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Zip für .NET erwerben?

 A4: Besorgen Sie sich eine temporäre Lizenz für Aspose.Zip für .NET[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Gibt es bestimmte Systemanforderungen für die Verwendung von Aspose.Zip für .NET?

 A5: Siehe[Dokumentation](https://reference.aspose.com/zip/net/) für detaillierte Systemanforderungen.