---
date: 2025-12-25
description: 學習如何使用 Aspose.Zip for .NET 以 C# 建立 7z 壓縮檔。此一步一步的指南向您展示如何以 C# 壓縮檔案及有效地將目錄壓縮為
  7z。
linktitle: Create SevenZip Entries
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: c# 建立 7z 壓縮檔 – 使用 Aspose.Zip for .NET 建立 SevenZip 條目
url: /zh-hant/net/sevenzip-compression/create-sevenzip-entries/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# 建立 7z 壓縮檔 – 使用 Aspose.Zip for .NET 建立 SevenZip 條目

## 簡介

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Zip for .NET 建立 SevenZip 條目並將其儲存為 7z 壓縮檔。  
- **主要目標關鍵字為何？** c# create 7z archive。  
- **需要授權嗎？** 測試可使用臨時授權；正式環境需購買正式授權。  
- **可以在 Linux 上執行嗎？** 可以 – Aspose.Zip for .NET 為跨平台。  
- **實作大約需要多久？** 基本壓縮檔約 5‑10 分鐘即可完成。

## 先決條件

在開始本教學之前，請確保已具備以下先決條件：

- 具備 C# 與 .NET 開發的基本知識。  
- 使用如 Visual Studio 等整合開發環境 (IDE)。  
- 已安裝 Aspose.Zip for .NET 函式庫。若未安裝，可於 [here](https://releases.aspose.com/zip/net/) 下載。

## 匯入命名空間

在 C# 專案中，請先匯入使用 Aspose.Zip 所需的命名空間。於程式碼開頭加入以下程式碼：

```csharp
using Aspose.Zip.SevenZip;
using System;
```

接下來，我們將把範例拆解為多個步驟，以便深入了解。

## c# 建立 7z 壓縮檔 – 步驟說明指南

### 步驟 1：設定資源目錄路徑

在建立 SevenZip 條目之前，先設定資源目錄的路徑。將 `dataDir` 變數中的 `"Your Document Directory"` 替換為實際路徑。

```csharp
string dataDir = "Your Document Directory";
```

> **小技巧：** 使用絕對路徑可避免程式在不同工作目錄執行時產生混淆。

### 步驟 2：建立 SevenZip 條目

現在，我們進入流程核心 – 建立 SevenZip 條目。此步驟會 **將目錄壓縮為 7z** 格式。

```csharp
//ExStart: CreateSevenZipEntries
using (SevenZipArchive archive = new SevenZipArchive())
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip.7z");
}
//ExEnd: CreateSevenZipEntries
```

上述程式碼會初始化 `SevenZipArchive`，將指定資料夾內的所有檔案加入，並將壓縮檔寫入 **SevenZip.7z**。

### 步驟 3：顯示成功訊息

為確保流程順利完成，顯示成功訊息：

```csharp
Console.WriteLine("Successfully Created a Seven Zip File");
```

現在您已擁有可供分享的 **7z 壓縮檔**，可進行傳輸、儲存或後續處理。

## 為什麼要使用 Aspose.Zip for .NET？

- **高效能：** 最佳化的壓縮演算法，效能優於多數開源方案。  
- **跨平台支援：** 在 Windows、Linux 與 macOS 上皆可執行，無需修改程式碼。  
- **豐富 API：** 提供對壓縮等級、加密與壓縮檔結構的細緻控制。  
- **無外部相依性：** 不需安裝原生 7‑Zip 二進位檔。

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| **壓縮檔為空** | 確認 `dataDir` 指向的資料夾內有檔案。可使用 `Directory.Exists` 進行驗證。 |
| **存取被拒錯誤** | 確保應用程式對來源資料夾具有讀取權限，且對輸出路徑具有寫入權限。 |
| **大型檔案導致 OutOfMemoryException** | 使用具串流選項的 `SevenZipArchive`，或將壓縮檔分割為多個部分。 |

## 常見問答

### **我可以在 Windows 與 Linux 環境中使用 Aspose.Zip for .NET 嗎？**
可以，Aspose.Zip for .NET 為跨平台，可在 Windows 與 Linux 環境中無縫使用。

### **是否提供測試用的臨時授權？**
當然可以！您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權，探索 Aspose.Zip 的完整功能。

### **在哪裡可以找到 Aspose.Zip for .NET 的完整文件？**
欲取得詳細文件，請參考 [Aspose.Zip for .NET Documentation](https://reference.aspose.com/zip/net/)。

### **實作過程中若遇到問題或有特定疑問該怎麼辦？**
歡迎前往 [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) 尋求協助，社群與支援團隊會提供協助！

### **在購買前是否有免費試用？**
可以，您可於 [here](https://releases.aspose.com/) 取得免費試用，先行體驗功能再決定是否購買。

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}