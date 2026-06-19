---
date: 2026-06-19
description: Erfahren Sie, wie Sie Tar-Dateien komprimieren, Targz-Archive erstellen
  und passwortgeschützte Zip-Dateien mit Aspose.Zip für .NET extrahieren – und dabei
  die Speichereffizienz und Sicherheit steigern.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Archivextraktion und Formate
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man Tar-Dateien mit Aspose.Zip für .NET komprimiert
url: /de/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Tar-Dateien mit Aspose.Zip für .NET komprimiert

## Einführung

In diesem Leitfaden entdecken Sie **wie man Tar komprimiert** Dateien mit Aspose.Zip für .NET, lernen, TarGz-Archive zu erstellen, und sehen, wie Sie passwortgeschützte Zip-Archive extrahieren. Effizientes Archivhandling ist eine Kernkompetenz für moderne .NET‑Entwickler — ob Sie einen Backup‑Dienst, einen Cloud‑Storage‑Client oder eine Datenverarbeitungspipeline bauen, das Beherrschen dieser Formate reduziert Speicherkosten, beschleunigt Übertragungen und schützt sensible Daten.

## Schnelle Antworten
- **Was ist TarBz2?** Ein komprimiertes Archiv, das die TAR‑Paketierung mit BZIP2‑Kompression für hohe Kompressionsraten kombiniert.  
- **Warum Aspose.Zip für .NET wählen?** Es bietet eine einheitliche, fluente API zum Erstellen und Extrahieren vieler Archivformate ohne externe Abhängigkeiten.  
- **Kann ich ein TarGz‑Archiv erstellen?** Ja – Aspose.Zip unterstützt TarGz, TarLz, TarXz, TarZ und mehr.  
- **Wie extrahiere ich ein passwortgeschütztes Zip‑Archiv?** Verwenden Sie die `Password`‑Eigenschaft des `ArchiveEntry`‑Objekts beim Extrahieren.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich; eine kostenlose Testversion steht für die Evaluierung zur Verfügung.

## Was ist Tar-Kompression?
Tar (Tape Archive) ist ein Containerformat, das mehrere Dateien und Verzeichnisse zu einem einzigen Stream bündelt, jedoch ohne Kompression. Wenn Sie einen Kompressionsalgorithmus wie BZIP2, GZip, LZMA oder XZ anwenden, entsteht ein **tar‑basiertes Archiv** wie `.tar.bz2`, `.tar.gz`, `.tar.lz` usw. Diese Formate werden breit unterstützt unter Linux, macOS und Windows und eignen sich ideal für plattformübergreifenden Datenaustausch.

## Warum Aspose.Zip für .NET verwenden, um diese Formate zu verarbeiten?
Aspose.Zip bietet eine **einheitliche, abhangkeitsfreie API**, die über 50 Archiv‑ und Kompressionsformate unterstützt, darunter TarBz2, TarGz, TarLz, TarXz und TarZ. Es läuft auf Windows, Linux und macOS, und seine stream‑basierte Architektur hält den Speicherverbrauch unter 10 MB selbst bei Archiven von mehreren hundert Megabyte. Passwortschutz ist integriert und ermöglicht die Verschlüsselung pro Eintrag ohne zusätzliche Bibliotheken.

## Voraussetzungen
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, oder .NET 5–10.  
- Aspose.Zip für .NET NuGet‑Paket installiert (`Install-Package Aspose.Zip`).  
- Grundlegende Kenntnisse von C# Datei‑I/O und dem .NET‑Projektsystem.

## Schritt‑für‑Schritt‑Anleitung

### Wie man Tar-Dateien komprimiert – Direkte Antwort
`Archive` repräsentiert eine Archivdatei und stellt Methoden zum Hinzufügen von Einträgen und zum Speichern bereit.  
Erstellen Sie eine `Archive`‑Instanz, fügen Sie die gewünschten Dateien hinzu, setzen Sie `CompressionType.BZip2` und rufen Sie `Save` mit `ArchiveFormat.TarBz2` auf. Die Bibliothek schreibt den TAR‑Container und komprimiert ihn in einem einzigen Streaming‑Durchlauf, sodass das gesamte Archiv nie vollständig in den Speicher geladen wird.

