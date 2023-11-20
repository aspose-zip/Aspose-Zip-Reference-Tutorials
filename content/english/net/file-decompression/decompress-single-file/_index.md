---
title: Decompressing a Single File with Aspose.Zip for .NET
linktitle: Decompressing a Single File with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 12
url: /net/file-decompression/decompress-single-file/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System;
using System.IO;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFiles
{
    public class DecompressSingleFile
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();
            CompressSingleFile.Run();       //Create a compressed file to work with

            //ExStart: DecompressSingleFile
            using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
            {
                using (Archive archive = new Archive(fs))
                {
                    int percentReady = 0;
                    archive.Entries[0].ExtractionProgressed += (s, e) =>
                    {
                        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
                        if (percent > percentReady)
                        {
                            Console.WriteLine(string.Format("{0}% decompressed", percent));
                            percentReady = percent;
                        }
                    };
                    archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
                }
            }
            //ExEnd: DecompressSingleFile
        }
    }
}

```
