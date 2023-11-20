---
title: Compressing to TarGz with Aspose.Zip for .NET
linktitle: Compressing to TarGz with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 12
url: /net/archive-extraction-and-formats/compress-to-tar-gz/
---

## Complete Source Code
```csharp
using System;
using Aspose.Zip.Tar;

namespace Aspose.ZIP.Examples.CompressToTarXX
{
    public class CompressToTarGz
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: CompressFile
            using (TarArchive archive = new TarArchive())
            {
                archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
                archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
                archive.SaveGzipped(dataDir + "archive.tar.gz");
            }
            //ExEnd: CompressFile
            
        }
    }
}
```
