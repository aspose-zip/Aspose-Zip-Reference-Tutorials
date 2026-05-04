---
date: 2026-02-28
description: 學習如何使用 Aspose.Zip for .NET 壓縮檔案並設定密碼、加密 ZIP 壓縮檔，內容涵蓋 7z 密碼保護以及在 C# 中對單一檔案設定
  ZIP 密碼。
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮檔案並設定密碼，並以不同密碼加密 ZIP 條目
url: /zh-hant/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 壓縮檔案並以不同密碼加密 ZIP 條目

## 介紹

如果您需要 **compress files with password** 並且為每個條目設定各自的密碼，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.Zip for .NET 建立一個 7‑zip 壓縮檔，讓每個檔案都以唯一的密碼受到保護。完成後，您將了解為何每條目加密很重要、如何設定，以及如何在自己的專案中驗證結果。

## 快速解答
- **What does “encrypt zip” mean?** 它表示對 ZIP/7z 壓縮檔的內容套用基於密碼的保護（AES 或 ZipCrypto）。  
- **Can each entry have a different password?** 是的 — Aspose.Zip 允許您為每個檔案指派不同的密碼。  
- **Which .NET versions are supported?** 支援所有現代的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **Do I need a license for production?** 生產環境需要商業授權；亦提供免費試用版。  
- **What compression format is used in the example?** 範例會建立使用 AES‑256 加密的 7z 壓縮檔。

## 使用 Aspose.Zip for .NET 壓縮檔案並設定密碼

在本節中，我們直接回應主要問題，並為接下來的逐步指南奠定基礎。

## 使用 Aspose.Zip 進行「encrypt zip」是什麼意思？

對 ZIP（或 7z）檔案進行加密，即是保護其條目，使其在未提供正確密碼時無法開啟。Aspose.Zip for .NET 同時支援傳統的 ZipCrypto 與更強大的 AES 加密，且允許您針對每個條目設定加密參數，提供細緻的安全控制。

## 為何每個條目使用不同的密碼？

- **Security segmentation:** 若其中一個密碼外洩，其他檔案仍可保持受保護。  
- **Regulatory compliance:** 某些產業需對不同資料類別使用獨立憑證。  
- **User‑specific access:** 您可以將同一壓縮檔分發給多位使用者，讓每位使用者僅能解鎖其被授權檢視的檔案。

## 前置條件

在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 已安裝 – 請參閱官方[文件](https://reference.aspose.com/zip/net/)取得下載與安裝說明。  
- 您電腦上的一個資料夾，用於存放來源檔案（即「Document Directory」）。  
- 具備 C# 與 Visual Studio（或您偏好的 .NET IDE）的基本知識。

## 匯入命名空間

我們先引入包含所需類別的命名空間。

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

## 步驟 1：設定 Document Directory

定義保存欲壓縮檔案之路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立具有不同密碼的條目

以下為本教學的核心。我們開啟一個新的 7z 檔案，建立三個 `FileInfo` 物件，並將每個檔案以各自的 AES 密碼加入為條目。

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

### 工作原理說明

- `SevenZipArchive` 為 7‑z 壓縮檔的容器。  
- `CreateEntry` 接受條目名稱、來源檔案、覆寫旗標，以及 `SevenZipEntrySettings` 物件。  
- 在 `SevenZipEntrySettings` 中，我們提供兩個設定物件：一個用於壓縮（`SevenZipStoreCompressionSettings`），另一個用於加密（`SevenZipAESEncryptionSettings`）。  
- 每次呼叫皆提供 **不同的密碼**（`"test1"`、`"test2"`、`"test3"`），實現每條目保護。

## 步驟 3：驗證

壓縮檔儲存後，您可以輸出簡單的確認訊息。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

執行程式，然後使用 7‑Zip 等工具開啟 `archive.7z`。系統會針對每個條目要求輸入密碼，以確認密碼確實不同。

## 常見問題與解決方案

| Issue | Reason | Fix |
|-------|--------|-----|
| **Incorrect password error** | 密碼字串包含多餘的空格或不可見字元。 | 修剪密碼字串 (`new SevenZipAESEncryptionSettings(password.Trim())`)。 |
| **Archive not opening in older tools** | 某些舊版 ZIP 工具不支援 7z 使用的 AES‑256 加密。 | 使用新版解壓縮工具（7‑Zip 19.00 以上）。 |
| **File not added to archive** | 來源檔案路徑錯誤或檔案不存在。 | 確認 `dataDir` 及檔名，或使用 `Path.Combine(dataDir, "data1.bin")`。 |

## 常見問答

### Q1：Aspose.Zip for .NET 是否相容所有 .NET 版本？

A1：是的，Aspose.Zip for .NET 設計上能無縫整合所有 .NET Framework 版本。

### Q2：我可以在商業專案中使用 Aspose.Zip for .NET 嗎？

A2：當然可以！Aspose.Zip for .NET 提供商業授權，您可在此處了解購買方式：[here](https://purchase.aspose.com/buy)。

### Q3：是否提供免費試用？

A3：是的，您可以透過免費試用體驗 Aspose.Zip for .NET 的功能。立即開始[here](https://releases.aspose.com/)。

### Q4：如何取得 Aspose.Zip for .NET 的支援？

A4：如有任何問題或需要協助，請前往 [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37)。

### Q5：我可以在沒有永久授權的情況下使用 Aspose.Zip for .NET 嗎？

A5：是的，您可以取得臨時授權以滿足短期需求。更多資訊請參考[here](https://purchase.aspose.com/temporary-license/)。

## 結論

您剛剛學會了 **how to compress files with password**，並使用 Aspose.Zip for .NET 為 ZIP 壓縮檔的每個條目設定不同密碼。此技巧讓您能個別保護每個檔案，符合更嚴格的安全需求，同時簡化針對使用者的分發。歡迎嘗試其他壓縮設定、較大的檔案集合，或將此邏輯整合至即時產生安全壓縮檔的 Web 服務中。

---

**最後更新:** 2026-02-28  
**測試環境:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}