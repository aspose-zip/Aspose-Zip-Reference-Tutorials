---
title: Entries with Different Passwords in Aspose.Zip for .NET
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 13
url: /net/other-compression-techniques/entries-with-different-passwords/
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
    public class EntriesWithDifferentPasswords
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: EntriesWithDifferentPasswords
            using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
            {
                FileInfo fi1 = new FileInfo("data1.bin");
                FileInfo fi2 = new FileInfo("data2.bin");
                FileInfo fi3 = new FileInfo("data3.bin");
                using (var archive = new SevenZipArchive())
                {
                    archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
                    archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
                    archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
                    archive.Save(sevenZipFile);
                }
            }
            //ExEnd: EntriesWithDifferentPasswords
            Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
        }
    }
}

```
