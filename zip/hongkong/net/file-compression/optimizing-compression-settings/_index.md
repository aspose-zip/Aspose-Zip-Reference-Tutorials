---
date: 2025-12-10
description: 學習使用 Aspose.Zip for .NET 建立 LZMA Zip 壓縮檔，並使用 Store 壓縮方式。優化 Bzip2、LZMA、PPMd、增強
  Deflate 及 Store 方法。
linktitle: Optimizing Compression Settings
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 建立 LZMA zip 壓縮檔
url: /zh-hant/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 優化 Aspose.Zip for .NET 的壓縮設定

在 .NET 開發的世界裡，高效的 **file compression** 能顯著降低儲存成本並加快資料傳輸速度。無論您是構建 ASP.NET 網頁應用、桌面工具，或是雲端服務，了解如何 **create LZMA zip archive** 都能為高壓縮比提供強大優勢。在本教學中，我們將逐一說明每種壓縮方法——Bzip2、LZMA、PPMd、Enhanced Deflate 與 Store——讓您能針對情境選擇合適的演算法，並微調設定以取得最佳效果。

## 快速回答
- **What is the primary benefit of LZMA compression?** 最高的壓縮比，同時在大多數檔案類型上保持合理的速度。  
- **Which method stores files without compression?** Store compression（亦稱 “store compression zip”。）  
- **Can I use these settings in an ASP.NET application?** 可以——只需在專案中引用 Aspose.Zip 並呼叫相同的 API。  
- **Do I need a license for production use?** 生產環境需要商業授權；亦提供免費試用版。  
- **What .NET versions are supported?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是 “create LZMA zip archive”？
建立 LZMA zip archive 表示將一個或多個檔案打包至 ZIP 容器，並套用 LZMA 演算法以獲得卓越的壓縮效果。Aspose.Zip 抽象化底層細節，讓您專注於業務邏輯。

## 為何在 .NET 使用 Aspose.Zip 進行檔案壓縮？
- **Unified API** – 為 Bzip2、LZMA、PPMd、Enhanced Deflate 與 Store 提供一致的介面。  
- **Performance‑tuned** – 經過優化的原生實作，提供快速處理。  
- **ASP.NET friendly** – 在 Web 專案、背景服務與 Azure Functions 中無縫運作。  
- **Fine‑grained control** – 可調整字典大小、壓縮等級等參數。

## 前置條件
- **Aspose.Zip for .NET Library** – 從 [Aspose documentation](https://reference.aspose.com/zip/net/) 下載並安裝。  
- **Sample Text File** – 準備一個範例檔案（例如 `sample.txt`），供壓縮使用。  
- **.NET development environment** – Visual Studio 2022 或任何相容的 IDE。

## 匯入命名空間

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在讓我們探討每個壓縮設定。

## 使用 Bzip2 壓縮設定

### 步驟 1：初始化 Bzip2 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new Bzip2CompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## 如何使用 Aspose.Zip 建立 LZMA zip archive

### 步驟 1：初始化 LZMA 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new LzmaCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## 使用 PPMd 壓縮設定

### 步驟 1：初始化 PPMd 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new PPMdCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## 使用 Enhanced Deflate 壓縮設定

### 步驟 1：初始化 Enhanced Deflate 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new EnhancedDeflateCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

## 使用 Store 壓縮設定（store compression zip）

### 步驟 1：初始化 Store 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **Pro tip:** 調整 `dataDir` 變數以指向實際的工作目錄，若需將多個檔案加入同一個壓縮檔，請重複使用相同的 `Archive` 實例。

## 常見問題與解決方案
- **“File not found” errors** – 確認 `dataDir` 以路徑分隔符（`\` 或 `/`）結尾，且 `sample.txt` 存在。  
- **Memory consumption with large files** – 使用 `ArchiveEntrySettings` 開啟串流模式，直接將資料寫入輸出串流。  
- **Incompatible compression level** – 某些演算法（如 LZMA）會公開額外屬性，例如 `DictionarySize`。若需更細緻的控制，請參考 API 文件。

## 常見問答

**Q: Can I use Aspose.Zip for .NET with other compression libraries?**  
A: Aspose.Zip 設計為使用內建的演算法。雖然可以整合第三方函式庫，但需在 Aspose API 之外自行處理。

**Q: How can I add password protection to a zip created with Aspose.Zip?**  
A: Aspose.Zip 支援密碼保護。請參閱 [documentation](https://reference.aspose.com/zip/net/) 中的 `SetPassword` 方法。

**Q: Is there a trial version I can test?**  
A: 有，您可在 [here](https://releases.aspose.com/) 取得試用版。

**Q: Where can I get community help or ask questions?**  
A: 如需支援與社群討論，請前往 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)。

**Q: Can I obtain a temporary license for evaluation?**  
A: 有，您可在 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: How does this help with asp.net file compression?**  
A: 只要在 ASP.NET 控制器或中介軟體中呼叫相同的 API，即可在傳送給客戶端前即時壓縮檔案，降低頻寬使用並提升感知效能。

---

**最後更新：** 2025-12-10  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}