---
date: 2026-02-05
description: Erfahren Sie, wie Sie mehrere Dateien in C# zippen und ein ZIP‑Archiv
  in .NET mit Aspose.Zip erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt das
  Komprimieren von Dateien mit FileInfo in ASP.NET‑Projekten.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man mehrere Dateien in C# mit Aspose.Zip für .NET zippt
url: /de/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man mehrere Dateien in C# mit Aspose.Zip für .NET zippt

## Einführung

Wenn Sie **mehrere Dateien in C#** programmgesteuert zippen müssen, bietet Aspose.Zip für .NET eine saubere, hochleistungsfähige API, die in jeder .NET‑Anwendung (einschließlich ASP.NET) funktioniert. In diesem Tutorial führen wir Sie durch das Komprimieren von Dateien mit der `FileInfo`‑Klasse, zeigen Ihnen, wie Sie **Dateien zum Zip‑Archiv hinzufügen**, und erklären, warum dieser Ansatz ideal für moderne .NET‑Projekte ist. Los geht’s!

## Schnellantworten
- **Was ist der einfachste Weg, ein Zip‑Archiv zu erstellen?** Verwenden Sie die `Archive`‑Klasse von Aspose.Zip zusammen mit `FileInfo`‑Objekten.  
- **Kann ich mehrere Dateien auf einmal hinzufügen?** Ja – erstellen Sie einfach für jede Datei ein `FileInfo` und rufen Sie `CreateEntry` auf.  
- **Benötige ich eine spezielle Lizenz für ASP.NET?** Für den Produktionseinsatz ist eine kommerzielle Aspose.Zip‑Lizenz erforderlich; eine kostenlose Testversion reicht für Evaluierungen.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ist die API thread‑sicher?** Ja, solange jeder Thread mit seiner eigenen `Archive`‑Instanz arbeitet.  
- **Wie zippe ich Dateien in C# ohne sie vollständig in den Speicher zu laden?** Verwenden Sie `FileInfo`‑Objekte – sie streamen die Daten direkt.  

## Wie man mehrere Dateien in C# zippt
Ein Zip‑Archiv bündelt eine oder mehrere Dateien in einem einzigen, komprimierten Container. Das reduziert den Speicherplatzbedarf, beschleunigt Netzwerkübertragungen und vereinfacht die Verteilung. Egal, ob Sie Protokolle bereitstellen, Berichte exportieren oder Assets für einen Kunden paketieren – das programmgesteuerte **Zippen von Dateien in C#** ist eine wertvolle Fähigkeit für jeden .NET‑Entwickler.

## Warum Aspose.Zip zum Hinzufügen von Dateien zum Zip‑Archiv verwenden?
- **Keine externen Abhängigkeiten** – reine .NET‑Implementierung.  
- **Vollständige Kontrolle über Komprimierungsgrad und Kodierung** (ASCII, UTF‑8 usw.).  
- **Unterstützt große Dateien** (> 4 GB) und Passwortschutz.  
- **Konsistente API über .NET Framework, .NET Core und .NET 5+ hinweg**.

## Voraussetzungen

Bevor wir zum Code kommen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Zip für .NET** installiert. Laden Sie das neueste Paket von der [Aspose.Zip‑Download‑Seite](https://releases.aspose.com/zip/net/) herunter.  
2. Einen Ordner auf Ihrem Rechner, der die zu komprimierenden Dateien enthält (z. B. `alice29.txt` und `fields.c`).  

## Namespaces importieren

Fügen Sie in jeder C#‑Datei, in der Sie mit Zip‑Archiven arbeiten, die folgenden `using`‑Anweisungen hinzu:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Diese Namespaces geben Ihnen Zugriff auf die `Archive`‑Klasse, Speicheroptionen und die Standard‑I/O‑Hilfsmittel.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ihr Dokumentenverzeichnis festlegen

Definieren Sie zuerst den Ordner, der die Quelldateien enthält. Ersetzen Sie den Platzhalter durch den absoluten oder relativen Pfad auf Ihrem System:

```csharp
string dataDir = "Your Document Directory";
```

> **Profi‑Tipp:** Verwenden Sie `Path.Combine`, um Pfade plattformübergreifend zu erstellen.

### Schritt 2: Eine Zip‑Datei zum Schreiben öffnen

Erzeugen Sie einen `FileStream`, der auf die Ausgabedatei verweist. Der Stream wird im **Create**‑Modus geöffnet, wodurch eine eventuell vorhandene Datei gleichen Namens überschrieben wird:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Schritt 3: `FileInfo`‑Objekte für jede Quelldatei vorbereiten

`FileInfo` gibt Aspose.Zip direkten Zugriff auf die physischen Dateien auf dem Datenträger. Erstellen Sie für jede zu komprimierende Datei eine Instanz:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Warum `FileInfo` verwenden?** Es verhindert das Laden der gesamten Datei in den Speicher, was besonders bei großen Dateien hilfreich ist.

### Schritt 4: Das Archiv erstellen und Einträge hinzufügen

Instanziieren Sie ein `Archive`‑Objekt und rufen Sie `CreateEntry` für jedes `FileInfo`‑Objekt auf. Das erste Argument ist der Name, den die Datei im Zip‑Archiv erhalten soll, das zweite Argument ist das Quell‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Schritt 5: Das Zip‑Archiv mit gewünschter Kodierung speichern

Speichern Sie schließlich das Archiv in dem zuvor geöffneten `FileStream`. Hier verwenden wir ASCII‑Kodierung für die Eintragsnamen, Sie können jedoch zu UTF‑8 wechseln, wenn Ihre Dateinamen Nicht‑ASCII‑Zeichen enthalten:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Wenn die `using`‑Blöcke verlassen werden, schließen sich die Streams automatisch und die Zip‑Datei ist einsatzbereit.

## Häufige Probleme & Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Leere Zip‑Datei** | `FileInfo` verweist auf einen nicht existierenden Pfad | Überprüfen Sie `dataDir` und die Dateinamen; verwenden Sie `File.Exists`, um vor dem Erstellen von Einträgen zu prüfen. |
| **Falsche Dateinamen‑Kodierung** | Standard‑Kodierung wird bei Nicht‑ASCII‑Namen verwendet | Setzen Sie `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException bei großen Dateien** | Die gesamte Datei wird in den Speicher geladen | `FileInfo` streamt die Datei; stellen Sie sicher, dass Sie die Datei nicht an anderer Stelle in ein Byte‑Array einlesen. |
| **Zugriff verweigert** | Anwendung hat keine Schreibberechtigung für das Ausgabeverzeichnis | Führen Sie die Anwendung mit entsprechenden Rechten aus oder wählen Sie ein beschreibbares Verzeichnis. |

## Häufig gestellte Fragen

**F: Kann ich dem Zip‑Archiv einen Passwortschutz hinzufügen?**  
A: Ja. Nachdem Sie das `Archive` erstellt haben, setzen Sie `archive.Password = "yourPassword"` bevor Sie `Save` aufrufen.

**F: Ist es möglich, ein bestehendes Zip‑Archiv zu aktualisieren?**  
A: Aspose.Zip unterstützt das Öffnen eines bestehenden Archivs mit `Archive.Open` und das anschließende Hinzufügen neuer Einträge.

**F: Wie komprimiere ich Dateien in einem ASP.NET MVC‑Controller?**  
A: Der gleiche Code funktioniert; stellen Sie lediglich sicher, dass der Ausgabestream als `FileResult` an den Client zurückgesendet wird.

**F: Unterstützt Aspose.Zip Verschlüsselungsalgorithmen?**  
A: Es unterstützt das standardmäßige ZipCrypto sowie AES‑256‑Verschlüsselung.

**F: Was, wenn ich einen Ordner rekursiv komprimieren muss?**  
A: Durchlaufen Sie `Directory.GetFiles` (und Unterordner) und erstellen Sie für jede Datei ein `FileInfo`, das Sie dann dem Archiv hinzufügen.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Fazit

Sie wissen jetzt, **wie man mehrere Dateien in C# mit Aspose.Zip für .NET zippt**, wie man **Dateien zum Zip‑Archiv hinzufügt**, und warum diese Methode ideal für ASP.NET und andere .NET‑Anwendungen ist. Experimentieren Sie mit verschiedenen Komprimierungsgraden, Kodierungen und Verschlüsselungsoptionen, um das Archiv exakt an Ihre Bedürfnisse anzupassen. Viel Spaß beim Komprimieren!

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}