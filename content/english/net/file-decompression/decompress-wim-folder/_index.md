---
title: Decompress Wim to Folder in Aspose.Zip for .NET
linktitle: Decompress Wim to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 16
url: /net/file-decompression/decompress-wim-folder/
---

## Complete Source Code
```csharp
using System.IO;
using Aspose.Zip.Wim;

namespace Aspose.ZIP.Examples.WorkingWithWim
{
    public class DecompressWimToFolder
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: DecompressWimArchive
            using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
            {
                using (WimArchive archive = new WimArchive(fs))
                {
                    archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
                }
            }
            //ExEnd: DecompressWimArchive
        }
    }
}
```
