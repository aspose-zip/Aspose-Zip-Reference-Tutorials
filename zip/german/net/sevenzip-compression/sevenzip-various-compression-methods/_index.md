---
date: 2026-06-29
description: Erfahren Sie, wie Sie einen Ordner mit Aspose.Zip für .NET zu 7z komprimieren,
  wobei verschiedene 7z‑Komprimierungsmethoden wie LZMA2, BZip2 und Store behandelt
  werden. Ideal zum programmgesteuerten Erstellen von 7z‑Archiven.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip mit verschiedenen Komprimierungsmethoden
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man einen Ordner zu 7z komprimiert – Aspose.Zip für .NET Tutorial
url: /de/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Ordner zu 7z komprimiert – Aspose.Zip für .NET Tutorial

## Einführung

Wenn Sie **compress folder to 7z** Archive programmgesteuert in einer .NET-Anwendung erstellen müssen, sind Sie hier genau richtig. Aspose.Zip für .NET ermöglicht es, Seven Zip-Archive mit jedem der unterstützten Komprimierungsalgorithmen zu erzeugen, egal ob Sie ein ganzes Verzeichnis für die Verteilung bündeln möchten oder einfach eine zuverlässige **seven zip archive .net**‑Lösung benötigen. In diesem Leitfaden gehen wir die drei beliebten Komprimierungsmethoden LZMA2, BZip2 und Store (keine Kompression) durch und zeigen Ihnen genau, wie Sie mit nur wenigen Zeilen C#‑Code eine 7z‑Datei erzeugen.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET bietet das vollständigste Set an Seven‑Zip‑Funktionen.  
- **Welche Komprimierungsmethode liefert das beste Verhältnis?** LZMA2 liefert in der Regel die höchste Kompression für gemischte Daten.  
- **Kann ich ein 7z ohne Kompression erstellen?** Ja – verwenden Sie die Store‑Methode (keine Kompression).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Ist das kompatibel mit .NET 6/7?** Absolut – Aspose.Zip unterstützt .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 und .NET 5–10.

## Was sind die Seven‑Zip‑Komprimierungsmethoden?

