---
date: 2025-12-25
description: 學習如何使用 Aspose.Zip for .NET 建立 7z 檔案，涵蓋 LZMA2、BZip2 以及 Store 等七種壓縮方法。非常適合將資料夾壓縮為
  7z 的情境。
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何建立 7z 檔案 – Aspose.Zip for .NET 教學
url: /zh-hant/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立 7z 檔案 – Aspose.Zip for .NET 教學

## Introduction

如果您需要在 .NET 應用程式中以程式方式 **how to create 7z** 壓縮檔案，您來對地方了。Aspose.Zip for .NET 讓產生 Seven Zip 壓縮檔變得簡單，支援任何壓縮演算法，無論您是想 **compress folder to 7z** 以供發佈，或只是需要可靠的 **seven zip archive .net** 解決方案。本指南將說明三種常用的壓縮方法——LZMA2、BZip2 與 Store（不壓縮），並示範如何只用幾行 C# 程式碼產生 7z 檔案。

## Quick Answers
- **What library should I use?** Aspose.Zip for .NET 提供最完整的 Seven Zip 功能集。  
- **Which compression method gives the best ratio?** LZMA2 通常在混合資料上提供最高壓縮率。  
- **Can I create a 7z without any compression?** 是的——使用 Store（不壓縮）方法。  
- **Do I need a license for development?** 可使用免費試用版；正式環境需購買授權。  
- **Is this compatible with .NET 6/7?** 當然可以——Aspose.Zip 支援 .NET Framework、.NET Core 以及 .NET 5 以上版本。

## What Are the Seven Zip Compression Methods?

Seven Zip 支援多種演算法，各自針對不同情境進行最佳化：

* **LZMA2** – 高壓縮比，適合大型混合類型檔案。  
* **BZip2** – 壓縮效果佳，但較 LZMA2 緩慢；在需要與舊工具相容時很有用。  
* **Store** – 不壓縮；當只需要封存而不減少檔案大小時非常適合（例如保留原始檔案時間戳記）。  

了解這些 **seven zip compression methods** 可協助您為專案挑選合適的設定。

## Prerequisites

在開始之前，請確保您已具備以下條件：

- 基本的 C# 與 Visual Studio 知識。  
- 已安裝 Aspose.Zip for .NET 函式庫。可從官方下載頁面 **[here](https://releases.aspose.com/zip/net/)** 取得。  
- 一個資料夾 (`dataDir`) 內放置您欲封存的檔案。

## Import Namespaces

首先，於 C# 檔案中加入所需的命名空間：

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

這些類別讓您存取壓縮設定與封存處理功能。

## LZMA2 Compression – How to Create a 7z with Maximum Ratio

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2 最適合來源檔案大於 1 MB 的情況。對於大量小檔案，BZip2 可能較快。

## BZip2 Compression – A Balanced Choice

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 在提供穩定壓縮的同時保持合理速度，當目標環境不支援 LZMA2 時，是不錯的備選方案。

## Store (No Compression) – When Size Doesn’t Matter

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

若僅需將檔案打包而不改變其大小，請使用 Store 方法——非常適合保留原始時間戳記或即時解壓的情況。

## Common Use Cases

| 情境 | 建議方法 |
|----------|--------------------|
| 發佈大型安裝程式 | LZMA2 |
| 與舊版工具分享日誌 | BZip2 |
| 打包檔案以快速解壓 | Store (no compression) |
| 需要在 Web 服務即時 **compress folder to 7z** | LZMA2 (for best ratio) |

## Troubleshooting & Tips

- **Missing files in the archive?** 請確認 `dataDir` 指向正確目錄且程式具有讀取權限。  
- **Archive fails to open on older 7‑Zip versions?** 請改用 BZip2 或 Store，因為 LZMA2 可能需要較新的解壓縮函式庫。  
- **Performance bottleneck?** 面對大量資料時，建議以串流方式產生封存，而非一次載入所有項目至記憶體。

## Frequently Asked Questions

**Q: 我可以在 Aspose.Zip for .NET 中使用任何類型的檔案嗎？**  
A: 可以，Aspose.Zip 支援廣泛的檔案格式，讓您幾乎可以壓縮與解壓任何檔案類型。

**Q: Aspose.Zip for .NET 有提供免費試用嗎？**  
A: 有，您可在 **[here](https://releases.aspose.com/)** 取得免費試用版。

**Q: 我在哪裡可以找到 Aspose.Zip for .NET 的文件？**  
A: 完整的 API 參考文件可於 **[here](https://reference.aspose.com/zip/net/)** 取得。

**Q: 我該如何取得 Aspose.Zip for .NET 的臨時授權？**  
A: 可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 我該向哪裡尋求 Aspose.Zip for .NET 的支援？**  
A: 您可在 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** 上取得支援。

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最後更新：** 2025-12-25  
**測試環境：** Aspose.Zip for .NET 24.12  
**作者：** Aspose  

---