---
title: Compress Multiple Files with Traditional Encryption in Aspose.Zip for .NET
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 17
url: /net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class CompressMultipleFilesWithTraditionalEncryption
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: CompressMultipleFilesWithTraditionalEncryption
            using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
            {
                FileInfo source1 = new FileInfo(".\\CanterburyCorpus\\alice29.txt");
                FileInfo source2 = new FileInfo(".\\CanterburyCorpus\\asyoulik.txt");
                FileInfo source3 = new FileInfo(".\\CanterburyCorpus\\fields.c");

                using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
                {
                    archive.CreateEntry("alice29.txt", source1);
                    archive.CreateEntry("asyoulik.txt", source2);
                    archive.CreateEntry("fields.c", source3);
                    archive.Save(zipFile);
                }
            }
            //ExEnd: CompressMultipleFilesWithTraditionalEncryption
        }
    }
}

```
