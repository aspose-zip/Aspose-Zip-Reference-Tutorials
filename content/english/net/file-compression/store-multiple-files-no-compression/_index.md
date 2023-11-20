---
title: Storing Multiple Files Without Compression in Aspose.Zip for .NET
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 16
url: /net/file-compression/store-multiple-files-no-compression/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFiles
{
    public class StoreMultipleFilesWithoutCompression
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: StoreMultipleFilesWithoutCompression
            //Creates zip archive without compressing files
            using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
            {
                FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
                FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

                using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
                {
                    archive.CreateEntry("alice29.txt", fi1);
                    archive.CreateEntry("lcet10.txt", fi2);
                    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
                }

            }
            //ExEnd: StoreMultipleFilesWithoutCompression
        }
    }
}

```
