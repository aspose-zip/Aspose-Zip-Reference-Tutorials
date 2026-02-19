---
date: 2025-12-25
description: Erfahren Sie, wie Sie mit Aspose.Zip für .NET 7z‑Dateien erstellen, wobei
  sieben Zip‑Komprimierungsmethoden wie LZMA2, BZip2 und Store abgedeckt werden. Perfekt
  für Szenarien, in denen Ordner zu 7z komprimiert werden.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Wie man 7z‑Dateien erstellt – Aspose.Zip für .NET Tutorial
url: /de/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie 7z-Dateien – Aspose.Zip für .NET Tutorial

## Einführung

Wenn Sie **how to create 7z** Archive programmgesteuert in einer .NET-Anwendung erstellen müssen, sind Sie hier genau richtig. Aspose.Zip für .NET ermöglicht es, Seven Zip Archive mit jedem der unterstützten Kompressionsalgorithmen zu erzeugen, egal ob Sie **compress folder to 7z** für die Verteilung benötigen oder einfach eine zuverlässige **seven zip archive .net** Lösung suchen. In diesem Leitfaden gehen wir die drei beliebten Kompressionsmethoden – LZMA2, BZip2 und Store (keine Kompression) – durch und zeigen Ihnen genau, wie Sie in nur wenigen Zeilen C#‑Code eine 7z‑Datei erzeugen.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Zip für .NET bietet den vollständigsten Satz an Seven‑Zip‑Funktionen.  
- **Welche Kompressionsmethode liefert das beste Verhältnis?** LZMA2 liefert in der Regel die höchste Kompression für gemischte Daten.  
- **Kann ich ein 7z ohne Kompression erstellen?** Ja – verwenden Sie die Store‑Methode (keine Kompression).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Ist dies kompatibel mit .NET 6/7?** Absolut – Aspose.Zip unterstützt .NET Framework, .NET Core und .NET 5+.

## Was sind die Seven‑Zip‑Kompressionsmethoden?

Seven‑Zip unterstützt mehrere Algorithmen, die jeweils für unterschiedliche Szenarien optimiert sind:

* **LZMA2** – hohes Kompressionsverhältnis, ideal für große gemischte Dateien.  
* **BZip2** – solide Kompression, aber langsamer als LZMA2; nützlich, wenn Kompatibilität mit älteren Werkzeugen erforderlich ist.  
* **Store** – keine Kompression; perfekt, wenn Sie nur archivieren möchten, ohne die Dateigröße zu reduzieren (z. B. beim Beibehalten der ursprünglichen Dateizeitstempel).

Das Verständnis dieser **seven zip compression methods** hilft Ihnen, die richtige Einstellung für Ihr Projekt zu wählen.

## Voraussetzungen

- Grundkenntnisse in C# und Visual Studio.  
- Die Aspose.Zip für .NET Bibliothek installiert. Laden Sie sie von der offiziellen Download‑Seite **[here](https://releases.aspose.com/zip/net/)** herunter.  
- Ein Ordner (`dataDir`) mit den Dateien, die Sie archivieren möchten.

## Namespaces importieren

Zuerst fügen Sie die erforderlichen Namespaces zu Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Diese Klassen geben Ihnen Zugriff auf die Kompressionseinstellungen und die Archivverwaltung.

## LZMA2‑Kompression – So erstellen Sie ein 7z mit maximalem Verhältnis

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

**Pro Tipp:** LZMA2 funktioniert am besten, wenn die Quelldateien größer als 1 MB sind. Bei vielen kleinen Dateien kann BZip2 schneller sein.

## BZip2‑Kompression – Eine ausgewogene Wahl

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 bietet solide Kompression bei gleichzeitig akzeptabler Geschwindigkeit und ist ein guter Rückgriff, wenn LZMA2 in der Zielumgebung nicht unterstützt wird.

## Store (keine Kompression) – Wenn die Größe keine Rolle spielt

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Verwenden Sie die Store‑Methode, wenn Sie Dateien lediglich bündeln möchten, ohne deren Größe zu verändern – perfekt, um ursprüngliche Zeitstempel beizubehalten oder wenn das Archiv on‑the‑fly dekomprimiert wird.

## Häufige Anwendungsfälle

| Szenario | Empfohlene Methode |
|----------|--------------------|
| Große Installer verteilen | LZMA2 |
| Protokolle mit Legacy‑Tools teilen | BZip2 |
| Dateien für schnelle Extraktion paketieren | Store (keine Kompression) |
| Benötigen Sie **compress folder to 7z** on the fly in einem Web‑Service | LZMA2 (für bestes Verhältnis) |

## Fehlersuche & Tipps

- **Fehlende Dateien im Archiv?** Stellen Sie sicher, dass `dataDir` auf das richtige Verzeichnis zeigt und der Prozess Lese‑Berechtigungen hat.  
- **Archiv lässt sich in älteren 7‑Zip‑Versionen nicht öffnen?** Verwenden Sie BZip2 oder Store, da LZMA2 möglicherweise neuere Dekompressionsbibliotheken erfordert.  
- **Leistungsengpass?** Bei sehr großen Datenmengen sollten Sie das Archiv streamen, anstatt alle Einträge in den Speicher zu laden.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Zip für .NET mit jedem Dateityp verwenden?**  
A: Ja, Aspose.Zip unterstützt eine breite Palette von Dateiformaten und ermöglicht das Komprimieren und Dekomprimieren praktisch jeder Datei.

**Q: Ist eine kostenlose Testversion für Aspose.Zip für .NET verfügbar?**  
A: Ja, Sie können eine kostenlose Testversion **[here](https://releases.aspose.com/)** erhalten.

**Q: Wo finde ich die Dokumentation für Aspose.Zip für .NET?**  
A: Die vollständige API‑Referenz ist **[here](https://reference.aspose.com/zip/net/)** verfügbar.

**Q: Wie kann ich temporäre Lizenzen für Aspose.Zip für .NET erhalten?**  
A: Temporäre Lizenzen können Sie **[here](https://purchase.aspose.com/temporary-license/)** erhalten.

**Q: Wo kann ich Support für Aspose.Zip für .NET erhalten?**  
A: Sie können Support im **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** erhalten.

---

**Zuletzt aktualisiert:** 2025-12-25  
**Getestet mit:** Aspose.Zip für .NET 24.12  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
