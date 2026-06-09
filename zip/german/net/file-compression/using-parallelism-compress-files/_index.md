---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mehrere Dateien in C# mit Aspose.Zip Parallel Compression zippen

## Einführung

Wenn Sie **zip multiple files c#** schnell und effizient durchführen müssen, ist die Nutzung von Parallelverarbeitung der richtige Ansatz. In modernen .NET‑Anwendungen kann das Erstellen großer ZIP‑Archive zum Engpass werden – insbesondere bei Dutzenden oder Hunderten von Dateien. Aspose.Zip für .NET beseitigt dieses Problem, indem es integrierte **parallel zip compression** bereitstellt, die die Arbeit auf alle verfügbaren CPU‑Kerne verteilt. In diesem Tutorial führen wir Sie durch den gesamten Prozess: von der Einrichtung der Umgebung bis zum Speichern eines ZIP‑Archivs mit aktivierter Parallelität, und wir zeigen Ihnen außerdem, wie Sie **create zip archive c#** erstellen, das reibungslos unter .NET Core läuft.

## Schnelle Antworten
- **Was ist parallel zip compression?** Sie komprimiert mehrere Dateien gleichzeitig, indem mehrere Threads verwendet werden, um die Gesamtverarbeitungszeit zu verkürzen.  
- **Welche .NET‑Bibliothek unterstützt das?** Aspose.Zip für .NET bietet eine einfache API für parallele Kompression.  
- **Benötige ich eine Lizenz für die Produktion?** Ja – eine Volllizenz ist erforderlich; eine temporäre Lizenz ist für Tests verfügbar.  
- **Kann ich Dateien während des Zippen hinzufügen?** Absolut – verwenden Sie `Archive.CreateEntry` für jede Datei, die Sie einschließen möchten.  
- **Ist es mit .NET 6/7 kompatibel?** Ja, die API funktioniert mit allen modernen .NET‑Laufzeiten.

## Was ist zip multiple files c#?
`zip multiple files c#` bezieht sich auf die Praxis, ein einzelnes ZIP‑Archiv zu erstellen, das viele einzelne Dateien enthält, mithilfe von C#‑Code. Kombiniert man dies mit **parallel zip compression**, verarbeitet die Bibliothek jede Datei in einem separaten Thread, wodurch die Zeit zur Erstellung des endgültigen Archivs drastisch reduziert wird.

## Warum Aspose.Zip für parallele Kompression verwenden?
Parallele Kompression ermöglicht es Ihnen, jeden Kern einer Mehrkernmaschine zu nutzen und liefert oft **2‑3× schnellere** Durchsatzrate im Vergleich zu einem einstufigen Ansatz. Sie skaliert zudem elegant: Das Hinzufügen weiterer Dateien erhöht die Echtzeit nicht linear, und die API übernimmt das Thread‑Management für Sie, sodass Sie sich auf die Geschäftslogik konzentrieren können.

