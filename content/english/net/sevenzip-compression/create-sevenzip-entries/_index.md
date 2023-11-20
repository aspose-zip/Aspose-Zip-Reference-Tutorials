---
title: Create SevenZip Entries in Aspose.Zip for .NET
linktitle: Create SevenZip Entries
second_title: Aspose.Zip .NET API for Files Compression & Archiving
description: 
type: docs
weight: 10
url: /net/sevenzip-compression/create-sevenzip-entries/
---

## Complete Source Code
```csharp
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.ZIP.Examples.WorkingWithSevenZip
{
    public class CreateSevenZipEntries
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"

            //ExStart: CreateSevenZipEntries
            using (SevenZipArchive archive = new SevenZipArchive())
            {
                archive.CreateEntries(dataDir);
                archive.Save("SevenZip.7z");
            }
            //ExEnd: CreateSevenZipEntries
            Console.WriteLine("Successfully Created a Seven Zip File");
        }
    }
}

```
