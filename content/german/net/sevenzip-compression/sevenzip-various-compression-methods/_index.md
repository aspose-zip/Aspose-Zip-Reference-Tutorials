---
title: Sieben Zip-Dateien erstellen – Aspose.Zip für .NET-Tutorial
linktitle: SevenZip mit verschiedenen Komprimierungsmethoden
second_title: Aspose.Zip .NET API für Dateikomprimierung und -archivierung
description: Erfahren Sie, wie Sie mit Aspose.Zip für .NET unter Verwendung verschiedener Komprimierungsmethoden sieben Zip-Dateien erstellen. Einfache Schritte für LZMA2, BZip2 und Store (keine Komprimierung).
type: docs
weight: 12
url: /de/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## Einführung

Im Bereich der .NET-Entwicklung ist das Verwalten und Komprimieren von Dateien eine häufige Aufgabe. Aspose.Zip für .NET bietet eine leistungsstarke Lösung für die Arbeit mit komprimierten Archiven und bietet eine Vielzahl von Komprimierungsmethoden. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Zip für .NET sieben Zip-Dateien mit unterschiedlichen Komprimierungsmethoden erstellen.

## Voraussetzungen

Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Ein grundlegendes Verständnis der C#-Programmierung.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Zip für .NET-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/zip/net/).

## Namespaces importieren

Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr C#-Projekt. Verwenden Sie zum Einstieg den folgenden Codeausschnitt:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2-Komprimierung

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

## BZip2-Komprimierung

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Speichern, keine Komprimierung

```csharp
//Speichern, keine Komprimierung
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Abschluss

In diesem Tutorial haben wir die Vielseitigkeit von Aspose.Zip für .NET beim Erstellen von Seven Zip-Dateien mit verschiedenen Komprimierungsmethoden untersucht. Ganz gleich, ob Sie hohe Komprimierungsraten benötigen oder überhaupt keine Komprimierung bevorzugen, Aspose.Zip bietet die Flexibilität, Ihre Anforderungen zu erfüllen.

## FAQs

### Kann ich Aspose.Zip für .NET mit jedem Dateityp verwenden?
Ja, Aspose.Zip für .NET unterstützt eine Vielzahl von Dateitypen und ermöglicht Ihnen das Komprimieren und Dekomprimieren verschiedener Formate.

### Ist eine kostenlose Testversion für Aspose.Zip für .NET verfügbar?
 Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).

### Wo finde ich Dokumentation für Aspose.Zip für .NET?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/zip/net/).

### Wie kann ich temporäre Lizenzen für Aspose.Zip für .NET erhalten?
 Es können befristete Lizenzen erworben werden[Hier](https://purchase.aspose.com/temporary-license/).

### Wo erhalte ich Unterstützung für Aspose.Zip für .NET?
 Unterstützung können Sie hier suchen[Aspose.Zip-Forum](https://forum.aspose.com/c/zip/37).
