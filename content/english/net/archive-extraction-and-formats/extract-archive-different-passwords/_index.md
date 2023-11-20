---
title: Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET
linktitle: Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/archive-extraction-and-formats/extract-archive-different-passwords/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFolders
{
    public class ExtractArchiveWithEntriesHavingDifferentPasswords
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: ExtractArchiveWithEntriesHavingDifferentPasswords
            using (FileStream zipFile = File.Open(dataDir + "\\different_password.zip", FileMode.Open))
            {
                using (Archive archive = new Archive(zipFile))
                {
                    archive.Entries[0].Extract(dataDir + "alice29_extracted_pass_out.txt", "first_pass");
                    archive.Entries[1].Extract(dataDir + "asyoulik_extracted_pass_out.txt", "second_pass");
                }
            }
            //ExEnd: ExtractArchiveWithEntriesHavingDifferentPasswords
        }
    }
}

```
