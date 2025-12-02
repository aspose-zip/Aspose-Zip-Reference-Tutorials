---
date: 2025-11-29
description: 學習如何使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarZ——一步一步的高效 .NET 檔案處理指南。
language: zh-hant
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarZ
url: /net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將檔案加入 tar 並壓縮為 TarZ（使用 Aspose.Zip for .NET）

## 簡介

如果您需要 **將檔案加入 tar**，然後將壓縮檔案轉為 TarZ 格式，Aspose.Zip for .NET 可讓整個流程輕鬆無憂。在本教學中，我們將逐步說明每個步驟——從設定專案、建立 tar 壓縮檔、加入檔案，到最後儲存為 .tar.z 壓縮檔。完成後，您將擁有一段可在任何 .NET 應用程式中直接使用的可重用程式碼片段。

## 快速答覆
- **哪個函式庫負責建立 tar？** Aspose.Zip for .NET  
- **程式碼行數大約多少？** 約 15 行（不含註解）  
- **測試是否需要授權？** 可使用免費試用版；正式環境需購買授權。  
- **支援的 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上  
- **能壓縮資料夾而不只是單一檔案嗎？** 可以——您可以使用迴圈一次加入整個目錄。  

## 什麼是 **將檔案加入 tar**？

將檔案加入 tar 壓縮檔會將它們打包成單一的未壓縮容器，並保留目錄結構與檔案的中繼資料。Tar 是傳統的 Unix 格式，也是許多壓縮工作流程的基礎，包括本指南中使用的 TarZ 格式。

## 為什麼在壓縮為 TarZ 前先將檔案加入 tar？

- **可移植性** – tar 壓縮檔可在不同平台間使用，無需擔心單一檔案的處理方式。  
- **速度** – 建立 tar 容器速度快；隨後的 Z‑壓縮僅專注於縮小檔案大小。  
- **相容性** – 許多舊有工具在套用 gzip 類型壓縮前，需要先有 `.tar`，這正是 `.tar.z` 所提供的。  

## 先決條件

在進入程式碼之前，請先確保您已具備以下條件：

- 已安裝 **Aspose.Zip for .NET**。可從官方網站[此處](https://releases.aspose.com/zip/net/)下載。  
- 您電腦上有一個資料夾，內含欲壓縮的檔案。請將佔位路徑替換為實際目錄路徑。

## 匯入命名空間

在 C# 檔案的頂部加入所需的 `using` 陳述式：

```csharp
using System;
using Aspose.Zip.Tar;
```

## 逐步指南

### 步驟 1：定義文件目錄

```csharp
string dataDir = "Your Document Directory";
```

> **小技巧：** 若需動態組合路徑，請使用 `Path.Combine`；可避免在不同作業系統上遺漏路徑分隔符。

### 步驟 2：建立 Tar 壓縮檔並加入檔案

#### 2.1：建立 Tar 壓縮檔實例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2：將檔案加入壓縮檔  

在 `using` 區塊內，加入您想要包含的每個檔案：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以依需求多次呼叫 `CreateEntry`，或使用迴圈遍歷目錄以程式方式加入檔案。

#### 2.3：儲存壓縮的 TarZ 檔案  

加入所有項目後，將 tar 壓縮檔壓縮為 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

產生的 `archive.tar.z` 檔案會位於您於 `dataDir` 指定的同一資料夾中。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **找不到檔案** | 路徑錯誤或缺少檔案副檔名 | 確認 `dataDir` 以路徑分隔符結尾，且檔名正確。 |
| **存取被拒** | 目標資料夾權限不足 | 以適當權限執行應用程式，或選擇可寫入的資料夾。 |
| **壓縮檔大於預期** | 原始檔案已經是壓縮過的（例如圖片、影片） | TarZ 最適合文字或日誌檔案；對已壓縮的檔案可保持原樣。 |

## 常見問答

**問：我可以使用 Aspose.Zip for .NET 壓縮整個資料夾嗎？**  
**答：** 當然可以。使用 `Directory.GetFiles` 迴圈，對每個檔案呼叫 `CreateEntry`，保留相對路徑。

**問：Aspose.Zip for .NET 有提供試用版嗎？**  
**答：** 有，您可從[此處](https://releases.aspose.com/)下載免費試用版，探索 Aspose.Zip for .NET 的功能。

**問：在哪裡可以找到 Aspose.Zip for .NET 的完整文件？**  
**答：** 文件可在[此處](https://reference.aspose.com/zip/net/)取得，提供關於函式庫功能與使用方式的詳細說明。

**問：如何取得 Aspose.Zip for .NET 的支援？**  
**答：** 請前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 尋求協助、分享經驗，並與社群互動。

**問：我可以取得 Aspose.Zip for .NET 的臨時授權嗎？**  
**答：** 可以，若需要臨時授權，請於[此處](https://purchase.aspose.com/temporary-license/)取得。

## 結論

您現在已學會如何 **將檔案加入 tar**，並使用 Aspose.Zip for .NET 將結果壓縮為 TarZ 壓縮檔。此方法可產生乾淨且可移植的套件，便於傳輸、儲存或進一步處理。歡迎自行調整程式碼以批次處理目錄、整合至建置流程，或與其他 Aspose 元件結合，打造更豐富的文件工作流程。

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