### Schritt 1: Wählen Sie das benötigte Archivformat
Entscheiden Sie, welches tar‑basierte Format am besten zu Ihrem Kompressions‑Geschwindigkeits‑Abwägungs‑Verhältnis passt:

- **TarBz2** – Höchstes Kompressionsverhältnis (≈30 % kleiner als TarGz), aber langsamer.  
- **TarGz** – Gute Balance zwischen Geschwindigkeit und Größe; ideal für die meisten Cloud‑Speicher‑Szenarien.  
- **TarLz / TarXz** – Sehr hohe Kompression bei moderater Geschwindigkeit, nützlich für Archivspeicherung.  
- **TarZ** – Legacy‑Format für Kompatibilität mit älteren Unix‑Werkzeugen.

### Schritt 2: Erstellen Sie eine neue `Archive`‑Instanz
`Archive` ist das oberste Objekt, das eine einzelne Archivdatei im Speicher repräsentiert.  

Die `Archive`‑Klasse verwaltet den Pack‑ und Kompressions‑Workflow und stellt Methoden zum Hinzufügen von Einträgen und zum Schreiben der finalen Datei bereit.

### Schritt 3: Dateien und Ordner hinzufügen
Sie können einen gesamten Verzeichnisbaum mit `AddAll` oder einzelne Dateien mit `AddFile` hinzufügen. Das Beibehalten der ursprünglichen Ordnerhierarchie ist so einfach wie das Übergeben des Basisverzeichnispfads.

### Schritt 4: Gewünschten Kompressionstyp festlegen
`CompressionType` enumeriert die unterstützten Algorithmen.  

`CompressionType` definiert den Algorithmus (BZip2, GZip, LZMA, XZ usw.), der beim Speichern auf den TAR‑Stream angewendet wird.

### Schritt 5: Archiv speichern
`ArchiveFormat` ist ein Enum‑Satz (z. B. `TarBz2`, `TarGz`), der dem Writer mitteilt, welchen Container und welche Kompression verwendet werden sollen.  

Durch Aufruf von `Save` wird das Archiv mit dem ausgewählten Format auf die Festplatte geschrieben.

### Schritt 6: Archive mit Passwörtern extrahieren
`ArchiveEntry` repräsentiert einen einzelnen Datei‑ oder Verzeichniseintrag innerhalb eines Archivs.  

Um ein passwortgeschütztes Zip zu extrahieren, öffnen Sie das Archiv, lokalisieren jeden `ArchiveEntry`, setzen dessen `Password`‑Eigenschaft und rufen `Extract` auf. Dieses Modell ermöglicht das Schützen einzelner Dateien innerhalb eines einzigen Zip‑Archivs.

### Schritt 7: Ergebnis überprüfen
Nach dem Extrahieren vergleichen Sie Dateigrößen und SHA‑256‑Prüfsummen, um zu bestätigen, dass die Archiv‑Rundreise die Datenintegrität bewahrt hat.

## Häufige Anwendungsfälle
- **Backup‑Werkzeuge** – Tägliche Backups als `.tar.bz2` speichern, um Speicherkosten um bis zu 30 % zu senken.  
- **Plattformübergreifender Datenaustausch** – Tar‑basierte Formate werden nativ von Linux-, macOS‑ und Windows‑Werkzeugen verstanden.  
- **Sichere Verteilung** – Passwörter sensiblen Einträgen zuweisen, um Compliance‑Anforderungen zu erfüllen, ohne zusätzliche Verschlüsselungswerkzeuge.

## Fehlersuche & Tipps
- **Große Archive** – Bevorzugen Sie die Streaming‑API (`Archive.CreateEntryFromFile`), um den Speicherverbrauch gering zu halten.  
- **Passwort‑Mismatches** – Das für jedes `ArchiveEntry` festgelegte Passwort muss exakt übereinstimmen; andernfalls wird `InvalidPasswordException` ausgelöst.  
- **Kompressionsstufe** – BZIP2 bietet keine benutzerdefinierten Stufen; benötigen Sie feinere Kontrolle, wechseln Sie zu LZMA (`CompressionType.LZMA`) oder XZ (`CompressionType.XZ`).  

