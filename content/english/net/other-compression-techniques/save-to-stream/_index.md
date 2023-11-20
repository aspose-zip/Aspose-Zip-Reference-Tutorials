---
title: Saving to Stream with Aspose.Zip for .NET
linktitle: Saving to Stream 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 12
url: /net/other-compression-techniques/save-to-stream/
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
    public class SaveToStream
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: SaveToStream
            //Writes compressed data to http response stream.
            var ms = new MemoryStream();
            using (var archive = new GzipArchive())
            {
                archive.SetSource(new FileInfo(dataDir + "data.bin"));
                archive.Save(ms);
            }
            //ExEnd: SaveToStream
            Console.WriteLine("Successfully Saved to Stream");
        }
    }
}

```
