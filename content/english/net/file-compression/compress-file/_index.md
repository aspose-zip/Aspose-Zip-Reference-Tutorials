---
title: Compressing a File with Aspose.Zip for .NET
linktitle: Compressing a File 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/file-compression/compress-file/
---

## Complete Source Code
```csharp
using System;
using Aspose.Zip.Cpio;

namespace Aspose.ZIP.Examples.WorkingWithCpio
{
    public class CompressCpioFile
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: CompressFile
            using (CpioArchive archive = new CpioArchive())
            {
                archive.CreateEntries(dataDir);
                archive.Save(dataDir + "archive.cpio");
            }
            //ExEnd: CompressFile
            Console.WriteLine("Successfully Compressed Files");
        }
    }
}
```
