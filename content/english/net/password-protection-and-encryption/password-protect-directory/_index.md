---
title: Password Protect Directory in Aspose.Zip for .NET
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/password-protection-and-encryption/password-protect-directory/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class PasswordProtectDirectory
    {
        public static void Run()
        {
            //ExStart: PasswordProtectDirectory
            using (FileStream zipFile = File.Open(".\\all_corpus_encrypted_out.zip", FileMode.Create))
            {
                DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
                using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
                {
                    archive.CreateEntries(corpus);
                    archive.Save(zipFile);
                    //ExEnd: PasswordProtectDirectory
                }
            }
        }
    }
}

```
