---
date: 2026-02-05
description: 學習如何使用 C# 及 Aspose.Zip 壓縮多個檔案並建立 .NET ZIP 壓縮檔。本步驟指南示範在 ASP.NET 專案中使用
  FileInfo 進行檔案壓縮。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 C# 中使用 Aspose.Zip for .NET 壓縮多個檔案
url: /zh-hant/net/file-compression/compress-files-fileinfo/
weight: 11
---

 craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspise.Zip for .NET 在 C# 中壓縮多個檔案

## 簡介

如果您需要以程式方式 **zip multiple files c#**，Aspose.Zip for .NET 為您提供乾淨且高效能的 API，適用於任何 .NET（包括 ASP.NET）應用程式。在本教學中，我們將示範如何使用 `FileInfo` 類別壓縮檔案，說明如何 **add files to zip**，以及為何此方法非常適合現代 .NET 專案。讓我們開始吧！

## 快速解答
- **建立 zip 壓縮檔的最簡單方法是什麼？** 使用 Aspose.Zip 的 `Archive` 類別搭配 `FileInfo` 物件。  
- **我可以一次加入多個檔案嗎？** 可以 – 只需為每個檔案建立 `FileInfo`，然後呼叫 `CreateEntry`。  
- **我需要為 ASP.NET 取得特殊授權嗎？** 在正式環境需要商業版 Aspose.Zip 授權；免費試用版可用於評估。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API 是否為執行緒安全？** 是，只要每個執行緒使用各自的 `Archive` 實例即可。  
- **如何在不將檔案載入記憶體的情況下 zip files c#？** 使用 `FileInfo` 物件 – 它會直接串流資料。

## 如何在 C# 中 zip 多個檔案
Zip 壓縮檔將一個或多個檔案打包成單一的壓縮容器。這可減少儲存空間、加快網路傳輸，並簡化發佈流程。無論是傳送日誌、匯出報告，或為客戶打包資產，掌握 **how to zip files c#** 的程式化方法都是任何 .NET 開發人員的寶貴技能。

## 為什麼使用 Aspose.Zip 加入檔案至 Zip？
- **零外部相依性** – 純 .NET 實作。  
- **完整控制壓縮等級與編碼**（ASCII、UTF‑8 等）。  
- **支援大型檔案**（> 4 GB）與密碼保護。  
- **跨 .NET Framework、.NET Core 與 .NET 5+ 保持一致的 API**。

## 先決條件

在深入程式碼之前，請確保您已具備以下條件：

1. 已安裝 **Aspose.Zip for .NET**。從 [Aspose.Zip 下載頁面](https://releases.aspose.com/zip/net/) 取得最新套件。  
2. 您電腦上有一個資料夾，內含欲壓縮的檔案（例如 `alice29.txt` 與 `fields.c`）。

## 匯入命名空間

在任何需要處理 zip 壓縮檔的 C# 檔案中，加入以下 `using` 陳述式：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

這些命名空間讓您可以使用 `Archive` 類別、儲存選項以及標準 I/O 工具。

## 逐步指南

### 步驟 1：設定文件目錄

首先，定義保存來源檔案的資料夾。將佔位符替換為您系統上的絕對或相對路徑：

```csharp
string dataDir = "Your Document Directory";
```

> **專業提示：** 使用 `Path.Combine` 以跨平台方式組合路徑。

### 步驟 2：開啟 Zip 檔案以寫入

建立指向輸出 zip 檔的 `FileStream`。此串流以 **Create** 模式開啟，會覆寫同名的既有檔案：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步驟 3：為每個來源檔案準備 `FileInfo` 物件

`FileInfo` 讓 Aspose.Zip 直接存取磁碟上的實體檔案。為每個欲壓縮的檔案建立一個實例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **為什麼使用 `FileInfo`？** 它避免將整個檔案載入記憶體，對大型檔案特別有幫助。

### 步驟 4：建立 Archive 並加入條目

實例化 `Archive` 物件，然後對每個 `FileInfo` 呼叫 `CreateEntry`。第一個參數是檔案在 zip 內的名稱，第二個參數是來源的 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步驟 5：使用指定編碼儲存 Zip 壓縮檔

最後，將 Archive 儲存至先前開啟的 `FileStream`。此處使用 ASCII 編碼作為條目名稱，但若檔名包含非 ASCII 字元，可改為 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

當 `using` 區塊結束時，串流會自動關閉，zip 檔即可使用。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|-------|-------|-----|
| **空的 zip 檔** | `FileInfo` 指向不存在的路徑 | 確認 `dataDir` 與檔名；在建立條目前使用 `File.Exists` 檢查。 |
| **檔名編碼不正確** | 使用預設編碼處理非 ASCII 名稱 | 在 `ArchiveSaveOptions` 中設定 `Encoding = Encoding.UTF8`。 |
| **大型檔案導致 OutOfMemoryException** | 將整個檔案載入記憶體 | `FileInfo` 會串流檔案；確保未在其他地方將檔案讀入位元組陣列。 |
| **權限被拒絕** | 應用程式沒有輸出資料夾的寫入權限 | 以適當權限執行應用程式或選擇可寫入的目錄。 |

## 常見問與答

**Q: 我可以為 zip 壓縮檔加入密碼保護嗎？**  
A: 可以。建立 `Archive` 後，在呼叫 `Save` 前設定 `archive.Password = "yourPassword"`。

**Q: 是否可以更新已存在的 zip 檔案？**  
A: Aspose.Zip 支援使用 `Archive.Open` 開啟現有壓縮檔，然後加入新條目。

**Q: 如何在 ASP.NET MVC 控制器中壓縮檔案？**  
A: 同樣的程式碼即可，只需確保將輸出串流以 `FileResult` 回傳給客戶端。

**Q: Aspose.Zip 支援哪些加密演算法？**  
A: 它支援標準的 ZipCrypto 與 AES‑256 加密。

**Q: 如果需要遞迴壓縮資料夾該怎麼做？**  
A: 迭代 `Directory.GetFiles`（以及子資料夾），為每個檔案建立 `FileInfo`，再將其加入壓縮檔。

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## 結論

現在您已了解如何使用 Aspose.Zip for .NET **how to zip multiple files c#**，以及如何 **add files to zip**，並且明白此方法為 ASP.NET 與其他 .NET 應用程式的理想選擇。可嘗試不同的壓縮等級、編碼與加密選項，以符合您的具體需求。祝壓縮愉快！

---

**最後更新：** 2026-02-05  
**測試環境：** Aspose.Zip for .NET 24.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}