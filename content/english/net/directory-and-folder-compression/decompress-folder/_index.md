---
title: Decompressing a Folder with Aspose.Zip for .NET
linktitle: Decompressing a Folder 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 11
url: /net/directory-and-folder-compression/decompress-folder/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFolders
{
    public class DecompressFolder
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            CompressDirectory.Run();    //Create a zip file from Directory to be decompressed later int this example

            //ExStart: DecompressFolder
            using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
            {
                using (var archive = new Archive(zipFile))
                {
                    archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
                }
            }
            //ExEnd: DecompressFolder
        }
    }
}

```
