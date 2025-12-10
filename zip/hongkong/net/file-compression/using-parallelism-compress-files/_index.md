---
date: 2025-12-10
description: 學習在 .NET 中使用 Aspose.Zip 進行平行檔案壓縮。透過我們的逐步指南，高效壓縮多個檔案。
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 進行並行檔案壓縮
url: /zh-hant/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 進行平行檔案壓縮

## 介紹

在 .NET 開發領域，**平行檔案壓縮**對於優化儲存空間與加速資料傳輸至關重要。Aspose.Zip for .NET 提供了強大的解決方案，其突出功能之一即是能利用平行化進行檔案壓縮。在本教學中，我們將示範如何使用 Aspose.Zip for .NET **同時壓縮多個檔案**，以達到高效能的目的。

## 快速回答
- **什麼是平行檔案壓縮？** 同時壓縮多個檔案，利用多個 CPU 核心減少整體處理時間的技術。  
- **哪個 .NET 函式庫支援此功能？** Aspose.Zip for .NET 內建平行壓縮選項。  
- **需要授權嗎？** 測試用的臨時授權可用；正式環境需購買完整授權。  
- **可以即時將檔案加入 zip 嗎？** 可以——使用 `Archive.CreateEntry` 來加入每個想要的檔案。  
- **相容於 .NET Core/5/6 嗎？** 完全相容，API 可在所有現代 .NET 執行環境下運作。

## 什麼是平行檔案壓縮？
平行檔案壓縮是指將壓縮工作分散到多個執行緒或核心，同時壓縮多個檔案（或大型檔案的多個部分）。與傳統的順序壓縮相比，這種方式能顯著縮短建立 **zip archive c#** 的時間。

## 為什麼選擇 Aspose.Zip 進行平行壓縮？
- **速度：** 完全發揮多核心 CPU 的效能。  
- **可擴展性：** 處理大量檔案時，處理時間不會成比例增加。  
- **簡易性：** 高階 API 抽象了執行緒的複雜性。  
- **彈性：** 支援任何 .NET 版本，且可順利整合至現有程式碼基礎。

## 前置條件

在開始之前，請確保您已具備：

- 基本的 C# 與 .NET 開發知識。  
- 已安裝 Aspose.Zip for .NET 函式庫。您可以在 **[此處](https://releases.aspose.com/zip/net/)** 下載。  
- 了解一般檔案壓縮的概念。

## 匯入命名空間

首先，將所需的命名空間加入 C# 檔案，讓編譯器能找到您將使用的類別。

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 步驟 1：設定文件目錄

定義包含欲壓縮檔案的資料夾路徑，該路徑會儲存在 `dataDir` 變數中。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：初始化壓縮程序

開啟一個新的 ZIP 檔案以供寫入。`using` 陳述式確保檔案串流在操作完成後正確釋放。

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## 步驟 3：平行讀取與壓縮檔案

開啟每個要加入壓縮檔的來源檔案。以下範例使用兩本經典文本，您亦可 **add files to zip** 任意數量的文件。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## 步驟 4：建立壓縮檔條目

建立 `Archive` 實例，並將每個檔案作為獨立條目加入。此處即為 **create zip archive c#** 的步驟。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## 步驟 5：定義平行化條件

透過設定 `ParallelOptions` 來啟用平行壓縮。`ParallelCompressInMemory` 旗標告訴 Aspose.Zip 必定使用平行處理。

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## 步驟 6：儲存壓縮檔案

最後，將壓縮檔寫入磁碟，並套用先前定義的選項，包括編碼、註解以及平行設定。

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

恭喜！您已成功使用 Aspose.Zip for .NET 執行 **平行檔案壓縮**，高效地 **壓縮多個檔案** 成為單一壓縮檔。

## 常見問題與技巧

- **大型檔案：** 若遇到記憶體壓力，建議將檔案分塊壓縮，而非一次載入全部內容。  
- **執行緒安全：** Aspose.Zip API 在平行模式下是執行緒安全的；請避免在庫外部同時由多個執行緒修改同一串流。  
- **效能調校：** 若需在共享伺服器上限制 CPU 使用率，可調整 `ParallelOptions.MaxDegreeOfParallelism`。

## 常見問答

### Q1：我可以將 Aspose.Zip for .NET 與其他 .NET 函式庫一起使用嗎？

A1：可以，Aspose.Zip for .NET 設計上可與其他 .NET 函式庫無縫整合。

### Q2：是否提供測試用的臨時授權？

A2：有，您可從 **[此處](https://purchase.aspose.com/temporary-license/)** 取得測試用的臨時授權。

### Q3：在哪裡可以取得更多支援或提問？

A3：請前往 **[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)** 取得社群支援與討論。

### Q4：是否有其他範例或文件可供參考？

A4：請參閱 **[Aspose.Zip 文件](https://reference.aspose.com/zip/net/)**，內含完整範例與說明文件。

### Q5：如何購買 Aspose.Zip for .NET？

A5：您可在 **[此處](https://purchase.aspose.com/buy)** 購買 Aspose.Zip for .NET。

---

**最後更新：** 2025-12-10  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}