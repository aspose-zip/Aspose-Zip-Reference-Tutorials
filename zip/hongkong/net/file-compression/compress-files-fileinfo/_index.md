---
date: 2026-07-18
description: 了解如何使用 Aspose.Zip for .NET 將資料夾加入 Zip 以及將檔案加入 Zip。本分步指南示範如何在 ASP.NET
  專案中使用 FileInfo 壓縮檔案。
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: 使用 FileInfo 壓縮檔案
og_description: 使用 Aspose.Zip for .NET 將資料夾加入 Zip。了解如何建立 zip 壓縮檔、將檔案加入 Zip，以及在 ASP.NET
  中高效壓縮資料夾。
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: 將資料夾加入 Zip – 使用 Aspose.Zip for .NET 壓縮檔案
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: 使用 Aspose.Zip for .NET 將資料夾加入 Zip – 使用 FileInfo 壓縮檔案
url: /zh-hant/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 將資料夾加入 Zip

## 介紹

如果您需要以程式方式 **將資料夾加入 zip**，Aspose.Zip for .NET 提供乾淨且高效能的 API，適用於任何 .NET（包括 ASP.NET）應用程式。在本教學中，我們將示範如何使用 `FileInfo` 類別壓縮檔案，說明如何 **將檔案加入 zip**，並解釋為何此方法適合現代 .NET 專案。我們也會說明 **將資料夾加入 zip** 的完整步驟，讓您一次性打包整個目錄。讓我們開始吧！

## 快速解答
- **建立 zip 壓縮檔最簡單的方法是什麼？** 使用 Aspose.Zip 的 `Archive` 類別搭配 `FileInfo` 物件。  
- **我可以一次加入多個檔案嗎？** 可以，只要為每個檔案建立 `FileInfo`，然後呼叫 `CreateEntry`。  
- **ASP.NET 需要特別授權嗎？** 生產環境需要商業版 Aspose.Zip 授權；免費試用版可用於評估。  
- **支援哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。  
- **API 是否為執行緒安全？** 是，只要每個執行緒使用自己的 `Archive` 實例。

## 什麼是 Zip 壓縮檔以及為何要建立它？

Zip 壓縮檔會將一個或多個檔案打包成單一的壓縮容器，減少儲存空間、加速網路傳輸，並簡化分發流程。無論是傳送日誌、匯出報表，或為客戶打包資產，能以程式方式 **建立 zip 壓縮檔** 都是每位 .NET 開發者的必備技能。

## 為什麼使用 Aspose.Zip 將檔案加入 Zip？

Aspose.Zip 提供純 .NET 解決方案，無需外部相依性，同時讓開發者對壓縮、編碼與安全性擁有精細控制。它支援大型檔案、密碼保護，且在所有支援的 .NET 版本上表現一致，是舊版與新版應用程式的可靠選擇。

- **零外部相依性** – 純 .NET 實作。  
- **完整控制壓縮等級與編碼**（ASCII、UTF‑8 等）。  
- **支援大於 4 GB 的檔案** 以及密碼保護。  
- **跨 50 多個 .NET 版本保持一致的 API** – 從 .NET Framework 2.0 到 .NET 10。  

## 前置條件

在開始撰寫程式碼之前，請確保您已完成以下項目：

