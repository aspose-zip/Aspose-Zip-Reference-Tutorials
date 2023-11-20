---
title: Decompressing a RAR Entry with Aspose.Zip for .NET
linktitle: Decompressing a RAR Entry with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 11
url: /net/rar-archive/decompress-rar-entry/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using Aspose.Zip;
using Aspose.Zip.Rar;

namespace Aspose.ZIP.Examples.RarExtraction
{
    public class DecompressRarEntry
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: DecompressRarEntry
            using (FileStream fs = File.OpenRead(dataDir + "plrabn12.rar"))
            {
                using (RarArchive archive = new RarArchive(fs))
                {
                    archive.Entries[0].Extract(dataDir + "plrabn12_out.txt");
                }
            }
            //ExEnd: DecompressRarEntry
        }
    }
}
```