- **Geschwindigkeit:** Nutzt alle logischen Prozessoren und reduziert die Zeit zur ZIP‑Erstellung um bis zu 70 % bei typischen Arbeitslasten.  
- **Skalierbarkeit:** Verarbeitet Stapel von über 500 Dateien, ohne dass die CPU‑Zeit proportional ansteigt.  
- **Einfachheit:** Hoch‑level‑Methoden verbergen die Komplexität von `System.Threading.Tasks`.  
- **Flexibilität:** Unterstützt .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 und .NET 5–10, einschließlich .NET 6/7 für cloud‑native Dienste.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in C# und .NET‑Entwicklung.  
- Aspose.Zip für .NET installiert. Sie können es **[hier](https://releases.aspose.com/zip/net/)** herunterladen.  
- Eine temporäre oder Volllizenz (die temporäre Lizenz reicht für dieses Tutorial aus).  

## Namespaces importieren

Der Namespace `Aspose.Zip` enthält alle Typen, die Sie für die Arbeit mit ZIP‑Archiven benötigen.

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Zuerst importieren Sie die erforderlichen Namespaces in Ihre C#‑Datei, damit der Compiler weiß, wo die Klassen zu finden sind, die Sie verwenden werden.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Schritt 1: Dokumentverzeichnis einrichten

Definieren Sie den Ordner, der die zu komprimierenden Dateien enthält. Dieser Pfad wird in der Variable `dataDir` gespeichert, die Sie auf einen beliebigen Ort auf dem Datenträger verweisen können.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Komprimierungsprozess initialisieren

Öffnen Sie eine neue ZIP‑Datei zum Schreiben. Die `using`‑Anweisung stellt sicher, dass der Dateistream nach dem Vorgang ordnungsgemäß freigegeben wird, wodurch Dateihandle‑Lecks vermieden werden.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Schritt 3: Dateien parallel lesen und komprimieren

`Parallel.ForEach` führt eine foreach‑Schleife aus, bei der die Iterationen gleichzeitig auf mehreren Threads laufen können.  

Öffnen Sie jede Quelldatei, die Sie dem Archiv hinzufügen möchten. In diesem Beispiel arbeiten wir mit zwei klassischen Texten, aber Sie können **add files to zip** für beliebig viele Dokumente verwenden. Die `Parallel.ForEach`‑Schleife verteilt die Arbeit automatisch auf die Threads.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

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

Die Klasse `Archive` ist das Top‑Level‑Objekt von Aspose.Zip, das den ZIP‑Container repräsentiert, den Sie erstellen.  

`CreateEntry` erzeugt einen neuen Eintrag im ZIP‑Archiv für eine angegebene Datei. Jeder Aufruf von `CreateEntry` fügt dem Archiv einen neuen Dateieintrag hinzu.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Schritt 5: Parallelitätskriterium festlegen

`ParallelOptions` ist ein .NET‑Typ, der steuert, wie parallele Schleifen ausgeführt werden.  

Konfigurieren Sie die Kompression, um parallel zu laufen, indem Sie `ParallelOptions` festlegen. Das Flag `ParallelCompressInMemory` weist Aspose.Zip an, stets parallele Verarbeitung zu verwenden, während `MaxDegreeOfParallelism` Ihnen ermöglicht, die Anzahl gleichzeitiger Threads zu begrenzen.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Schritt 6: Komprimiertes Archiv speichern

Abschließend schreiben Sie das Archiv mit den gewünschten Optionen auf die Festplatte, einschließlich Kodierung, Kommentar und den zuvor definierten Parallel‑Einstellungen. Die Methode `Save` finalisiert die ZIP‑Datei.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro Tipp:** Wenn Sie sehr große Dateien komprimieren, sollten Sie `ParallelOptions.MaxDegreeOfParallelism` auf einen Wert unterhalb der Anzahl logischer Prozessoren setzen. Dies hilft, Ihren Server unter Last reaktionsfähig zu halten.

### Häufige Anwendungsfälle

- **Batch‑Reporting:** Erstellen Sie ein ZIP‑Paket mit täglichen CSV‑Berichten für nachgelagerte Systeme.  
- **Dokumentenarchivierung:** Speichern Sie große Sammlungen von PDFs, Bildern oder Protokollen in einem einzigen Archiv für die Sicherung.  
- **Datenexport‑APIs:** Geben Sie eine ZIP‑Datei zurück, die mehrere Daten­dateien enthält, an einen Client in einer einzigen HTTP‑Antwort.  

## Häufige Probleme & Tipps

- **Speicherbelastung bei riesigen Dateien:** Laden Sie nicht die gesamte Datei in den Speicher, sondern streamen Sie die Datei in Teilen oder verwenden Sie den Modus `ParallelCompressInMemory` selektiv.  
- **Thread‑Sicherheit:** Die Aspose.Zip‑API ist für den Parallelmodus thread‑sicher, vermeiden Sie jedoch, den gleichen `FileStream` außerhalb der Bibliothek zu ändern, während die Kompression läuft.  
- **Performance‑Optimierung:** Experimentieren Sie mit `ParallelOptions.MaxDegreeOfParallelism`, wenn Sie die CPU‑Auslastung auf gemeinsam genutzten Servern begrenzen müssen.  

## Häufig gestellte Fragen

**F: Kann ich Aspose.Zip für .NET zusammen mit anderen Kompressionsbibliotheken verwenden?**  
A: Ja, Aspose.Zip kann neben anderen .NET‑Bibliotheken koexistieren; achten Sie nur darauf, ihre Namespaces eindeutig zu halten.

**F: Ist eine temporäre Lizenz für Testzwecke verfügbar?**  
A: Ja, Sie können eine temporäre Lizenz zum Testen **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

**F: Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?**  
A: Besuchen Sie das **[Aspose.Zip‑Forum](https://forum.aspose.com/c/zip/37)** für Community‑Support und Diskussionen.

**F: Wo finde ich weitere Code‑Beispiele und detaillierte API‑Dokumentation?**  
A: Durchstöbern Sie die **[Aspose.Zip‑Dokumentation](https://reference.aspose.com/zip/net/)** für umfassende Beispiele.

**F: Wie kaufe ich eine Volllizenz für Aspose.Zip?**  
A: Sie können Aspose.Zip für .NET **[hier](https://purchase.aspose.com/buy)** erwerben.

**Zuletzt aktualisiert:** 2026-06-09  
**Getestet mit:** Aspose.Zip 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [zip multiple files c# – Mühelose Kompression mit Aspose.Zip für .NET](/zip/net/file-compression/compress-multiple-files/)
- [Wie man ein ZIP‑Archiv erstellt und Dateien zu einem ZIP mit Aspose.Zip für .NET hinzufügt](/zip/net/file-compression/compress-single-file/)
- [Mehrere Dateien mit Verschlüsselung in Aspose.Zip .NET komprimieren](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}