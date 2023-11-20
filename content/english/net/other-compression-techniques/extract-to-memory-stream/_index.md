---
title: Extracting to Memory Stream with Aspose.Zip for .NET
linktitle: Extracting to Memory Stream with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/other-compression-techniques/extract-to-memory-stream/
---

## Complete Source Code
```csharp
using Aspose.Zip.Gzip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.ZIP.Examples.WorkingWithGZip
{
    public class ExtractToMemoryStream
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: ExtractToMemoryStream
            //Open an archive from a stream and extract it to a MemoryStream
            var ms = new MemoryStream();
            using (GzipArchive archive = new GzipArchive(File.OpenRead(dataDir + "sample.gz")))
            {
                archive.Open().CopyTo(ms);
                Console.WriteLine(archive.Name);
            }
            //ExEnd: ExtractToMemoryStream
            Console.WriteLine("Successfully Extractd to Memory Stream");
        }
    }
}

```
