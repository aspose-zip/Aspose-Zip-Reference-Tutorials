---
title: How to Compress Multiple Files with Aspose.Zip for .NET
linktitle: How to Compress Multiple Files 
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 13
url: /net/file-compression/compress-multiple-files/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFiles
{
    public class CompressMultipleFiles
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"
            //ExStart: CompressMultipleFiles
            using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Create))
            {
                using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
                {
                    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
                    {
                        using (var archive = new Archive())
                        {
                            archive.CreateEntry("alice29.txt", source1);
                            archive.CreateEntry("asyoulik.txt", source2);
                            archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII, ArchiveComment = "There are two poems from Canterbury corpus" });
                        }
                    }
                }
            }
            //ExEnd: CompressMultipleFiles
        }
    }
}

```
