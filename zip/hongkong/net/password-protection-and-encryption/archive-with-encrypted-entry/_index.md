---
date: 2026-03-05
description: 學習如何在 .NET 中使用 Aspose.Zip 建立具 AES 加密的 7z 檔案，以實現安全壓縮。
linktitle: Archive with Encrypted Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 .NET 中使用 Aspose.Zip 建立具安全封存功能的 7z 檔案
url: /zh-hant/net/password-protection-and-encryption/archive-with-encrypted-entry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip 在 .NET 中建立具安全封存功能的 7z 檔案

## Introduction

如果您需要建立既緊湊又受保護的 **how to create 7z** 壓縮檔，您來對地方了。在現代 .NET 應用程式中，安全封存對於保護智慧財產、遵守資料隱私法規以及降低儲存成本至關重要。Aspose.Zip for .NET 為您提供簡易的 API，能產生 **Seven Zip** 壓縮檔、套用 **AES 加密**，甚至 **password protect 7z** 檔案——全部在 C# 環境中完成。

在本教學中，我們將逐步說明建立 7z 壓縮檔、加密 zip 條目以及將結果儲存至磁碟的完整流程。完成後，您將了解如何 **how to encrypt zip** 檔案、使用 **seven zip compression**，並將安全封存整合至任何 .NET 專案中。

## Quick Answers
- **哪個函式庫支援 7z 建立？** Aspose.Zip for .NET  
- **我可以加密單一條目嗎？** Yes, using `SevenZipAESEncryptionSettings`  
- **是否提供密碼保護？** Absolutely – the AES key acts as the password  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **生產環境是否需要授權？** A commercial license is required for production use  

## What is a 7z Archive and Why Use AES Encryption?
**7z** 檔案是一種由 7‑Zip 工具建立的高壓縮率封存格式。它支援 LZMA/LZMA2 等先進演算法以及強大的 **AES‑256** 加密，讓它在 **secure archiving .net** 場景中同時兼顧容量與機密性，表現理想。

## Why Choose Aspose.Zip for .NET?
- **原生 .NET API** – 無需外部執行檔或原生互操作。  
- **完整控制** 壓縮等級、加密設定與條目串流。  
- **跨平台** 支援 Windows、Linux 與 macOS。  
- **完整文件** 與活躍社群支援。  

## Prerequisites

- 具備 .NET 開發環境（Visual Studio、VS Code 或 Rider）。  
- 已安裝 Aspose.Zip for .NET – 請參閱文件 **[here](https://reference.aspose.com/zip/net/)**。  
- 從 **[download link](https://releases.aspose.com/zip/net/)** 下載函式庫。  
- 具備 C# 與檔案 I/O 的基本知識。  

## Import Namespaces

在您的 C# 專案中，先匯入所需的命名空間：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Step 1: Set the Resource Directory Path

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create a Seven Zip File with AES Encryption

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ExEnd: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

**Explanation:**  
在此步驟中，我們開啟（或建立）名為 **archive.7z** 的檔案，新增一個名為 **entry1.bin** 的條目，並使用密碼 `"test1"` 套用 **AES 加密**。`SevenZipLZMACompressionSettings` 物件負責壓縮演算法，而 `SevenZipAESEncryptionSettings` 處理加密。若有需要，您可以重複呼叫 `CreateEntry` 以加入更多檔案，並為每個檔案設定各自的加密配置。

### 如何單獨加密 zip 條目
如果需要為 **encrypt zip entry** 物件使用不同密碼，只需在每次呼叫 `CreateEntry` 時實例化新的 `SevenZipAESEncryptionSettings` 即可。

### 如何為 7z 檔案設定密碼保護
在 `SevenZipAESEncryptionSettings` 中提供的密碼即為整個封存的 **password protection**。開啟封存時，必須提供相同的密碼。

## Common Issues and Troubleshooting

| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| 開啟封存時出現 “Invalid password” 錯誤 | 密碼不符或缺少 `SevenZipAESEncryptionSettings` | 確認密碼字串完全相符（區分大小寫）。 |
| 封存大小大於預期 | 使用預設壓縮等級 | 調整 `SevenZipLZMACompressionSettings`（例如，將 `CompressionLevel = CompressionLevel.High`）。 |
| 非 Windows 作業系統上發生執行時例外 | 缺少原生相依性 | 確保使用最新的 Aspose.Zip 版本，該版本已捆綁所需的原生程式庫。 |

## Conclusion

您現在已學會使用 Aspose.Zip for .NET 以 AES 加密建立 **how to create 7z** 壓縮檔。此技術讓您能打造 **secure archiving .net** 解決方案，保護敏感資料同時將檔案大小維持在最低。歡迎探索其他設定，例如自訂壓縮等級或多執行緒封存，以微調特定情境的效能。

## FAQs

### 我可以在非商業專案中使用 Aspose.Zip for .NET 嗎？
Yes, Aspose.Zip for .NET can be used in both commercial and non‑commercial projects.

### 我該如何取得 Aspose.Zip for .NET 的臨時授權？
Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.

### 是否有 Aspose.Zip for .NET 的社群支援？
Yes, visit the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** for community support.

### 除了 LZMA，還支援其他壓縮演算法嗎？
Aspose.Zip for .NET supports multiple algorithms, including LZMA, LZMA2, BZIP2, and PPMd. Check the documentation for full details.

### 我可以進一步自訂加密設定嗎？
Absolutely! Explore the documentation for advanced encryption options such as custom key lengths and iteration counts.

## Frequently Asked Questions

**Q: 如何在同一個 7z 封存中加入多個加密條目？**  
A: 重複呼叫 `archive.CreateEntry`，若需要不同密碼，為每個條目提供獨立的 `SevenZipAESEncryptionSettings`。

**Q: Aspose.Zip 是否支援串流大型檔案而不需全部載入記憶體？**  
A: 可以，您可以將 `FileStream` 或其他串流傳遞給 `CreateEntry`，以有效處理大型檔案。

**Q: 我可以使用 Aspose.Zip 解密已存在的 7z 封存嗎？**  
A: 使用接受串流的 `SevenZipArchive` 建構子，並透過 `SevenZipAESEncryptionSettings` 提供正確的密碼。

**Q: 能否為每個條目單獨設定壓縮等級？**  
A: 可以，在呼叫 `CreateEntry` 前為每個條目配置 `SevenZipLZMACompressionSettings`。

**Q: 官方測試過哪些 .NET 執行環境與 Aspose.Zip 相容？**  
A: .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5、.NET 6 以及更高版本。

---

**最後更新：** 2026-03-05  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}