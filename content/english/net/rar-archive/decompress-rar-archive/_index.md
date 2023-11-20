---
title: Decompressing a RAR Archive with Aspose.Zip for .NET
linktitle: Decompressing a RAR Archive 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/rar-archive/decompress-rar-archive/
---

## Complete Source Code
```csharp
using System.IO;
using Aspose.Zip.Rar;

namespace Aspose.ZIP.Examples.RarExtraction
{
    public class DecompressRarArchive
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: DecompressRarArchive
            using (FileStream fs = File.OpenRead(dataDir + "plrabn12.rar"))
            {
                using (RarArchive archive = new RarArchive(fs))
                {
                    archive.ExtractToDirectory(dataDir + "DecompressRar_out");
                }
            }
            //ExEnd: DecompressRarArchive
        }
    }
}
```
