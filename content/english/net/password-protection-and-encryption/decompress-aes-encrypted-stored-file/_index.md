---
title: Decompress AES Encrypted Stored File in Aspose.Zip for .NET
linktitle: Decompress AES Encrypted Stored File in Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 19
url: /net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class DecompressAESEncryptedStoredFile
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            StoreMutlipleFilesWithoutCompressionWithPassword.Run();

            //ExStart: DecompressAESEncryptedStoredFile
            using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
            {
                using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
                {
                    using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
                    {
                        using (var decompressed = archive.Entries[0].Open())
                        {
                            byte[] b = new byte[8192];
                            int bytesRead;
                            while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
                            {
                                extracted.Write(b, 0, bytesRead);
                            }
                        }
                    }
                }
            }
            //ExEnd: DecompressAESEncryptedStoredFile
        }
    }
}
```
