---
date: 2026-06-29
description: 了解如何使用 Aspose.Zip for .NET 將 WIM 檔案解壓縮至資料夾。請依照本步驟指南，在您的 .NET 應用程式中有效率地解壓縮
  WIM 壓縮檔。
keywords:
- how to extract wim
- asp
- aspose zip
- wim extraction .net
linktitle: 將 Wim 解壓縮至資料夾
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  headline: How to Extract WIM to Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract WIM files to a folder with Aspose.Zip for .NET.
    Follow this step‑by‑step guide to decompress WIM archives efficiently in your
    .NET apps.
  name: How to Extract WIM to Folder Using Aspose.Zip for .NET
  steps:
  - name: Set Your Document Directory
    text: Define the folder that contains the source `.wim` file and the output folder
      where the extracted files will be written. Replace the placeholder path with
      your actual locations. The `dataDir` variable holds the source directory, while
      `outDir` is the destination for the extracted image.
  - name: Open the WIM Archive
    text: Create a `FileStream` for the `.wim` file and instantiate a `WimArchive`.
      The constructor reads the archive header without loading all image data into
      memory.
  - name: Extract the Desired Image
    text: Select the first image (`Images[0]`) and invoke `ExtractAll`. `ExtractAll`
      extracts all files from the selected image to a directory. If the archive contains
      multiple images, change the index to target a different one. The snippet reads
      the WIM file, accesses its first image, and writes all files to
  type: HowTo
