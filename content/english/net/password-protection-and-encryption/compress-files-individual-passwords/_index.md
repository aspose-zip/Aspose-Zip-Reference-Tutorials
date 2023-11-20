---
title: Compress Files with Individual Passwords in Aspose.Zip for .NET
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 16
url: /net/password-protection-and-encryption/compress-files-individual-passwords/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class CompressFilesWithIndividualPasswords
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: CompressFilesWithIndividualPasswords
            using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
            {
                FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
                FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
                FileInfo source3 = new FileInfo(dataDir + "fields.c");

                using (var archive = new Archive())
                {
                    archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
                    archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
                    archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
                    archive.Save(zipFile);
                }
            }

            //ExEnd: CompressFilesWithIndividualPasswords
        }
    }
}
```
