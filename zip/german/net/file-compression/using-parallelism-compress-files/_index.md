---
date: 2025-12-10
description: Erfahren Sie, wie Sie in .NET mit Aspose.Zip parallele Dateikomprimierung
  durchführen. Komprimieren Sie mehrere Dateien effizient mit unserer Schritt‑für‑Schritt‑Anleitung.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Parallele Dateikomprimierung mit Aspose.Zip für .NET
url: /de/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Parallele Dateikomprimierung mit Aspose.Zip für .NET

## Einführung

In der .NET-Entwicklung ist **parallel file compression** entscheidend, um Speicherplatz zu optimieren und die Datenübertragung zu beschleunigen. Aspose.Zip für .NET bietet eine leistungsstarke Lösung, und eines seiner herausragenden Merkmale ist die Möglichkeit, Parallelität für die Dateikomprimierung zu nutzen. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Verwendung von Parallelität, um **mehrere Dateien** effizient mit Aspose.Zip für .NET zu **komprimieren**.

## Schnelle Antworten
- **Was ist parallel file compression?** Eine Technik, die mehrere Dateien gleichzeitig komprimiert und dabei mehrere CPU‑Kerne nutzt, um die Gesamtverarbeitungszeit zu reduzieren.  
- **Welche Bibliothek unterstützt das in .NET?** Aspose.Zip für .NET bietet integrierte Optionen für parallele Komprimierung.  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz ist für Tests verfügbar; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich Dateien on the fly zu zip hinzufügen?** Ja – verwenden Sie `Archive.CreateEntry` für jede Datei, die Sie einschließen möchten.  
- **Ist es kompatibel mit .NET Core/5/6?** Absolut, die API funktioniert in allen modernen .NET‑Laufzeiten.

## Was ist parallel file compression?
Parallel file compression bedeutet, die Komprimierungsarbeit auf mehrere Threads oder Kerne zu verteilen, sodass mehrere Dateien (oder Teile einer großen Datei) gleichzeitig komprimiert werden können. Dieser Ansatz verkürzt die Zeit zur Erstellung eines **zip archive c#** erheblich im Vergleich zur herkömmlichen sequenziellen Komprimierung.

## Warum Aspose.Zip für parallele Komprimierung verwenden?
- **Speed:** Nutzt die volle Leistung von Multi‑Core‑CPUs.  
- **Scalability:** Verarbeitet große Dateibatches, ohne dass die Verarbeitungszeit proportional ansteigt.  
- **Simplicity:** Die High‑Level‑API abstrahiert Thread‑Komplexitäten.  
- **Flexibility:** Funktioniert mit jeder .NET‑Version und lässt sich nahtlos in bestehende Codebasen integrieren.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in C# und .NET‑Entwicklung.  
- Die Aspose.Zip für .NET‑Bibliothek installiert. Sie können sie **[here](https://releases.aspose.com/zip/net/)** herunterladen.  
- Ein Verständnis der gängigen Dateikomprimierungskonzepte.

## Namespaces importieren

Zuerst importieren Sie die erforderlichen Namespaces in Ihre C#‑Datei, damit der Compiler weiß, wo die Klassen zu finden sind, die Sie verwenden werden.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Schritt 1: Dokumentverzeichnis einrichten

Definieren Sie den Ordner, der die zu komprimierenden Dateien enthält. Dieser Pfad wird in der Variable `dataDir` gespeichert.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Komprimierungsprozess initialisieren

Öffnen Sie eine neue ZIP‑Datei zum Schreiben. Die `using`‑Anweisung stellt sicher, dass der Dateistream nach dem Vorgang ordnungsgemäß freigegeben wird.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Schritt 3: Dateien parallel lesen und komprimieren

Öffnen Sie jede Quelldatei, die Sie dem Archiv hinzufügen möchten. In diesem Beispiel arbeiten wir mit zwei klassischen Texten, aber Sie können **add files to zip** für beliebig viele Dokumente verwenden.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Schritt 4: Archiveinträge erstellen

Erzeugen Sie eine `Archive`‑Instanz und fügen Sie jede Datei als separaten Eintrag hinzu. Hier findet der Schritt **create zip archive c#** statt.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Schritt 5: Parallelitätskriterium festlegen

Konfigurieren Sie die Komprimierung, parallel zu laufen, indem Sie `ParallelOptions` setzen. Das Flag `ParallelCompressInMemory` weist Aspose.Zip an, stets parallele Verarbeitung zu verwenden.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Schritt 6: Komprimiertes Archiv speichern

Schließlich schreiben Sie das Archiv mit den gewünschten Optionen auf die Festplatte, einschließlich Kodierung, einem Kommentar und den zuvor definierten Parallel‑Einstellungen.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

Herzlichen Glückwunsch! Sie haben gerade **parallel file compression** mit Aspose.Zip für .NET durchgeführt und **mehrere Dateien** effizient in ein einzelnes Archiv **komprimiert**.

## Häufige Probleme & Tipps

- **Large Files:** Wenn Sie Speicherengpässe feststellen, sollten Sie erwägen, Dateien in Teilen zu komprimieren, anstatt die gesamte Datei in den Speicher zu laden.  
- **Thread Safety:** Die Aspose.Zip‑API ist im Parallelmodus thread‑sicher; vermeiden Sie es, denselben Stream von mehreren Threads außerhalb der Bibliothek zu modifizieren.  
- **Performance Tuning:** Experimentieren Sie mit `ParallelOptions.MaxDegreeOfParallelism`, wenn Sie die CPU‑Auslastung auf gemeinsam genutzten Servern begrenzen müssen.  

## FAQ

### Q1: Kann ich Aspose.Zip für .NET mit anderen .NET‑Bibliotheken verwenden?

A1: Ja, Aspose.Zip für .NET ist so konzipiert, dass es nahtlos mit anderen .NET‑Bibliotheken integriert werden kann.

### Q2: Ist eine temporäre Lizenz für Testzwecke verfügbar?

A2: Ja, Sie können eine temporäre Lizenz zum Testen von **[here](https://purchase.aspose.com/temporary-license/)** erhalten.

### Q3: Wo finde ich zusätzlichen Support oder kann Fragen stellen?

A3: Besuchen Sie das **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** für Community‑Support und Diskussionen.

### Q4: Gibt es Beispiele oder Dokumentation?

A4: Durchstöbern Sie die **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** für umfassende Beispiele und Dokumentation.

### Q5: Wie kann ich Aspose.Zip für .NET erwerben?

A5: Sie können Aspose.Zip für .NET **[here](https://purchase.aspose.com/buy)** kaufen.

**Zuletzt aktualisiert:** 2025-12-10  
**Getestet mit:** Aspose.Zip 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}