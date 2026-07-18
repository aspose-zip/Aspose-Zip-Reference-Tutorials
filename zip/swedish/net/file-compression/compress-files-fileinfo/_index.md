---
date: 2026-07-18
description: Lär dig hur du lägger till en mapp i zip och lägger till filer i zip
  med Aspose.Zip för .NET. Denna steg‑för‑steg‑guide visar hur du komprimerar filer
  med FileInfo i ASP.NET‑projekt.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Komprimera filer med FileInfo
og_description: Lägg till mapp i zip med Aspose.Zip för .NET. Lär dig hur du skapar
  zip‑arkiv, lägger till filer i zip och komprimerar mappar effektivt i ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Lägg till mapp i zip – Komprimera filer med Aspose.Zip för .NET
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
title: Lägg till mapp i zip med Aspose.Zip för .NET – Komprimera filer med FileInfo
url: /sv/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till mapp i zip med Aspose.Zip för .NET

## Introduktion

If you need to **add folder to zip** programmatically, Aspose.Zip for .NET offers a clean, high‑performance API that works in any .NET (including ASP.NET) application. In this tutorial we’ll walk through compressing files with the `FileInfo` class, show you how to **add files to zip**, and explain why this approach is ideal for modern .NET projects. We’ll also cover the exact steps to **add folder to zip** so you can bundle whole directories in a single operation. Let’s get started!

## Snabba svar
- **Vad är det enklaste sättet att skapa ett zip‑arkiv?** Use Aspose.Zip’s `Archive` class together with `FileInfo` objects.  
- **Kan jag lägga till flera filer samtidigt?** Yes – just create a `FileInfo` for each file and call `CreateEntry`.  
- **Behöver jag en speciell licens för ASP.NET?** A commercial Aspose.Zip license is required for production; a free trial works for evaluation.  
- **Vilka .NET‑versioner stöds?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **Är API‑et trådsäkert?** Yes, as long as each thread works with its own `Archive` instance.

## Vad är ett zip‑arkiv och varför skapa ett?

A zip archive bundles one or more files into a single, compressed container. This reduces storage space, speeds up network transfers, and simplifies distribution. Whether you’re delivering logs, exporting reports, or packaging assets for a client, knowing **how to create zip archive** files programmatically is a valuable skill for any .NET developer.

## Varför använda Aspose.Zip för att lägga till filer i zip?

Aspose.Zip provides a pure‑.NET solution that eliminates external dependencies while giving developers fine‑grained control over compression, encoding, and security. It supports large files, password protection, and works consistently across all supported .NET versions, making it a reliable choice for both legacy and modern applications.  

- **Ingen externa beroenden** – pure .NET implementation.  
- **Full kontroll över komprimeringsnivå och kodning** (ASCII, UTF‑8, etc.).  
- **Stöder filer större än 4 GB** and password protection.  
- **Konsekvent API över 50+ .NET versions** – from .NET Framework 2.0 up to .NET 10.  

## Förutsättningar

Before we dive into the code, make sure you have:

1. **Aspose.Zip for .NET** installed. Download the latest package from the [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. A folder on your machine containing the files you want to compress (e.g., `alice29.txt` and `fields.c`).  

## Importera namnrymder

In any C# file where you’ll work with zip archives, add the following `using` statements:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

These namespaces give you access to the `Archive` class, saving options, and the standard I/O utilities.

## Steg‑för‑steg‑guide

### Steg 1: Ställ in din dokumentkatalog

First, define the folder that holds the source files. Replace the placeholder with the absolute or relative path on your system:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Use `Path.Combine` to build paths in a cross‑platform way.

### Steg 2: Öppna en zip‑fil för skrivning

Create a `FileStream` that points to the output zip file. The stream is opened in **Create** mode, which overwrites any existing file with the same name:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Steg 3: Förbered `FileInfo`‑objekt för varje källfil

`FileInfo` gives Aspose.Zip direct access to the physical files on disk. Create one instance per file you want to compress:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** It avoids loading the entire file into memory, which is especially helpful for large files.

### Steg 4: Skapa arkivet och lägg till poster

The `Archive` class is Aspose.Zip's core object that represents a zip container in memory. Instantiate an `Archive` object, then call `CreateEntry` for each `FileInfo`. The first argument is the name the file will have inside the zip, the second argument is the source `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

The `CreateEntry` method adds a new file entry to the archive, linking the entry name with the source `FileInfo` so the data is streamed directly from disk when the archive is saved.

### Steg 5: Spara zip‑arkivet med önskad kodning

Finally, persist the archive to the `FileStream` you opened earlier. Here we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames contain non‑ASCII characters:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

When the `using` blocks exit, the streams are automatically closed and the zip file is ready for use.

## Hur lägger man till en mapp i zip med Aspose.Zip?

Load the target directory, enumerate every file, and add each one with a relative path that includes the folder name. This approach lets you **add folder to zip** without manually listing each file. By preserving the folder hierarchy in the entry names, the resulting archive can be extracted with the original directory structure intact, which is essential for many deployment scenarios.

1. Använd `DirectoryInfo` för att peka på mappen du vill komprimera.  
2. Anropa `GetFiles("*", SearchOption.AllDirectories)` för att hämta alla filer rekursivt.  
3. För varje fil, skapa ett `FileInfo` och anropa `CreateEntry` med en sökväg som t.ex. `"MyFolder/Report.pdf"`.  

Because the API works with `FileInfo`, it streams each file directly from disk, keeping memory usage low even for folders containing hundreds of megabytes.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Tom zip‑fil** | `FileInfo` pekar på en icke‑existerande sökväg | Verify `dataDir` and file names; use `File.Exists` to check before creating entries. |
| **Felaktig filnamn‑kodning** | Using the default encoding with non‑ASCII names | Set `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException vid stora filer** | Loading whole file into memory | `FileInfo` streams the file; ensure you are not reading the file into a byte array elsewhere. |
| **Behörighet nekad** | Application lacks write permission for the output folder | Run the app with appropriate rights or choose a writable directory. |

## Vanliga frågor

**Q: Kan jag lägga till en hel mapp i ett zip‑arkiv med ett enda anrop?**  
A: No single‑call method exists, but enumerating files with `DirectoryInfo` and adding each via `CreateEntry` achieves the same result efficiently.

**Q: Stöder Aspose.Zip lösenordsskydd?**  
A: Yes, you can set a password on the `Archive` object before saving to encrypt the entire archive.

**Q: Hur stor zip‑fil kan Aspose.Zip hantera?**  
A: The library processes files larger than 4 GB and can create archives exceeding 10 GB without loading the whole archive into memory.

**Q: Är API‑et kompatibelt med .NET 6 och .NET 8?**  
A: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current LTS releases.

**Q: Vilka komprimeringsnivåer finns tillgängliga?**  
A: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or `Maximum` to balance speed and size.

## Ytterligare resurser

- Download the latest Aspose.Zip package: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Purchase a license for production use: [purchase page](https://purchase.aspose.com/buy)  
- Get help from the community: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Try Aspose.Zip for free: [free trial here](https://releases.aspose.com/)  
- Obtain a temporary license for evaluation: [this link](https://purchase.aspose.com/temporary-license/)

## Slutsats

You now know **how to add folder to zip** and **how to create zip archive** files using Aspose.Zip for .NET, how to **add files to zip**, and why this method is ideal for ASP.NET and other .NET applications. Experiment with different compression levels, encodings, and encryption options to tailor the archive to your exact needs. Happy compressing!

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Effortless Compression with Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Archive .NET – File Compression with Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}