1. 已安裝 **Aspose.Zip for .NET**。從 [Aspose.Zip 下載頁面](https://releases.aspose.com/zip/net/) 取得最新套件。  
2. 在本機上有一個資料夾，內含您想壓縮的檔案（例如 `alice29.txt` 與 `fields.c`）。  

## 匯入命名空間

在任何需要處理 zip 壓縮檔的 C# 檔案中，加入以下 `using` 陳述式：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

這些命名空間讓您可以存取 `Archive` 類別、儲存選項以及標準 I/O 工具。

## 步驟說明

### 步驟 1：設定文件目錄

首先，定義保存來源檔案的資料夾。將佔位符替換為您系統上的絕對或相對路徑：

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** 使用 `Path.Combine` 以跨平台方式組合路徑。

### 步驟 2：開啟 Zip 檔案以寫入

建立指向輸出 zip 檔的 `FileStream`。此串流以 **Create** 模式開啟，會覆寫同名的既有檔案：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步驟 3：為每個來源檔案準備 `FileInfo` 物件

`FileInfo` 讓 Aspose.Zip 直接存取磁碟上的實體檔案。為每個要壓縮的檔案建立一個實例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** 它避免將整個檔案載入記憶體，對大型檔案尤為有用。

### 步驟 4：建立 Archive 並新增條目

`Archive` 類別是 Aspose.Zip 的核心物件，代表記憶體中的 zip 容器。先實例化 `Archive`，再對每個 `FileInfo` 呼叫 `CreateEntry`。第一個參數是檔案在 zip 中的名稱，第二個參數是來源 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` 方法會將新檔案條目加入壓縮檔，將條目名稱與來源 `FileInfo` 連結，儲存時會直接從磁碟串流資料。

### 步驟 5：使用所需編碼儲存 Zip Archive

最後，將 Archive 持久化到先前開啟的 `FileStream`。此範例使用 ASCII 編碼作為條目名稱，但若檔名包含非 ASCII 字元，可改用 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

當 `using` 區塊結束時，串流會自動關閉，zip 檔即完成。

## 如何使用 Aspose.Zip 將資料夾加入 Zip？

載入目標目錄，列舉所有檔案，並以包含資料夾名稱的相對路徑逐一加入。此方式讓您 **將資料夾加入 zip** 而無需手動列出每個檔案。透過在條目名稱中保留資料夾層級，最終的壓縮檔在解壓縮時會還原原始目錄結構，這對許多部署情境相當重要。

1. 使用 `DirectoryInfo` 指向欲壓縮的資料夾。  
2. 呼叫 `GetFiles("*", SearchOption.AllDirectories)` 以遞迴取得所有檔案。  
3. 對每個檔案建立 `FileInfo`，並以 `"MyFolder/Report.pdf"` 之類的路徑呼叫 `CreateEntry`。  

因為 API 使用 `FileInfo`，每個檔案都直接從磁碟串流，即使資料夾容量達數百 MB，也能保持低記憶體使用量。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **空的 zip 檔案** | `FileInfo` 指向不存在的路徑 | 驗證 `dataDir` 與檔名；在建立條目前使用 `File.Exists` 檢查。 |
| **檔名編碼不正確** | 在非 ASCII 名稱下使用預設編碼 | 在 `ArchiveSaveOptions` 中設定 `Encoding = Encoding.UTF8`。 |
| **大型檔案導致 OutOfMemoryException** | 將整個檔案載入記憶體 | `FileInfo` 會串流檔案；確保未在其他地方將檔案讀入位元組陣列。 |
| **權限被拒絕** | 應用程式沒有對輸出資料夾的寫入權限 | 以適當權限執行應用程式或選擇可寫入的目錄。 |

## 常見問答

**Q: 我可以一次以單一呼叫將整個資料夾加入 zip 壓縮檔嗎？**  
A: 沒有單一呼叫的方法，但使用 `DirectoryInfo` 列舉檔案並逐一透過 `CreateEntry` 加入，可有效達成相同結果。

**Q: Aspose.Zip 支援密碼保護嗎？**  
A: 支援，您可以在儲存前於 `Archive` 物件設定密碼，以加密整個壓縮檔。

**Q: Aspose.Zip 能處理多大的 zip 檔案？**  
A: 此函式庫可處理超過 4 GB 的檔案，且可建立超過 10 GB 的壓縮檔，且不需將整個壓縮檔載入記憶體。

**Q: API 是否相容 .NET 6 與 .NET 8？**  
A: 完全相容。Aspose.Zip 支援 .NET 5 直至 .NET 10，涵蓋所有目前的 LTS 版本。

**Q: 有哪些壓縮等級可供選擇？**  
A: 您可以選擇 `CompressionLevel.NoCompression`、`Fast`、`Normal` 或 `Maximum`，以在速度與檔案大小之間取得平衡。

## 進一步資源

- 下載最新的 Aspose.Zip 套件：[Aspose.Zip 下載頁面](https://releases.aspose.com/zip/net/)  
- 購買正式授權以供生產使用：[購買頁面](https://purchase.aspose.com/buy)  
- 從社群取得協助：[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)  
- 免費試用 Aspose.Zip：[此處免費試用](https://releases.aspose.com/)  
- 取得評估用臨時授權：[此連結](https://purchase.aspose.com/temporary-license/)

## 結論

現在您已掌握 **如何將資料夾加入 zip** 以及 **如何建立 zip 壓縮檔**，同時了解 **如何將檔案加入 zip**，並明白此方法為 ASP.NET 與其他 .NET 應用程式的理想選擇。請嘗試不同的壓縮等級、編碼與加密選項，以符合您的精確需求。祝您壓縮順利！

---

**最後更新：** 2026-07-18  
**測試環境：** Aspose.Zip for .NET 24.12 (latest)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Zip for .NET 壓縮資料夾](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – 使用 Aspose.Zip for .NET 輕鬆壓縮多個檔案](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Archive .NET – 使用 Aspose.Zip 進行檔案壓縮](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}