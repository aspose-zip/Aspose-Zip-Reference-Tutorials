---
date: 2026-02-28
description: Erfahren Sie, wie Sie einen Ordner zu einer ZIP-Datei hinzufügen und
  Dateien mit Aspose.Zip für .NET zur ZIP-Datei hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung
  zeigt, wie Sie Dateien mit FileInfo in ASP.NET‑Projekten komprimieren.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man einen Ordner zu einer ZIP-Datei mit Aspose.Zip für .NET hinzufügt –
  Dateien mit FileInfo komprimieren
url: /de/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Ordner zu Zip mit Aspose.Zip für .NET hinzufügt

## Einführung

Wenn Sie **programmgesteuert ein Zip‑Archiv erstellen** müssen, bietet Aspose.Zip für .NET eine saubere, hochleistungsfähige API, die in jeder .NET‑Anwendung (einschließlich ASP.NET) funktioniert. In diesem Tutorial führen wir Sie durch das Komprimieren von Dateien mit der `FileInfo`‑Klasse, zeigen Ihnen, wie Sie **Dateien zu Zip hinzufügen**, und erklären, warum dieser Ansatz ideal für moderne .NET‑Projekte ist. Außerdem behandeln wir, **wie man einen Ordner zu Zip hinzufügt**, sodass Sie ganze Verzeichnisse in einem Schritt bündeln können. Los geht’s!

## Schnelle Antworten
- **Was ist der einfachste Weg, ein Zip‑Archiv zu erstellen?** Verwenden Sie die `Archive`‑Klasse von Aspose.Zip zusammen mit `FileInfo`‑Objekten.  
- **Kann ich mehrere Dateien auf einmal hinzufügen?** Ja – erstellen Sie einfach ein `FileInfo`‑Objekt für jede Datei und rufen Sie `CreateEntry` auf.  
- **Benötige ich eine spezielle Lizenz für ASP.NET?** Für die Produktion ist eine kommerzielle Aspose.Zip‑Lizenz erforderlich; eine kostenlose Testversion reicht für Evaluierungen.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ist die API thread‑sicher?** Ja, solange jeder Thread mit seiner eigenen `Archive`‑Instanz arbeitet.

## Was ist ein Zip‑Archiv und warum ein solches erstellen?
Ein Zip‑Archiv bündelt eine oder mehrere Dateien in einem einzigen, komprimierten Container. Das reduziert den Speicherplatz, beschleunigt Netzwerkübertragungen und vereinfacht die Verteilung. Egal, ob Sie Protokolle bereitstellen, Berichte exportieren oder Assets für einen Kunden paketieren – das **programmgesteuerte Erstellen von Zip‑Archiven** ist eine wertvolle Fähigkeit für jeden .NET‑Entwickler.

## Warum Aspose.Zip zum Hinzufügen von Dateien zu Zip verwenden?
- **Keine externen Abhängigkeiten** – reine .NET‑Implementierung.  
- **Vollständige Kontrolle über Kompressionsgrad und Kodierung** (ASCII, UTF‑8 usw.).  
- **Unterstützt große Dateien** (> 4 GB) und Passwortschutz.  
- **Konsistente API über .NET Framework, .NET Core und .NET 5+ hinweg**.

