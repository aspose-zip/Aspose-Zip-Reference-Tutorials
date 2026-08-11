---
date: 2026-05-30
description: 了解如何在 .NET 中使用 Aspose.Zip for .NET 建立不壓縮的 zip。本指南將示範如何在不壓縮的情況下 zip 檔案、以未壓縮方式儲存檔案，以及有效管理壓縮檔案。
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: 儲存多個檔案（不壓縮）
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 在 .NET 中使用 Aspose.Zip 建立不壓縮的 zip
url: /zh-hant/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 建立無壓縮的 zip

在現代 .NET 開發中，**建立無壓縮的 zip** 可以顯著提升壓縮速度並使檔案大小可預測。當您需要**在不壓縮的情況下壓縮檔案**——例如，符合監管規定、加速下游處理，或保證原始位元組序列保持不變——Aspose.Zip for .NET 提供了簡潔、直接的 API。本教學將逐步說明如何建立未壓縮的 ZIP 壓縮檔、加入檔案，並將解決方案整合到您的應用程式中。

## 快速解答
- **「未壓縮 zip」是什麼意思？** 它是一個 ZIP 壓縮檔，其中每個條目使用「store」方法儲存，原始檔案位元組保持不變。  
- **為什麼要避免壓縮？** 為了加快壓縮速度、保留原始檔案大小以供下游處理，或符合禁止資料變更的監管要求。  
- **哪個 Aspose.Zip 類別處理此功能？** `ArchiveEntrySettings` 結合 `StoreCompressionSettings`。  
- **我需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。  

## 什麼是無壓縮的 zip？
**無壓縮的 Zip** 是一個 ZIP 壓縮檔，其中每個檔案條目使用 *store* 方法，表示資料會原樣複製到壓縮檔中，未套用任何壓縮演算法。這會使壓縮檔的大小基本上等於原始檔案的總和，加上少量 ZIP 之額外開銷。

## 為什麼在無壓縮的 zip 檔案中使用 Aspose.Zip？
Aspose.Zip 針對高效能壓縮進行了最佳化，讓您能即時儲存檔案而不需承擔壓縮演算法的開銷。它保證完整的 ZIP 相容性，允許您在同一個壓縮檔中混合未壓縮與壓縮的條目，並提供簡潔的 API，抽象低階的 ZIP 結構，使實作快速且可靠。

## 前置條件
- **Aspose.Zip for .NET** – 已整合至您的專案。請參閱官方[文件](https://reference.aspose.com/zip/net/)了解安裝步驟。  
- **.NET Development Environment** – Visual Studio、VS Code 或您偏好的任何 IDE。  
- **Document Directory** – 您電腦上的資料夾，內含欲壓縮的檔案（例如「Your Document Directory」）。

## 匯入命名空間
在撰寫程式碼之前，先匯入所需的命名空間，讓編譯器知道 Aspose 類別的所在位置。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 步驟 1：設定文件目錄
定義來源檔案所在的路徑。將佔位符替換為系統上實際的資料夾路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立無壓縮的 Zip 壓縮檔
教程的核心 – 我們建立一個以 `StoreCompressionSettings` 設定的 `Archive` 實例。`Archive` 代表一個可容納多個條目的 ZIP 容器。`StoreCompressionSettings` 指定條目以無壓縮方式儲存。這告訴 Aspose.Zip *store*（即不壓縮）每個條目。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **小技巧：** 如果您需要在 **將檔案儲存至 zip** 時，同時壓縮部分檔案而保留其他檔案為未壓縮，請為每個檔案建立獨立的 `ArchiveEntrySettings` 實例，並將它們加入同一個 `Archive`。

## 如何在 .NET 中建立無壓縮的 zip？
載入來源檔案，實例化 `Archive` 物件，並使用 `new StoreCompressionSettings()` 的 `ArchiveEntrySettings` 逐一加入每個檔案。整個操作僅需三行程式碼，且執行時間與總檔案大小呈線性關係，為您提供最快速的壓縮體驗。

### 步驟說明
1. **建立壓縮檔** – 使用目標串流或檔案路徑實例化 `Archive`。  
2. **設定條目屬性** – 對每個檔案，建立 `ArchiveEntrySettings` 物件，並將 `new StoreCompressionSettings()` 指派給其 `Compression` 屬性。  
3. **加入條目** – 為每個檔案呼叫 `archive.Add(entrySettings)`，最後以 `archive.Save()` 完成。

## 常見問題與解決方案
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **找不到檔案** | `dataDir` 路徑不正確或缺少檔案副檔名。 | 核對路徑並確保檔案存在。使用 `Path.Combine` 以獲得更安全的串接方式。 |
| **存取被拒** | 程式缺乏讀取來源檔案或寫入 ZIP 的權限。 | 以適當的權限執行應用程式，或選擇具有寫入權限的資料夾。 |
| **ZIP 中的檔案大小異常** | 壓縮檔使用了預設的壓縮方式建立。 | 確認已將 `new StoreCompressionSettings()` 傳遞給 `ArchiveEntrySettings`。 |

## 常見問與答

**Q: 我可以在壓縮特定檔案類型的同時，將其他檔案以未壓縮方式儲存嗎？**  
A: 可以，您可以為每個檔案建立不同的 `ArchiveEntrySettings`，並在同一個壓縮檔中混合壓縮與未壓縮的條目。

**Q: Aspose.Zip for .NET 是否相容於 .NET Core 與 .NET 5/6？**  
A: 絕對相容。此函式庫支援 .NET Framework、.NET Core、.NET Standard 以及最新的 .NET 版本。

**Q: 在壓縮過程中應如何處理例外情況？**  
A: 將壓縮程式碼包在 `try‑catch` 區塊中，並記錄例外細節。這可確保程式優雅失敗並便於除錯。

**Q: Aspose.Zip 是否支援多執行緒壓縮？**  
A: 可以，您可以平行處理多個檔案並將其加入壓縮檔，但需注意 `Archive` 物件本身非執行緒安全；在加入條目時需同步存取。

**Q: 我可以將 Aspose.Zip 整合到現有專案而不需大量程式碼變更嗎？**  
A: 當然可以。API 設計為簡易即插即用。請參考官方[文件](https://reference.aspose.com/zip/net/)取得遷移指南。

---
**最後更新：** 2026-05-30  
**測試環境：** Aspose.Zip for .NET（撰寫時的最新版本）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}