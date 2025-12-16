---
date: 2025-12-14
description: 學習如何在 C# 專案中使用 Aspose.Zip for .NET 解壓縮 Zip 檔案並提取單一檔案。
linktitle: Decompressing a Single File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 解壓 zip C# – 使用 Aspose.Zip 提取單一檔案
url: /zh-hant/net/file-decompression/decompress-single-file/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 解壓 zip c# – 使用 Aspose.Zip 提取單一檔案

## 簡介

如果您需要 **decompress zip c#** 檔案並只提取其中一個項目，Aspose.Zip for .NET 可讓此工作變得簡單。在本教學中，我們將逐步示範一個完整、真實的範例，說明如何從 ZIP 壓縮檔中提取單一檔案、監控進度，並以乾淨且易於維護的方式處理結果。完成後，您將能自信地在任何 C# 應用程式中加入 zip 解壓功能。

## 快速答覆
- **本教學涵蓋什麼內容？** 使用 Aspose.Zip for .NET 解壓 ZIP 壓縮檔並提取單一檔案。  
- **目標主要關鍵字為何？** decompress zip c#  
- **我需要授權嗎？** 免費試用可用於開發；正式上線需購買商業授權。  
- **支援 .NET Core 嗎？** 支援 – 相同程式碼可在 .NET Framework 與 .NET Core 上執行。  
- **實作需要多久？** 基本設定大約需 10‑15 分鐘。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

- Aspose.Zip for .NET Library：從 [Aspose.Zip for .NET Documentation](https://reference.aspose.com/zip/net/) 下載並安裝此函式庫。  
- 開發環境：具備可使用的 .NET 開發環境，包含 Visual Studio 或其他相容的 IDE。  
- C# 基礎認識：熟悉 C# 程式設計的基本概念。

現在，讓我們動手寫程式碼吧！

## 匯入命名空間

首先匯入必要的命名空間，以展開 Aspose.Zip 的使用：

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

### 步驟指南：Decompress zip c#

#### 步驟 1：設定文件目錄

首先指定文件儲存的目錄。將 `"Your Document Directory"` 替換為實際路徑。

```csharp
string dataDir = "Your Document Directory";
```

#### 步驟 2：建立壓縮檔（示範設定）

以下程式碼會建立一個示範用的 ZIP 檔，稍後我們會將其解壓。這模擬了您已擁有 ZIP 壓縮檔的常見情況。

```csharp
CompressSingleFile.Run();
```

#### 步驟 3：解壓檔案 – 提取單一 Zip 檔案

現在，我們進入重點 – 提取單一項目。以下程式碼會開啟 ZIP 壓縮檔、掛載進度處理程式，並將第一個項目解壓為文字檔。

```csharp
// ExStart: DecompressSingleFile
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

此程式碼片段 **提取單一 zip 項目**，同時即時列印進度（例如「30% decompressed」）。您可以調整索引 (`Entries[0]`) 以針對壓縮檔內的其他檔案。

## 為何使用 Aspose.Zip 進行 C# 檔案解壓？

- **無外部相依性** – 純 .NET 函式庫。  
- **支援大型壓縮檔**，採用串流方式，降低記憶體使用量。  
- **內建進度事件**，讓 UI 反饋更簡易。  
- **可跨 .NET Framework、.NET Core 以及 .NET 5/6 使用**。

## 常見問題與技巧

- **檔案路徑分隔符** – 使用 `Path.Combine` 以確保跨平台安全。  
- **受密碼保護的 ZIP** – 在解壓前設定 `archive.Password`。  
- **多個項目** – 迭代 `archive.Entries` 並以 `FileName` 匹配目標檔案。

## 常見問答

### Q1：我可以使用 Aspose.Zip for .NET 壓縮多個檔案嗎？

A1：可以，Aspose.Zip for .NET 支援壓縮多個檔案。請參考文件取得詳細說明。

### Q2：Aspose.Zip 相容於 .NET Core 嗎？

A2：絕對相容！Aspose.Zip 可無縫整合於 .NET Framework 與 .NET Core。

### Q3：我該如何處理受密碼保護的壓縮檔？

A3：Aspose.Zip 提供處理受密碼保護壓縮檔的方法，請參閱文件取得指引。

### Q4：使用 Aspose.Zip 有哪些授權考量？

A4：請於 [Aspose website](https://purchase.aspose.com/buy) 查看授權資訊。

### Q5：如果遇到問題，我可以在哪裡取得協助？

A5：前往 [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) 取得社群支援。

## 結論

恭喜！您已成功掌握 **decompress zip c#** 的細節，並使用 Aspose.Zip for .NET 提取單一檔案。將此模式套用於您的應用程式，可簡化檔案處理、提升使用者體驗，並保持程式碼庫整潔。

---

**最後更新：** 2025-12-14  
**測試版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}