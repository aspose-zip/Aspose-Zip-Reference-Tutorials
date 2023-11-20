---
title: Store Multiple Files Without Compression with Password in Aspose.Zip for .NET
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 13
url: /net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class StoreMutlipleFilesWithoutCompressionWithPassword
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
            using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
            {
                using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
                {
                    using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
                    {
                        archive.CreateEntry("alice29.txt", source1);
                        archive.Save(zipFile);
                    }
                }
            }
            //ExEnd: StoreMutlipleFilesWithoutCompressionWithPassword
        }
    }
}

```