## Häufig gestellte Fragen

**F: Wie erstelle ich ein TarGz‑Archiv?**  
A: Setzen Sie `CompressionType.GZip` und verwenden Sie `ArchiveFormat.TarGz` beim Aufruf von `Save`. Dadurch entsteht in einem Schritt eine `.tar.gz`‑Datei.

**F: Kann ich ein passwortgeschütztes Archiv extrahieren, ohne das Passwort zu kennen?**  
A: Nein. Jeder Eintrag muss mit dem korrekten Passwort versehen werden; andernfalls schlägt die Extraktion mit einer `InvalidPasswordException` fehl.

**F: Unterstützt Aspose.Zip das Extrahieren von Archiven mit unterschiedlichen Passwörtern pro Eintrag?**  
A: Ja. Weisen Sie jedem `ArchiveEntry` vor dem Aufruf von `Extract` ein individuelles Passwort zu.

**F: Welches Format liefert die beste Kompression?**  
A: TarBz2 liefert in der Regel die kleinste Größe, gefolgt von TarLz und TarXz. TarGz bietet eine schnellere, dennoch effektive Alternative.

**F: Gibt es ein Limit für die Anzahl der Dateien, die ich zu einem TAR‑Archiv hinzufügen kann?**  
A: Praktisch gibt es kein Limit, aber extrem große Archive (>10 GB) können von einer Aufteilung in mehrere Teile profitieren, um die Handhabung zu erleichtern.

## Archivextraktion und Format‑Tutorials
### [Dateikomprimierung zu TarBz2 mit Aspose.Zip für .NET](./compress-to-tar-bz2/)
Erfahren Sie, wie Sie Dateien im .NET‑Umfeld mit Aspose.Zip in das TarBz2‑Format komprimieren. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung für effiziente Dateikomprimierung.  
### [Komprimierung zu TarGz mit Aspose.Zip für .NET](./compress-to-tar-gz/)
Entdecken Sie effiziente Dateikomprimierung in .NET mit Aspose.Zip. Komprimieren Sie mühelos zu TarGz.  
### [Komprimierung zu TarLz mit Aspose.Zip für .NET](./compress-to-tar-lz/)
Komprimieren Sie Dateien in .NET mühelos mit Aspose.Zip. Lernen Sie, TarLz‑Archive Schritt für Schritt zu erstellen.  
### [Komprimierung zu TarXz mit Aspose.Zip für .NET](./compress-to-tar-xz/)
Erfahren Sie, wie Sie Dateien im .NET‑Umfeld mit Aspose.Zip in das TarXz‑Format komprimieren. Folgen Sie unserem Leitfaden für effiziente Speicherung und Übertragung.  
### [Komprimierung zu TarZ mit Aspose.Zip für .NET](./compress-to-tar-z/)
Entdecken Sie die schrittweise Komprimierung zu TarZ mit Aspose.Zip für .NET. Effiziente Dateiverarbeitung für Ihre .NET‑Projekte.  
### [Extrahieren von Archiveinträgen mit unterschiedlichen Passwörtern in Aspose.Zip für .NET](./extract-archive-different-passwords/)
Erfahren Sie, wie Sie Archiveinträge mit unterschiedlichen Passwörtern in Aspose.Zip für .NET extrahieren. Erhöhen Sie Sicherheit und Flexibilität in Ihren Anwendungen.

---

**Zuletzt aktualisiert:** 2026-06-19  
**Getestet mit:** Aspose.Zip für .NET 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Tar-Archiv erstellen und Dateien zu Tar hinzufügen mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Wie man Tar komprimiert und TarBz2 mit Aspose.Zip für .NET erstellt](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dateien zu Tar hinzufügen und TarXz-Archiv mit Aspose.Zip erstellen](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}