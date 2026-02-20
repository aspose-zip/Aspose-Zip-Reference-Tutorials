---
date: 2026-02-20
description: 學習如何使用 Aspose.Zip for .NET 建立 tar 壓縮檔、將檔案加入 tar 並壓縮為 tar.gz —— 一種快速、跨平台的
  TarGz 壓縮檔製作方式。
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 建立 tar 檔案並將檔案加入 tar
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 建立 tar 壓縮檔並將檔案加入 tar

## Introduction

在現代 .NET 應用程式中，**建立 tar 壓縮檔**以及**將檔案加入 tar**快速且可靠是一項常見需求——無論是打包日誌、為雲端儲存準備資料，或是建立部署套件。Aspose.Zip for .NET 提供乾淨、高效能的 API 來**將檔案加入 tar**，然後將壓縮檔壓縮成廣泛使用的 **tar.gz** 格式。在本指南中，我們將從設定專案到產生可直接使用的 `archive.tar.gz`，一步步說明完整流程。

## Quick Answers
- **我應該使用哪個函式庫？** Aspose.Zip for .NET  
- **如何將檔案加入 tar？** 使用 `TarArchive.CreateEntry` 為每個檔案。  
- **可以直接壓縮成 tar.gz 嗎？** 可以——呼叫 `SaveGzipped`。  
- **正式環境需要授權嗎？** 非試用情況下需要有效的 Aspose 授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## What is “add files to tar”?

將檔案加入 tar 壓縮檔表示將多個檔案打包成單一未壓縮的容器。tar 格式保留目錄結構與檔案中繼資料，非常適合在可選的壓縮（例如 gzip）之前進行歸檔，以**建立 tar.gz 壓縮檔**。

## Why use Aspose.Zip to compress files to tar.gz?
- **不需外部工具** – 所有操作皆在 .NET 程式碼內執行。  
- **高效能** – 基於串流的 API 能有效處理大型檔案。  
- **跨平台 tar** – 在 Windows、Linux、macOS 上皆可使用，無需變更。  
- **功能豐富** – 支援加密、密碼保護與自訂條目屬性。

## Prerequisites

在開始之前，請確保您已具備：

- 具備基本的 .NET 開發經驗。  
- Visual Studio（或任何偏好的 IDE）。  
- 已安裝 Aspose.Zip for .NET – 請參閱官方文件 [here](https://reference.aspose.com/zip/net/)。  
- 從 [this link](https://releases.aspose.com/zip/net/) 下載 Aspose.Zip 函式庫。

## Import Namespaces

在 .NET 專案中，匯入提供 tar 相關類別的命名空間：

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to add files to tar using Aspose.Zip for .NET

### Step 1: Set Your Document Directory

首先，將程式碼指向包含要封存檔案的資料夾。

```csharp
string dataDir = "Your Document Directory";
```

> **專業提示：** 建立路徑時使用 `Path.Combine` 可避免平台特定的分隔符問題。

### Step 2: Create a TarGz Archive

現在我們將建立 tar 壓縮檔，加入條目，並在同一個流暢的流程中壓縮它。

#### 2.1 Initialize the TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Add Files – the core of “add files to tar”

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

每個 `CreateEntry` 呼叫接受 **條目名稱**（檔案在 tar 內的顯示名稱）與磁碟上的 **來源檔案路徑**。您可以重複呼叫 `CreateEntry` 以在單一壓縮檔中**加入多個檔案至 tar**。

#### 2.3 Save as a Gzipped Tar (how to compress tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` 將 tar 內容寫入 gzip 串流，產生緊湊的 `archive.tar.gz` 檔案，隨時可供分發。

## Common Use Cases

| 情境 | 為何「將檔案加入 tar」有幫助 |
|----------|------------------------------|
| **日誌彙總** | 在上傳至雲端儲存前，將每日日誌打包成單一壓縮檔。 |
| **部署套件** | 從 Windows 建置管線產生可於 Linux 伺服器使用的可攜式 tar.gz 套件。 |
| **資料備份** | 保留資料夾階層與中繼資料，同時降低備份檔案大小。 |

## Common Issues and Solutions

- **找不到檔案錯誤** – 確認 `dataDir` 以正確的路徑分隔符結尾，或使用 `Path.Combine`。  
- **大型檔案導致記憶體壓力** – 使用基於串流的重載（`CreateEntry` 搭配 `Stream`）以避免將整個檔案載入記憶體。  
- **Gzip 輸出損毀** – 在呼叫 `SaveGzipped` 前，確認壓縮檔已關閉（`using` 區塊）。

## Frequently Asked Questions

**Q: Aspose.Zip for .NET 是否相容所有 .NET 應用程式？**  
A: 是的，它支援 .NET Framework、.NET Core 以及 .NET 5/6/7 專案。

**Q: 如何取得 Aspose.Zip for .NET 的臨時授權？**  
A: 前往 [temporary‑license page](https://purchase.aspose.com/temporary-license/) 申請試用授權。

**Q: 有檔案大小限制嗎？**  
A: 此函式庫已針對大型檔案進行最佳化，除系統可用記憶體外，沒有硬性大小限制。

**Q: 我可以在哪裡取得支援？**  
A: 使用社群驅動的支援論壇 [here](https://forum.aspose.com/c/zip/37) 向 Aspose 工程師與其他開發者求助。

**Q: 可以免費試用 Aspose.Zip for .NET 嗎？**  
A: 當然可以——從 [Aspose Zip releases page](https://releases.aspose.com/zip/net) 下載免費試用版。

## Conclusion

您現在已學會如何使用 Aspose.Zip for .NET **建立 tar 壓縮檔**、將檔案加入其中，並壓縮成 **tar.gz**。此方法省去外部依賴，讓您能細緻控制壓縮檔內容，且能擴展至大型資料集。歡迎探索 Aspose.Zip 的其他功能，如加密、自訂條目屬性與串流 API，以進一步提升您的歸檔工作流程。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新:** 2026-02-20  
**測試版本:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose