---
title: Decompress Compressed Folder to Directory in Aspose.Zip for .NET
linktitle: Decompress Compressed Folder to Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 14
url: /net/file-decompression/decompress-compressed-folder-directory/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class DecompressCompressedFolderToDirectory
    {
        public static void Run()
        {
            //ExStart: DecompressCompressedFolderToDirectory
            using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
            {
                new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }).ExtractToDirectory(".\\all_corpus_decrypted");
            }
            //ExEnd: DecompressCompressedFolderToDirectory
        }
    }
}

```
