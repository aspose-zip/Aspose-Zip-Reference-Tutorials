---
date: 2026-07-18
description: Erfahren Sie, wie Sie einen Ordner zu ZIP hinzufügen und Dateien zu ZIP
  hinzufügen mit Aspose.Zip für .NET. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie
  Sie Dateien mit FileInfo in ASP.NET‑Projekten komprimieren.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Dateien mit FileInfo komprimieren
og_description: Ordner zu ZIP hinzufügen mit Aspose.Zip für .NET. Erfahren Sie, wie
  Sie ein ZIP‑Archiv erstellen, Dateien zu ZIP hinzufügen und Ordner effizient in
  ASP.NET komprimieren.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Ordner zu ZIP hinzufügen – Dateien mit Aspose.Zip für .NET komprimieren
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Ordner zu ZIP hinzufügen mit Aspose.Zip für .NET – Dateien mit FileInfo komprimieren
url: /de/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ordner zu Zip hinzufügen mit Aspose.Zip für .NET

## Einführung

Wenn Sie **Ordner zu Zip hinzufügen** programmgesteuert benötigen, bietet Aspose.Zip für .NET eine saubere, leistungsstarke API, die in jeder .NET‑Anwendung (einschließlich ASP.NET) funktioniert. In diesem Tutorial führen wir Sie durch das Komprimieren von Dateien mit der `FileInfo`‑Klasse, zeigen Ihnen, wie Sie **Dateien zu Zip hinzufügen**, und erklären, warum dieser Ansatz für moderne .NET‑Projekte ideal ist. Wir behandeln außerdem die genauen Schritte zum **Ordner zu Zip hinzufügen**, damit Sie ganze Verzeichnisse in einem einzigen Vorgang bündeln können. Lassen Sie uns beginnen!

## Schnelle Antworten
- **Was ist der einfachste Weg, ein Zip-Archiv zu erstellen?** Verwenden Sie die `Archive`‑Klasse von Aspose.Zip zusammen mit `FileInfo`‑Objekten.  
- **Kann ich mehrere Dateien gleichzeitig hinzufügen?** Ja – erstellen Sie einfach für jede Datei ein `FileInfo` und rufen Sie `CreateEntry` auf.  
- **Benötige ich eine spezielle Lizenz für ASP.NET?** Für den Produktionseinsatz ist eine kommerzielle Aspose.Zip‑Lizenz erforderlich; eine kostenlose Testversion funktioniert für Evaluierungszwecke.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 und .NET 5–10.  
- **Ist die API thread‑sicher?** Ja, solange jeder Thread mit seiner eigenen `Archive`‑Instanz arbeitet.

## Was ist ein Zip-Archiv und warum eines erstellen?

Ein Zip‑Archiv bündelt eine oder mehrere Dateien in einem einzigen, komprimierten Container. Das reduziert den Speicherplatz, beschleunigt Netzwerkübertragungen und vereinfacht die Verteilung. Egal, ob Sie Protokolle bereitstellen, Berichte exportieren oder Assets für einen Kunden paketieren – das programmgesteuerte **Erstellen von Zip‑Archiven** zu kennen, ist eine wertvolle Fähigkeit für jeden .NET‑Entwickler.

## Warum Aspose.Zip zum Hinzufügen von Dateien zu Zip verwenden?

Aspose.Zip bietet eine reine .NET‑Lösung, die externe Abhängigkeiten eliminiert und Entwicklern eine feinkörnige Kontrolle über Kompression, Kodierung und Sicherheit gibt. Es unterstützt große Dateien, Passwortschutz und funktioniert konsistent über alle unterstützten .NET‑Versionen hinweg, was es zu einer zuverlässigen Wahl für sowohl Legacy‑ als auch moderne Anwendungen macht.  

- **Keine externen Abhängigkeiten** – reine .NET‑Implementierung.  
- **Vollständige Kontrolle über Kompressionsgrad und Kodierung** (ASCII, UTF‑8 usw.).  
- **Unterstützt Dateien größer als 4 GB** und Passwortschutz.  
- **Konsistente API über mehr als 50 .NET‑Versionen** – von .NET Framework 2.0 bis .NET 10.  

