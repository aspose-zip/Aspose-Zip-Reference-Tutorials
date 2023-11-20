---
title: Compressing to TarXz with Aspose.Zip for .NET
linktitle: Compressing to TarXz with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 14
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
---

## Complete Source Code
```csharp
using System;
using Aspose.Zip.Tar;

namespace Aspose.ZIP.Examples.CompressToTarXX
{
    public class CompressToTarXz
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: CompressFile
            using (TarArchive archive = new TarArchive())
            {
                archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
                archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
                archive.SaveXzCompressed(dataDir + "archive.tar.xz");
            }
            //ExEnd: CompressFile
            
        }
    }
}
```
