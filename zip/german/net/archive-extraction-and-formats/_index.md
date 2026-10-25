---
date: 2026-10-25
description: Erfahren Sie, wie Sie das ZIP-Passwort extrahieren und den Kompressionsalgorithmus
  beim Komprimieren von TAR-Dateien mit Aspose.Zip für .NET festlegen, um die Speichereffizienz
  und Sicherheit zu erhöhen.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Archivextraktion und Formate
og_description: Erfahren Sie, wie Sie das ZIP-Passwort extrahieren und den Kompressionsalgorithmus
  beim Komprimieren von TAR-Dateien mit Aspose.Zip für .NET festlegen, um die Speichereffizienz
  und Sicherheit zu erhöhen.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: ZIP-Passwort extrahieren und TAR-Dateien mit Aspose.Zip komprimieren
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: ZIP-Passwort extrahieren und TAR-Dateien mit Aspose.Zip komprimieren
url: /de/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ZIP-Passwort extrahieren und TAR-Dateien mit Aspose.Zip komprimieren

## Einleitung

In diesem Leitfaden entdecken Sie **extract zip password**‑Techniken, lernen, wie Sie den Kompressionsalgorithmus beim Erstellen tar‑basierter Archive festlegen, und sehen, wie Sie TarGz, TarBz2 und andere Formate mit Aspose.Zip für .NET erstellen. Egal, ob Sie einen Backup‑Dienst, einen Cloud‑Storage‑Client oder eine Datenverarbeitungspipeline bauen, das Beherrschen dieser Vorgänge reduziert Speicherkosten, beschleunigt Übertragungen und sichert sensible Dateien.

## Schnelle Antworten
- **Was ist TarBz2?** Ein komprimiertes Archiv, das TAR‑Verpackung mit BZIP2‑Kompression kombiniert und hohe Kompressionsraten erzielt.  
- **Warum Aspose.Zip für .NET wählen?** Es unterstützt mehr als 50 Archiv‑ und Kompressionsformate, läuft unter Windows, Linux und macOS und hält den Speicherverbrauch bei Archiven von mehreren hundert Megabyte unter 10 MB.  
- **Kann ich ein TarGz‑Archiv erstellen?** Ja – Aspose.Zip bietet TarGz, TarLz, TarXz, TarZ und mehr.  
- **Wie extrahiere ich ein passwortgeschütztes ZIP‑Archiv?** Setzen Sie die `Password`‑Eigenschaft jedes `ArchiveEntry`, bevor Sie `Extract` aufrufen.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Für die Produktion ist eine kommerzielle Lizenz erforderlich; ein kostenloser Testzeitraum steht zur Evaluierung bereit.

## Was ist Tar-Kompression?

Tar‑Kompression kombiniert den TAR‑Container mit einem Kompressionsalgorithmus wie BZIP2, GZIP, LZMA oder XZ. Das Ergebnis ist eine einzelne Datei (z. B. `.tar.gz`, `.tar.bz2`), die unter Linux, macOS und Windows entpackt werden kann. Sie bewahrt die ursprüngliche Verzeichnisstruktur, ermöglicht zufälligen Zugriff beim Extrahieren und wird von Kommandozeilen‑Tools sowie Programmbibliotheken breit unterstützt, was sie ideal für plattformübergreifende Verteilung und Archivspeicherung macht.

## Warum Aspose.Zip für .NET verwenden, um diese Formate zu verarbeiten?

Aspose.Zip bietet eine einheitliche, abhängigkeitfreie API, die **50+** Archiv‑ und Kompressionsformate unterstützt, einschließlich aller gängigen tar‑basierten Typen. Seine Streaming‑Architektur verarbeitet Archive größer als 10 GB, während der RAM‑Verbrauch unter 10 MB bleibt, was sie ideal für Hochdurchsatz‑Server‑Workloads macht.

**Direkte Antwort:** Sie verwenden Aspose.Zip, weil es Ihnen ermöglicht, tar‑basierte Archive und passwortgeschützte ZIP‑Dateien mit einer einzigen flüssigen API zu erstellen, zu komprimieren und zu extrahieren, ohne externe Werkzeuge, und dabei Multi‑Gigabyte‑Archive in einem speichereffizienten Streaming‑Modus zu verarbeiten.

## Voraussetzungen
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 oder .NET 5–10.  
- Aspose.Zip für .NET NuGet‑Paket (`Install-Package Aspose.Zip`).  
- Grundlegende Kenntnisse in C#‑Datei‑I/O und dem .NET‑Projekt‑System.

