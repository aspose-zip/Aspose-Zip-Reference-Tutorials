---
title: AES Encryption Settings in Aspose.Zip for .NET
linktitle: AES Encryption Settings in Aspose.Zip for .NET
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 14
url: /net/password-protection-and-encryption/aes-encryption-settings/
---

## Complete Source Code
```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.ZIP.Examples.WorkingWithSevenZip
{
    public class AESEncryptionSettings
    {
        public static void Run()
        {
            string dataDir = RunExamples.GetDataDir_Data();

            //ExStart: AESEncryptionSettings
            using (var archive = new SevenZipArchive(new SevenZipEntrySettings(null, new SevenZipAESEncryptionSettings("p@s$"))))
            {
                archive.CreateEntry("data.bin", new MemoryStream(new byte[] { 0x00, 0xFF }));
                archive.Save("archive.7z");
            }
            //ExEnd: AESEncryptionSettings
            Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
        }
    }
}

```