## Voraussetzungen

Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Zip für .NET** installiert. Laden Sie das neueste Paket von der [Aspose.Zip‑Download‑Seite](https://releases.aspose.com/zip/net/) herunter.  
2. Ein Ordner auf Ihrem Rechner, der die zu komprimierenden Dateien enthält (z. B. `alice29.txt` und `fields.c`).  

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

### Schritt 1: Dokumentenverzeichnis einrichten

Definieren Sie zunächst den Ordner, der die Quelldateien enthält. Ersetzen Sie den Platzhalter durch den absoluten oder relativen Pfad auf Ihrem System:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro Tipp:** Verwenden Sie `Path.Combine`, um Pfade plattformübergreifend zu erstellen.

### Schritt 2: Zip‑Datei zum Schreiben öffnen

Erzeugen Sie einen `FileStream`, der auf die Ausgabedatei zeigt. Der Stream wird im **Create**‑Modus geöffnet, wodurch eine eventuell vorhandene Datei gleichen Namens überschrieben wird:

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

Instanziieren Sie ein `Archive`‑Objekt und rufen Sie `CreateEntry` für jedes `FileInfo`‑Objekt auf. Das erste Argument ist der Name, den die Datei im Zip‑Archiv erhalten soll, das zweite Argument ist das Quell‑`FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Schritt 5: Zip‑Archiv mit gewünschter Kodierung speichern

Speichern Sie schließlich das Archiv in dem zuvor geöffneten `FileStream`. Hier verwenden wir ASCII‑Kodierung für die Eintragsnamen, Sie können jedoch zu UTF‑8 wechseln, wenn Ihre Dateinamen Nicht‑ASCII‑Zeichen enthalten:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Wenn die `using`‑Blöcke beendet werden, schließen sich die Streams automatisch und die Zip‑Datei ist einsatzbereit.

## Wie man einen Ordner zu Zip mit Aspose.Zip hinzufügt

Wenn Sie **einen Ordner zu Zip hinzufügen** möchten, anstatt einzelne Dateien, ist der Vorgang unkompliziert:

1. **Den Ordner enumerieren** mit `DirectoryInfo.GetFiles` (und optional `GetDirectories` für Rekursion).  
2. **Für jede gefundene Datei ein `FileInfo` erstellen**.  
3. **`CreateEntry` aufrufen** mit einem relativen Pfad, der den Ordnernamen enthält, z. B. `"MyFolder/Report.pdf"`.

Da die API mit `FileInfo` arbeitet, müssen Sie nie ganze Dateien in den Speicher laden – das ist besonders bei großen Verzeichnissen sicher. Diese Technik funktioniert auch für **zip multiple files asp.net**‑Szenarien, bei denen Sie einen Berichtssatz on‑the‑fly erzeugen und als ein einziges Archiv bereitstellen müssen.

## Häufige Probleme & Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Leere Zip‑Datei** | `FileInfo` verweist auf einen nicht vorhandenen Pfad | `dataDir` und Dateinamen prüfen; `File.Exists` verwenden, bevor Einträge erstellt werden. |
| **Falsche Dateinamen‑Kodierung** | Standard‑Kodierung wird bei Nicht‑ASCII‑Namen verwendet | `Encoding = Encoding.UTF8` in `ArchiveSaveOptions` setzen. |
| **OutOfMemoryException bei großen Dateien** | Ganze Datei wird in den Speicher geladen | `FileInfo` streamt die Datei; sicherstellen, dass Sie die Datei nicht anderweitig in ein Byte‑Array einlesen. |
| **Zugriff verweigert** | Anwendung hat keine Schreibrechte für das Ausgabeverzeichnis | Anwendung mit entsprechenden Rechten ausführen oder ein beschreibbares Verzeichnis wählen. |

### Häufig gestellte Fragen

#### F1: Ist Aspose.Zip mit allen Dateitypen kompatibel?

A1: Aspose.Zip unterstützt eine Vielzahl von Dateitypen und bietet so vielseitige Komprimierungsmöglichkeiten.

#### F2: Kann ich Aspose.Zip für kommerzielle Projekte verwenden?

A2: Selbstverständlich! Besuchen Sie unsere [Kaufseite](https://purchase.aspose.com/buy), um sich über die Lizenzoptionen zu informieren.

#### F3: Wie erhalte ich Support für Aspose.Zip?

A3: Treten Sie unserer Community im [Aspose.Zip-Forum](https://forum.aspose.com/c/zip/37) bei, um Hilfe zu erhalten und sich mit anderen auszutauschen.

#### F4: Gibt es eine kostenlose Testversion?

A4: Ja, Sie können Ihre [kostenlose Testversion hier](https://releases.aspose.com/) herunterladen.

#### F5: Wie erhalte ich eine temporäre Lizenz für Aspose.Zip?

A5: Unter [diesem Link](https://purchase.aspose.com/temporary-license/) finden Sie Informationen zum Erhalt einer temporären Lizenz.

## Fazit

Sie wissen jetzt, **wie man einen Ordner zu Zip hinzufügt** und **wie man Zip‑Archive** mit Aspose.Zip für .NET erstellt, wie man **Dateien zu Zip hinzufügt** und warum diese Methode ideal für ASP.NET und andere .NET‑Anwendungen ist. Experimentieren Sie mit verschiedenen Kompressionsgraden, Kodierungen und Verschlüsselungsoptionen, um das Archiv exakt an Ihre Bedürfnisse anzupassen. Viel Spaß beim Komprimieren!

---

**Zuletzt aktualisiert:** 2026-02-28  
**Getestet mit:** Aspose.Zip für .NET 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}