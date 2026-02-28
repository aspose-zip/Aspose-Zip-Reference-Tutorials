---
title: How to Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: Learn how to add folder to zip and add files to zip using Aspose.Zip for .NET. This step‑by‑step guide shows how to compress files with FileInfo in ASP.NET projects.
weight: 11
url: /net/file-compression/compress-files-fileinfo/
date: 2026-02-28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Folder to Zip Using Aspose.Zip for .NET

## Introduction

If you need to **create a zip archive** programmatically, Aspose.Zip for .NET gives you a clean, high‑performance API that works in any .NET (including ASP.NET) application. In this tutorial we’ll walk through compressing files with the `FileInfo` class, show you how to **add files to zip**, and explain why this approach is ideal for modern .NET projects. We’ll also cover how to **add folder to zip** so you can bundle whole directories in a single step. Let’s get started!

## Quick Answers
- **What is the easiest way to create a zip archive?** Use Aspose.Zip’s `Archive` class together with `FileInfo` objects.  
- **Can I add multiple files at once?** Yes – just create a `FileInfo` for each file and call `CreateEntry`.  
- **Do I need a special license for ASP.NET?** A commercial Aspose.Zip license is required for production; a free trial works for evaluation.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Is the API thread‑safe?** Yes, as long as each thread works with its own `Archive` instance.

## What is a Zip Archive and Why Create One?
A zip archive bundles one or more files into a single, compressed container. This reduces storage space, speeds up network transfers, and simplifies distribution. Whether you’re delivering logs, exporting reports, or packaging assets for a client, knowing **how to create zip archive** files programmatically is a valuable skill for any .NET developer.

## Why Use Aspose.Zip to Add Files to Zip?
- **Zero external dependencies** – pure .NET implementation.  
- **Full control over compression level and encoding** (ASCII, UTF‑8, etc.).  
- **Supports large files** (> 4 GB) and password protection.  
- **Consistent API across .NET Framework, .NET Core, and .NET 5+**.

## Prerequisites

Before we dive into the code, make sure you have:

1. **Aspose.Zip for .NET** installed. Download the latest package from the [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. A folder on your machine containing the files you want to compress (e.g., `alice29.txt` and `fields.c`).  

## Import Namespaces

In any C# file where you’ll work with zip archives, add the following `using` statements:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

These namespaces give you access to the `Archive` class, saving options, and the standard I/O utilities.

## Step‑by‑Step Guide

### Step 1: Set Up Your Document Directory

First, define the folder that holds the source files. Replace the placeholder with the absolute or relative path on your system:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Use `Path.Combine` to build paths in a cross‑platform way.

### Step 2: Open a Zip File for Writing

Create a `FileStream` that points to the output zip file. The stream is opened in **Create** mode, which overwrites any existing file with the same name:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Step 3: Prepare `FileInfo` Objects for Each Source File

`FileInfo` gives Aspose.Zip direct access to the physical files on disk. Create one instance per file you want to compress:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** It avoids loading the entire file into memory, which is especially helpful for large files.

### Step 4: Create the Archive and Add Entries

Instantiate an `Archive` object, then call `CreateEntry` for each `FileInfo`. The first argument is the name the file will have inside the zip, the second argument is the source `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Step 5: Save the Zip Archive with Desired Encoding

Finally, persist the archive to the `FileStream` you opened earlier. Here we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames contain non‑ASCII characters:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

When the `using` blocks exit, the streams are automatically closed and the zip file is ready for use.

## How to Add Folder to Zip Using Aspose.Zip

If you need to **add folder to zip** rather than individual files, the process is straightforward:

1. **Enumerate the folder** with `DirectoryInfo.GetFiles` (and optionally `GetDirectories` for recursion).  
2. **Create a `FileInfo`** for each discovered file.  
3. **Call `CreateEntry`** with a relative path that includes the folder name, e.g., `"MyFolder/Report.pdf"`.  

Because the API works with `FileInfo`, you never have to load whole files into memory, making it safe for large directories. This technique also works for **zip multiple files asp.net** scenarios where you generate a report set on the fly and need to deliver it as a single archive.

## Common Issues & Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Empty zip file** | `FileInfo` points to a non‑existent path | Verify `dataDir` and file names; use `File.Exists` to check before creating entries. |
| **Incorrect filename encoding** | Using the default encoding with non‑ASCII names | Set `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException on large files** | Loading whole file into memory | `FileInfo` streams the file; ensure you are not reading the file into a byte array elsewhere. |
| **Permission denied** | Application lacks write permission for the output folder | Run the app with appropriate rights or choose a writable directory. |

## Frequently Asked Questions

**Q: Can I add password protection to the zip archive?**  
A: Yes. After creating the `Archive`, set `archive.Password = "yourPassword"` before calling `Save`.

**Q: Is it possible to update an existing zip file?**  
A: Aspose.Zip supports opening an existing archive with `Archive.Open` and then adding new entries.

**Q: How do I compress files in an ASP.NET MVC controller?**  
A: The same code works; just ensure the output stream is returned as a `FileResult` to the client.

**Q: Does Aspose.Zip support encryption algorithms?**  
A: It supports standard ZipCrypto and AES‑256 encryption.

**Q: What if I need to compress a folder recursively?**  
A: Loop through `Directory.GetFiles` (and sub‑folders) and create a `FileInfo` for each file, then add them to the archive.

## Additional FAQ

**Q: How do I create zip archive .net for large data sets?**  
A: Use `FileInfo` objects to stream data and set `CompressionLevel` in `ArchiveSaveOptions` for optimal performance.

**Q: Can I use Aspose.Zip in a .NET Core web API (zip files asp.net core)?**  
A: Absolutely – the library is fully compatible with .NET Core 3.1 and later.

**Q: Is there a way to add folder to zip without writing a custom loop?**  
A: Aspose.Zip does not have a single “add folder” method, but iterating with `DirectoryInfo` is lightweight and gives you full control over entry names.

**Q: Does zip archive password protection affect compression speed?**  
A: Enabling encryption adds a small overhead, but the impact is minimal for most use cases.

**Q: What licensing is required for commercial deployment?**  
A: A paid Aspose.Zip license is required for production; a free trial can be used for development and testing.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusion

You now know **how to add folder to zip** and **how to create zip archive** files using Aspose.Zip for .NET, how to **add files to zip**, and why this method is ideal for ASP.NET and other .NET applications. Experiment with different compression levels, encodings, and encryption options to tailor the archive to your exact needs. Happy compressing!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}