Seven Zip unterstützt mehrere Algorithmen, die jeweils für unterschiedliche Szenarien optimiert sind. **LZMA2** bietet das höchste Kompressionsverhältnis (oft 30‑40 % kleiner als BZip2), **BZip2** liefert solide Kompression mit breiterer Unterstützung für ältere Werkzeuge, und **Store** archiviert Dateien einfach, ohne sie zu verkleinern, und bewahrt die ursprünglichen Zeitstempel perfekt.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in C# und Visual Studio.  
- Die Aspose.Zip für .NET‑Bibliothek installiert. Laden Sie sie von der offiziellen Download‑Seite **[here](https://releases.aspose.com/zip/net/)** herunter.  
- Einen Ordner (`dataDir`) mit den Dateien, die Sie archivieren möchten.

## Namespaces importieren

Fügen Sie zunächst die erforderlichen Namespaces zu Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Diese Klassen geben Ihnen Zugriff auf die Kompressionseinstellungen und die Archivverwaltung.

## LZMA2‑Kompression – Wie man ein 7z mit maximalem Verhältnis erstellt

Die Klasse `Archive` repräsentiert ein 7z‑Archiv, das mehrere Dateien enthalten kann.  
Der LZMA2‑Algorithmus liefert das höchste Kompressionsverhältnis unter den unterstützten Methoden. Er funktioniert, indem die Eingabe in Blöcke aufgeteilt und eine ausgeklügelte Wörterbuchkompression angewendet wird. In Aspose.Zip setzen Sie die `CompressionMethod` auf `CompressionMethod.Lzma2` im `Archive`‑Objekt, bevor Sie Dateien hinzufügen.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro Tipp:** LZMA2 funktioniert am besten, wenn die Quelldateien größer als 1 MB sind. Bei vielen kleinen Dateien kann BZip2 schneller sein.

## BZip2‑Kompression – Eine ausgewogene Wahl

Die Klasse `Archive` repräsentiert ein 7z‑Archiv, das mehrere Dateien enthalten kann.  
BZip2 bietet solide Kompression mit guter Kompatibilität für ältere Werkzeuge. Es verwendet die Burrows‑Wheeler‑Transformation und Huffman‑Kodierung, um die Größe zu reduzieren. In Aspose.Zip wählen Sie `CompressionMethod.BZip2` beim Konfigurieren der `Archive`‑Instanz, was Geschwindigkeit und Kompressionsverhältnis für die meisten Text‑ und Binärdateien ausbalanciert.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 bietet solide Kompression bei gleichzeitig angemessener Geschwindigkeit und ist ein guter Rückgriff, wenn LZMA2 in der Zielumgebung nicht unterstützt wird.

## Store (keine Kompression) – Wenn die Größe keine Rolle spielt

Die Klasse `Archive` repräsentiert ein 7z‑Archiv, das mehrere Dateien enthalten kann.  
Die Store‑Methode erstellt ein Archiv, ohne die Daten zu komprimieren. Sie kopiert einfach die Originaldateien in den 7z‑Container und bewahrt Zeitstempel und Verzeichnisstruktur. Um sie in Aspose.Zip zu verwenden, setzen Sie `CompressionMethod.Store` im `Archive`, bevor Sie die Dateien hinzufügen, die Sie bündeln möchten.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Verwenden Sie die Store‑Methode, wenn Sie Dateien lediglich zusammenbündeln möchten, ohne ihre Größe zu verändern – ideal zum Bewahren der Originalzeitstempel oder wenn das Archiv unterwegs dekomprimiert wird.

## Wie füge ich Dateien zu 7z hinzu?

Fügen Sie Dateien zu einem 7z‑Archiv hinzu, indem Sie eine `Archive`‑Instanz erstellen, die gewünschte `CompressionMethod` festlegen und `AddAllFiles(dataDir)` aufrufen. Die Methode durchsucht den angegebenen Ordner rekursiv und bewahrt die Verzeichnisstruktur im Archiv. Dieser Ansatz ermöglicht es Ihnen, **compress folder to 7z** mit einer einzigen Codezeile nach der ersten Einrichtung zu erledigen.

## Häufige Anwendungsfälle

| Szenario | Empfohlene Methode |
|----------|--------------------|
| Große Installer verteilen | LZMA2 |
| Protokolle mit Legacy‑Tools teilen | BZip2 |
| Dateien für schnelle Extraktion paketieren | Store (no compression) |
| **compress folder to 7z** on the fly in a web service benötigen | LZMA2 (for best ratio) |

## Fehlerbehebung & Tipps

- **Fehlende Dateien im Archiv?** Stellen Sie sicher, dass `dataDir` auf das richtige Verzeichnis zeigt und der Prozess Leseberechtigungen hat.  
- **Archiv lässt sich in älteren 7‑Zip‑Versionen nicht öffnen?** Bleiben Sie bei BZip2 oder Store, da LZMA2 möglicherweise neuere Dekompressionsbibliotheken erfordert.  
- **Leistungsengpass?** Bei sehr großen Datenmengen sollten Sie das Archiv streamen, anstatt alle Einträge in den Speicher zu laden.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Zip für .NET mit jedem Dateityp verwenden?**  
A: Ja, Aspose.Zip unterstützt eine breite Palette von Dateiformaten und ermöglicht das Komprimieren und Dekomprimieren praktisch jedes Dateityps.

**Q: Ist eine kostenlose Testversion für Aspose.Zip für .NET verfügbar?**  
A: Ja, Sie können eine kostenlose Testversion **[here](https://releases.aspose.com/)** erhalten.

**Q: Wo finde ich die Dokumentation für Aspose.Zip für .NET?**  
A: Die vollständige API‑Referenz ist **[here](https://reference.aspose.com/zip/net/)** verfügbar.

**Q: Wie kann ich temporäre Lizenzen für Aspose.Zip für .NET erhalten?**  
A: Temporäre Lizenzen können **[here](https://purchase.aspose.com/temporary-license/)** bezogen werden.

**Q: Wo kann ich Support für Aspose.Zip für .NET erhalten?**  
A: Sie können Support im **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** finden.

**Zuletzt aktualisiert:** 2026-06-29  
**Getestet mit:** Aspose.Zip für .NET 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Dateien komprimieren c# – 7z-Archiv mit Aspose.Zip für .NET erstellen](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Ordner mit Aspose.Zip für .NET zippen](/zip/net/directory-and-folder-compression/compress-directory/)
- [LZMA in Aspose.Zip für .NET komprimieren](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}