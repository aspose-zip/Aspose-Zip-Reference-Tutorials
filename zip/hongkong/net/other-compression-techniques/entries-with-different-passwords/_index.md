---
date: 2025-12-18
description: 學習如何使用 Aspose.Zip for .NET 為 ZIP 檔案設定不同的密碼進行加密。本指南將示範如何以密碼壓縮檔案，並在 C#
  中建立 7z 壓縮檔。
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 Aspose.Zip for .NET 中使用不同密碼加密 ZIP 檔案
url: /zh-hant/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Zip for .NET 中使用不同密碼加密 ZIP 檔案

## 介紹

如果您需要 **how to encrypt zip** 壓縮檔，同時為每個條目設定獨立密碼，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.Zip for .NET 建立一個 7‑zip 壓縮檔，讓每個檔案都有唯一的密碼。完成後，您將了解為何需要逐條目加密、如何設定以及如何在自己的專案中驗證結果。

## 快速回答
- **What does “encrypt zip” mean?** 它是指對 ZIP/7z 壓縮檔的內容套用基於密碼的保護（AES 或 ZipCrypto）。  
- **Can each entry have a different password?** 可以 — Aspose.Zip 允許您為每個檔案指定不同的密碼。  
- **Which .NET versions are supported?** 支援所有現代的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **Do I need a license for production?** 生產環境需要商業授權；同時提供免費試用版。  
- **What compression format is used in the example?** 範例會建立使用 AES‑256 加密的 7z 壓縮檔。

## 什麼是使用 Aspose.Zip 的 “how to encrypt zip”？

加密 ZIP（或 7z）檔案即是確保其條目在未輸入正確密碼前無法被開啟。Aspose.Zip for .NET 同時支援傳統的 ZipCrypto 與更強大的 AES 加密，且允許您針對每個條目設定加密參數，提供細緻的安全控制。

## 為什麼要為每個條目使用不同的密碼？

- **安全分段**：即使其中一個密碼外洩，其他檔案仍保持受保護。  
- **法規遵循**：某些產業要求對不同資料類別使用獨立憑證。  
- **使用者專屬存取**：您可以將同一壓縮檔分發給多位使用者，讓每位使用者只能解開其授權的檔案。

## 前置條件

在開始之前，請確保您已具備以下條件：

- **Aspose.Zip for .NET** 已安裝 — 請參閱官方 [documentation](https://reference.aspose.com/zip/net/) 取得下載與安裝說明。  
- 在本機建立一個資料夾，用來放置來源檔案（即「Document Directory」）。  
- 具備基本的 C# 與 Visual Studio（或您慣用的 .NET IDE）使用經驗。

## 匯入命名空間

我們先引入需要使用的命名空間。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步驟 1：設定文件目錄

定義保存欲壓縮檔案的路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立具有不同密碼的條目

以下是本教學的核心。我們開啟一個新的 7z 檔案，建立三個 `FileInfo` 物件，並以各自的 AES 密碼將它們加入為條目。

```csharp
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
```

### 工作原理

- `SevenZipArchive` 是 7‑z 壓縮檔的容器。  
- `CreateEntry` 需要提供條目名稱、來源檔案、是否覆寫的旗標，以及 `SevenZipEntrySettings` 物件。  
- 在 `SevenZipEntrySettings` 中，我們同時提供兩個設定物件：一個用於壓縮（`SevenZipStoreCompressionSettings`），另一個用於加密（`SevenZipAESEncryptionSettings`）。  
- 每次呼叫都傳入 **不同的密碼**（`"test1"`、`"test2"`、`"test3"`），從而實現逐條目保護。

## 步驟 3：驗證

壓縮檔儲存完成後，您可以輸出簡單的確認訊息。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

執行程式後，使用 7‑Zip 等工具開啟 `archive.7z`。系統會針對每個條目要求輸入密碼，證實各條目的密碼確實不同。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **Incorrect password error** | 密碼字串中包含多餘的空格或不可見字元。 | 使用 `Trim` 去除多餘空格（`new SevenZipAESEncryptionSettings(password.Trim())`）。 |
| **Archive not opening in older tools** | 部分舊版 ZIP 工具不支援 7z 使用的 AES‑256 加密。 | 改用支援的新版解壓縮工具（如 7‑Zip 19.00 以上）。 |
| **File not added to archive** | 來源檔案路徑錯誤或檔案不存在。 | 檢查 `dataDir` 與檔名，或使用 `Path.Combine(dataDir, "data1.bin")`。 |

## 常見問答

### Q1: Aspose.Zip for .NET 是否相容所有 .NET 版本？

A1: 是的，Aspose.Zip for .NET 設計上可無縫整合至所有版本的 .NET Framework。

### Q2: 我可以在商業專案中使用 Aspose.Zip for .NET 嗎？

A2: 當然可以！Aspose.Zip for .NET 提供商業授權，更多購買資訊請參考 [here](https://purchase.aspose.com/buy)。

### Q3: 是否提供免費試用？

A3: 有的，您可以透過免費試用版探索 Aspose.Zip for .NET 的功能。立即開始請前往 [here](https://releases.aspose.com/)。

### Q4: 如何取得 Aspose.Zip for .NET 的支援？

A4: 如有任何問題或需要協助，請造訪 [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37)。

### Q5: 我可以在沒有永久授權的情況下使用 Aspose.Zip for .NET 嗎？

A5: 可以，您可以取得臨時授權以滿足短期需求。詳情請見 [here](https://purchase.aspose.com/temporary-license/)。

## 結論

您已學會如何使用 Aspose.Zip for .NET 以逐條目密碼加密 ZIP 檔案。此技巧讓您能針對每個檔案單獨保護，符合更嚴格的安全需求，同時簡化使用者專屬的分發方式。歡迎嘗試其他壓縮設定、處理更大量的檔案，或將此邏輯整合至即時產生安全壓縮檔的 Web 服務中。

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.Zip for .NET 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}