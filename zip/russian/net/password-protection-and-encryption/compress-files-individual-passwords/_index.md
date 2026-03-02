---
date: 2026-03-02
description: Узнайте, как создать zip‑архив, защищённый паролем, и сжать файлы с паролями
  в .NET с помощью Aspose.Zip. Следуйте нашему пошаговому руководству.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание защищённого паролем ZIP‑архива в .NET с помощью Aspose.Zip
url: /ru/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание защищённого паролем ZIP‑архива в .NET с Aspose.Zip

## Introduction

Когда необходимо обмениваться конфиденциальными данными, **защищённый паролем zip‑архив** — один из самых простых и эффективных способов обеспечить безопасность информации. В приложениях .NET библиотека Aspose.Zip упрощает **сжатие файлов с паролями**, предоставляя каждому файлу собственный ключ шифрования. В этом руководстве вы узнаете, как именно создать такой архив, почему это важно и где его можно применить в реальных проектах.

## Quick Answers
- **What library should I use?** Aspose.Zip for .NET provides built‑in support for per‑file passwords and multiple encryption methods.  
- **How many lines of code?** About 30 lines, including setup and saving the archive.  
- **Can each file have a different password?** Yes – you can assign a unique password to every entry.  
- **Which encryption methods are available?** Traditional ZipCrypto, AES‑128, and AES‑256.  
- **Do I need a license for production?** A commercial license is required for production use; a free trial is available.

## What is a password protected zip archive?
Защищённый паролем zip‑архив — это сжатый файл (ZIP), для извлечения содержимого которого требуется пароль. Пароль может защищать весь архив или отдельные записи, а современные алгоритмы, такие как AES‑128/256, обеспечивают надёжное шифрование.

## Why compress files with passwords using Aspose.Zip?
- **Granular security** – assign a distinct password per file, ideal for multi‑tenant scenarios.  
- **Multiple encryption standards** – choose between legacy ZipCrypto and strong AES.  
- **No external tools** – everything is handled programmatically within your .NET codebase.  
- **Performance** – fast compression with Deflate while keeping the archive size small.

## Prerequisites

Before you start, make sure you have:

- **Aspose.Zip for .NET** – install the library in your project. Detailed docs are available [here](https://reference.aspose.com/zip/net/).  
- **Download the latest package** if you haven’t already, from [this link](https://releases.aspose.com/zip/net/).  
- A folder containing the files you want to compress.

## Import Namespaces

Add the required namespaces at the top of your C# file:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

Point the code to the folder that holds the source files:

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

Now we’ll create a **password protected zip archive** where each file uses its own password and encryption method. The example uses three sample files (`alice29.txt`, `asyoulik.txt`, and `fields.c`) with different passwords.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How it works
- **CreateEntry** adds a file to the archive.  
- The fourth argument (`ArchiveEntrySettings`) lets you specify both compression (`DeflateCompressionSettings`) and encryption (`TraditionalEncryptionSettings` or `AesEcryptionSettings`).  
- By passing a different password string for each entry, you end up with a **password protected zip archive** where every file is unlocked only with its own key.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Extraction fails with “Wrong password” | Password mismatch or wrong encryption method | Verify the exact password string and ensure you used the same `EncryptionMethod` when extracting. |
| Archive size is larger than expected | Using AES‑256 on small text files can add overhead | For small files, AES‑128 may be sufficient and yields a smaller archive. |
| Runtime exception on `archive.Save` | Missing write permission on the target folder | Ensure the application has write access to `dataDir` or use a different output path. |

## Frequently Asked Questions (FAQs)

### Can I use different encryption methods for each file?
Yes, Aspose.Zip for .NET allows you to mix encryption methods—traditional ZipCrypto, AES‑128, and AES‑256—on a per‑file basis.

### Is there a trial version available?
Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).

### How can I get support if I encounter issues?
Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance from the community and Aspose support.

### Where can I find detailed documentation for Aspose.Zip for .NET?
The documentation is available [here](https://reference.aspose.com/zip/net/).

### Can I purchase a temporary license for testing purposes?
Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose