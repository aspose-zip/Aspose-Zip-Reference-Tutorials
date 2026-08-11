---
title: Create zip without compression in .NET using Aspose.Zip
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: Learn how to create zip without compression in .NET with Aspose.Zip for .NET. This guide shows you how to zip files without compression, store files uncompressed, and manage archives efficiently.
weight: 16
url: /net/file-compression/store-multiple-files-no-compression/
date: 2026-05-30
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
schemas:
- type: TechArticle
  headline: Create zip without compression in .NET using Aspose.Zip
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  dateModified: '2026-05-30'
  author: Aspose
- type: HowTo
  name: Create zip without compression in .NET using Aspose.Zip
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
- type: FAQPage
  questions:
  - question: Can I compress specific file types while storing others without compression?
    answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
  - question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
    answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
  - question: How should I handle exceptions during the archiving process?
    answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
  - question: Does Aspose.Zip support multi‑threaded archiving?
    answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
  - question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
    answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create zip without compression in .NET using Aspose.Zip

In modern .NET development, **creating a zip without compression** can dramatically improve archiving speed and keep file sizes predictable. When you need to **zip files without compression**—for example, to meet regulatory rules, speed up downstream processing, or guarantee that the original byte sequence stays intact—Aspose.Zip for .NET provides a clean, straightforward API. In this tutorial we’ll walk through the exact steps to create an uncompressed ZIP archive, add files, and integrate the solution into your application.

## Quick Answers
- **What does “uncompressed zip” mean?** It’s a ZIP archive where each entry is stored using the “store” method, leaving the original file bytes untouched.  
- **Why avoid compression?** To speed up archiving, preserve original file sizes for downstream processing, or meet regulatory requirements that forbid data alteration.  
- **Which Aspose.Zip class handles this?** `ArchiveEntrySettings` combined with `StoreCompressionSettings`.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **Supported .NET versions?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  

## What is zip without compression?
**Zip without compression** is a ZIP archive where each file entry uses the *store* method, meaning the data is copied verbatim into the archive without any compression algorithm applied. This results in an archive whose size is essentially the sum of the original files plus a few bytes of ZIP overhead.

## Why use Aspose.Zip for zip files without compression?
Aspose.Zip is optimized for high‑performance archiving, allowing you to store files instantly without the overhead of compression algorithms. It guarantees full ZIP compatibility, lets you mix stored and compressed entries, and provides a simple API that abstracts low‑level ZIP structures, making implementation fast and reliable.

## Prerequisites
- **Aspose.Zip for .NET** – integrated into your project. See the official [documentation](https://reference.aspose.com/zip/net/) for installation steps.  
- **.NET Development Environment** – Visual Studio, VS Code, or any IDE you prefer.  
- **Document Directory** – a folder on your machine containing the files you want to archive (e.g., “Your Document Directory”).

## Import Namespaces
Before writing any code, import the required namespaces so the compiler knows where to find the Aspose classes.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Step 1: Set Document Directory
Define the path where your source files reside. Replace the placeholder with the actual folder on your system.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Zip Archive Without Compression
The core of the tutorial – we create an `Archive` instance configured with `StoreCompressionSettings`. `Archive` represents a ZIP container that can hold multiple entries. `StoreCompressionSettings` specifies that an entry should be stored without compression. This tells Aspose.Zip to *store* (i.e., not compress) each entry.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Pro tip:** If you need to **save files to zip** while compressing some and leaving others uncompressed, create separate `ArchiveEntrySettings` instances for each file and add them to the same `Archive`.

## How to create zip without compression in .NET?
Load your source files, instantiate an `Archive` object, and add each file using `ArchiveEntrySettings` with `new StoreCompressionSettings()`. The entire operation requires only three lines of code and runs in linear time relative to the total file size, giving you the fastest possible archiving experience.

### Step‑by‑step walkthrough
1. **Create the archive** – instantiate `Archive` with a target stream or file path.  
2. **Configure entry settings** – for each file, create an `ArchiveEntrySettings` object and assign `new StoreCompressionSettings()` to its `Compression` property.  
3. **Add entries** – call `archive.Add(entrySettings)` for every file, then finalize with `archive.Save()`.

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **File not found** | Incorrect `dataDir` path or missing file extension. | Verify the path and ensure the files exist. Use `Path.Combine` for safer concatenation. |
| **Access denied** | The process lacks permission to read the source files or write the ZIP. | Run the application with appropriate rights or choose a folder with write access. |
| **Unexpected file size in ZIP** | The archive was created with default compression. | Ensure `new StoreCompressionSettings()` is passed to `ArchiveEntrySettings`. |

## Frequently Asked Questions

**Q: Can I compress specific file types while storing others without compression?**  
A: Yes, you can create different `ArchiveEntrySettings` for each file and mix compressed and uncompressed entries in the same archive.

**Q: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?**  
A: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard, and the latest .NET versions.

**Q: How should I handle exceptions during the archiving process?**  
A: Wrap the archiving code in a `try‑catch` block and log the exception details. This ensures graceful failure and easier debugging.

**Q: Does Aspose.Zip support multi‑threaded archiving?**  
A: Yes, you can process multiple files in parallel and add them to the archive, but remember that the `Archive` object itself is not thread‑safe; synchronize access when adding entries.

**Q: Can I integrate Aspose.Zip into an existing project without major code changes?**  
A: Definitely. The API is designed for simple drop‑in usage. Refer to the official [documentation](https://reference.aspose.com/zip/net/) for migration guidance.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip for .NET (latest version at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}