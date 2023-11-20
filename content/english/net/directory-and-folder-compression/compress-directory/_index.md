---
title: How to Compress a Directory with Aspose.Zip for .NET
linktitle: How to Compress a Directory with Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/directory-and-folder-compression/compress-directory/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;

namespace Aspose.ZIP.Examples.CompressingAndDecompressingFolders
{
    public class CompressDirectory
    {
        public static void Run()
        {
            //ExStart: DeCompressDirectory
            string dataDir = RunExamples.GetDataDir_Data();

            using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
            {
                using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
                {
                    using (Archive archive = new Archive())
                    {
                        DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
                        archive.CreateEntries(corpus);
                        archive.Save(zipFile);
                        archive.Save(zipFile2);
                    }
                }
            }
            //ExEnd: DeCompressDirectory
        }
    }
}

```
