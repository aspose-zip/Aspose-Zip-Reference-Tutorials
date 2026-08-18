---
date: 2026-06-29
description: 了解如何使用 Aspose.Zip for .NET 將資料夾壓縮為 7z，涵蓋七種壓縮方法，例如 LZMA2、BZip2 及 Store。非常適合以程式方式建立
  7z 壓縮檔。
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip 多種壓縮方法
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何將資料夾壓縮為 7z – Aspose.Zip for .NET 教學
url: /zh-hant/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何將資料夾壓縮為 7z – Aspose.Zip for .NET 教程

## 簡介

如果您需要在 .NET 應用程式中以程式方式 **compress folder to 7z** 壓縮檔案，您來對地方了。Aspose.Zip for .NET 讓產生 Seven Zip 壓縮檔變得簡單，支援所有可用的壓縮演算法，無論您是想將整個目錄打包以供發佈，或只是需要一個可靠的 **seven zip archive .net** 解決方案。本指南將逐一說明三種常用的壓縮方法——LZMA2、BZip2 與 Store（無壓縮），並示範如何只用幾行 C# 程式碼產生 7z 檔案。

## 快速回答

- **我應該使用哪個函式庫？** Aspose.Zip for .NET 提供最完整的 Seven Zip 功能套件。  
- **哪種壓縮方法能提供最佳壓縮率？** LZMA2 通常在混合資料上提供最高的壓縮率。  
- **我可以建立沒有任何壓縮的 7z 嗎？** 可以——使用 Store（無壓縮）方法。  
- **開發時需要授權嗎？** 可使用免費試用版；正式環境需購買授權。  
- **這是否相容於 .NET 6/7？** 完全相容——Aspose.Zip 支援 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。

## Seven Zip 壓縮方法有哪些？

Seven Zip 支援多種演算法，每種皆針對不同情境進行最佳化。**LZMA2** 提供最高的壓縮比（通常比 BZip2 小 30‑40 %），**BZip2** 在保有較廣泛的舊版工具相容性下提供穩定的壓縮，而 **Store** 則僅將檔案封存而不壓縮，完美保留原始時間戳記。

## 先決條件

在開始之前，請確保您已具備：

- 基本的 C# 與 Visual Studio 知識。  
- 已安裝 Aspose.Zip for .NET 函式庫。可從官方下載頁面 **[here](https://releases.aspose.com/zip/net/)** 取得。  
- 一個包含欲封存檔案的資料夾 (`dataDir`)。

## 匯入命名空間

首先，將所需的命名空間加入您的 C# 檔案：

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

這些類別讓您能存取壓縮設定與壓縮檔處理。

## LZMA2 壓縮 – 如何建立具最高壓縮比的 7z

`Archive` 類別代表一個可包含多個檔案的 7z 壓縮檔。  
LZMA2 演算法在支援的方法中提供最高的壓縮比。它透過將輸入分割成區塊並套用複雜的字典壓縮來運作。在 Aspose.Zip 中，您需在將檔案加入之前，於 `Archive` 物件上將 `CompressionMethod` 設為 `CompressionMethod.Lzma2`。

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

> **專業提示：** 當來源檔案大於 1 MB 時，LZMA2 效能最佳。對於大量小檔案，BZip2 可能較快。

## BZip2 壓縮 – 均衡的選擇

`Archive` 類別代表一個可包含多個檔案的 7z 壓縮檔。  
BZip2 提供穩定的壓縮，同時具備對舊版工具的良好相容性。它使用 Burrows‑Wheeler 轉換與 Huffman 編碼來縮減大小。在 Aspose.Zip 中，您在設定 `Archive` 實例時選擇 `CompressionMethod.BZip2`，此方式在大多數文字與二進位檔案間取得速度與壓縮比的平衡。

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 在保持合理速度的同時提供穩定的壓縮，當目標環境不支援 LZMA2 時，是不錯的備援選擇。

## Store（無壓縮） – 當大小不重要時

`Archive` 類別代表一個可包含多個檔案的 7z 壓縮檔。  
Store 方法會在不壓縮資料的情況下建立壓縮檔。它僅將原始檔案複製到 7z 容器中，保留時間戳記與目錄結構。若要在 Aspose.Zip 中使用，請在加入欲封裝的檔案前，於 `Archive` 上設定 `CompressionMethod.Store`。

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

若您僅需將檔案打包而不改變其大小，請使用 Store 方法——非常適合保留原始時間戳記或在即時解壓縮的情況下使用。

## 如何將檔案加入 7z？

透過建立 `Archive` 實例、設定欲使用的 `CompressionMethod`，再呼叫 `AddAllFiles(dataDir)`，即可將檔案加入 7z 壓縮檔。此方法會遞迴掃描指定的資料夾，保留壓縮檔內的目錄層級。此做法讓您在完成初始設定後，只需一行程式碼即可 **compress folder to 7z**。

## 常見使用情境

| 情境 | 建議方法 |
|----------|--------------------|
| 發佈大型安裝程式 | LZMA2 |
| 與舊版工具分享日誌 | BZip2 |
| 快速解壓縮的檔案封裝 | Store (no compression) |
| 在 Web 服務即時 **compress folder to 7z** 的需求 | LZMA2（取得最佳比例） |

## 故障排除與技巧

- **壓縮檔中遺失檔案？** 請確認 `dataDir` 指向正確的目錄，且執行程序具備讀取權限。  
- **舊版 7‑Zip 無法開啟壓縮檔？** 請使用 BZip2 或 Store，因為 LZMA2 可能需要較新的解壓縮函式庫。  
- **效能瓶頸？** 對於龐大的資料集，建議以串流方式處理壓縮檔，而非一次載入所有條目至記憶體。

## 常見問題

**Q: 我可以在 .NET 使用 Aspose.Zip 處理任何類型的檔案嗎？**  
A: 可以，Aspose.Zip 支援廣泛的檔案格式，讓您幾乎能壓縮與解壓縮任何檔案類型。

**Q: 是否提供 Aspose.Zip for .NET 的免費試用？**  
A: 有，您可在 **[here](https://releases.aspose.com/)** 取得免費試用版。

**Q: 我可以在哪裡找到 Aspose.Zip for .NET 的文件？**  
A: 完整的 API 參考可於 **[here](https://reference.aspose.com/zip/net/)** 取得。

**Q: 如何取得 Aspose.Zip for .NET 的臨時授權？**  
A: 可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 我可以在哪裡取得 Aspose.Zip for .NET 的支援？**  
A: 您可於 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** 尋求協助。

---

**最後更新：** 2026-06-29  
**測試版本：** Aspose.Zip for .NET 24.12  
**作者：** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [壓縮檔案 C# – 使用 Aspose.Zip for .NET 建立 7z 壓縮檔](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [如何使用 Aspose.Zip for .NET 壓縮資料夾](/zip/net/directory-and-folder-compression/compress-directory/)
- [如何在 Aspose.Zip for .NET 中壓縮 LZMA](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}