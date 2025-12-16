---
date: 2025-12-12
description: 學習如何使用 Aspose.Zip 快速在 .NET 中解壓縮檔案。逐步教學 .NET 壓縮檔解壓與 C# 從壓縮檔提取。
linktitle: Decompressing a File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中解壓縮檔案
url: /zh-hant/net/file-decompression/decompress-file/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 解壓縮 .NET 檔案

## 介紹

在 .NET 開發的世界裡，學會如何 **decompress file .NET** 高效執行對於效能關鍵的應用程式至關重要。Aspose.Zip for .NET 提供一套簡潔且高效能的 API，讓您在不必處理低階串流管理的情況下完成 .NET 壓縮檔案的解壓縮。本教學將帶您走過完整的 **Aspose.Zip extraction** 範例——開啟 Lzip 壓縮檔並僅用幾行 C# 程式碼將其內容解壓縮。

## 快速答覆
- **什麼函式庫負責 .NET 壓縮檔案解壓縮？** Aspose.Zip for .NET  
- **哪個方法在 C# 中解壓 Lzip 壓縮檔？** `LzipArchive.Extract`  
- **生產環境是否需要授權？** 是，非評估使用需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **基本解壓大約需要多久？** 小檔案通常在一秒內完成。

## 什麼是「decompress file .NET」？
在 .NET 中解壓縮檔案指的是讀取壓縮檔（例如 ZIP、LZIP、GZIP），並將其原始內容寫回檔案系統。Aspose.Zip 抽象掉複雜性，讓您專注於業務邏輯，而不必關心壓縮演算法的細節。

## 為什麼使用 Aspose.Zip 進行 .NET 壓縮檔案解壓縮？
- **零相依性** – 無需外部原生二進位檔。  
- **豐富格式支援** – ZIP、GZIP、TAR、LZIP 等。  
- **執行緒安全 API** – 適用於 Web 服務與背景工作。  
- **完整文件** 與 **Aspose.Zip 教學** 資源。

## 前置條件

- **Aspose.Zip for .NET** – 安裝 NuGet 套件或下載程式庫。文件可於 [此處](https://reference.aspose.com/zip/net/) 找到。  
- **開發環境** – Visual Studio 2022、.NET 6 SDK，或任何支援 C# 的 IDE。  
- **您的文件目錄** – 磁碟上存放壓縮檔 (`archive.lz`) 且欲儲存解壓後檔案的資料夾。

## 匯入命名空間

首先，匯入檔案 I/O 與 Aspose.Zip Lzip 支援所需的命名空間：

```csharp
using System;
using System.IO;
using Aspose.Zip.Lzip;
```

## .NET 壓縮檔案解壓縮：設定工作資料夾

```csharp
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為包含 `archive.lz` 的絕對或相對路徑。將路徑存於變數中可提升程式碼的可重用性與維護性。

## 步驟 1：使用 C# 開啟並解壓 Lzip 壓縮檔

核心的 **c# extract from archive** 操作只需一個簡短的 `using` 區塊，即可開啟 Lzip 檔並將解壓後資料寫入新檔。

```csharp
//ExStart: OpenLzipArchive
using (var archive = new LzipArchive(Path.Combine(dataDir, "archive.lz")))
{
    using (var extracted = File.Create(Path.Combine(dataDir, "output.txt")))
    {
        archive.Extract(extracted);
    }
}
//ExEnd: OpenLzipArchive
Console.WriteLine("Successfully Opened Lzip Archive");
```

此程式碼片段示範 **extract lzip archive c#** 的模式：

1. **建立** 指向來源檔案的 `LzipArchive` 實例。  
2. **建立** 目的檔案 (`output.txt`)。  
3. **呼叫** `Extract` 以寫入解壓後的位元組。  
4. `using` 陳述式確保所有串流自動關閉。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| `FileNotFoundException` | `dataDir` 路徑錯誤 | 核對資料夾路徑，確保 `archive.lz` 存在。 |
| `UnauthorizedAccessException` | 權限不足無法寫入 | 以適當權限執行應用程式，或選擇可寫入的資料夾。 |
| 輸出檔案為空 | 壓縮檔損毀或非 Lzip 檔案 | 確認來源檔案為有效的 Lzip 壓縮檔；必要時使用 `LzipArchive.IsValid`。 |

## 常見問答

**問：Aspose.Zip 是否相容所有 .NET 應用程式？**  
答：是，Aspose.Zip for .NET 可整合於桌面、Web、雲端與微服務等各類專案。

**問：我可以在個人與商業專案中使用 Aspose.Zip 嗎？**  
答：當然可以。此函式庫提供評估、個人與商業使用的彈性授權。

**問：如何取得 Aspose.Zip for .NET 的支援？**  
答：請前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 提問並與社群交流。

**問：是否提供免費試用？**  
答：是的，您可於 [此處](https://releases.aspose.com/) 下載免費試用版。

**問：在哪裡購買 Aspose.Zip for .NET？**  
答：購買授權請前往 [購買頁面](https://purchase.aspose.com/buy)。

## 結論

您現在已掌握如何使用 Aspose.Zip 的簡潔 API **decompress file .NET**。此方法簡化 .NET 壓縮檔案的解壓縮流程，減少樣板程式碼，且能在大規模應用中良好擴展。欲了解更深入的情境——如受密碼保護的壓縮檔、多檔案解壓或自訂壓縮等級——請參考完整的 [文件](https://reference.aspose.com/zip/net/)。

---

**最後更新：** 2025-12-12  
**測試版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
