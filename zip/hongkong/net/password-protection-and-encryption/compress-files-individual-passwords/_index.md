---
date: 2025-12-20
description: 了解如何在 .NET 中使用 Aspose.Zip 建立受密碼保護的 zip 壓縮檔。本步驟指南示範如何以密碼壓縮檔案、設定 zip 條目密碼，以及使用
  AES 加密。
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 在 .NET 中使用 Aspose.Zip 建立受密碼保護的 ZIP 檔案
url: /zh-hant/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 建立受密碼保護的 ZIP 檔案

## Introduction

如果您需要在 .NET 應用程式中 **建立受密碼保護的 zip** 壓縮檔，Aspose.Zip 讓這個工作變得相當簡單。只要為每個條目指派唯一的密碼，即可在保護敏感文件的同時，仍享受 ZIP 壓縮的便利。在本教學中，您將學會如何使用個別密碼壓縮檔案、選擇不同的加密方式，以及設定 zip 條目密碼——全部以清晰、可直接投入生產的程式碼示範。

## Quick Answers
- **What library should I use?** Aspose.Zip for .NET.
- **Can I assign a different password per file?** Yes, each entry can have its own password.
- **Which encryption algorithms are supported?** Traditional ZipCrypto, AES‑128, and AES‑256.
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.
- **Is this compatible with .NET 6+?** Absolutely – the API targets .NET Standard 2.0 and later.

## What is “create password protected zip”?
建立受密碼保護的 zip 意指在 ZIP 壓縮檔內的其中一個或多個條目加入加密，讓未取得正確密碼的情況下無法開啟內容。此功能非常適合傳輸機密檔案、儲存備份，或遵循資料保護政策。

## Why use Aspose.Zip for password‑protected archives?
- **Fine‑grained control** – set a distinct password per file.
- **Multiple encryption options** – from legacy ZipCrypto to strong AES‑128/256.
- **No external dependencies** – pure .NET library, easy to integrate.
- **Comprehensive documentation** – includes an **aspose zip tutorial** for deeper scenarios.

## Prerequisites

在開始教學之前，請先確保具備以下前置條件：

- Aspose.Zip for .NET：確保已在您的 .NET 專案中安裝 Aspose.Zip 程式庫。相關文件可於 [此處](https://reference.aspose.com/zip/net/) 取得。
- Download：若尚未下載，請從 [此連結](https://releases.aspose.com/zip/net/) 下載 Aspose.Zip for .NET 程式庫。
- Document Directory：準備一個資料夾，內含您欲壓縮的檔案。

## Import Namespaces

在您的 .NET 專案中，務必匯入必要的命名空間：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

定義資源目錄的路徑，該目錄放置您的來源檔案。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

現在，我們來示範如何使用個別密碼壓縮檔案。以下範例使用三個樣本檔 (`alice29.txt`、`asyoulik.txt`、`fields.c`)，每個檔案皆設定不同的密碼。此示例說明了 **compress files with passwords** 以及 **set zip entry password** 的做法，並展示了 **zip archive with aes** 的不同加密方案。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How this works
- **TraditionalEncryptionSettings** 使用較舊的 ZipCrypto 演算法（相容於大多數 ZIP 工具）。
- **AesEcryptionSettings** 讓您選擇 AES‑128 或 AES‑256，以提供更強的安全性。
- 每一次呼叫 `CreateEntry` 時，都會傳入一個 `ArchiveEntrySettings` 物件，我們在其中同時指定壓縮方式與加密設定，從而 **password protect zip archive** 條目。

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| “Invalid password” when opening the ZIP | Mismatch between password used in code and the one entered in the extractor | Verify the exact string passed to `TraditionalEncryptionSettings` or `AesEcryptionSettings`. |
| Older extraction tools cannot open AES‑encrypted entries | Not all ZIP utilities support AES encryption | Use the traditional ZipCrypto method for maximum compatibility, or advise users to use a modern tool (e.g., 7‑Zip). |
| Large files cause `OutOfMemoryException` | Loading huge files into memory before compression | Stream the file directly using `FileStream` without loading the entire file into a `FileInfo` object. |

## Frequently Asked Questions (FAQs)

### Can I use different encryption methods for each file?
Yes, Aspose.Zip for .NET allows you to use different encryption methods for each file during compression.

### Is there a trial version available?
Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).

### How can I get support if I encounter issues?
Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance from the community and Aspose support.

### Where can I find detailed documentation for Aspose.Zip for .NET?
The documentation is available [here](https://reference.aspose.com/zip/net/).

### Can I purchase a temporary license for testing purposes?
Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Additional Quick FAQ

**Q: Does the library support .NET Core and .NET 5/6?**  
A: Yes, Aspose.Zip targets .NET Standard, making it compatible with .NET Framework, .NET Core, and .NET 5/6.

**Q: Can I add a comment to each ZIP entry?**  
A: While Aspose.Zip focuses on compression and encryption, you can store metadata in a separate manifest file inside the archive.

**Q: Is it possible to encrypt the entire archive with a single password?**  
A: You can set a password on each entry individually (as shown) or apply the same password to all entries for a simpler “zip archive with aes” approach.

## Conclusion

You’ve now mastered how to **create password protected zip** files in .NET using Aspose.Zip. By assigning individual passwords and choosing the appropriate encryption method, you can keep your data secure without sacrificing the convenience of ZIP compression. Explore other Aspose.Zip features such as streaming large files, adding custom metadata, and integrating with cloud storage for even more powerful scenarios.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Zip for .NET 23.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}