## Schritt‑für‑Schritt‑Anleitung

### Wie man TAR-Dateien komprimiert – direkte Antwort
Erstellen Sie eine `Archive`‑Instanz, fügen Sie die zu bündelnden Dateien hinzu, setzen Sie `CompressionType.BZip2` (oder einen anderen Algorithmus) und rufen Sie `Save` mit `ArchiveFormat.TarBz2` auf. Die Bibliothek schreibt den TAR‑Container und komprimiert ihn in einem einzigen Streaming‑Durchlauf, sodass das gesamte Archiv nie vollständig in den Speicher geladen wird.

### Schritt 1: Wählen Sie das benötigte Archivformat
Entscheiden Sie, welches tar‑basierte Format am besten zu Ihrem Kompressions‑Geschwindigkeits‑Kompromiss passt:

- **TarBz2** – Höchstes Kompressionsverhältnis (≈30 % kleiner als TarGz), aber langsamer.  
- **TarGz** – Gutes Gleichgewicht zwischen Geschwindigkeit und Größe; ideal für die meisten Cloud‑Storage‑Szenarien.  
- **TarLz / TarXz** – Sehr hohe Kompression bei moderater Geschwindigkeit, nützlich für Archivspeicherung.  
- **TarZ** – Legacy‑Format für die Kompatibilität mit älteren Unix‑Tools.

### Schritt 2: Erstellen Sie eine neue `Archive`‑Instanz
`Archive` repräsentiert eine einzelne Archivdatei und bietet Methoden zum Hinzufügen von Einträgen und zum Speichern des Archivs.

Die Klasse `Archive` verwaltet den Pack‑ und Komprimierungs‑Workflow und stellt Methoden zum Hinzufügen von Einträgen und zum Schreiben der endgültigen Datei bereit.

### Schritt 3: Dateien und Ordner hinzufügen
Sie können einen gesamten Verzeichnisbaum mit `AddAll` hinzufügen oder einzelne Dateien mit `AddFile`.

`AddAll` fügt einen gesamten Verzeichnisbaum dem Archiv hinzu und bewahrt dessen Struktur.

`AddFile` fügt eine einzelne Datei dem Archiv hinzu. Das Bewahren der ursprünglichen Ordnerhierarchie ist so einfach wie das Übergeben des Basisverzeichnispfads.

### Schritt 4: Gewünschten Kompressionstyp festlegen
Der `CompressionType`‑Enum gibt den auf den TAR‑Stream angewendeten Kompressionsalgorithmus an.

`CompressionType` listet die unterstützten Algorithmen (BZip2, GZip, LZMA, XZ usw.) auf, die beim Speichern angewendet werden.

### Schritt 5: Archiv speichern
Der `ArchiveFormat`‑Enum wählt die Container‑ und Kompressionskombination für die Ausgabedatei.

Der Aufruf von `Save` schreibt das Archiv mit dem gewählten Format auf die Festplatte.

### Schritt 6: Archive mit Passwörtern extrahieren
`ArchiveEntry` repräsentiert einen einzelnen Datei‑ oder Verzeichniseintrag innerhalb eines Archivs.

Um ein passwortgeschütztes ZIP zu extrahieren, öffnen Sie das Archiv, finden jedes `ArchiveEntry`, weisen dessen `Password`‑Eigenschaft zu und rufen `Extract` auf. Die `Password`‑Eigenschaft legt das Entschlüsselungspasswort für einen ZIP‑Eintrag fest. Dieses Modell mit Passwort pro Eintrag ermöglicht es, einzelne Dateien innerhalb eines einzigen ZIP zu schützen.

### Schritt 7: Ergebnis überprüfen
Nach dem Extrahieren vergleichen Sie Dateigrößen und SHA‑256‑Prüfsummen, um zu bestätigen, dass der Rundlauf des Archivs die Datenintegrität bewahrt hat.

## Häufige Anwendungsfälle
- **Backup‑Utilities** – Speichern Sie tägliche Backups als `.tar.bz2`, um Speicherkosten um bis zu 30 % zu senken.  
- **Plattformübergreifender Datenaustausch** – Tar‑basierte Formate werden nativ von Linux-, macOS- und Windows‑Tools verstanden.  
- **Sichere Verteilung** – Weisen Sie sensiblen Einträgen Passwörter zu, um Compliance‑Anforderungen zu erfüllen, ohne zusätzliche Verschlüsselungs‑Tools.

