---
title: Decompress Xar to Folder in Aspose.Zip for .NET
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 17
url: /net/file-decompression/decompress-xar-folder/
---

## Complete Source Code
```csharp
using System.IO;
using Aspose.Zip.Xar;

namespace Aspose.ZIP.Examples.WorkingWithXar
{
    public class DecompressXarToFolder
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: DecompressXarArchive
            using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
            {
                using (XarArchive archive = new XarArchive(fs))
                {
                    archive.ExtractToDirectory(dataDir + "DecompressXar_out");
                }
            }
            //ExEnd: DecompressXarArchive
        }
    }
}
```
