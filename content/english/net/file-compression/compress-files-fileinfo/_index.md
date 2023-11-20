---
title: Compress Files using FileInfo in Aspose.Zip for .NET
linktitle: Compress Files using FileInfo in Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 11
url: /net/file-compression/compress-files-fileinfo/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFiles
{
    public class CompressFilesByFileInfo
    {
        public static void Run()
        {
            string dataDir  = RunExamples.GetDataDir_Data();

            //ExStart: CompressFilesByFileInfo
            using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
            {
                FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
                FileInfo fi2 = new FileInfo(dataDir + "fields.c");

                using (var archive = new Archive())
                {
                    archive.CreateEntry("alice29.txt", fi1);
                    archive.CreateEntry("fields.c", fi2);
                    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
                }
            }
            //ExEnd: CompressFilesByFileInfo
        }
    }
}

```