## Voraussetzungen

Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Zip für .NET** installiert. Laden Sie das neueste Paket von der [Aspose.Zip‑Download‑Seite](https://releases.aspose.com/zip/net/) herunter.  
2. Einen Ordner auf Ihrem Rechner, der die zu komprimierenden Dateien enthält (z. B. `alice29.txt` und `fields.c`).  

## Namespaces importieren

In jeder C#‑Datei, in der Sie mit Zip‑Archiven arbeiten, fügen Sie die folgenden `using`‑Anweisungen hinzu:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Diese Namespaces geben Ihnen Zugriff auf die `Archive`‑Klasse, Speicheroptionen und die Standard‑I/O‑Hilfsmittel.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dokumentverzeichnis einrichten

Zuerst definieren Sie den Ordner, der die Quelldateien enthält. Ersetzen Sie den Platzhalter durch den absoluten oder relativen Pfad auf Ihrem System:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro‑Tipp:** Verwenden Sie `Path.Combine`, um Pfade plattformübergreifend zu erstellen.

### Schritt 2: Zip-Datei zum Schreiben öffnen

Erstellen Sie einen `FileStream`, der auf die Ausgabedatei des Zip‑Archivs zeigt. Der Stream wird im **Create**‑Modus geöffnet, wodurch jede bereits vorhandene Datei mit demselben Namen überschrieben wird:

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

### Schritt 4: Archiv erstellen und Einträge hinzufügen

Die `Archive`‑Klasse ist das Kernobjekt von Aspose.Zip, das einen Zip‑Container im Speicher repräsentiert. Instanziieren Sie ein `Archive`‑Objekt und rufen Sie anschließend `CreateEntry` für jedes `FileInfo` auf. Das erste Argument ist der Name, den die Datei im Zip‑Archiv erhalten soll, das zweite Argument ist das Quell‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Die Methode `CreateEntry` fügt dem Archiv einen neuen Dateieintrag hinzu, verknüpft den Eintragsnamen mit dem Quell‑`FileInfo`, sodass die Daten beim Speichern des Archivs direkt von der Festplatte gestreamt werden.

### Schritt 5: Zip-Archiv mit gewünschter Kodierung speichern

Abschließend speichern Sie das Archiv in den zuvor geöffneten `FileStream`. Hier verwenden wir ASCII‑Kodierung für die Eintragsnamen, Sie können jedoch zu UTF‑8 wechseln, wenn Ihre Dateinamen Nicht‑ASCII‑Zeichen enthalten:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Wenn die `using`‑Blöcke beendet werden, schließen sich die Streams automatisch und die Zip‑Datei ist einsatzbereit.

## Wie man Ordner zu Zip mit Aspose.Zip hinzufügt?

Laden Sie das Zielverzeichnis, enumerieren Sie jede Datei und fügen Sie jede mit einem relativen Pfad hinzu, der den Ordnernamen enthält. Dieser Ansatz ermöglicht es Ihnen, **Ordner zu Zip hinzufügen**, ohne jede Datei manuell auflisten zu müssen. Durch das Beibehalten der Ordnerhierarchie in den Eintragsnamen kann das resultierende Archiv mit der ursprünglichen Verzeichnisstruktur extrahiert werden, was für viele Bereitstellungsszenarien entscheidend ist.

1. Verwenden Sie `DirectoryInfo`, um auf den zu komprimierenden Ordner zu zeigen.  
2. Rufen Sie `GetFiles("*", SearchOption.AllDirectories)` auf, um alle Dateien rekursiv abzurufen.  
3. Für jede Datei erstellen Sie ein `FileInfo` und rufen `CreateEntry` mit einem Pfad wie `"MyFolder/Report.pdf"` auf.

Da die API mit `FileInfo` arbeitet, wird jede Datei direkt von der Festplatte gestreamt, wodurch der Speicherverbrauch auch bei Ordnern mit mehreren hundert Megabyte niedrig bleibt.

## Häufige Probleme & Lösungen

| Problem | Ursache | Lösung |
|-------|-------|-----|
| **Leere Zip‑Datei** | `FileInfo` verweist auf einen nicht existierenden Pfad | Überprüfen Sie `dataDir` und Dateinamen; verwenden Sie `File.Exists`, um vor dem Erstellen von Einträgen zu prüfen. |
| **Falsche Dateinamen‑Kodierung** | Verwendung der Standardkodierung bei Nicht‑ASCII‑Namen | Setzen Sie `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException bei großen Dateien** | Laden der gesamten Datei in den Speicher | `FileInfo` streamt die Datei; stellen Sie sicher, dass Sie die Datei nicht an anderer Stelle in ein Byte‑Array einlesen. |
| **Zugriff verweigert** | Anwendung hat keine Schreibberechtigung für den Ausgabordner | Führen Sie die Anwendung mit entsprechenden Rechten aus oder wählen Sie ein beschreibbares Verzeichnis. |

## Häufig gestellte Fragen

**Q: Kann ich einen gesamten Ordner in einem einzigen Aufruf zu einem Zip‑Archiv hinzufügen?**  
A: Es gibt keine Ein‑Aufruf‑Methode, aber das Auflisten von Dateien mit `DirectoryInfo` und das Hinzufügen jeder Datei über `CreateEntry` erzielt das gleiche Ergebnis effizient.

**Q: Unterstützt Aspose.Zip Passwortschutz?**  
A: Ja, Sie können ein Passwort am `Archive`‑Objekt festlegen, bevor Sie es speichern, um das gesamte Archiv zu verschlüsseln.

**Q: Wie groß kann eine Zip‑Datei sein, die Aspose.Zip verarbeiten kann?**  
A: Die Bibliothek verarbeitet Dateien größer als 4 GB und kann Archive von über 10 GB erstellen, ohne das gesamte Archiv in den Speicher zu laden.

**Q: Ist die API mit .NET 6 und .NET 8 kompatibel?**  
A: Absolut. Aspose.Zip unterstützt .NET 5 bis .NET 10 und deckt damit alle aktuellen LTS‑Versionen ab.

**Q: Welche Kompressionsstufen stehen zur Verfügung?**  
A: Sie können `CompressionLevel.NoCompression`, `Fast`, `Normal` oder `Maximum` wählen, um Geschwindigkeit und Größe auszubalancieren.

## Weitere Ressourcen

- Laden Sie das neueste Aspose.Zip‑Paket herunter: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Kaufen Sie eine Lizenz für den Produktionseinsatz: [purchase page](https://purchase.aspose.com/buy)  
- Holen Sie sich Hilfe von der Community: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Testen Sie Aspose.Zip kostenlos: [free trial here](https://releases.aspose.com/)  
- Erhalten Sie eine temporäre Lizenz für Evaluierungszwecke: [this link](https://purchase.aspose.com/temporary-license/)

## Fazit

Sie wissen jetzt, **wie man Ordner zu Zip hinzufügt** und **wie man Zip‑Archive** mit Aspose.Zip für .NET erstellt, wie man **Dateien zu Zip hinzufügt** und warum diese Methode für ASP.NET und andere .NET‑Anwendungen ideal ist. Experimentieren Sie mit verschiedenen Kompressionsstufen, Kodierungen und Verschlüsselungsoptionen, um das Archiv exakt an Ihre Anforderungen anzupassen. Viel Spaß beim Komprimieren!

---

**Zuletzt aktualisiert:** 2026-07-18  
**Getestet mit:** Aspose.Zip für .NET 24.12 (neueste)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Ordner mit Aspose.Zip für .NET zippt](/zip/net/directory-and-folder-compression/compress-directory/)
- [Mehrere Dateien zippen c# – Mühelose Kompression mit Aspose.Zip für .NET](/zip/net/file-compression/compress-multiple-files/)
- [Zip‑Archiv erstellen .NET – Dateikompression mit Aspose.Zip](/zip/net/file-compression/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}