- questions:
  - answer: Yes. Aspose.Zip supports **50+ formats** including ZIP, TAR, GZIP, 7z,
      and WIM, allowing you to handle virtually any compression scenario.
    question: Can I use Aspose.Zip for .NET with other archive formats?
  - answer: Explore the [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)
      for in‑depth guides, code samples, and performance best practices.
    question: Where can I find more examples and detailed API docs?
  - answer: Absolutely. You can download a trial version from the [website](https://releases.aspose.com/zip/net/)
      and evaluate all features without a license.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: Temporary licenses are provided through the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      – use **[this link](https://purchase.aspose.com/temporary-license/)** to request
      one.
    question: How do I obtain a temporary license for testing?
  - answer: The official [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) is
      the best place to interact with other developers and Aspose engineers.
    question: Where can I get community support or ask technical questions?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 將 WIM 解壓縮至資料夾
url: /zh-hant/net/file-decompression/decompress-wim-folder/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 將 WIM 解壓縮至資料夾

## 簡介

在本教學中，您將學習 **如何提取 WIM** 檔案至資料夾，使用 Aspose.Zip for .NET。無論您是要建立 Windows 部署工具、備份程式，或僅需檢視 Windows Imaging Format 壓縮檔的內容，以下步驟都能協助您從原始 `.wim` 檔案轉換為在任何支援的 .NET 執行環境中完整的目錄。我們將說明環境設定、精確的 API 呼叫，以及提取後的技巧，讓您能自信地將此邏輯整合到實際專案中。

## 快速答案

- **建議使用哪個函式庫？** Aspose.Zip for .NET  
- **我可以在 .NET Core 上提取 WIM 檔案嗎？** Yes – the API supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **在正式環境需要授權嗎？** A commercial license is required for production; a free trial is available for evaluation.  
- **最低支援的 .NET 版本是什麼？** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **提取通常需要多長時間？** Standard images finish in a few seconds; multi‑hundred‑megabyte images may need longer, but the API streams data to keep memory usage low.

## 什麼是 WIM 檔案？

WIM（Windows Imaging Format）壓縮檔將一個或多個磁碟映像儲存在單一的壓縮容器中。它是 Windows 安裝程式、DISM 以及許多企業部署流程的核心格式，允許在不解壓整個檔案的情況下，選擇性地提取單一映像。

## 為什麼使用 Aspose.Zip for .NET？

Aspose.Zip 提供純受管理、跨平台的解決方案，消除對原生 DLL 的依賴。它支援 **50+ 輸入與輸出格式**（包括 ZIP、TAR、GZIP、7z 與 WIM），且能在不將整個檔案載入記憶體的情況下處理 **多百頁的壓縮檔**。基於串流的提取方式使典型 WIM 檔的記憶體使用量維持在 10 MB 以下，非常適合伺服器端或容器化的工作負載。

## 先決條件

- **Aspose.Zip Library** – 從 [website](https://releases.aspose.com/zip/net/) 或主發行頁面 [here](https://releases.aspose.com/) 下載最新版本。  
- **WIM 壓縮檔** – 將您要解壓縮的 `.wim` 放置於已知資料夾（例如 `C:\Archives`）。  
- **.NET 開發環境** – Visual Studio、VS Code，或任何支援 C# 的編輯器。  
- **有效的 Aspose.Zip 授權** 用於正式建置（免費試用版可用於測試）。

## 匯入命名空間

以下的 `using` 指令讓您取得處理 WIM 所需的 Aspose.Zip 核心類別。

```csharp
using Aspose.Zip;
using System.IO;
```

這兩個命名空間即為您所需的全部；函式庫在內部處理壓縮、解壓縮與映像列舉。

## 如何將 WIM 解壓縮至資料夾？

載入 WIM 檔案，選取您想要的映像，並將其內容串流至目標目錄。Aspose.Zip API 以三個簡潔步驟完成解壓縮，內部處理壓縮並在大型壓縮檔中仍保持低記憶體使用量。此方法適用於所有支援的 .NET 執行環境，且僅需少量程式碼。`WimArchive` 是代表 WIM 檔案的 Aspose.Zip 類別，提供對其內含映像的存取。

### 直接答案

使用 `new WimArchive(stream)` 載入 WIM，透過 `Images[0]` 選取第一個映像，然後呼叫 `ExtractAll(destinationPath)`。此單行呼叫會在串流資料的同時提取所選映像的所有檔案，因而即使在大型壓縮檔中，記憶體消耗亦保持在最低。

### 步驟 1：設定文件目錄

定義包含來源 `.wim` 檔案的資料夾以及寫入解壓縮檔案的輸出資料夾。將佔位路徑替換為實際位置。

`dataDir` 變數保存來源目錄，而 `outDir` 為提取映像的目標目錄。

```csharp
string dataDir = @"C:\Archives";          // folder with your .wim file
string outDir = Path.Combine(dataDir, "DecompressWim_out"); // extraction target
```

### 步驟 2：開啟 WIM 壓縮檔

為 `.wim` 檔案建立 `FileStream`，並實例化 `WimArchive`。建構子會讀取壓縮檔標頭，而不將所有映像資料載入記憶體。

```csharp
using (FileStream wimStream = File.OpenRead(Path.Combine(dataDir, "corpus.wim")))
{
    WimArchive wim = new WimArchive(wimStream);
```

### 步驟 3：提取目標映像

選取第一個映像 (`Images[0]`) 並呼叫 `ExtractAll`。`ExtractAll` 會將所選映像的所有檔案提取至目錄。若壓縮檔包含多個映像，可更改索引以針對其他映像。

```csharp
    // Extract the first image to the output directory
    wim.Images[0].ExtractAll(outDir);
}
```

此程式碼片段讀取 WIM 檔案，存取其第一個映像，並將所有檔案寫入 **DecompressWim_out**。如需提取壓縮檔中其他映像，請調整索引。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| **`FileNotFoundException`** | `dataDir` 或檔名不正確 | 驗證路徑，並確保 `corpus.wim` 存在於指定位置。 |
| **`UnauthorizedAccessException`** | 目標資料夾為唯讀 | 以提升的權限執行應用程式，或選擇可寫入的目錄。 |
| **Extraction is slow** | WIM 檔案非常大或硬體規格低 | 改為提取特定映像而非整個壓縮檔，或對大型檔案使用非同步串流。 |

## 常見問答

**Q: 我可以在 .NET 使用 Aspose.Zip 處理其他壓縮格式嗎？**  
A: 可以。Aspose.Zip 支援 **50+ 格式**，包括 ZIP、TAR、GZIP、7z 與 WIM，讓您幾乎能處理任何壓縮情境。

**Q: 我在哪裡可以找到更多範例與詳細的 API 文件？**  
A: 前往 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 取得深入指南、程式碼範例與效能最佳實踐。

**Q: Aspose.Zip for .NET 有提供免費試用嗎？**  
A: 當然。您可從 [website](https://releases.aspose.com/zip/net/) 下載試用版，無需授權即可評估所有功能。

**Q: 我如何取得測試用的臨時授權？**  
A: 臨時授權可透過 [temporary‑license page](https://purchase.aspose.com/temporary-license/) 取得 – 使用 **[this link](https://purchase.aspose.com/temporary-license/)** 申請。

**Q: 我可以在哪裡取得社群支援或提出技術問題？**  
A: 官方的 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 是與其他開發者及 Aspose 工程師交流的最佳場所。

---

**最後更新：** 2026-06-29  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

```csharp
using System.IO;
using Aspose.Zip.Wim;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (FileStream fs = File.OpenRead(dataDir + "corpus.wim"))
{
    using (WimArchive archive = new WimArchive(fs))
    {
        archive.Images[0].ExtractToDirectory(dataDir + "DecompressWim_out");
    }
}
```

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Zip for .NET 解壓縮檔案](/zip/net/file-decompression/)
- [如何使用 Aspose.Zip for .NET 將 zip 解壓縮至資料夾](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [如何使用 Aspose.Zip for .NET 將 Xar 壓縮檔解壓縮至資料夾](/zip/net/file-decompression/decompress-xar-folder/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}