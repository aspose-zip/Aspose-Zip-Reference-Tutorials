---
title: Aspose.Zip for .NET - Secure File Storage Tutorial
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: Explore how to use Aspose.Zip for .NET to securely store multiple files without compression. Easy steps for password protection. Unlock the power of file management!
type: docs
weight: 13
url: /net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

In the world of .NET development, managing and manipulating files is a common task. Aspose.Zip for .NET is a powerful library that provides developers with the capability to compress, decompress, and manipulate zip archives seamlessly. In this tutorial, we will delve into a specific scenario: storing multiple files without compression and protecting them with a password. By the end of this guide, you'll be equipped with the knowledge to implement this functionality using Aspose.Zip for .NET.

## Prerequisites

Before we dive into the tutorial, ensure you have the following prerequisites in place:

- Aspose.Zip for .NET Library: Make sure you have the Aspose.Zip for .NET library installed. You can download it [here](https://releases.aspose.com/zip/net/).

- Document Directory: Prepare a directory where your source files are located. In the provided example, the variable `dataDir` represents your document directory.

## Import Namespaces

To begin, let's import the necessary namespaces for our code:

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Step 1: Open the Zip File

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

This step involves creating a new zip file using `FileStream`. The file will be named "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## Step 2: Open the Source File

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Here, we open the first source file, "alice29.txt," which will be stored in the zip archive.

## Step 3: Create an Archive

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

In this step, we create an instance of the `Archive` class, specifying the compression and encryption settings. We use the `StoreCompressionSettings` to store files without compression and `AesEcryptionSettings` to apply AES encryption with a password ("p@s$").

## Step 4: Create Archive Entry and Save

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

This final step involves creating an entry in the archive for "alice29.txt" and saving the archive, completing the process of storing a file without compression and with password protection.

Conclude your tutorial by summarizing the key points and encouraging readers to explore further possibilities with Aspose.Zip for .NET.

## Conclusion

In this tutorial, we explored how to use Aspose.Zip for .NET to store multiple files without compression and secure them with a password. As you continue your journey with .NET development, leverage the capabilities of Aspose.Zip to streamline file management tasks and enhance the security of your applications.

---

### FAQs

### Can I use Aspose.Zip for .NET with other encryption methods?
Yes, Aspose.Zip supports various encryption methods. Check the documentation [here](https://reference.aspose.com/zip/net/) for details.

### Where can I get support for Aspose.Zip for .NET?
Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community support and discussions.

### Is there a free trial available for Aspose.Zip for .NET?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### How can I obtain a temporary license for Aspose.Zip for .NET?
Request a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Where can I purchase Aspose.Zip for .NET?
You can buy Aspose.Zip for .NET [here](https://purchase.aspose.com/buy).

