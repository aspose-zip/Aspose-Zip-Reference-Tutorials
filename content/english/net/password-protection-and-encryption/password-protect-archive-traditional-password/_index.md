---
title: Password Protect Archive with Traditional Password in Aspose.Zip for .NET
linktitle: Password Protect Archive with Traditional Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 12
url: /net/password-protection-and-encryption/password-protect-archive-traditional-password/
---

## Complete Source Code
```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;

namespace Aspose.ZIP.Examples.WorkingWithPasswordProtectedArchives
{
    public class PasswordPrtoectArchiveWithTraditionalPassword
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: PasswordPrtoectArchiveWithTraditionalPassword
            using (FileStream zipFile = File.Open(dataDir + "CompressWithTraditionalEncryption_out.zip", FileMode.Create))
            {
                using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
                {
                    var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$")));
                    archive.CreateEntry("alice29.txt", source1);
                    archive.Save(zipFile);
                }
            }
            //ExEnd: PasswordPrtoectArchiveWithTraditionalPassword
        }
    }
}

```
