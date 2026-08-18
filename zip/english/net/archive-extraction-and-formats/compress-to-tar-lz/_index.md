---
title: How to compress multiple files tar with Aspose.Zip for .NET
linktitle: Compressing to TarLz 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: Learn how to compress multiple files into a tar.lz archive using the Aspose.Zip for .NET API, covering single‑file and multi‑file scenarios with clear code examples.
weight: 13
url: /net/archive-extraction-and-formats/compress-to-tar-lz/
date: 2026-07-04
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
schemas:
- type: TechArticle
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  dateModified: '2026-07-04'
  author: Aspose
- type: HowTo
  name: How to compress multiple files tar with Aspose.Zip for .NET
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
- type: FAQPage
  questions:
  - question: What library should I use?
    answer: Aspose.Zip for .NET.
  - question: How long does the implementation take?
    answer: About 5‑10 minutes for a basic example.
  - question: Do I need a license?
    answer: A free trial works for testing; a commercial license is required for production.
  - question: Which .NET versions are supported?
    answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
  - question: Can I compress multiple files at once?
    answer: Yes – just add more entries before saving.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to compress multiple files tar with Aspose.Zip for .NET

In modern .NET development, efficiently packaging files can dramatically improve deployment size and network transfer times. **Compress multiple files tar** is a frequent requirement when you need a lightweight, LZ‑compressed TAR archive for backups, distribution, or cloud uploads. In this tutorial we’ll walk through a clear, step‑by‑step **tar.lz compression example** using the Aspose.Zip library, so you can quickly create a **tar.lz archive** in your own applications.

## Quick Answers
- **What library should I use?** Aspose.Zip for .NET.  
- **How long does the implementation take?** About 5‑10 minutes for a basic example.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I compress multiple files at once?** Yes – just add more entries before saving.

## How do I compress multiple files tar with Aspose.Zip for .NET?
Load your source files, create a `TarArchive` instance, add each file with `CreateEntry`, and finish by calling `SaveLzipped`. The library handles the TAR structure and LZ compression internally, so you end up with a single `*.tar.lz` file in just a few lines of code. This approach works on Windows, Linux, and macOS without any native dependencies.

## What is tar.lz compression?
`tar.lz` is a TAR archive that has been compressed using the LZMA algorithm (often referred to simply as **LZ**). It combines the simplicity of TAR’s file‑grouping with the high compression ratio of LZ, making it ideal for backup files, package distribution, or any scenario where bandwidth matters.

## Why use Aspose.Zip for .NET?
Aspose.Zip provides a pure‑managed, cross‑platform solution that creates TAR, ZIP, and LZ‑based archives without external tools, supports over 30 archive formats, and delivers up to 30 % better compression on large files, while offering detailed exceptions for robust error handling. It also integrates seamlessly with .NET logging frameworks and provides detailed progress events.

## Prerequisites
Before you start, make sure you have:

- **Aspose.Zip for .NET** library – download it from [Aspose.Zip .NET download page](https://releases.aspose.com/zip/net/).  
- A folder that contains the files you want to archive. The path to this folder will be stored in the `dataDir` variable (you’ll set it in Step 3).

## Import Namespaces
Add the required namespaces so the compiler knows where to find the classes we’ll use.

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to create tar.lz archive – Step‑by‑Step Guide

### Step 1: Compress a single file
The first example shows the most basic scenario – adding one file to a TAR archive and then saving it as a **tar.lz** file.

The `TarArchive` class represents a TAR container that can hold multiple files in a single archive.  

**Explanation**

- `new TarArchive()` creates an empty TAR container.  
- `CreateEntry` adds the file `alice29.txt` from your `dataDir`.  
- `SaveLzipped` writes the archive to disk and applies LZ compression, producing `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Step 2: Compress multiple files in one archive
Often you’ll need to bundle several files together. Just call `CreateEntry` for each file before saving. This demonstrates **add files to tar lz** and effectively **compress multiple files tar**.

**Explanation**

- The code follows the same pattern as Step 1, but adds a second entry (`lcet10.txt`).  
- You can repeat `CreateEntry` as many times as needed; the library handles the internal TAR structure automatically.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Step 3: Specify your document directory
Replace the placeholder with the actual path where your source files live. This path is used by the examples above.

**Explanation**

- Set `dataDir` to a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`.  
- Keeping the directory in a variable makes the code reusable and easier to maintain.

```csharp
string dataDir = "Your Document Directory";
```

## Common pitfalls & troubleshooting
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `FileNotFoundException` when running the sample | `dataDir` points to a non‑existent folder or the file name is misspelled | Verify the path and file names; use `Path.Combine` for safety. |
| Output file is **0 KB** | `archive.SaveLzipped` was called before any entries were added | Ensure at least one `CreateEntry` call precedes `SaveLzipped`. |
| Compression seems slow | Large files with default buffer size | Consider processing files in chunks or using asynchronous I/O if performance is critical. |

## Conclusion
You now know **how to compress tar.lz** files using Aspose.Zip for .NET, whether you’re dealing with a single document or a collection of files. This **tar.lz compression example** demonstrates a clean, production‑ready way to **create tar lz archive** files that can be easily transferred or stored. You can compress files to tar.lz using the same API by calling `SaveLzipped` after adding all desired entries.

## Frequently asked questions

**Q:** Can I compress files of any size using Aspose.Zip for .NET?  
**A:** Yes, the library handles both small and very large files; just ensure you have sufficient memory and disk space for the temporary TAR structure.

**Q:** Is the code compatible with the latest Aspose.Zip release?  
**A:** The sample targets the current version; always keep the NuGet package up to date for bug fixes and new features.

**Q:** Are there licensing considerations?  
**A:** A commercial license is required for production use. See the licensing details on the [Aspose website](https://purchase.aspose.com/buy).

**Q:** Can I use this in a commercial project?  
**A:** Absolutely – once you have a valid license, you can embed the library in any commercial application.

**Q:** Where can I get help if I run into issues?  
**A:** Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community support and official assistance.

---

**Last Updated:** 2026-07-04  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}