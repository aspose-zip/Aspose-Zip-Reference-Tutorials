---
date: 2026-02-12
description: 學習如何使用 Aspose.Zip for .NET 加入 ZIP 密碼並建立 LZMA ZIP 壓縮檔。本 ZIP 壓縮教學涵蓋 Bzip2、LZMA（包括字典大小）、PPMd、增強型
  Deflate、儲存壓縮，以及 ASP.NET 大型檔案的壓縮。
linktitle: Optimizing Compression Settings
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 為 LZMA zip 添加密碼
url: /zh-hant/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 為 LZMA zip 添加密碼

在現代 .NET 應用程式中，**添加 zip 密碼**於建立高壓縮率的 LZMA zip 壓縮檔時，可保護敏感資料，同時提供最佳的壓縮效果。無論您是構建 ASP.NET 檔案壓縮服務、處理大型檔案的桌面工具，或是雲端工作流程，本教學將一步步示範如何使用 Aspose.Zip for .NET 來保護與壓縮檔案。

## 快速解答
- **LZMA 壓縮的主要好處是什麼？** 最高的壓縮比，同時對大多數檔案類型保持合理的速度。  
- **哪種方法在不壓縮的情況下儲存檔案？** Store compression（亦稱 “store compression zip”）。  
- **我可以在 ASP.NET 應用程式中使用這些設定嗎？** 可以——只需在專案中參考 Aspose.Zip 並呼叫相同的 API。  
- **在正式環境使用是否需要授權？** 正式環境需要商業授權；亦提供免費試用版。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 在 Aspose.Zip 中什麼是「添加 zip 密碼」？

添加 zip 密碼即是對 ZIP 壓縮檔內的項目進行加密，只有知道密碼的使用者才能解壓縮檔案。Aspose.Zip 提供簡單的 `SetPassword` 方法，適用於所有壓縮演算法——Bzip2、LZMA、PPMd、Enhanced Deflate 以及 Store。

## 為什麼要使用 Aspose.Zip 進行 .NET 檔案壓縮？

- **Unified API** – 為 Bzip2、LZMA、PPMd、Enhanced Deflate 以及 Store 提供一致的介面。  
- **Performance‑tuned** – 採用最佳化的原生實作，處理速度快。  
- **ASP.NET friendly** – 在 Web 專案、背景服務與 Azure Functions 中可無縫運作。  
- **Fine‑grained control** – 可調整字典大小、壓縮等級，並以單一呼叫添加 zip 密碼。  
- **Compress large files** efficiently by streaming data directly to the output stream. – 透過直接將資料串流至輸出串流，能有效壓縮大型檔案。

## 前置條件
- **Aspose.Zip for .NET Library** – 從 [Aspose documentation](https://reference.aspose.com/zip/net/) 下載並安裝。  
- **Sample Text File** – 準備一個範例檔案（例如 `sample.txt`），用於壓縮。  
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

現在讓我們探討每個壓縮設定，並查看在適當的情況下如何 **添加 zip 密碼**。

## 使用 Bzip2 壓縮設定

### 步驟 1：初始化 Bzip2 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new Bzip2CompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Optional: protect the archive with a password
        archive.SetPassword("MySecret123");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

*`SetPassword` 呼叫示範了如何 **添加 zip 密碼** 至 Bzip2 壓縮的壓縮檔。*

## 如何使用 Aspose.Zip for .NET 添加 zip 密碼

您可以在呼叫 `Save` 之前，對任何 Archive 實例套用密碼。相同的方法同樣適用於 LZMA、PPMd、Enhanced Deflate 以及 Store 壓縮。只需在保留 `SetPassword` 呼叫的同時，替換壓縮設定物件即可。

## 如何使用 Aspose.Zip 建立 LZMA zip 壓縮檔

### 步驟 1：初始化 LZMA 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new LzmaCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Add password protection (LZMA supports it)
        archive.SetPassword("StrongPwd!2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **提示：** LZMA 提供可設定的 **LZMA dictionary size**，會影響壓縮比與記憶體使用量。若需針對極大型檔案進行微調，可透過 `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` 來設定。

## 使用 PPMd 壓縮設定

### 步驟 1：初始化 PPMd 壓縮

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (Archive archive = new Archive(new ArchiveEntrySettings(new PPMdCompressionSettings())))
    {
        // Step 2: Create Entry
        archive.CreateEntry("sample.txt", dataDir + "sample.txt");
        
        // Secure the archive
        archive.SetPassword("PPMdPwd#2026");
        
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
        
        // Password protection works here as well
        archive.SetPassword("DeflatePwd2026");
        
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
        
        // Even for store compression you can add a password
        archive.SetPassword("StorePwd2026");
        
        // Step 3: Save Archive
        archive.Save(zipFile);
    }
}
```

> **專業提示：** 調整 `dataDir` 變數以指向實際的工作目錄，若需將多個檔案加入同一壓縮檔，請重複使用相同的 `Archive` 實例。

## 常見問題與解決方案
- **「找不到檔案」錯誤** – 請確認 `dataDir` 以路徑分隔符（`\` 或 `/`）結尾，且 `sample.txt` 確實存在。  
- **大型檔案的記憶體消耗** – 使用 `ArchiveEntrySettings` 啟用串流模式，直接將資料寫入輸出串流。  
- **不相容的壓縮等級** – 某些演算法（例如 LZMA）會公開額外屬性如 `DictionarySize`。若需更細緻的控制，請參考 API 文件。  
- **密碼未套用** – 確保在 `archive.Save(zipFile);` 之前呼叫 `SetPassword` *before*。

## 常見問答

**Q: 我可以將 Aspose.Zip for .NET 與其他壓縮函式庫一起使用嗎？**  
A: Aspose.Zip 設計為使用其內建演算法。雖然可以整合第三方函式庫，但需在 Aspose API 之外自行處理。

**Q: 如何為使用 Aspose.Zip 建立的 zip 加上密碼保護？**  
A: 在儲存之前，於 `Archive` 物件上使用 `SetPassword(string password)` 方法。詳情請參閱 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 有可供測試的試用版嗎？**  
A: 有，您可在此取得試用版 [here](https://releases.aspose.com/)。

**Q: 我可以在哪裡取得社群協助或提問？**  
A: 如需支援與社群討論，請前往 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)。

**Q: 我可以取得臨時授權以進行評估嗎？**  
A: 可以，請在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

**Q: 這對 asp.net 檔案壓縮有何幫助？**  
A: 只要在 ASP.NET 控制器或中介軟體中呼叫相同的 API，即可在即時傳送給客戶端前壓縮檔案，減少頻寬使用並提升感知效能。

**Q: 有效壓縮大型檔案的最佳方法是什麼？**  
A: 結合串流模式與 LZMA 壓縮，並設定適當的 `DictionarySize`。此方式在巨量資料集上平衡記憶體使用與壓縮比。

---

**最後更新：** 2026-02-12  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}