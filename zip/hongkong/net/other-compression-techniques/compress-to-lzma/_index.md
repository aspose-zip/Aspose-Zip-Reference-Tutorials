---
date: 2026-06-24
description: 了解如何在 Aspose.Zip for .NET 中壓縮 LZMA，以優化儲存空間與資料傳輸效率。
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: 壓縮至 Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 Aspose.Zip for .NET 中壓縮 LZMA
url: /zh-hant/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Zip for .NET 中壓縮 LZMA

## 介紹

在本教學中，您將學習 **如何在 Aspose.Zip for .NET 中壓縮 LZMA**，這是一項優化儲存空間與提升資料傳輸效率的關鍵技能。LZMA（Lempel‑Ziv‑Markov chain 演算法）相較於傳統 ZIP 可產生最高 70 % 更小的壓縮檔，同時保持快速解壓縮，適用於頻寬受限的情境。

## 快速答覆
- **需要的函式庫是什麼？** Aspose.Zip for .NET  
- **本指南涵蓋哪種演算法？** LZMA 壓縮  
- **我需要授權嗎？** 測試時臨時授權即可；正式環境需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10  
- **實作需要多長時間？** 基本檔案通常在 10 分鐘內完成。

## 什麼是 LZMA 壓縮？

LZMA 是一種高壓縮比的無損壓縮演算法，採用字典壓縮與範圍編碼。它可將文字檔縮小 30‑70 %，且解壓縮速度與 ZIP 相當。對於大型資料集，LZMA 能降低儲存成本並加快網路傳輸，同時不影響資料完整性。

## 為什麼使用 Aspose.Zip 進行 LZMA 壓縮？

Aspose.Zip 支援 **5 種壓縮演算法**（ZIP、Deflate、BZIP2、LZMA 與 ZSTD），且可處理最高 **4 GB** 的壓縮檔而不需將整個檔案載入記憶體。此函式庫在一般伺服器上可於 **2 秒** 內處理數百頁文件，兼具效能與可擴充性。

## 前置條件

在開始之前，請確保您已具備以下項目：

- Aspose.Zip for .NET：確保已安裝 Aspose.Zip 函式庫。您可於[此處](https://reference.aspose.com/zip/net/)取得文件說明。  
- 文件目錄：選擇或建立一個包含欲壓縮檔案的資料夾。

## 匯入命名空間

在 C# 檔案的頂部加入所需的命名空間，以便使用 Aspose.Zip 的 LZMA 功能：

```csharp
using System;
using Aspose.Zip.LZMA;
```

## 如何設定壓縮的來源資料夾？

指定保存欲壓縮檔案的資料夾。提供專屬的來源目錄可確保僅處理預期的檔案，降低誤將不需要的資料納入的風險，且在同一專案中執行多個壓縮任務時，路徑管理也更為簡便。

```csharp
string dataDir = "Your Document Directory";
```

## 如何使用 LZMA 壓縮檔案？

`LzmaArchive` 為 Aspose.Zip 用於建立與管理 LZMA 壓縮檔的類別。

建立 `LzmaArchive` 實例，指向來源檔案，然後呼叫 `Save` 產生 `.lzma` 壓縮檔。此兩行程式碼即可完成整個壓縮流程，內部處理串流管理，產出可供分發或儲存的緊湊檔案。

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## 如何確認壓縮成功？

`Console.WriteLine` 會將文字寫入標準輸出主控台。

壓縮檔儲存完成後，使用 `Console.WriteLine` 輸出簡短的確認訊息。此即時回饋可協助開發者驗證壓縮步驟是否順利完成，簡化自動建置時的除錯，並在將此例程整合至大型應用程式或腳本時提供清晰的狀態資訊。

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## 常見問題與解決方案

- **找不到檔案** – 請確認路徑字串使用雙反斜線 (`\\`) 或逐字字串 (`@"C:\Path"`)。  
- **記憶體不足** – Aspose.Zip 會以串流方式處理資料，但極大型檔案可能需要提升程式的記憶體上限。  
- **授權未套用** – 請確保在任何 Aspose.Zip 操作之前呼叫 `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");`。

## 常見問答

**Q: 我可以將多個檔案壓縮成單一 LZMA 壓縮檔嗎？**  
A: 可以。在呼叫 `archive.Save()` 前，對每個檔案使用 `archive.AddFile()`。

**Q: 有辦法設定 LZMA 的壓縮等級嗎？**  
A: `LzmaArchive` 類別使用預設的壓縮等級，能在速度與檔案大小之間取得良好平衡。如需更細緻的控制，可透過 `LzmaEncoder` 取得進階設定。

**Q: 產生的 .lzma 檔案能在非 Windows 平台上使用嗎？**  
A: 絕對可以。LZMA 格式與平台無關，只要有相容的 LZMA 工具，任何作業系統皆可解壓縮。

**Q: 如何使用 Aspose.Zip 解壓縮 LZMA 壓縮檔？**  
A: 使用帶有壓縮檔路徑的 `LzmaArchive` 建構子，然後呼叫 `ExtractToDirectory()` 以解壓縮其內容。

**Q: Aspose.Zip 是否支援串流壓縮，以避免將整個檔案載入記憶體？**  
A: 支援。您可將 `Stream` 物件傳入 `SetSource()` 與 `Save()` 方法，以使用串流方式壓縮。

---

**最後更新：** 2026-06-24  
**測試環境：** Aspose.Zip for .NET（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Zip for .NET 壓縮檔案](/zip/net/file-compression/compress-file/)
- [如何使用 Aspose.Zip for .NET 開啟 GZip 壓縮檔及其他壓縮技術](/zip/net/other-compression-techniques/)
- [compress files c# – 使用 Aspose.Zip for .NET 建立 7z 壓縮檔](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}