## Fehlerbehebung & Tipps
- **Große Archive** – Verwenden Sie die Streaming‑API (`Archive.CreateEntryFromFile`), um den Speicherverbrauch niedrig zu halten.  
- **Passwort‑Mismatches** – Das für jedes `ArchiveEntry` festgelegte Passwort muss exakt übereinstimmen; andernfalls wird `InvalidPasswordException` ausgelöst.  
- **Kompressionsgrad** – BZIP2 bietet keine benutzerdefinierten Stufen; benötigen Sie feinere Kontrolle, wechseln Sie zu LZMA (`CompressionType.LZMA`) oder XZ (`CompressionType.XZ`).

## Häufig gestellte Fragen

**Q: Wie erstelle ich ein TarGz‑Archiv?**  
A: Setzen Sie `CompressionType.GZip` und verwenden Sie `ArchiveFormat.TarGz` beim Aufruf von `Save`. Dies erzeugt eine `.tar.gz`‑Datei in einem einzigen Schritt.

**Q: Kann ich ein passwortgeschütztes Archiv extrahieren, ohne das Passwort zu kennen?**  
A: Nein. Jeder Eintrag muss mit dem korrekten Passwort versehen werden; andernfalls schlägt das Extrahieren mit einer `InvalidPasswordException` fehl.

**Q: Unterstützt Aspose.Zip das Extrahieren von Archiven mit unterschiedlichen Passwörtern pro Eintrag?**  
A: Ja. Weisen Sie jedem `ArchiveEntry` vor dem Aufruf von `Extract` ein individuelles Passwort zu.

**Q: Welches Format liefert die beste Kompression?**  
A: TarBz2 ergibt in der Regel die kleinste Größe, gefolgt von TarLz und TarXz. TarGz bietet eine schnellere, aber immer noch effektive Alternative.

**Q: Gibt es ein Limit für die Anzahl der Dateien, die ich zu einem TAR‑Archiv hinzufügen kann?**  
A: Praktisch gibt es keins, aber extrem große Archive (>10 GB) können von einer Aufteilung in mehrere Teile profitieren, um die Handhabung zu erleichtern.

## Archive-Extraktion und Format‑Tutorials
### [Dateien komprimieren zu TarBz2 mit Aspose.Zip für .NET](./compress-to-tar-bz2/)
Erfahren Sie, wie Sie Dateien im .NET‑Umfeld mit Aspose.Zip in das TarBz2‑Format komprimieren. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung für effiziente Dateikompression.  
### [Komprimieren zu TarGz mit Aspose.Zip für .NET](./compress-to-tar-gz/)
Entdecken Sie effiziente Dateikompression in .NET mit Aspose.Zip. Komprimieren Sie mühelos zu TarGz.  
### [Komprimieren zu TarLz mit Aspose.Zip für .NET](./compress-to-tar-lz/)
Komprimieren Sie Dateien mühelos in .NET mit Aspose.Zip. Lernen Sie, TarLz‑Archive Schritt für Schritt zu erstellen.  
### [Komprimieren zu TarXz mit Aspose.Zip für .NET](./compress-to-tar-xz/)
Erfahren Sie, wie Sie Dateien im .NET‑Umfeld mit Aspose.Zip in das TarXz‑Format komprimieren. Folgen Sie unserer Anleitung für effiziente Speicherung und Übertragung.  
### [Komprimieren zu TarZ mit Aspose.Zip für .NET](./compress-to-tar-z/)
Entdecken Sie die Schritt‑für‑Schritt‑Kompression zu TarZ mit Aspose.Zip für .NET. Effiziente Dateiverarbeitung für Ihre .NET‑Projekte.  
### [Extrahieren von Archiveinträgen mit unterschiedlichen Passwörtern in Aspose.Zip für .NET](./extract-archive-different-passwords/)
Erfahren Sie, wie Sie Archiveinträge mit unterschiedlichen Passwörtern in Aspose.Zip für .NET extrahieren. Erhöhen Sie Sicherheit und Flexibilität in Ihren Anwendungen.

## Verwandte Tutorials

- [Tar-Archiv erstellen und Dateien zu TAR hinzufügen mit Aspose.Zip für .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Wie man TAR komprimiert und TarBz2 mit Aspose.Zip für .NET erstellt](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dateien zu TAR hinzufügen und TarXz-Archiv mit Aspose.Zip erstellen](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Zuletzt aktualisiert:** 2026-10-25  
**Getestet mit:** Aspose.Zip für .NET 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}